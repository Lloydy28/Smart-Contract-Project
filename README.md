# Smart Contract Project
For this project, write a smart contract that implements the require(), assert() and revert() statements.

# Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Restaurant {
    struct Menu 
    {        
      string food;
      uint256 value;
    }

    Menu[] public foods;

    function foodsmenu(string memory _food, uint256 _value) public {
        require(_value >= 1000, "Price must be less or equal to 1000");

        foods.push(Menu(_food, _value));
    }

    function totalmenu(uint256 _value) pure  public {
        if (_value <=100) {
          revert("Price must be less than or equal to 100");
        }
    }

    function valuemenu(uint256 _value) public pure  {
        assert(_value > 100);

    }
}


        


# Author
NTC

Tenefrancia, John Lloyd B.

8215176@ntc.edu.ph
