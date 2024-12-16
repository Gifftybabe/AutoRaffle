
AutoRaffle is a decentralized lottery system built on Ethereum, designed for fairness, transparency, and automation. Participants enter the raffle by purchasing tickets, and at the end of a specified period, the contract programmatically selects a winner using Chainlink VRF for secure randomness. The entire process is automated using Chainlink Automation, ensuring timely and trustless execution without manual intervention.

## Key Features
- **Provable Randomness:** Ensures fairness by leveraging Chainlink VRF to generate tamper-proof random results.
- **Time-Based Automation:** Chainlink Automation triggers the draw after the predefined period, making it completely autonomous.
- **Transparent and Decentralized:** All transactions and operations are recorded on-chain, guaranteeing transparency.
- **Efficient Ticketing System:** Users can easily enter the raffle by sending ETH to the contract, with funds pooled for the winner.

## How It Works
1. **Enter the Raffle:** Users purchase tickets by sending ETH to the smart contract.
2. **Ticket Pooling:** All ticket fees are pooled in the contract.
3. **Automated Draw:** After a specified time, Chainlink Automation triggers the winner selection.
4. **Random Winner Selection:** Chainlink VRF generates a random number to fairly select a winner.
5. **Prize Distribution:** The contract automatically transfers the pooled funds to the winner.

## Technical Details
### Prerequisites
- **Chainlink VRF:** Provides secure randomness for winner selection.
- **Chainlink Automation:** Ensures the draw occurs at the right time without manual input.
- **Solidity Version:** Compatible with Solidity ^0.8.0.

### Contract Structure
- **Ticket Purchase:** Each ticket purchase is logged with the user's address.
- **Time Management:** The contract maintains a countdown for the raffle duration.
- **Winner Selection:** A winner is selected programmatically using the VRF-generated random number.

### Deployment Steps
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-repo/autoraffle.git
   cd autoraffle
   ```

2. **Install Dependencies:**
   Ensure you have the required dependencies for Foundry:
   ```bash
   forge install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file and set up the following:
   ```env
   VRF_COORDINATOR_ADDRESS=<Chainlink VRF Coordinator Address>
   LINK_TOKEN_ADDRESS=<Chainlink LINK Token Address>
   KEY_HASH=<Chainlink VRF Key Hash>
   SUBSCRIPTION_ID=<Your Subscription ID>
   AUTOMATION_REGISTRY=<Chainlink Automation Registry Address>
   ```

4. **Deploy the Contract:**
   Use Foundry scripts to deploy:
   ```bash
   forge script script/DeployAutoRaffle.s.sol:DeployAutoRaffle --rpc-url <NETWORK_URL> --private-key <PRIVATE_KEY> --broadcast
   ```

5. **Fund the Subscription:**
   Fund your Chainlink VRF and Automation subscription with LINK.

6. **Run Tests:**
   Ensure all tests pass before deploying to mainnet:
   ```bash
   forge test
   ```

### Usage
- **Enter the Raffle:** Send ETH to the contract address to purchase tickets.
- **Check Draw Status:** View the raffle status and countdown via contract calls.
- **Claim Winnings:** The winner's address will automatically receive the prize.

## Future Enhancements
- **Multi-Raffle Support:** Enable simultaneous raffles within a single contract.
- **Dynamic Ticket Pricing:** Adjust ticket prices based on demand.
- **Cross-Chain Compatibility:** Expand to other EVM-compatible chains.

## License
This project is licensed under the MIT License.

