# Token Creation
This Solidity program serves as a foundational example of token creation, illustrating key principles of smart contract development. It can be used as a stepping stone for more complex projects in the future, providing a solid understanding of basic token mechanics in Solidity.
## Description
This program demonstrates fundamental concepts in smart contract development, highlighting my understanding and application of Solidity programming techniques. It is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract includes functions to mint and burn tokens, effectively managing the token supply. The use of public variables and mapping allows for transparent and efficient tracking of token balances across addresses.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

After navigating to the Remix website, I created a file named Token.sol, where .sol is the extension used for Solidity files. I then pasted the code below into this file.

```javascript
pragma solidity ^0.8.13;

contract MyToken {

    // Public variables to store the details about the coin
    string public name = "NIFTY";
    string public symbol = "NIFT";
    uint public totalSupply = 0;

    // Mapping to store balances of addresses
    mapping(address => uint) public balances;

    // Mint function to increase total supply and balance of the sender's address
    function mint(address _to, uint _value) public 
    {
        totalSupply = totalSupply+_value;
        balances[_to] = balances[_to]+_value;
    }

    // Burn function to decrease total supply and balance of the sender's address
    function burn(address _from, uint _value) public 
    {
        require(balances[_from] >= _value, "Insufficient balance to burn");
        totalSupply = totalSupply - _value;
        balances[_from] = balances[_from] - _value;
    }
}

```

To compile the code, I clicked on the "Solidity Compiler" tab in the left-hand sidebar and ensured that the compiler version was greater than or equal to "0.8.4" so that my Solidity code could run properly without any errors. Then, I clicked on the "Compile Token.sol" button.

After the code was compiled, I deployed the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. I selected the "Token" contract from the dropdown menu and then clicked on the "Deploy" button.


Once the contract was deployed, I interacted with it by passing the address of the account and value in the mint and burn functions of the "Token" contract. I clicked on the "Transact" button in the mint and burn functions. Then, I clicked on the "totalsupply" function to see the total supply of tokens. To check the remaining tokens in a specific wallet, I pasted the address of the wallet into the balance function and clicked on "Call".

## Author

Pratap Aditya Singh



## License

This program is licensed by the MIT License.
