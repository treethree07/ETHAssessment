# My Token
This project is a simple Ethereum token contract that has function call mint and burn.

## Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a two function first is the mint function where it increases the total suplply and adds token to a given address to you. The second is burn function where it does a contrary of mint, this function instead decreases the total supply and removes token to the given address but only if the addess has enought to tokens to burn.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
pragma solidity 0.8.18;
contract myToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances [_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        } 
    } 
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the function. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function. To add a address just simply copy the account address at the top and paste it and input a number that you want to add and click on the "transact" button to execute the function. And if you want to burn tokens you can do the same like what you did in the mint just click instead the "burn" button. If you want how many total supply and balances button you can just click it to see.

## Authors
Triscia Joy Mendoza from 2.2 BSIT in NTC.
