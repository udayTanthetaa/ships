---
title: Deploy your Smart Contract on Testnet
takes: 5
---

# Deploy your Smart Contract on Testnet --takes 5 min.

> Why do it? -- Coz' you can't stay on localhost forever :)

## 1. cloning

Clone [this](link) repo -- maintained by your fellow shipper.

```bash
git clone link
```

## 2. installing

Go inside the folder and install packages.

```bash
npm install
```

## 3. deploying

-   Create an Alchemy account from [here](https://www.alchemy.com/)
-   Go to dashboard over [here](https://dashboard.alchemy.com/), then click on `Create App`

![Create App on Alchemy](https://i.imgur.com/ZHnZxAb.png)

-   Go to dashboard again [here](https://dashboard.alchemy.com/), then click on `View Key` + copy the HTTPS url

![Copy HTTPS URL from Alchemy](https://i.imgur.com/lB1n0eI.png)

-   Create .env file + paste the copied URL there

```env
ALCHEMY_RPC_URL = https://polygon-mumbai.g.alchemy.com/v2/HXjU_LEQGsJdorj0WvERDM33FLGv5tnk
```

-   Now, copy your Metamask private key (don't know where it is? --
    refer from [here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-export-an-account-s-private-key#:~:text=On%20the%20account%20page%2C%20click,click%20%E2%80%9CConfirm%E2%80%9D%20to%20proceed.)) + paste
    it in .env as well

```env
PRIVATE_KEY = 0754508311e37c1c3e98aff90cae665ac797666a8e983059cb05022257aa9f33
```

-   Drop your smart contract in `contracts` folder
-   Open the file `deploy.js` under `scripts` folder
-   Replace **Hello** with _your_ smart contract name + if you got constructor arguments, replace them too or else
    just leave it blank

```js
...
const contractFactory = await hre.ethers.getContractFactory("Hello");
const contract = await contractFactory.deploy("Helu Shipper", "Shipends");
...
```

-   Finally, run this command in terminal `npx hardhat run scripts/deploy.js --network mumbai`

```bash
npx hardhat run scripts/deploy.js --network mumbai
```

## 4. confirming

Go to Polygonscan Mumbai from [here](https://mumbai.polygonscan.com/) + paste your deployed contract address in search bar --
voila, your smart contract is live for anyone to use, isn't that cool!

## what's next?

> You know what's more cool? -- that green check mark on your deployed contract like below :)

![Green check on Etherscan](https://i.imgur.com/zcKN61w.png)

Click [here](./verify_etherscan.md) & make your smart contract verified -- in just 5 mins.
