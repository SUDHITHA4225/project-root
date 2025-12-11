## NFT Collection — ERC-721 Smart Contract + Automated Test Suite

A complete ERC-721–compatible NFT smart contract built using Solidity, fully tested with Hardhat, and packaged inside a Docker container for reproducible evaluation.
This project demonstrates secure NFT minting, ownership tracking, transfers, approvals, metadata handling, and enforcing a maximum token supply.
---
# Features

Fully ERC-721–compatible NFT contract

Secure minting (owner-only + max supply enforced)

Unique token ownership & metadata via tokenURI

Safe transfers (safeTransferFrom)

Approvals & operator approvals (approve, setApprovalForAll)

Burn support with full state cleanup

Pause & unpause minting

Complete automated test suite

Dockerized test runner (no external dependencies required)

Clean revert messages & predictable behavior
---
# Project Structure
project-root/
│
├── contracts/
│   └── NftCollection.sol       # Main ERC-721 NFT contract
│
├── test/
│   └── NftCollection.test.js   # Hardhat test suite for full NFT behavior
│
├── Dockerfile                  # Builds container that installs deps + runs tests
├── .dockerignore               # Speeds up Docker builds
│
├── package.json                # Hardhat + testing dependencies
├── package-lock.json
├── hardhat.config.js           # Hardhat configuration
│
└── README.md                   # Project documentation
---
# Technology Stack

Solidity (0.8.x)
OpenZeppelin ERC-721 base contracts
Hardhat (compilation + testing)
Mocha + Chai (test runner & assertions)
Node.js
Docker for isolated environment execution
---
# How to Build & Test
1. Install dependencies
npm install

2. Compile contracts
npx hardhat compile

3. Run all tests
npx hardhat test

Docker Instructions
Build the Docker image
docker build -t nft-contract .
Run all tests inside the container
docker run --rm nft-contract
The container automatically compiles the contract and executes the entire test suite.
---
# Contract Highlights

Owner-only minting using OpenZeppelin Ownable
Max supply limit enforced on every mint
Token ID validation to avoid collisions or invalid IDs
Pause/unpause minting for additional control
Accurate balance & ownership tracking
Standard ERC-721 events (Transfer, Approval, ApprovalForAll)
tokenURI support using a clean base-URI pattern
Burn function that updates all internal state correctly
---
# Test Coverage

The automated test suite validates:
Initial contract configuration
Owner-only minting
Zero-address safety checks
Double-minting prevention
Max supply enforcement
Transfers (including safe transfers)
Approvals / operator approvals
Approval revocation
Non-existent token handling
Burn correctness
Gas usage bounds for mint + transfer
All tests pass both locally and in the Docker container.
---
# Submission Package

This repository includes:
Complete ERC-721 smart contract implementation
Full Hardhat test suite
Dockerfile that runs the tests automatically
Clean folder structure with no unwanted files (node_modules, artifacts, etc.)
Ready-to-review submission for automated evaluation
---
# Task Summary

This project fulfills all requirements:
 ERC-721–compatible smart contract
 Maximum supply + admin-only minting
 Complete automated test suite
 Handles all error scenarios
 Dockerized environment runs tests with 1 command
 Clean, readable structure
 Fully reproducible on any machine
