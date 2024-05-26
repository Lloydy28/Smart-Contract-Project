# Smart Contract Project
For this project, write a smart contract that implements the require(), assert() and revert() statements.

# Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract GymRat {
 
    function squatreps(uint reps) public pure {

        require(reps >= 10, "Not Enough Reps for squats");
        
    }

    function benchpressreps(uint reps) public pure {
        

        if (reps <=12){
          revert("Not enought Reps for benchpress");
        }
        
    }

    function Deadliftreps(uint reps) public pure 
     {
        assert(reps >=6);
    }
}

        


# Author
NTC

Tenefrancia, John Lloyd B.

8215176@ntc.edu.ph
