---
title: Deploy smart contracts locally
takes: 5
---

# Deploy smart contracts locally --takes 5 min.

## Prerequisites

-   [Hardhat Setup](./setting_up_hardhat.md)
-   [How it Works?](./under_the_hood.md)

## 1. Creating Deploy Script

Create **deploy.js** file in `scripts` folder -- if it _already_ exists, `delete` all the content in it,
coz' we _gonna_ start from scratch -- like **_pros_**.

## 2. Writing Boilerplate

`Copy + Paste` the following code in `deploy.js`

```js
const hre = require("hardhat");

const main = async () => {
	// We'll write deployment logic here
};

main().catch((error) => {
	console.error(error);
	process.exitCode = 1;
});
```

## 3. (Optional) Understanding Deployment Process

-   To _deploy_ a smart contract, it's `bytecode` is required -- you can find bytecode's value in `artifacts/contracts/[CONTRACT_NAME].sol/[CONTRACT_NAME].json` stored in the **bytecode** variable.
-   Bytecode is taken by a function of _ethers_ called `getContractFactory`.
-   Then, we will call the **_deploy_** method returned by getContractFactory object.
-   Now, just _wait_ for the `deployed promise` to get fulfilled.

> **Note:** Bytecode consists of _anything + everything_ your smart contract does. It will be then converted to machine level _binary code_.

## 4. Writing Deployment Logic

-   Setting `Contract Factory`

```js
const contractFactory = await hre.ethers.getContractFactory("CONTRACT_NAME");
```

-   Calling **Deploy** Method

```js
const contract = await contractFactory.deploy();
```

-   **Waiting** for Deployment to Complete

```js
await contract.deployed();
```

-   Finally, your `main` function will look like **below**.

```js
const main = async () => {
	const contractFactory = await hre.ethers.getContractFactory("Hello");
	const contract = await contractFactory.deploy();
	await contract.deployed();

	console.log(`Deployment address is ${contract.address}`);
};
```

> **_p.s._**, you can also **console.log** _contractFactory + contract_ objects to see all that _nerdy_ stuff which happens behind the scenes.

## 5. Executing Deploy Script

Run **below** command in terminal -- it will _spin_ a local blockchain -> `execute` your deploy script ->
_terminate_ the local instance -- all in just **one** command, that's Hardhat _bruh_ :)

```bash
npx hardhat run scripts/deploy.js
```

## 6. What's Next?

You have learnt how to build, now it's time to ship those smart contracts to actual Testnet, wink wink.

### Click [here](./deploy_testnet.md) to deploy smart contracts + go live, fr.
