# AVAXGods Smart Contract

**Version:** 1.0.0  
**License:** MIT

## Project Overview

AVAXGods is a decentralized battle card game built on the Avalanche blockchain. The game revolves around minting unique game tokens, registering players, and engaging in strategic battles. Each battle card has distinct attack and defense strengths, which are randomly generated. Players can engage in battles with other players, where strategic decisions influence the outcome.

## Contract Details

The `AVAXGods` smart contract is an ERC1155 token contract that handles the minting of game tokens and the logic for conducting battles between players. It extends the `ERC1155` and `Ownable` contracts from OpenZeppelin to manage token ownership and access control.

### Key Features

- **Token Management:** Mint and manage unique battle cards with distinct attack and defense strengths.
- **Player Registration:** Register players who can participate in the game.
- **Battle Mechanics:** Facilitate battles between players, with logic to handle moves, health, and mana.
- **Randomization:** Generate random attributes for game tokens and battle outcomes.
- **Events:** Emit events for significant actions, such as player registration, battle creation, and battle results.

### Contract Structure

- `Player`: Struct to store player information, including address, name, mana, health, and battle status.
- `GameToken`: Struct to store game token details, including name, ID, attack strength, and defense strength.
- `Battle`: Struct to store battle information, including status, hash, name, players, moves, and winner.
- Mappings to track player information, tokens, and battles.

### Functions Overview

- **Registration:** `registerPlayer(string _name, string _gameTokenName)` - Registers a new player and mints a game token.
- **Battle Management:** `createBattle(string _name)` - Creates a new battle; `joinBattle(string _name)` - Joins an existing battle.
- **Battle Actions:** `attackOrDefendChoice(uint8 _choice, string _battleName)` - Registers a player's move during the battle.
- **Utility:** `getPlayer(address addr)` - Retrieves player information; `getBattle(string _name)` - Retrieves battle details.

## Prerequisites

- Solidity version 0.8.16 or later
- [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) installed
- [Truffle](https://www.trufflesuite.com/truffle) or [Hardhat](https://hardhat.org/) framework for deployment
- [OpenZeppelin Contracts](https://openzeppelin.com/contracts/) library

## Deployment

To deploy the `AVAXGods` smart contract, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/AVAXGods.git
   cd AVAXGods
   ```

2. Install the necessary dependencies:

   ```bash
   npm install
   ```

3. Compile the contract:

   ```bash
   npx hardhat compile
   ```

4. Deploy the contract to your desired network:

   ```bash
   npx hardhat run scripts/deploy.js --network <network-name>
   ```

5. (Optional) Verify the contract on a block explorer:

   ```bash
   npx hardhat verify --network <network-name> <deployed-contract-address>
   ```

## Usage

Once deployed, the `AVAXGods` contract can be interacted with via a frontend dApp, web3 provider, or directly through command-line tools like Hardhat or Truffle.

### Example Interactions

1. **Register a Player:**

   ```solidity
   avaxGods.registerPlayer("PlayerName", "TokenName");
   ```

2. **Create a Battle:**

   ```solidity
   avaxGods.createBattle("BattleName");
   ```

3. **Join a Battle:**

   ```solidity
   avaxGods.joinBattle("BattleName");
   ```

4. **Make a Move:**

   ```solidity
   avaxGods.attackOrDefendChoice(1, "BattleName"); // 1 for attack, 2 for defense
   ```

## Testing

To run the test suite, execute the following command:

```bash
npx hardhat test
```

Ensure that the tests cover all critical functionalities, including player registration, token minting, battle creation, and battle outcomes.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure that your code follows the established coding standards and includes relevant tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Authors and Acknowledgments

- **Ava-Labs**

Special thanks to the Avalanche community and the OpenZeppelin team for their libraries and support.
