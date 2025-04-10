
# Blockchain-practical-metamask-wallet
This repo contains my blockchain practical screenshots and transaction hash.
# Create Metamask Wallet (Sepolia Testnet)

## Introduction 
This is a practical task demonstrate how to create a Metamask wallet and perform a transaction using the Sepolia Testnet.

## Transaction details
Network : Sepolia Testent
Amount Sent : 0.02 ETH
Transaction hash: 0x7cf27df61b25a56c316ceaf087a566567c4283908cebf60da27fdcc4a4bd9172[view transaction on etherscan](https://sepolia.etherscan.io/tx/0x7cf27df61b25a56c316ceaf087a566567c4283908cebf60da27fdcc4a4bd9172)
Status : Successful

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
docker-compose --version
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
![Screenshot 2025-04-10 190035](https://github.com/user-attachments/assets/cbe5bdd1-b025-4c91-8fa5-85731caaf946)


6.  Download Fabric Binaries
```
curl -sSL https://bit.ly/2ysbOFE | bash -s
```
Downloads necessary Fabric binaries and Docker images like peer, orderer, and cryptogen.

## Screenshot




7.Enter the Test Network Directory
```
cd test-network
```
Navigates to the directory that contains scripts for running a sample Fabric network.

## Screenshot



8.  View the Network Script
```
./network.sh
```
Shows the options available with the network.sh script.

## Screenshot


9. Start the Fabric Network
```
./network.sh up
```
Starts the network by launching peer, orderer, and CA containers, and generates the required cryptographic materials.

## Screenshot


10. Create a Channel
```
./network.sh createChannel
```
Creates a default channel (usually named mychannel) and joins the peers to it.

## Screenshot


11. Shut Down the Network
```
./network.sh down
```
Stops all containers and deletes the crypto material and artifacts created during the setup.

## Screenshot






