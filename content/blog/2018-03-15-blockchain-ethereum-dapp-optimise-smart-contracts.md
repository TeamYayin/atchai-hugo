---
author: JohnGriffin
date: "2018-03-15"
published: false
title: "Optimizing Smart Contracts"
header_image: "/images/blog-header-generic.png"
---

### Execution 
Show diagram of stack

Your solidity code will be compiled to bytecode, which consists of Ethereum Virtual Machine (EVM) instructions. The gas cost of a function call is the sum of the gas cost of all the EVM instructions that were executed. 


### What are Expensive Operations
```
Operation         Gas           Description

ADD/SUB           3             Arithmetic operation
MUL/DIV           5             Arithmetic operation
ADDMOD/MULMOD     8             Arithmetic operation
AND/OR/XOR        3             Bitwise logic operation
LT/GT/SLT/SGT/EQ  3             Comparison operation
POP               2             Stack operation 
PUSH/DUP/SWAP     3             Stack operation
MLOAD/MSTORE      3             Memory operation
JUMP              8             Unconditional jump
JUMPI             10            Conditional jump
SLOAD             200           Storage operation
SSTORE            5,000/20,000  Storage operation
BALANCE           400           Get balance of an account
CREATE            32,000        Create a new account using CREATE
CALL              25,000        Create a new account using CALL
```


### General Tips
Cost of deploying a contract
Cost to call the contract functions


Are comments included with deployed contracts and do they increase deployment gas?

No, everything that is not needed for execution is removed during compilation. This includes, among others, comments, variable names and type names.

https://ethereum.stackexchange.com/questions/28813/how-to-write-an-optimized-gas-cost-smart-contract

### Using a Debugger