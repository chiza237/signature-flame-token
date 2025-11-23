```markdown
# Signature Flame (FLAME)

Signature Flame (FLAME) — ERC‑20 fixed‑supply token with:
- Fixed initial mint to a multisig treasury (Gnosis Safe).
- Burnable for holders.
- Pausable (owner) for emergency response.
- Optional timelock‑controlled mint via governance.
- Hardhat project with deploy scripts, tests, and CI.

Tokenomics (example)
- Total supply: 1,000,000,000 FLAME (18 decimals)
- Initial circulating supply: configurable (minted to treasury on deployment)
- Example allocations: team, advisors, ecosystem, staking, liquidity (see docs/tokenomics_one_pager.md)

Repository layout
- contracts/               Solidity contracts (SignatureFlameToken, vesting, etc.)
- scripts/                 deployment scripts (Hardhat)
- test/                    Hardhat tests (unit + small tests)
- docs/                    tokenomics docs, checklist
- .github/workflows/ci.yml GitHub Actions CI for tests

Quickstart (local)
1. Clone:
   git clone git@github.com:chiza237/signature-flame-token.git
   cd signature-flame-token

2. Install:
   npm ci

3. Compile:
   npx hardhat compile

4. Run tests:
   npx hardhat test

Deploy (testnet)
- Edit scripts/deploy_*.js and set SAFE_ADDRESS, RPC and private key via environment vars.
- Test on Sepolia/Goerli using a funded deployer and Safe.
- Typical deploy flow:
  1. Create Gnosis Safe (owners & threshold)
  2. Deploy token to testnet with treasury = Safe address
  3. (Optional) Deploy TimelockController and transfer ownership
  4. Fund vesting contracts from the Safe using multisig transactions

CI
- A GitHub Actions CI workflow runs `npx hardhat compile` and `npx hardhat test` on PRs and pushes to main.

Security & audits
- Run at least one third‑party audit before mainnet launch.
- Use hardware wallets for Safe owners.
- Publish vesting schedules and Merkle airdrop proofs for transparency.

License
- MIT (see LICENSE file).

Contact / Maintainer
- chiza237
```
