# Paymaster Tutorial with API3 dAPIs

This tutorial shows you how to build a custom paymaster that allows users to pay fees with a `mockUSDC` ERC20 token. You will:
- Create a paymaster that will take `mockUSDC` as gas to cover the transaction cost.
- Create the `mockUSDC` token contract and send some tokens to a new wallet.
- Send a `setGreeting` transaction to update the greeting from the newly created wallet via the paymaster. Although the transaction normally requires ETH to pay the gas fee, our paymaster executes the transaction in exchange for the same `mockUSDC` value.
- Utilize API3 Data Feeds within a paymaster.

The project was scaffolded with [zksync-cli](https://github.com/matter-labs/zksync-cli).
ZkSync tutorial can be found [here](https://era.zksync.io/docs/dev/tutorials/api3-usd-paymaster-tutorial.html).

## Project structure

- `/contracts`: smart contracts.
- `/deploy`: deployment and contract interaction scripts.
- `/test`: test files
- `hardhat.config.ts`: configuration file.

## Commands

- `yarn hardhat compile` will compile the contracts.
- `yarn run deploy-paymaster` will execute the deployment script `/deploy/deploy-paymaster.ts`. Requires [environment variable setup](#environment-variables).
- `yarn run use-paymaster` will execute the script `/deploy/use-paymaster.ts` demonstrates approval based Paymaster flow.
- `yarn test`: run tests. **Check test requirements below.**

Both `yarn run deploy-paymaster` and `yarn run use-paymaster` are configured in the `package.json` file and run `yarn hardhat deploy-zksync`.

### Environment variables

In order to prevent users to leak private keys, this project includes the `dotenv` package which is used to load environment variables. It's used to load the wallet private key, required to run the deploy script.

To use it, rename `.env.example` to `.env` and enter your private key.

```
WALLET_PRIVATE_KEY=123cde574ccff....
```

### Local testing

In order to run test, you need to start the zkSync local environment. Please check [this section of the docs](https://v2-docs.zksync.io/api/hardhat/testing.html#prerequisites) which contains all the details.

If you do not start the zkSync local environment, the tests will fail with error `Error: could not detect network (event="noNetwork", code=NETWORK_ERROR, version=providers/5.7.2)`

## Official Links

- [Website](https://zksync.io/)
- [Documentation](https://v2-docs.zksync.io/dev/)
- [GitHub](https://github.com/matter-labs)
- [Twitter](https://twitter.com/zksync)
- [Discord](https://discord.gg/nMaPGrDDwk)
