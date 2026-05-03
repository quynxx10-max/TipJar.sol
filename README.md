# TipJar.sol
TipJar.sol
pragma solidity ^0.8.20;
contract TipJar {
    address public owner = msg.sender;

    function tip() public payable {}

    function withdraw() public {
        require(msg.sender == owner);
        payable(owner).transfer(address(this).balance);
    }
}
