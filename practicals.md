# Practicals

1) Create a voting system with multiple candidates. Each address can vote only once

```
pragma solidity ^0.8.0;

contract Voting {
    struct Candidate {
        string name;
        uint voteCount;
    }

    address public owner;
    mapping(address => bool) public hasVoted;
    Candidate[] public candidates;

    constructor(string[] memory candidateNames) {
        owner = msg.sender;
        for (uint i = 0; i < candidateNames.length; i++) {
            candidates.push(Candidate(candidateNames[i], 0));
        }
    }

    function vote(uint candidateIndex) public {
        require(!hasVoted[msg.sender], "You have already voted.");
        require(candidateIndex < candidates.length, "Invalid candidate.");

        candidates[candidateIndex].voteCount += 1;
        hasVoted[msg.sender] = true;
    }

    function getCandidates() public view returns (Candidate[] memory) {
        return candidates;
    }

    function getCandidate(uint index) public view returns (string memory, uint) {
        require(index < candidates.length, "Invalid index.");
        Candidate storage c = candidates[index];
        return (c.name, c.voteCount);
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 134906](https://github.com/user-attachments/assets/8422e0bd-5815-40aa-bf88-a8cac143c135)

2) Write a contract that manages a list of student records (name, roll number). Allow adding and retrieving student data.

```
pragma solidity ^0.8.0;

contract StudentRecords {

    struct Student {
        string name;
        uint rollNumber;
    }

    Student[] public students;![Screenshot 2025-05-19 134906](https://github.com/user-attachments/assets/f83ae901-9f0b-4bca-b4a5-ad89191f371a)


    // Add new student
    function addStudent(string memory _name, uint _rollNumber) public {
        students.push(Student(_name, _rollNumber));
    }

    // Get student by index
    function getStudent(uint index) public view returns (string memory, uint) {
        require(index < students.length, "Invalid index");
        Student memory s = students[index];
        return (s.name, s.rollNumber);
    }

    // Optional: total number of students
    function getTotalStudents() public view returns (uint) {
        return students.length;
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 135610](https://github.com/user-attachments/assets/3f1a1da2-91f5-4d38-a5d9-192242e8cad0)

![Screenshot 2025-05-19 140927](https://github.com/user-attachments/assets/654a2959-7d24-49f0-be72-a17e7c23e5b7)

3) Develop a contract that only allows the deployer (owner) to call a specific function (use modifiers).

```
pragma solidity ^0.8.0;

contract OwnerOnly {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Not the owner");
        _;
    }

    function ownerFunction() external onlyOwner {
        
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 141725](https://github.com/user-attachments/assets/acf971d7-8b73-4cad-9138-d8fd6bfd1fe6)


4) Write a contract where people can donate Ether and the top 3 donors are tracked.

```
pragma solidity ^0.8.0;

contract TopDonors {
    mapping(address => uint256) public donations;

    struct Donor {
        address donorAddress;
        uint256 amount;
    }

    Donor[3] public topDonors;

    event DonationReceived(address indexed donor, uint256 amount);

    function donate() external payable {
        require(msg.value > 0, "Donate some ETH");

        donations[msg.sender] += msg.value;

        _updateTopDonors(msg.sender);

        emit DonationReceived(msg.sender, msg.value);
    }

    function _updateTopDonors(address donor) internal {
        uint256 donorAmount = donations[donor];

        for (uint8 i = 0; i < 3; i++) {
            if (topDonors[i].donorAddress == donor) {
                topDonors[i].amount = donorAmount;
                _sortTopDonors();
                return;
            }
        }

        if (donorAmount > topDonors[2].amount) {
            topDonors[2] = Donor(donor, donorAmount);
            _sortTopDonors();
        }
    }

    function _sortTopDonors() internal {
        for (uint8 i = 0; i < 2; i++) {
            for (uint8 j = i + 1; j < 3; j++) {
                if (topDonors[j].amount > topDonors[i].amount) {
                    Donor memory temp = topDonors[i];
                    topDonors[i] = topDonors[j];
                    topDonors[j] = temp;
                }
            }
        }
    }

    function getTopDonors() external view returns (Donor[3] memory) {
        return topDonors;
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 142144](https://github.com/user-attachments/assets/57ffd308-d289-483a-be5a-3f0a4eb88f2d)


5) Implement a simple auction system where users can place bids, and the highest bidder wins.

```
pragma solidity ^0.8.0;

contract SimpleAuction {
    address public highestBidder;
    uint public highestBid;
    address public owner;
    bool public ended;

    mapping(address => uint) public pendingReturns;

    event HighestBidIncreased(address bidder, uint amount);
    event AuctionEnded(address winner, uint amount);

    constructor() {
        owner = msg.sender;
    }

    function bid() public payable {
        require(!ended, "Auction already ended");
        require(msg.value > highestBid, "There already is a higher or equal bid");

        if (highestBid != 0) {
            pendingReturns[highestBidder] += highestBid;
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
        emit HighestBidIncreased(msg.sender, msg.value);
    }

    function withdraw() public returns (bool) {
        uint amount = pendingReturns[msg.sender];
        if (amount > 0) {
            pendingReturns[msg.sender] = 0;

            if (!payable(msg.sender).send(amount)) {
                pendingReturns[msg.sender] = amount;
                return false;
            }
        }
        return true;
    }

    function endAuction() public {
        require(msg.sender == owner, "Only owner can end the auction");
        require(!ended, "Auction already ended");

        ended = true;
        emit AuctionEnded(highestBidder, highestBid);

        payable(owner).transfer(highestBid);
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 142722](https://github.com/user-attachments/assets/946dd9f4-2245-4c75-b64d-b12b0b559b2d)


6) Create a contract that splits incoming Ether between 3 fixed addresses.

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract EtherSplitter {
    address payable public recipient1;
    address payable public recipient2;
    address payable public recipient3;

    constructor(
        address payable _recipient1,
        address payable _recipient2,
        address payable _recipient3
    ) {
        recipient1 = _recipient1;
        recipient2 = _recipient2;
        recipient3 = _recipient3;
    }

    receive() external payable {
        uint256 share = msg.value / 3;
        recipient1.transfer(share);
        recipient2.transfer(share);
        recipient3.transfer(msg.value - (2 * share));
    }

    function getContractBalance() public view returns (uint256) {
        return address(this).balance;
    }
}
```
## Screenshot :
![Screenshot 2025-05-19 144520](https://github.com/user-attachments/assets/b2ae9014-7e50-4498-bb08-f36acffb62f2)

