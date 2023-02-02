---
title: Verify your Smart Contract on Etherscan
takes: 5
---

# Verify your Smart Contract on Etherscan --takes 5 min.

> Why do it? -- Coz' you wanna look legit.

Think like this, why would I connect my wallet to a random website which only god knows
what the heck it does ??? -- 99% will just bounce, no matter how good your idea is.

But, what if you drop a link to your verified smart contract on Etherscan where anyone can
go + check out your actual code -- suddenly, you are legit.

Now, I am not so afraid to connect my wallet -- <s>steal</s> take my crypto dude, I believe yaaa.

> Lessgo & make it happen then.

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

## 3. verifying

-   Go [here](https://polygonscan.com/) + sign up / sign in
-   After logging in, head over [here](https://polygonscan.com/myapikey) and create your API key

![Create API Key on Polygonscan](https://i.imgur.com/WPkA4fP.png)

-   Copy that API Key + create .env file + paste it there

```
ETHERSCAN_API_KEY = A6NY2IUQX43A2F3PK9AU46PWXN8V5X6FPS
```

-   Create an Alchemy account from [here](https://www.alchemy.com/)
-   Go to dashboard over [here](https://dashboard.alchemy.com/), then click on `Create App`

![Create App on Alchemy](https://i.imgur.com/ZHnZxAb.png)

-   Go to dashboard again [here](https://dashboard.alchemy.com/), then click on `View Key` + copy the HTTPS url

![Copy HTTPS URL from Alchemy](https://i.imgur.com/lB1n0eI.png)

-   Paste that copied URL in .env too

```
ALCHEMY_RPC_URL = https://polygon-mumbai.g.alchemy.com/v2/HXjU_LEQGsJdorj0WvERDM33FLGv5tnk
```

-   Drop your smart contract in `contracts` folder

-   If your smart contract has any constructor arguments, open `arguments.js` + put those
    over there (Note -- arguments must be exactly same as when your contract was deployed)

```js
module.exports = ["Helu Shipper!", "Shipends"];
```

-   If you have contructor arguments, run this `npx hardhat verify --constructor-args arguments.js <YOUR_DEPLOYED_CONTRACT_ADDRESS> --network mumbai`

```bash
npx hardhat verify --constructor-args arguments.js 0xFB6dBBF6CA6445409D572D11Da2d38d8e97Ac7df --network mumbai
```

-   Or else run this one `npx hardhat verify <YOUR_DEPLOYED_CONTRACT_ADDRESS> --network mumbai`.

```bash
npx hardhat verify 0xFB6dBBF6CA6445409D572D11Da2d38d8e97Ac7df --network mumbai
```

## 4. confirming

Go to Polygonscan Mumbai from [here](https://mumbai.polygonscan.com/) + paste your deployed contract address in search bar --
you will see a green check mark on `Contract` tab + anyone can connect their wallet & interact with it -- you don't need
that hunky-funky frontend after all, gg!

![Green check on Etherscan](https://i.imgur.com/zcKN61w.png)

## 5. what's next?
