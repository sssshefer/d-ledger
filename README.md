# <img src="https://github.com/sssshefer/d-ledger/assets/63253440/cfd6e620-e108-4b03-b296-a7b0870b0e4e" width="28"> D-Ledger: A Decentralized Application on the Internet Computer

## Table of Contents
- [Introduction](#introduction)
- [Theory Notes](#theory-notes)
  - [Internet Computer](#internet-computer)
  - [DFX](#dfx)
- [Features and Functionality](#features-and-functionality)
- [Implementation](#implementation)
  - [Backend Code](#backend-code)
  - [Frontend Code](#frontend-code)
- [Running the Project Locally](#running-the-project-locally)

## Introduction
D-Ledger is a decentralized application (dApp) created to learn and demonstrate the capabilities of the Internet Computer (IC) blockchain. This application simulates a simple banking system where users can top-up, withdraw, and check their balance.

## Theory Notes

### Internet Computer
The Internet Computer is a blockchain that runs at web speed with unbounded capacity. It aims to extend the functionality of the public internet so that it can host backend software, transforming it into a global compute platform. Key features include:
- **Canisters**: Smart contracts on the Internet Computer that combine code and state.
- **Cycles**: The fuel that powers computation in the Internet Computer.
- **Motoko**: A programming language designed for the Internet Computer.

### DFX
DFX is the command-line tool used to manage, deploy, and interact with canisters on the Internet Computer. Key commands include:
- `dfx start`: Starts the local replica.
- `dfx new <project-name>`: Creates a new project.
- `dfx deploy`: Deploys the canisters.
- `dfx canister call <canister-name> <method-name>`: Calls a method on a canister.

To learn more before you start working with `dbank2`, see the following documentation available online:
- [Quick Start](https://internetcomputer.org/docs/current/developer-docs/setup/deploy-locally)
- [SDK Developer Tools](https://internetcomputer.org/docs/current/developer-docs/setup/install)
- [Motoko Programming Language Guide](https://internetcomputer.org/docs/current/motoko/main/motoko)
- [Motoko Language Quick Reference](https://internetcomputer.org/docs/current/motoko/main/language-manual)

## Features and Functionality
- **Top-Up**: Allows users to add funds to their account.
- **Withdraw**: Enables users to withdraw funds from their account, ensuring the balance does not go negative.
- **Check Balance**: Users can query their current balance at any time.
- **Compound Interest**: The balance compounds over time, simulating interest accrual.

## Implementation

### Backend Code
The backend canister is written in Motoko and manages the core banking operations: topping up, withdrawing, checking the balance, and compounding interest.

### Frontend Code
The frontend is a simple HTML page with a form for user interactions and JavaScript for handling user input and communicating with the backend.

## Running the Project Locally

If you want to test your project locally, you can use the following commands:

```bash
# Starts the replica, running in the background
dfx start --background

# Deploys your canisters to the replica and generates your candid interface
dfx deploy
```

Once the job completes, your application will be available at `http://localhost:4943?canisterId={asset_canister_id}`.

If you have made changes to your backend canister, you can generate a new candid interface with

```bash
npm run generate
```

at any time. This is recommended before starting the frontend development server, and will be run automatically any time you run `dfx deploy`.

If you are making frontend changes, you can start a development server with

```bash
npm start
```

Which will start a server at `http://localhost:8080`, proxying API requests to the replica at port 4943.

