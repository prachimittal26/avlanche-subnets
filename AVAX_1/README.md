# DeFi Empire Clone

## Description

The project consists of two smart contracts, GameToken and SecureVault, designed to facilitate a decentralized gaming ecosystem on the Avalanche blockchain. Players can engage in activities such as exploration, purchase and battle using digital assets and earn rewards with custom tokens.
The player is given choice boards based on their badge and can also transfer the badge to friends in the game. They also gain voting rights if they have won at least one major amendment that the owner is considering.

## EVM Subnet Configuration - Step by Step Guide

### 1. Deploying your EVM subnet using the Avalanche CLI
 1. To download a binary for the latest release, run: curl -sSfL https ://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s
 2. Adding Avalanche-CLI to Your PATH :export PATH=~/bin:$PATH >> .bashrc
 3. You can test your installation by running avalanche --version. The tool should print the running version.

### 2. Add your subnet to Metamask

Make sure your custom EVM subnet is added to Metamask so you can communicate with it. Metamask allows you to send events and interact with smart contracts installed on your subnet.

### 3. Make sure this is your network of choice in Metamask

Change your Metamask network to a custom EVM subnet so that all transactions and interactions happen on the correct network.

### 4. Connect Remix to your Metamask

Use the Remix IDE and connect it to Metamask using the Injected Provider service. This connection allows Remix to communicate with your Metamask account and deploy contracts directly from the Remix interface.

### 5. Define your currency

Execute GameToken.sol contracts with Remix. This token acts as an in-game currency.

### 6. Enable Smart Contracts

Copy and paste your solid smart contract code into Remix. Collect contracts and then deploy them to your custom EVM subnet using Remix's deployment interface.

### 7. Test your app!

## Game Mechanics

### GameToken.sol
The GameToken contract is an ERC20-like token contract with basic functionalities such as transferring tokens, approving allowances, and minting or burning tokens. Key features include:

1. Token Management: The contract defines the total supply, token balances for each account, and allowances for delegated transfers.
2. Transfers: Users can transfer tokens to other addresses or utilize allowances to enable third-party transfers.
3. Minting and Burning: The contract allows the minting of new tokens to the caller's account and burning tokens from the caller's balance.

### SecureVault.sol
The SecureVault contract acts as a vault that manages players and their interactions within the game, using GameToken as the primary in-game currency. Key functionalities include:

### 1. Player Management: 
Maintains a record of players (Gamer struct) with attributes like token balance, experience points, achievements, battles won, explorations, voting rights, player level and name
   
### 2. Token Operations:
Players can deposit (addTokens) and withdraw (removeTokens) tokens from the vault, with their balances being updated accordingly.

### 3. Game Interactions:
   
   1)Battles and Exploration: Players can engage in battles with other players (engageBattle) or embark on exploration missions (embarkExplore), earning rewards 
     and experience points.
   
   2)Purchasing Items: Players can spend tokens to buy in-game items (buyItem).
   
   3)Token Transfer: Allows players to transfer their in-game tokens to other players (transferTokens).
   
### 4. Leaderboard and Achievements:
   
   1)Leaderboard: Maintains a leaderboard sorted by players' token balances and battle wins (getLeaderboard).
   
   2)Achievements and Rewards: Players can earn additional tokens and rewards based on achievements and participation (rewardAchievements, awardTokenBonus).
   
### 5. Player Governance and Moderation:
   
   1)Voting Rights: Players can gain voting rights if they accumulate sufficient experience points.
   
   2)Player Data Management: Supports adding new players (addPlayer), simulating battles and explorations for testing purposes, and managing player data.

## Author:
Sandeep Kaur @Sandeep1925

## License
This project is licensed under the MIT License - see LICENSE.md for details. Create another Legumin file based on the following information.
