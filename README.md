# Merkle Airdrop

<div align="center">
  <a href="https://github.com/Ramprasad4121/merkle-airdrop">
    <img src="docs/images/merkle-banner.png" alt="Merkle Airdrop Banner" width="600" height="300">
  </a>
</div>

<div align="center">
  Merkle Tree-Based Token Airdrop for Ethereum & zkSync
  <br />
  <a href="#about"><strong>Explore the demo »</strong></a>
  <br />
  <br />
  <a href="https://github.com/Ramprasad4121/merkle-airdrop/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/Ramprasad4121/merkle-airdrop/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
  ·
  <a href="https://github.com/Ramprasad4121/merkle-airdrop/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+">Ask a Question</a>
</div>

<div align="center">
<br />

[![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-blue)](https://soliditylang.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

</div>

<details open="open">
<summary>Table of Contents</summary>

- [Merkle Airdrop](#merkle-airdrop)
  - [About](#about)
    - [Built With](#built-with)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
    - [Local Ethereum (Anvil)](#local-ethereum-anvil)
    - [zkSync Local](#zksync-local)
    - [zkSync Sepolia Testnet](#zksync-sepolia-testnet)
    - [Testing](#testing)
    - [Other Commands](#other-commands)
  - [Roadmap](#roadmap)
  - [Support](#support)
  - [Project Assistance](#project-assistance)
  - [Contributing](#contributing)
  - [Authors \& Contributors](#authors--contributors)
  - [Security](#security)
  - [License](#license)
  - [Acknowledgements](#acknowledgements)

</details>

---

## About

Efficient Merkle tree-based airdrop system for token distribution to whitelisted addresses. Generates proofs, deploys contracts, and enables claims on Ethereum (Anvil) or zkSync (local/Sepolia). Ensures gas-efficient, verifiable claims.

Why this? To demonstrate scalable airdrops with cross-chain support using Foundry tooling.

<details>
<summary>Screenshots</summary>
<br>

|                               Merkle Proof Generation                               |                               Claim Transaction                               |
| :-------------------------------------------------------------------: | :--------------------------------------------------------------------: |
| <img src="docs/images/merkle-generate.png" title="Proof Output" width="100%"> | <img src="docs/images/claim-tx.png" title="Claim on zkSync" width="100%"> |

> Add screenshots of `make merkle` output and `make claim` transaction.

</details>

### Built With

- [Foundry](https://book.getfoundry.sh/) – Forge, Cast, Anvil
- [foundry-zksync](https://github.com/zksync-toolchain/foundry-zksync) – zkSync support
- Solidity ^0.8.20
- [Make](https://www.gnu.org/software/make/) – Automation
- zkSync CLI, Docker – Local node

## Getting Started

### Prerequisites

- Git (`git --version`)
- Foundry (`curl -L https://foundry.paradigm.xyz | bash && foundryup`; `forge --version`)
- For zkSync: foundry-zksync (`curl -L https://github.com/zksync-toolchain/foundry-zksync/releases/latest/download/foundryup-init.sh | bash`; `foundryup-zksync`), npm (`npm --version`), Docker (`docker --version`)

### Installation

1. Clone:
   ```bash
   git clone https://github.com/Ramprasad4121/merkle-airdrop.git
   cd merkle-airdrop
   ```

2. Setup:
   ```bash
   make
   ```
   *(Runs `forge install && forge build`)*

3. Update whitelist in `script/GenerateInput.s.sol` and generate proofs: `make merkle`
4. Update `ROOT` in Makefile from `target/output.json`.

## Usage

### Local Ethereum (Anvil)

- Start node: `make anvil`
- Deploy: `make deploy`
- Sign claim: `make sign`
- Claim: `make claim`
- Check balance: `make balance`

### zkSync Local

1. Config: `npx zksync-cli dev config` (select in-memory)
2. Start: `npx zksync-cli dev start` or `make zk-anvil`
3. Deploy: `make deploy-zk`
4. Interact: `./interactZk.sh`

### zkSync Sepolia Testnet

- Deploy: `make deploy-zk-sepolia` (enter password)

### Testing

- Vanilla: `forge test`
- zkSync: `make zktest`
- Coverage: `forge coverage --report lcov`
- Gas: `forge snapshot`

### Other Commands

- Format: `forge fmt`
- Clean: `make clean`

## Roadmap

[Open issues](https://github.com/Ramprasad4121/merkle-airdrop/issues).

- Enhancements: Multi-token support, frontend
- Bugs: Vote with 👍

Future: Mainnet deployment, EIP-712 signatures.

## Support

- [Issues](https://github.com/Ramprasad4121/merkle-airdrop/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+)
- [X](https://x.com/0xramprasad)

## Project Assistance

- ⭐ [Star](https://github.com/Ramprasad4121/merkle-airdrop)
- Tweet: "#Airdrop #zkSync Merkle"
- Blog: [Dev.to](https://dev.to/)

## Contributing

Fork, branch (`git checkout -b feature/xyz`), commit, PR. See [CONTRIBUTING.md](docs/CONTRIBUTING.md).

## Authors & Contributors

- [Ramprasad4121](https://github.com/Ramprasad4121)

[Contributors](https://github.com/Ramprasad4121/merkle-airdrop/contributors)

## Security

Review proofs before prod. Report: [SECURITY.md](docs/SECURITY.md). "As is."

## License

MIT License. See [LICENSE](LICENSE).

## Acknowledgements

- [Foundry](https://getfoundry.sh/) – Tooling
- [zkSync](https://zksync.io/) – L2 support
- Ethereum community.