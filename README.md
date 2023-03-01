# Joint Savings Account challenge

![alt=“”](20-5-challenge-image.png)

### Background

In this challenge, I assumed a company that is disrupting the finance industry with its own cross-border, Ethereum-compatible blockchain that connects financial institutions. Currently, the team is building smart contracts to automate many of the institutions’ financial processes and features, such as hosting joint savings accounts.
![](banner.jpg)

To automate the creation of joint savings accounts, I’ll create a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. My smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

### What I am Creating

* The completed Solidity `JointSavings` smart contract.

* A folder named `Execution_Results` that contains at least eight images. These images should confirm that the deposit and withdrawal transactions, which are designed to test the `JointSavings` functionality in the JavaScript VM, worked as expected.

### Instructions

The steps for this challenge are divided into the following sections:

1. Create a Joint Savings Account Contract in Solidity

2. Compile and Deploy the Contract in the JavaScript VM

3. Interact with the Deployed Smart Contract

#### Step 1: Create a Joint Savings Account Contract in Solidity

1. I used Remix IDE.

2. I defined a new contract named `JointSavings`.

3. Define the variables in the new contract:

    * Two variables of type `address payable` named `accountOne` and `accountTwo`

    * A variable of type `address public` named `lastToWithdraw`

    * Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`


4. Define a function named `withdraw` that accepts two arguments: `amount` of type `uint` and `recipient` of type `payable address`. 
      In this function:

    * Define a `require` statement that checks if `recipient` is equal to either `accountOne` or `accountTwo`. If it isn’t, the `require` statement returns the “You don't own this account!” text.

    * Define a `require` statement that checks if `balance` is sufficient for accomplishing the withdrawal operation. If there are insufficient funds, it returns the “Insufficient funds!” text.

    * Add an `if` statement to check if `lastToWithdraw` is not equal (`!=`) to `recipient`. If it’s not equal, set it to the current value of `recipient`.

    * Call the `transfer` function of the `recipient`, and pass it the `amount` to transfer as an argument.

    * Set `lastWithdrawAmount` equal to `amount`.

    * Set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance` to reflect the new balance of the contract.


5. Define a `public payable` function named `deposit`.

    * Set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance`.

6. Define a `public` function named `setAccounts` that takes two `address payable` arguments, named `account1` and `account2`. In the body of the function, set the values of `accountOne` and `accountTwo` to `account1` and `account2`, respectively.

7. Add a fallback function so that my contract can store ether that’s sent from outside the deposit function.

#### Step 2: Compile and Deploy my Contract in the JavaScript VM

1. Compile my smart contract. 

2. “Deploy & Run Transactions” pane in `Remix`. I used “JavaScript VM” as the environment.


#### Step 3: Interact with my Deployed Smart Contract

Now that my contract is deployed, it’s time to test its functionality! I took a screenshot that  you can find at the end of this file.

To interact with my deployed smart contract, I completed the following steps:

1. Use the `setAccounts` function to define the authorized Ethereum address that will be able to withdraw funds from my contract.

2. Test the deposit functionality of my smart contract by sending some amounts of ether. 

    > `used [Ethereum Unit Converter](https://eth-converter.com/) to ease doing the conversion.`

3. Once I’ve successfully deposited funds into my contract, test the contract’s withdrawal functionality.

##### Here are some Remix screenshots that I took.
![](Remix screenshot.png)
