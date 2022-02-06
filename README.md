# Martian Token Crowdsale (Ethereum Token Smart Contracts) 
This repo represents a crowdsale for a fungible token that’s ERC-20 compliant. This token will be minted by using a Crowdsale contract from the OpenZeppelin Solidity library.

## Background

After waiting for years and passing several tests, the Martian Aerospace Agency selected you to become part of the first human colony on Mars. As a prominent fintech professional, they chose you to lead a project developing a monetary system for the new Mars colony. You decided to base this new system on blockchain technology and to define a new cryptocurrency named **KaseiCoin**. (Kasei means Mars in Japanese.)

KaseiCoin will be a fungible token that’s ERC-20 compliant. You’ll launch a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin.

### Step 1: Create the KaseiCoin Token Contract

In this subsection, you’ll create a smart contract that defines KaseiCoin as an ERC-20 token. To do so, complete the following steps:

1. Import the provided `KaseiCoin.sol` starter file into the Remix IDE.

2. Import the following contracts from the OpenZeppelin library:

    * `ERC20`

    * `ERC20Detailed`

    * `ERC20Mintable`

3. Define a contract for the KaseiCoin token, and name it `KaseiCoin`. Have the contract inherit the three contracts that you just imported from OpenZeppelin.

4. Inside your `KaseiCoin` contract, add a constructor with the following parameters: `name`, `symbol`, and `initial_supply`.

5. As part of your constructor definition, add a call to the constructor of the `ERC20Detailed` contract, passing the parameters `name`, `symbol`, and `18`. (Recall that 18 is the value for the `decimals` parameter.)

6. Compile the contract by using compiler version 0.5.0.

7. Check for any errors, and debug them as needed.

8. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your GitHub repository.


[![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/Screenshot1.png)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)

### Step 2: Create the KaseiCoin Crowdsale Contract

In this subsection, you’ll define the KaseiCoin crowdsale contract. To do so, complete the following steps:

1. Import the provided `KaseiCoinCrowdsale.sol` starter code into the Remix IDE.

2. Have this contract inherit the following OpenZeppelin contracts:

    * `Crowdsale`

    * `MintedCrowdsale`

3. In the `KaisenCoinCrowdsale` constructor, provide parameters for all the features of your crowdsale, such as `rate`, `wallet` (where to deposit the funds that the token raises), and `token`. Configure these parameters as you want for your KaseiCoin token.

 [![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/Screenshot2V2.png)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)

### Step 3: Create the KaseiCoin Deployer Contract

In this subsection, you’ll create the KaseiCoin deployer contract. Start by uncommenting the `KaseiCoinCrowdsaleDeployer` contract in the provided `KaseiCoinCrowdsale.sol` starter code.

Next, in the `KaseiCoinCrowdsaleDeployer` contract, you’ll add variables to store the addresses of the `KaseiCoin` and `KaseiCoinCrowdsale` contracts, which this contract will deploy. Finally, you’ll complete the `KaseiCoinCrowdsaleDeployer` contract. To do so, complete the following steps:

1. Create an `address public` variable named `kasei_token_address`, which will store the `KaseiCoin` address once that contract has been deployed.

2. Create an `address public` variable named `kasei_crowdsale_address`, which will store the `KaseiCoinCrowdsale` address once that contract has been deployed.

3. Add the following parameters to the constructor for the `KaseiCoinCrowdsaleDeployer` contract: `name`, `symbol`, and `wallet`.

4. Inside of the constructor body (that is, between the braces), complete the following steps:

    * Create a new instance of the `KaseiCoinToken` contract.

    * Assign the address of the KaseiCoin token contract to the `kasei_token_address` variable. (This will allow you to easily fetch the token's address later.)

    * Create a new instance of the `KaseiCoinCrowdsale` contract by using the following parameters:

      * The `rate` parameter: Set `rate` equal to 1 to maintain parity with ether.

      * The `wallet` parameter: Pass in `wallet` from the main constructor. This is the wallet that will get paid all the ether that the crowdsale contract raises.

      * The `token` parameter: Make this the `token` variable where `KaseiCoin` is stored.

    * Assign the address of the KaseiCoin crowdsale contract to the `kasei_crowdsale_address` variable. (This will allow you to easily fetch the crowdsale’s address later.)

    * Set the `KaseiCoinCrowdsale` contract as a minter.

    * Have the `KaseiCoinCrowdsaleDeployer` renounce its minter role.

5. Compile the contract by using compiler version 0.5.0.

6. Check for any errors, and debug them as needed.

7. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Git repository.

 [![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/Screenshot3.png)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)

### Step 4: Deploy and Test the Crowdsale on a Local Blockchain

In this subsection, you’ll deploy the crowdsale to a local blockchain. You’ll then perform a real-world, preproduction test of your crowdsale. To do so, complete the following steps:

###  **Important:** Record a short video or take screenshots that illustrate the following steps as evidence of your deployed crowdsale contract.

1. Deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

 [![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/Screenshot4v2.png)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)

2. Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances of those accounts.

 [![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/Screenshot5.png)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)



3. Review the total supply of minted tokens and the amount of wei that the crowdsale contract has raised.

 [![Crowdsale-Smart-Contracts-KaseiCoin](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/blob/main/Resources/screenVideo.gif)](https://github.com/benjaminweymouth/ETH-Crowdsale-Smart-Contracts-KaseiCoin/edit/main/README.md)
