---
title: Setting up hardhat
takes: 2
---

# Setting up hardhat --takes 2 min.

## 1. Installation

```bash
npm init -y
npm install --save-dev hardhat
```

## 2. Project Creation

Run `npx hardhat` in terminal -> Create a _JavaScript_ project -> `SPAM ENTER` for all other options.

```bash
npx hardhat
```

> **Note:** Whenever you _compile/run_ your smart contract, Hardhat automatically gets the required **version** downloaded + installed for you -- _pretty cool right!_

## 3. Quick Folder Intro

-   `node_modules` - All the magical spells of Hardhat reside here
-   `contracts` - Smart contracts are written here
-   `scripts` - Deployment scripts are made here
-   `test` - Testing scripts go here

## 4. Starter Contract

Create a file -- **Hello.sol** in `contracts` folder. Then, _copy + paste_ the following code.

```js
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.17;

import "hardhat/console.sol";

contract Hello {
    string public message = "Hello World";

    function getMessage() public view returns (string memory) {
        return message;
    }
}
```

## 5. (Optional) Pro Tips

-   Install `Solidity` extension in VS Code by _Juan Blanco_ from [here](https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity) -- it will help in debugging + developing _faster_.
-   Don't know how to write smart contracts? -- check [this](https://solidity-by-example.org/) out.

## 6. What's Next?

You have a hardhat project all set up, damn! But, it ain't worth something until you actually
deploy some cool contracts -- right?

### Click [here](./deploy_testnet.md) & let's get em' deployed -- within 3 min.
