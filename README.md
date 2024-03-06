#FUNDME PROJECT

Crowd funding platform for Ethereum

#Overview

Welcome to FundMe, a decentralized crowdfunding platform built on the Ethereum blockchain! This README provides essential information on deploying, testing, and interacting with the FundMe smart contract.

#Usage

##Deployment
To deploy FundMe, execute the following command:

[forge script script/DeployFundMe.s.sol]

##Testing

FundMe testing is divided into four tiers: Unit, Integration, Forked, and Staging. This repository covers Unit and Forked tests.

To run tests:[forge test]

or to run a specific test function:
forge test --match-test testFunctionName
or to run tests using a forked testnet:
forge test --fork-url $SEPOLIA_RPC_URL

##Test Coverage

To generate test coverage report:
[forge coverage]

#Deployment to Testnet or Mainnet

##Setup Environment Variables

Before deployment, set the following environment variables in a .env file:

PRIVATE_KEY: Your account's private key (from Metamask)
SEPOLIA_RPC_URL: URL of the Sepolia testnet node
Optionally, ETHERSCAN_API_KEY for contract verification on Etherscan
#Deploy

Deploy FundMe to a testnet or mainnet using:

[forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY]

##Scripts

After deployment, interact with the deployed contract using scripts:

[cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>]

or execute a script:

[forge script script/Interactions.s.sol --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast]

##Withdraw

Withdraw funds from FundMe contract:

[cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY>]

##Estimate Gas

To estimate gas costs:
[forge snapshot]

This generates a .gas-snapshot output file.

##Formatting

To format code:
[forge fmt]

#Thank You!

Thank you for using FundMe. Happy crowdfunding on the Ethereum blockchain! 🚀