---
title: Devlopement Setup
lang: en-US
---

:::info

Morphism is currently under rapid development, stay tuned for what's coming next

:::

<!-- For examples of deploying with hardhat see [practice examples](../Practice-Examples/1-ERC20.md). -->

<!--
# Start Developing on Morphism

Developing on Morphism is as easy as developing on Ethereum — literally!

To deploy contracts onto an morphism chain, simply set the RPC endpoint of your target morphism chain and deploy using your favorite Ethereum development framework;

- [Truffle](https://trufflesuite.com/)
- [Hardhat](https://hardhat.org/)
- [Foundry](https://github.com/foundry-rs/foundry)
- [Brownie](https://eth-brownie.readthedocs.io/en/stable/)
- [Alchemy](https://docs.alchemy.com/reference/alchemy-sdk-quickstart)

...it all just works!



For info on new / different behavior between morphism and Ethereum, see [differences with Ethereum](./1-difference-between-morphism-and-ethereum.md).

## Step 1: Network Configuration

Before you doing anything, make sure you are connected to the following Morphism Testnet.

| Name                      | RPC Url(s)                            | Chain ID | Block explorer             | Underlying L1 |
| ------------------------- | ------------------------------------- | -------- | -------------------------- | ------------- |
| Morphism Testnet             | https://rpc.testnet.morphism.xyz        | 2710    | https://explorer.testnet.morphism.xyz      | Ethereum      |


## Step 2: Set up your developing framework



### Hardhat

Modify your Hardhat config file hardhat.config.ts to point at the Morphism public RPC.
```
...

const config: HardhatUserConfig = {
  ...
  networks: {
    morphism: {
      url: "" || "",
      accounts:
        process.env.PRIVATE_KEY !== undefined ? [process.env.PRIVATE_KEY] : [],
    },
  },
};

...
```

### Foundry

To deploy using Morphism Public RPC, run:
```
forge create ... --rpc-url= --legacy
```


### Truffle
Assuming you already have a truffle environment setup, go to the Truffle configuration file, truffle.js. Make sure to have installed HDWalletProvider: npm install @truffle/hdwallet-provider@1.4.0
const HDWalletProvider = require("@truffle/hdwallet-provider")

```
...
module.exports = {
  networks: {
    morphism: {
      provider: () =>
        new HDWalletProvider(process.env.PRIVATE_KEY, ""),
      network_id: '*',
    },
  }
}

```

### Brownie

To add the Morphism, run the following command:
```
brownie networks add Ethereum morphism host= chainid=534353
```

To set this as your default network, add the following in your project config file:
```
networks:
    default: morphism    
```

Another way to add the Morphism is to create a yaml file and run a command to add it.

This is an example of a yaml file called network-config.yaml
```
live:
- name: Ethereum
 networks:
 - chainid: 534353
   explorer: https://
   host: https://
   id: morphism
   name: Morphism
```
To add Morphism to the network list, run the following command:
```
brownie networks import ./network-config.yaml
```

To deploy on Morphism, run the following command. In this example, token.py is the script to deploy the smart contract. Replace this with the name of your script:
```
brownie run token.py --network morphism
```

### ethers.js

Setting up a Morphism  provider in an ethers script:
import { ethers } from 'ethers';

```
const provider = new ethers.providers.JsonRpcProvider(
  'https://
);
```
## Step 3: Acquire Ether

To start building on Morphism, you may need to acquire some testnet ETH. 

Use [faucet](../../quick-start/faucet) to acquire Sepolia Ether. 

And then you can bridge the test Ethereum Ether to Morphism testnet.

-->