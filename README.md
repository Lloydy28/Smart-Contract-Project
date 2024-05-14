# Smart Contract Project
For this project, write a smart contract that implements the require(), assert() and revert() statements.

# Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Cresent {
    uint256 public value;

    function setValue(uint256 _newValue) external {
        
        require(_newValue != 2, "New value cannot be zero");
        
        
        assert(_newValue != 20); 
        
        
        if (_newValue == 10) {
            revert("New value cannot be 5");
        }

        value = _newValue;
    }
}

# Author
NTC

Tenefrancia, John Lloyd B.

8215176@ntc.edu.ph
