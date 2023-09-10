# Tokensol.sol

This is a solidity program in which I have explained the normal mint and burn functions to create a new token.
Solidity is a smart contract language used to create smart contracts which can be executed by themselves, solidity is used for smart contracts made in solidity.
This program helps to understand some basics of the solidity to learn more about the smart contracts.

# Description

In the following code I have created a new token where I used mint and burn functions. Mint and burn functions are the basic solidity functions which takes two argument in the below code from the user-
1. Address
2. 2. Value
      When user put this values and make the transaction, in mint function he can add token to the existing feature, and in the burn funciton it burns some tokens.

# How to run this
To run the above code you can copy this code and go the remix ide and paste this code and deploy this smart contract in the remix ide.

    pragma solidity ^0.8.0;
    
    contract MyToken {
        string public name;
        string public symbol;
        uint256 public totalSupply;

    mapping(address => uint256) public balances;

    constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
        name = _name;
        symbol = _symbol;
        totalSupply = _totalSupply;
        balances[msg.sender] = _totalSupply;
    }

    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
    }

  Then go to compile contract.sol and hit compile and after compiling check the deployment of the project and put some values in the mint and the burn values and tranjact some tokens.

  # Authors
  Aditi Singh

  This has the MIT license.


