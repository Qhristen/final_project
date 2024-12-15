https://explorer.solana.com/tx/3g9t53naMv6eW3G34TgyqWPU14Vvzvgn533xPu1wmxa6aVSxk7ZJNX47Rin2LaJbVHM62WMWnrpusTciCWFP6nTo?cluster=devnet


This repository provides a collection of utilities to interact with the Solana blockchain, specifically the Devnet. It demonstrates how to perform essential blockchain operations using the `@solana/web3.js` and `@coral-xyz/anchor` libraries. it include creating wallets, performing transactions and interacting with smart contracts (programs) like `wba_prereq`.


### Keygen.ts

This code snippet demonstrates how to generate a new Solana wallet using the `@solana/web3.js` library. It achieves the following:

1. **Generate a Keypair**:

   - Creates a new Solana wallet by generating a keypair using the `Keypair.generate()` method.
   - The keypair consists of:
     - **Public Key**: A unique identifier for the wallet, used for receiving funds and interacting with Solana programs.
     - **Secret Key**: A private key that should be kept secure, as it grants full access to the wallet's funds and transactions.

2. **Display Wallet Information**:
   - Logs the public key to the console, formatted as a base-58 string for readability.

### Airdop.ts

This code demonstrates how to request an airdrop of SOL tokens on the Solana Devnet. It achieves the following:

1. **Initialize a Keypair**:

   - Loads a wallet from a `dev-wallet.json` file and generates a keypair using the wallet's secret key.

2. **Establish a Connection**:

   - Creates a connection to the Solana Devnet using the RPC endpoint `https://api.devnet.solana.com`.

3. **Request an Airdrop**:

   - Requests an airdrop of 2 SOL tokens (converted into lamports, the smallest unit of SOL) to the wallet's public key using the `requestAirdrop` method.

4. **Log the Transaction**:
   - Upon success, the transaction hash is logged, along with a link to view the transaction details on the Solana Devnet Explorer.
   - If an error occurs, it logs the error message for debugging.

### Transfer.ts

This code demonstrates how to send SOL tokens from one wallet to another on the Solana Devnet using the `@solana/web3.js` library. It performs the following actions:

### Steps in the Code:

1. **Load the Sender Wallet**:

   - Imports the sender's wallet from the `dev-wallet.json` file and generates a `Keypair` object.

2. **Define the Recipient Wallet**:

   - Specifies the recipient's wallet using their **public key**.

3. **Establish a Devnet Connection**:

   - Connects to the Solana Devnet via the RPC endpoint `https://api.devnet.solana.com`.

4. **Create a Transaction**:

   - Constructs a transaction using the `SystemProgram.transfer` method, specifying:
     - `fromPubkey`: The sender's public key.
     - `toPubkey`: The recipient's public key.
     - `lamports`: The amount of SOL to transfer (in lamports, where 1 SOL = 1 billion lamports). In this example, 0.005 SOL is transferred (1 SOL ÷ 200).

5. **Add Blockhash and Fee Payer**:

   - Fetches the latest blockhash to include in the transaction.
   - Sets the sender's public key as the fee payer for the transaction.

6. **Sign and Broadcast the Transaction**:

   - Signs the transaction using the sender's keypair.
   - Sends the transaction to the Solana blockchain.
   - Waits for confirmation and retrieves the transaction signature.

7. **Log the Transaction Details**:
   - If successful, logs a link to view the transaction details on the Solana Devnet Explorer.
   - If an error occurs, logs the error for debugging purposes.

### Enroll.ts

The code achieves the following:

1. Sets up a connection to the Solana blockchain.
2. Initializes a wallet and Anchor provider for program interaction.
3. Defines a custom IDL type and object for the WBA program.
4. Generates a PDA using predefined seeds and the program ID to ensure unique account creation.
5. Submits a transaction to the WBA program, including your public key and GitHub username as proof of task completion.

**How to Run**

```
yarn or npm insall
```

```
yarn keygen
yarn airdrop
yarn transfer
yarn enroll
```
