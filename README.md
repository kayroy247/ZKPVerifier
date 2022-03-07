# Zero Knowledge Proof Verifier smart contract

- verify proof argument: ["0x0b49672ebed272dfec06ea42d14bc5aca14aabea11c7308cd27cc269535f5553", "0x04f5e1b0f26d301e7c4ec6fdfb4e8fbd183d0fffea0ff3271d31879cae6656ad"],[["0x3010b7b7a0cd4fdee65b4b76a380e1c1beb00c7239b8e22811e5c284a075a85e", "0x1c1c09676aae3aa87d8b0467b1acb0c26b0d19204269342f5c57e5e2955c0da3"],["0x266e547aeda72b059545e50b23fb5015b29838f9ea027583c6b677ab06623624", "0x161f0e550d5503d78979312466bb5978ad0440cee4cf10f137a044e2b254900a"]],["0x10cb30079234d238956c5fb69515a1a9db9b3000067153bb995a1bb3646f32ea", "0x2da35cf79ebd8e1090692e5b9bb8e914081dc369593a77bac47b1e49912ea58e"],["0x0000000000000000000000000000000000000000000000000000000000000021"]

Try running some of the following tasks:

```shell
npx hardhat accounts
npx hardhat compile
npx hardhat clean
npx hardhat test
npx hardhat node
npx hardhat help
REPORT_GAS=true npx hardhat test
npx hardhat coverage
npx hardhat run scripts/deploy.ts
TS_NODE_FILES=true npx ts-node scripts/deploy.ts
npx eslint '**/*.{js,ts}'
npx eslint '**/*.{js,ts}' --fix
npx prettier '**/*.{json,sol,md}' --check
npx prettier '**/*.{json,sol,md}' --write
npx solhint 'contracts/**/*.sol'
npx solhint 'contracts/**/*.sol' --fix
```

# Etherscan verification

To try out Etherscan verification, you first need to deploy a contract to an Ethereum network that's supported by Etherscan, such as Ropsten.

In this project, copy the .env.example file to a file named .env, and then edit it to fill in the details. Enter your Etherscan API key, your Ropsten node URL (eg from Alchemy), and the private key of the account which will send the deployment transaction. With a valid .env file in place, first deploy your contract:

```shell
hardhat run --network ropsten scripts/deploy.ts
```

Then, copy the deployment address and paste it in to replace `DEPLOYED_CONTRACT_ADDRESS` in this command:

```shell
npx hardhat verify --network ropsten DEPLOYED_CONTRACT_ADDRESS "Hello, Hardhat!"
```

# Performance optimizations

For faster runs of your tests and scripts, consider skipping ts-node's type checking by setting the environment variable `TS_NODE_TRANSPILE_ONLY` to `1` in hardhat's environment. For more details see [the documentation](https://hardhat.org/guides/typescript.html#performance-optimizations).
