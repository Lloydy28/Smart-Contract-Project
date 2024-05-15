# Smart Contract Project
For this project, write a smart contract that implements the require(), assert() and revert() statements.

# Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract BankAcc {
    address public holder;
    mapping(address => uint) public balances;

    event Deposit(address indexed shipper, uint amount);
    event Withdraw(address indexed receiver, uint amount);
    
    modifier onlyOwner() {
        require(msg.sender == holder, "Not the holder");
        _;
    }
    
    constructor() {
        holder = msg.sender;
    }
    
    function deposit() public payable {
        require(msg.value > 0, "Deposit must be above 100");
        balances[msg.sender] += msg.value;
        emit Deposit(msg.sender, msg.value);
    }
    
    function withdraw(uint amount) public {
        require(amount > 0, "Withdraw amount must be greater than 100");
        require(balances[msg.sender] >= amount, "Insufficient Money");
        
        balances[msg.sender] -= amount;
        payable(msg.sender).transfer(amount);
        
        emit Withdraw(msg.sender, amount);
    }
    
    function emergencyWithdraw() public onlyOwner {
        uint contractBalance = address(this).balance;
        
        assert(contractBalance >= 0);
        
        payable(holder).transfer(contractBalance);
        
        if (address(this).balance != 0) {
            revert(" Failed Withdrawal");
        }
    }
}
   
        


# Author
NTC

Tenefrancia, John Lloyd B.

8215176@ntc.edu.ph
