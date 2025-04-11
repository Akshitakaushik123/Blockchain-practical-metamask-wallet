
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

#solidity



Step 1: Set Up the Development Environment
You’ll need tools to write and deploy Solidity code. Most beginners start with:

✅ Remix IDE (Recommended for beginners)

Website: https://remix.ethereum.org

It’s an online editor where you can write, test, and deploy Solidity code directly in your browser. No installation needed.

Other tools (for later):

VS Code + Hardhat or Truffle for more advanced development.

Metamask wallet for interacting with deployed smart contracts.



Step 2: Write Your First Smart Contract (in Solidity)
Example:



![image](https://github.com/user-attachments/assets/d92ed1f0-35ba-42cc-9137-50c690e2c95d)


Step 3: Compile the Contract
In Remix:

Click on the Solidity compiler tab (compiler icon).

Click Compile to check for errors.

Step 4: Deploy the Smart Contract
Go to the Deploy & Run Transactions tab in Remix.

Choose Environment as "JavaScript VM" (for testing in browser).

Click Deploy.

After deployment, your contract will appear in the Deployed Contracts section.

Step 5: Interact with the Contract
Now you can:

Click message() to read the current message.

Use setMessage() to change the message.

This simulates how smart contracts work on blockchain.

Step 6 : (Optional) Deploy on Testnet
Once you're comfortable:

Connect your MetaMask wallet.

Switch Remix to Injected Web3.

Deploy to Ethereum testnets like Sepolia or Goerli using test ETH.


















