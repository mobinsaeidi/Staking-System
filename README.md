# ProfessionalToken

ProfessionalToken (PRO) is a simple yet powerful ERC-20 token with **staking and rewards** built in. If you're looking for a way to stake your tokens, earn passive income, and manage your holdings securely, this contract has you covered.

## What Makes It Special?
- **ERC-20 Compliant**: Built using OpenZeppelin’s trusted libraries.
- **Staking & Rewards**: Stake PRO tokens and earn a **5% annual return**.
- **Burn Mechanism**: Reduce total supply by burning your tokens.
- **Security First**: Protected against reentrancy attacks and includes pausable functionality.
- **Admin Controls**: Contract owner can pause and unpause operations for security reasons.

## Token Details
- **Name**: ProfessionalToken
- **Symbol**: PRO
- **Decimals**: 18
- **Total Supply**: 1,000,000 PRO (minted at deployment)

## How Staking Works
- **Minimum Stake**: 100 PRO
- **Lock Period**: 7 days (tokens can’t be unstaked before this)
- **Rewards**: 5% APY, calculated based on staking duration

## Getting Started
### Install Dependencies
```sh
npm install
```

### Compile the Contract
```sh
npx hardhat compile
```

### Deploy Locally
```sh
npx hardhat node
npx hardhat run --network localhost scripts/deploy.js
```

### Deploy to a Testnet (e.g., Goerli)
```sh
npx hardhat run --network goerli scripts/deploy.js
```

## Using the Contract
### Staking Tokens
```solidity
professionalToken.stake(500 * 10**18); // Stake 500 PRO
```

### Unstaking (After 7 Days)
```solidity
professionalToken.unstake(500 * 10**18); // Withdraw your stake + rewards
```

### Claim Rewards (Without Unstaking)
```solidity
professionalToken.claimRewards();
```

### Burning Tokens
```solidity
professionalToken.burn(200 * 10**18); // Burn 200 PRO tokens
```

### Pausing & Unpausing (Only for Admin)
```solidity
professionalToken.pause(); // Pause contract
professionalToken.unpause(); // Resume operations
```

## Security Measures
- **Reentrancy Guard**: Prevents exploits related to multiple function calls.
- **Emergency Pause**: Owner can disable staking and transfers when needed.
- **Safe Math**: Uses OpenZeppelin’s well-tested arithmetic functions.

## License
This project is **open-source** and licensed under the **MIT License**.

---



