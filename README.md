# HalittaToken-ERC20
// SPDX-License-Identifier: MIT
 
 pragma solidity ^0.8.6;

 import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol";

 contract HalittaToken is ERC20 {
     address public admin;
     constructor (uint256 initialCredit) ERC20( 'Halitta Token', 'HTK') {
         _mint(msg.sender, initialCredit);
         admin = msg.sender;
     }

     function mint(address to, uint amount) external {
         require(msg.sender == admin, "only admin");
         _mint(to, amount);
     }

     
 }
