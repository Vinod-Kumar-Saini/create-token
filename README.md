# CREATE A TOKEN 

Here we use solidity language for creating a token. 


## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. 
Here is line by line explanation :-


```solidity
contract variable {
```
This line declares the start of a Solidity smart contract named "variable".

```solidity
    string public tokenName = "Poly";
    string public tokenAbbrv = "Poy";
```
These lines declare two public string variables: `tokenName` and `tokenAbbrv`. The `public` keyword means that these variables can be accessed from outside the contract. They are initialized with the values "Poly" and "Poy" respectively.

```solidity
    // initial supply is 0
    uint public totalSupply = 0;
```
This line declares a public unsigned integer variable `totalSupply`, which represents the total supply of tokens. It is initialized with a value of 0.

```solidity
    // mapping variable 
    mapping(address => uint) public balances;
```
This line declares a public mapping named `balances`. A mapping in Solidity is like an associative array or a hash table. Here, it maps addresses to unsigned integers, representing the balance of tokens each address holds.

```solidity
    // mint function
    function mint(address address_ , uint values_) public {
        totalSupply += values_;
        balances[address_]+=values_;
    }
```
This declares a function named `mint` that takes two arguments: an address (`address_`) and an unsigned integer (`values_`). It increases the total supply by `values_` and adds `values_` to the balance of the specified address.

```solidity
    // burn function
    function burn (address address_ , uint values_) public{
        if(balances[address_] >= values_){
            totalSupply -= values_;
            balances[address_]-= values_;
        }
    }
```
This declares a function named `burn` that takes the same arguments as the `mint` function. It checks if the balance of the specified address is greater than or equal to the amount to burn (`values_`). If it is, it decreases the total supply by `values_` and subtracts `values_` from the balance of the specified address.
At last don't forget to commit "  SPDX-License-Identifier: MIT " before writing your contracts.
Overall, this contract allows for the creation (minting) and destruction (burning) of tokens, while keeping track of token balances for each address.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT


// REQUIREMENTS
//     1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
//     2. Your contract will have a mapping of addresses to balances (address => uint)
//     3. You will have a mint function that takes two parameters: an address and a value. 
//        The function then increases the total supply by that number and increases the balance 
//        of the “sender” address by that amount
//     4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
//        It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
//        and from the balance of the “sender”.
//     5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
//        to the amount that is supposed to be burned.

pragma solidity 0.8.25;
contract variable{

    string public tokenName = "Poly";
    string public tokenAbbrv = "Poy";
    // initial supply is 0
    uint public totalSupply = 0;


// mapping variable 
mapping(address => uint) public balances;

// mint function
function mint(address address_ , uint values_) public {
    totalSupply += values_;
    balances[address_]+=values_;
}

// burn function
function burn (address address_ , uint values_) public{
    if(balances[address_] >= values_){
        totalSupply -= values_;
        balances[address_]-= values_;
    }
}
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile file_name.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "file_name" contract from the dropdown menu, and then click on the "Deploy" button.
Then click on the bottom most section where your file is showing . Click on it and fill all the required information in it. Check whether you project works smoothly or not . 

## Authors

Vinod Kumar Saini 



## License

This project is licensed under the MIT License - see the LICENSE.md file for details
