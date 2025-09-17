**Overview** 
The PersonalLocker contract allows the deployer (owner) to store a secret message along with a password. The owner can update the message only by providing the correct password. The contract emits an event whenever the message is updated and provides a public view function to read the message
**Pre-requisites**
1.	Need Node.js in your local machine, In case, its not available Download node.js msi installer from https://nodejs.org/en/download/ ( For Windows )
Development steps
1.	Created a folder called "C:\blockchainpersonallocker"
2.	Used PowerShell to install install hardhat npm install --save-dev hardhat @nomicfoundation/hardhat-toolbox dotenv
3.	Create a javascript projects so that it creates the necessary folders required for the project like contracts, scripts etc.,
**Key files**
1.	contracts/PersonalLocker.sol - Contract files
2.	scripts/deploy.js - Deployment Script
3.	scripts/update.js - Update Script per requirement
4.	scripts/read.js - Reading the message (segregation of functions )
5.	hardhat.config - Config file
6.	.env file - This is not added in the repository as it contains sensitive information ( SECRET_PASSWORD, SEPOLIA_RPC_URL, PRIVATE_KEY)
7.	deployedAddress.json - Created when deploy.js is run. The address where the message is stored is written in this file so as to avoid hardcoding in update.js. update.js reads this file to update the message.
**Commands to run in local machine**
1.	Start local blockchain npx hardhat node. Sometimes Powershell can block running the script. So run Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass before running the previous script.
2.	Deploy contract locally npx hardhat run scripts/deploy.js --network localhost
3.	Update the contract with the message "Assignment Completed" npx hardhat run scripts/update.js --network localhost
**How did I deploy in Sepolia ?**
For running the contract in Sepolia Testnet there are three things required
1.	API endpoint which points to Sepolia - Got it from Alchemy
2.	For getting ETH, used https://cloud.google.com/application/web3/faucet/ethereum/sepolia and provided the ETH Wallet address which is got from Metamask
3.	The Metamask pprivate key is stored in .env
Commands to run in Sepolia Its the same set of commands which is run in local expect that the --network localhost is replaced with sepolia --network sepolia
1.	npx hardhat run scripts/deploy.js --network sepolia
2.	npx hardhat run scripts/update.js --network sepolia
**Screenshot 1 - deploy.js execution - LOCAL**
<img width="940" height="463" alt="image" src="https://github.com/user-attachments/assets/c8a1f1d0-e126-4bcb-a8aa-a9e976389b1b" />


Screenshot 2 - update.js execution - LOCAL 
<img width="940" height="378" alt="image" src="https://github.com/user-attachments/assets/ff672798-ab6d-4d8f-a223-799be2f6e576" />

Screenshot 3 - Metamask Chrome Extension for Wallet

<img width="467" height="698" alt="image" src="https://github.com/user-attachments/assets/287d2a42-2fcb-4f2a-a3b9-e750740ed7d8" />

 
Screenshot 4 - Ethereum Sepolia Faucet

<img width="940" height="525" alt="image" src="https://github.com/user-attachments/assets/d45c0c7d-15a8-44f5-9c41-c93728c8ea3c" />

 
Screenshot 5 - Alchemy Dashboard showing App deployment  
<img width="940" height="519" alt="image" src="https://github.com/user-attachments/assets/1df09c17-32da-4d9b-be1b-7c8f747669bf" />


Screenshot 6 - Deployment and Update in Sepolia  

<img width="940" height="381" alt="image" src="https://github.com/user-attachments/assets/f7c23b98-3f0a-461c-842a-283e354ad26b" />


