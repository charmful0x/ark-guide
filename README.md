## Ark UI Specs

## Step 1: EVM side (in this case Goerli Testnet)

- Goerli contract address: [0xdE44d3fB118E0f007f2C0D8fFFE98b994383949A](https://goerli.etherscan.io/address/0xde44d3fb118e0f007f2c0d8fffe98b994383949a)
- contract ABI: will share the `./build` directory by DM atm.
- wallet: MetaMask
- Interacting with Ethereum: [Infura.io](https://infura.io) (free acc for testing purpose works) for the RPC + etherjs && web3js -- object instance example https://github.com/decentldotland/ark-network/blob/main/src/utils/evm/ethers.js
- function to invoke: `linkIdentity("CALLER_ARWEAVE_ADDRESS")` --> return the interaction TXID

## Step 2: Arweave side
- SWC address: [qP614umsvOo9Szvl-xqvnXH0xLOg2eKOsLYnKx2l5SA](https://viewblock.io/arweave/address/qP614umsvOo9Szvl-xqvnXH0xLOg2eKOsLYnKx2l5SA)
- wallet: Arconnect
- function to invoke: https://github.com/decentldotland/ark-network/blob/main/ark-contracts/arweave/identity.js#L43 || `input.invocationReq` is the EVM TXID resulted from the last point in ***step 1*** and `input.address` is the EVM address. Omit telegram feature at this point.

## Logic Flow
1- the user connect both wallets and the UI show the read addresses (Arweave & EVM)

2- the user is requested to sign `step 1` TX then `step 2` TX.
