# JointSaving_SmartContract
A Solidity smart contract that accepts two user addresses to control a joint savings account.

## Technologies

This application works on:

* [Solidity](https://docs.soliditylang.org/en/v0.8.13/) - Solidity is an object-oriented, high-level language for implementing smart contracts. Smart contracts are programs which govern the behaviour of accounts within the Ethereum state.

---

## Detailed Explanation

### 1.Create a Joint Savings Account Contract in Solidity
1. In a new Solidity file named `joint_savings.sol` a new contract `JointSavings` is created with following variables:
  * Two variables of type `address payable` named `accountOne` and `accountTwo`
  * A variable of type `address public` named `lastToWithdraw`
  * Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`

2. A function named `withdraw` that accepts two arguments :`amount` of type `uint` and `recipient` of type `payable address`. The function does the following:
  * Defined a `require` statement that checks `if recipient is equal to either accountOne or accountTwo` and returns “You don't own this account!” text if not.
  * Defined a `require` statement that checks `if balance is sufficient for accomplishing the withdrawal` operation and returns “Insufficient funds!” text if not.
  * Added an if statement to check if lastToWithdraw is not equal (!=) to recipient. If it’s not equal, set it to the current value of recipient.
  * The `transfer` function of the recipient is called, with the amount to transfer as an argument.
  * Set `lastWithdrawAmount` equal to amount.
  * Set the `contractBalance` variable equal to the balance of the contract.

3. A function named `deposit` that set the `contractBalance` variable equal to the he balance of the contract.

4. A `public` function named `setAccounts` that takes two address payable and set the values of `accountOne` and `accountTwo`.
