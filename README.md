/README.md

# MultichainFund

MultichainFund is an experimental series of 30 smart contracts deployed and verified on **Base Mainnet** and **Celo Mainnet**. The goal is to explore patterns and functional evolutions—escrow, roles, access control, NFTs, staking, lending, etc.—and demonstrate multi-chain coherence and good practices.

## Structure

contracts/ # Solidity contracts: mc01 ... mc30
build-config/
base/ # Standard JSON inputs for verification on Base
celo/ # Standard JSON inputs for verification on Celo
interactions/
base/ # Post-deployment interaction logs (JSON)
celo/
deployments/
base/ # Deployment metadata per network (JSON)
celo/
scripts/ # Optional scripts for deploy / interaction


## Tooling

- **Solidity** `0.8.24`
- **EVM**: Cancun
- **Optimizer**: enabled, `runs=200`
- Recommended environment: Remix or Foundry/Hardhat (optional).

## Compile (Remix)

1. Open `contracts/mc01_BasicEscrow.sol`.
2. Compiler: Solidity **0.8.24**; EVM: **Cancun**; Optimizer: **enabled (200)**.
3. Compile.

## Deploy

Deploy `mc01_BasicEscrow` on:
- **Base Mainnet** (ETH as native token)
- **Celo Mainnet** (CELO as native token)

No constructor params. Keep track of the deployed address and creation tx hash.

## Verify

Use the **standard JSON input** files:
- `build-config/base/mc01_BasicEscrow_base.json`
- `build-config/celo/mc01_BasicEscrow_celo.json`

These mirror the Remix “Standard JSON Input” format and ensure a deterministic verification on Basescan / Celoscan.

## Record Metadata

After deployment, create:
- `deployments/<network>/mc01_BasicEscrow_<network>_deploy.json`  
  (address, creationTxHash, compiler, evmVersion, optimizerRuns, verifyUrl, etc.)
- `interactions/<network>/mc01_BasicEscrow_<network>_interactions.json`  
  (chronological list of interactions with tx hashes and block numbers)

## Minimal Interactions (for authenticity)

- 2–3 deposits from different EOAs (beneficiaries set and unset).
- 1–2 withdrawals from distinct beneficiaries.

These genuine interactions help demonstrate real usage and increase transparency for reputation programs.

## Roadmap

- `mc02_RolesAccess.sol` introducing role-based access control.
- Continue incrementally to mc30, keeping parity across Base and Celo.


/LICENSE (MIT)

MIT License

Copyright (c) 2025 MultichainFund
