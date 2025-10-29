// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

/*
   Jayendra Opinion Contract
   --------------------------
   A simple decentralized tool to collect public opinions.

   ✅ Anyone can submit their opinion.
   ✅ Opinions are stored permanently on blockchain (immutable).
   ✅ Anyone can read all opinions.
*/

contract Jayendra {
    struct Opinion {
        address author;      // Who submitted
        string message;      // Their opinion
        uint256 timestamp;   // When it was submitted
    }

    Opinion[] public opinions; // Dynamic list of all opinions

    // Add a new opinion
    function submitOpinion(string memory _message) public {
        require(bytes(_message).length > 0, "Opinion cannot be empty");
        opinions.push(Opinion(msg.sender, _message, block.timestamp));
    }

    // Get total number of opinions
    function getTotalOpinions() public view returns (uint256) {
        return opinions.length;
    }

    // Get a specific opinion by index
    function getOpinion(uint256 index)
        public
        view
        returns (address author, string memory message, uint256 timestamp)
    {
        require(index < opinions.length, "Invalid index");
        Opinion memory op = opinions[index];
        return (op.author, op.message, op.timestamp);
    }
}
