# Practical 1
# Blockchain-practical-metamask-wallet
This repo contains my blockchain practical screenshots and transaction hash.
# Create Metamask Wallet (Sepolia Testnet)

## Introduction 
This is a practical task demonstrate how to create a Metamask wallet and perform a transaction using the Sepolia Testnet.

## Transaction details
1) Network : Sepolia Testent
2) Amount Sent : 0.02 ETH
3) Transaction hash: 0x7cf27df61b25a56c316ceaf087a566567c4283908cebf60da27fdcc4a4bd9172[view transaction on etherscan](https://sepolia.etherscan.io/tx/0x7cf27df61b25a56c316ceaf087a566567c4283908cebf60da27fdcc4a4bd9172)
4) Status : Successful

## Getting Sepolia ETH from Faucet
1) Visited the google cloud Sepolia Faucet.
2) Logged in with my google account.
3) Entered my Metamask wallet address.
4) Clicked on "Request 0.02 ETH".
5) ETH was sent to my wallet within a few seconds.
6) Verified the transaction on sepolia Etherscan.

## Screenshot
Below is the screenshot of getting ETH from sepolia faucet using google cloud:
![Screenshot 2025-04-08 120659](https://github.com/user-attachments/assets/7e7eea2d-eb4d-46b6-b2dc-7764c9c1e01c)

## Steps followed
1. Connected Metamask to Sepolia Testnet.
2. Claimed Sepolia ETH from faucet.
3. Sent ETH to another Address.
4. Verified transaction was confirmed.

## Screenshot
Below is the screenshot of the transaction:
![Screenshot 2025-04-07 213239](https://github.com/user-attachments/assets/8f53c1eb-52cf-471e-9db2-0eabbe089740)


# Practical 2
# IPFS Practical - Uploading a file to IPFS
# IPFS Installation
I downloaded and install IPFS desktop for windows from the official website :
https://docs.ipfs.tech/install/ipfs-desktop/

## IPFS Setup
1) After installing, I launched the IPFS desktop.
2) IPFS node automatically connected and status showed as Online.

![Screenshot 2025-04-07 231756](https://github.com/user-attachments/assets/ea26e2be-042a-4718-aeea-efcce3058241)

## File Upload
1) I clicked on the file section in IPFS Desktop.
2) Then i selected the option "Import" and uploaded a sample file, picture of flower and music also.
3) Once the file was uploaded, IPFS generate a unique CID(Content Identifier) for the file.

![Screenshot 2025-04-10 130242](https://github.com/user-attachments/assets/d9b81626-3b4e-4eb6-8d9d-581fd2cb6221)


![Screenshot 2025-04-10 125946](https://github.com/user-attachments/assets/fa3b9104-c34f-4fcf-962e-642e8cef45c1)

## Encrypting and Decrypting

1) Download IPFS CLI:
```
wget https://dist.ipfs.tech/go-ipfs/v0.22.0/go-ipfs_v0.22.0_linux-amd64.tar.gz
```
2) Extract the tar file:
```
tar -xvzf go-ipfs_v0.22.0_linux-amd64.tar.gz
```
3) Install IPFS:
```
cd go-ipfs
./install.sh
```
4)  Initialize IPFS Node
```
~/.local/bin/ipfs init
```
5) Start IPFS Daemon
```
~/.local/bin/ipfs daemon
```

6) Create a sample file
```
echo "hello, IPFS!" > hello.txt
```

7) Add original file to IPFS
```
~/.local/bin/ipfs add hello.txt
```

8) Encrypt the file using OpenSSL
```
openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in hello.txt -out hello.enc
```

9) Upload the encrypted file to IPFS
 ```
~/.local/bin/ipfs add hello.enc
```

10) Decrypt the file
 ```
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in retrieved.enc -out decrypted.txt
```

11) See decrypted content
```
cat decrypted.txt
```

12) Add decrypted file to IPFS
```
~/.local/bin/ipfs add decrypted.txt
```
## Screenshot
![Screenshot 2025-04-18 125935](https://github.com/user-attachments/assets/cfb1cbb8-1108-4fe2-a40f-6b334822c78a)



# Practical 3
# Hyperledger Fabric Practical
1. Install Golang
```
sudo apt install golang-go
```
Installs Golang, which is necessary for running Hyperledger Fabric binaries.

## Screenshot
![Screenshot 2025-04-10 185728](https://github.com/user-attachments/assets/f02e6cc0-00cb-4023-b30e-13baa5dd98c2)


2. Check Docker Version
```
docker --version
```
Verifies that Docker is installed and running correctly.

## Screenshot
![Screenshot 2025-04-10 185749](https://github.com/user-attachments/assets/9baee78b-530f-43c1-8963-4efe00f0eb3f)


3. Check Docker Compose Version
```
docker compose version
```
Verifies the installation of Docker Compose.

## Screenshot
![Screenshot 2025-04-10 185804](https://github.com/user-attachments/assets/03fe5319-cd88-47a6-a068-6eebf9df2730)



4. List Files in Current Directory
```
ls
```
Shows the list of files and folders in the current directory.


5. Clone the Fabric Samples Repository and  Move into the Cloned Folder
```
git clone https://github.com/Akshitakaushik123/fabric-samples.git; cd fabric-samples
```
Downloads the official Hyperledger Fabric sample code from GitHub.
Enters the cloned folder where Fabric examples are available.

## Screenshot
![Screenshot 2025-04-10 185857](https://github.com/user-attachments/assets/e91eb998-e761-4070-bb20-cacc3b0f9480)



6.  Download Fabric Binaries
```
curl -sSL https://bit.ly/2ysbOFE | bash -s
```
Downloads necessary Fabric binaries and Docker images like peer, orderer, and cryptogen.

## Screenshot
![Screenshot 2025-04-10 200854](https://github.com/user-attachments/assets/3a308cd5-4e60-4e36-a164-8c9089763d8f)
![Screenshot 2025-04-10 200927](https://github.com/user-attachments/assets/a1af3740-ced3-4e55-a9dd-e3e2ffd02bc0)




7.Enter the Test Network Directory
```
cd test-network
```
Navigates to the directory that contains scripts for running a sample Fabric network.

## Screenshot
![Screenshot 2025-04-10 191001](https://github.com/user-attachments/assets/ec0b17d1-a4f6-4e0f-b0db-1f564288c6d5)



8.  View the Network Script
```
./network.sh
```
Shows the options available with the network.sh script.

## Screenshot
![Screenshot 2025-04-10 190210](https://github.com/user-attachments/assets/2381a5c2-20e8-4f8c-8ba0-63b8422618e0)



9. Start the Fabric Network
```
./network.sh up
```
Starts the network by launching peer, orderer, and CA containers, and generates the required cryptographic materials.

## Screenshot
![Screenshot 2025-04-10 201603](https://github.com/user-attachments/assets/7c24ed7b-e32e-4f7a-845f-fda0a0a90e99)




10. Create a Channel
```
./network.sh createChannel
```
Creates a default channel (usually named mychannel) and joins the peers to it.

## Screenshot
![Screenshot 2025-04-10 201754](https://github.com/user-attachments/assets/6dc7ed0d-44a1-4f1a-a2db-0e9a743433e3)
![Screenshot 2025-04-10 201844](https://github.com/user-attachments/assets/4a69f43b-6d31-4231-827b-5a746dff06a0)



11. Shut Down the Network
```
./network.sh down
```
Stops all containers and deletes the crypto material and artifacts created during the setup.

## Screenshot
![Screenshot 2025-04-10 201947](https://github.com/user-attachments/assets/e9636909-e96c-4912-8402-4c16ff6f7745)


# Practical 4
# Solidity



Step 1: Set Up the Development Environment

Website: https://remix.ethereum.org

It’s an online editor where you can write, test, and deploy Solidity code directly in your browser. No installation needed.


Step 2: Write Your First Smart Contract (in Solidity)
```
pragma solidity ^0.8.0;

contract HelloWorld {
    string public message = "Hello Blockchain!";

    function setMessage(string memory newMessage) public {
        message = newMessage;
    }
}
```


Step 3: Compile the Contract
In Remix:

Click on the Solidity compiler tab (compiler icon).

Click Compile to check for errors.
![Screenshot 2025-04-11 103802](https://github.com/user-attachments/assets/c07673ec-496e-4ebc-b65d-76a7dcdc49b4)


Step 4: Deploy the Smart Contract
Go to the Deploy & Run Transactions tab in Remix.

Choose Environment as "JavaScript VM" (for testing in browser).

Click Deploy.

After deployment, contract will appear in the Deployed Contracts section.

Step 5: Interact with the Contract
Now you can:

Click message() to read the current message.

Use setMessage() to change the message.

This simulates how smart contracts work on blockchain.



# Practicals

## 1) Create a voting system with multiple candidates. Each address can vote only once

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

## 2) Write a contract that manages a list of student records (name, roll number). Allow adding and retrieving student data.

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

## 3) Develop a contract that only allows the deployer (owner) to call a specific function (use modifiers).

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


## 4) Write a contract where people can donate Ether and the top 3 donors are tracked.

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


## 5) Implement a simple auction system where users can place bids, and the highest bidder wins.

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


## 6) Create a contract that splits incoming Ether between 3 fixed addresses.

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
















