# Project Title : Create a Token

This Solidity program implements a basic token contract called MyToken. The contract allows for the creation and destruction of tokens, as well as tracking the balance of token holders.

## Description

The MyToken contract is designed to create and manage tokens. It includes the following features:

1. Public Variables: The contract includes public variables to store the details about the token, such as the token name, token abbreviation, and total supply.

2. Balances Mapping: The contract uses a mapping variable to keep track of the balances of token holders. The mapping maps addresses to their respective token balances.

3. Mint Function: The contract provides a mint function that increases the total supply of tokens and adds the specified amount to the balance of a given address. The mint function takes two parameters: the address and the value to be minted.

4. Burn Function: The contract includes a burn function that works in the opposite way of the mint function. It decreases the total supply of tokens and subtracts the specified amount from the balance of a given address. The burn function takes two parameters: the address and the value to be burned. It includes conditionals to ensure that the balance of the "sender" is greater than or equal to the amount being burned.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```javascript
pragma solidity 0.8.18;
contract MyToken {

    // public variables here

    string public tokenName = "META";
    string public tokenAbbr = "MTA";
    uint public totalSupply = 0 ;

    // mapping variable here

    mapping(address=>uint) public balances ;

    // mint function

    function mint(address _address, uint value) public {
       totalSupply += value ;
       balances[_address] += value ;
    }

    // burn function

    function burn(address _address, uint value) public {
       if(balances[_address] >= value){
          totalSupply -= value ;
          balances[_address] -= value ;
       }

    }

}

```

Deploy the contract by compiling and deploying the Solidity code using a compatible development environment or Remix IDE.

Once the contract is deployed, you can interact with it by calling the mint and burn functions.

To mint new tokens, call the mint function and provide the address and the value to be minted as parameters. This will increase the total supply and update the balance of the specified address accordingly.

To burn tokens, call the burn function and provide the address and the value to be burned as parameters. This will decrease the total supply and update the balance of the specified address, but only if the balance is greater than or equal to the amount being burned.

## Authors

Lakshay Sindhu 

Student at Chandigarh University

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

