# Ballot Smart Contract

The Ballot Smart Contract is an Ethereum-based contract that implements a voting process along with vote delegation. It allows a chairperson to create a new ballot with a list of proposals and grant voting rights to voters. Voters can either vote directly for a proposal or delegate their votes to another voter.

## Features

1. Create a new ballot with a list of proposal names
2. Grant voting rights to a list of voter addresses
3. Delegate votes to another voter
4. Vote directly for a proposal
5. Compute the winning proposal
6. Get the winner's name

## Prerequisites

- Solidity ^0.8.10
- Ethereum development environment (e.g., Truffle, Remix, etc.)

## Functions

### Constructor

The constructor initializes the contract, sets the chairperson to the address deploying the contract, and creates a new ballot with a list of proposal names.

### giveRightToVote

`function giveRightToVote(address[] memory voter) public`

This function allows the chairperson to grant voting rights to a list of voter addresses by looping through each address and assigning a weight of 1 to each voter.

### delegate

`function delegate(address to) public`

This function allows a voter to delegate their vote to another voter. The function ensures that the voter has not already voted and is not delegating their vote to themselves. The vote is then delegated, and the delegate's weight is updated accordingly.

### vote

`function vote(uint proposal) public`

This function allows a voter to vote directly for a proposal. The voter must have the right to vote and must not have voted already. The function then updates the vote count for the chosen proposal.

### winningProposal

`function winningProposal() public view returns (uint winningProposal_)`

This function computes the winning proposal by iterating through all the proposals and finding the one with the highest vote count.

### winnerName

`function winnerName() public view returns (bytes32 winnerName_)`

This function calls the `winningProposal()` function to get the index of the winning proposal and returns the name of the winner.

## Usage

1. Deploy the Ballot Smart Contract to the Ethereum network using your preferred development environment.
2. Interact with the deployed contract by calling the functions to create a new ballot, grant voting rights, delegate votes, vote for proposals, and get the winner's name.
3. Ensure only the chairperson can grant voting rights to voter addresses.

## License

This smart contract is not licensed and is free for public use.
