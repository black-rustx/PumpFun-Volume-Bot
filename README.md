Here’s an improved, more polished version of your **Pump.Fun Volume Bot README** to make it visually appealing and more organized:

---

# 🚀 **Pump.Fun Volume Bot**

![Solana](https://img.shields.io/badge/Solana-362D59?style=for-the-badge&logo=solana&logoColor=white)  ![PumpFun](https://img.shields.io/badge/PumpFun-FF6B35?style=for-the-badge&logo=pumpfun&logoColor=white)

Automate volume generation and trades on **Pump.Fun** using this bot. It supports multiple modes like **Gen Volume**, **Human Mode**, and **MicroBuy**, integrated with **JITO Bundle** for transaction optimization and MEV (Miner Extractable Value) protection.

---

## 📚 **Table of Contents**

- [Config Guide](#config-guide)
- [How to Run](#how-to-run)
- [Modes of Operation](#modes-of-operation)
  - [Buy Modes](#buy-modes)
  - [Sell Modes](#sell-modes)
  - [Wallet Modes](#wallet-modes)
  - [Transfer Modes](#transfer-modes)
- [BlockEngine URLs](#blockengine-urls)

---

## 🔧 **Config Guide**

The **config.json** file is essential for setting up your bot. Here's an overview of the config options:

```json
{
  "rpc": "Your RPC URL (http or https supported) (must support GPA)",
  "ws": "Your WSS URL (ws or wss supported) (must support GPA)",
  "delay": 5000,
  "slippage": "Your desired slippage for buying tokens (ex: 0.15 = 15%)",
  "minBuy": "Minimum buy amount (ex: 0.0001)",
  "maxBuy": "Maximum buy amount (ex: 0.1)",
  "microBuyAmount": "0.0001",
  "computeUnit": "100",
  "computeLimit": "100000",
  "blockEngineUrl": "JITO BlockEngine URL",
  "jitoTipPK": "JITO Tip Private Key",
  "jitoTipAmount": "JITO Tip Amount (ex: 0.01)",
  "sender": "PRIVATE KEY for the wallet that distributes SOL",
  "devWallet": "PUBLIC KEY of the deployer wallet to monitor for new launches",
  "useJITO": true/false
}
```

### **BlockEngine URLs**

Select the BlockEngine URL closest to your location:

- **AMSTERDAM**: `amsterdam.mainnet.block-engine.jito.wtf`
- **FRANKFURT**: `frankfurt.mainnet.block-engine.jito.wtf`
- **NEW YORK**: `ny.mainnet.block-engine.jito.wtf`
- **TOKYO**: `tokyo.mainnet.block-engine.jito.wtf`

---

## 🚀 **How to Run**

1. **Install Node.js**  
   Download and install Node.js from [here](https://nodejs.org).

2. **Install Dependencies**  
   Open your terminal and run:

   ```bash
   npm install
   ```

3. **Edit the config.json File**  
   Modify the `config.json` file with your details (RPC URL, wallet addresses, etc.).

4. **Run the Bot**  
   Execute the following command to start the bot:

   ```bash
   node main.js
   ```

---

## 🎮 **Modes of Operation**

The bot offers several modes for different use cases, each designed for specific tasks like generating volume, trading, and wallet management.

### 1️⃣ **Buy Modes**

1. **Gen Volume (JITO)**

   - **How it works**: Bundles up to 10 wallets to buy a token until all wallets have participated.
   - **When to use**: When you need to generate volume for a token.

2. **Auto Volume (JITO)**

   - **How it works**: Monitors the dev address for new Pump.Fun launches and automatically runs human-like trades to generate volume.
   - **When to use**: Ideal for automatic token volume generation after new token launches.

3. **Human Mode (JITO)**

   - **How it works**: Executes the “Buy Buy Sell” strategy across all wallets to simulate human trading behavior.
   - **When to use**: When you want to simulate realistic trades with each wallet.

4. **MicroBuy (SPAM)**

   - **How it works**: Continuously buys small amounts of a token using the configuration values, without using JITO.
   - **When to use**: Ideal for generating micro volume and spamming buys.

5. **Same TX**

   - **How it works**: Spams buy & sell transactions with the same wallet in a loop.
   - **When to use**: Useful for constant trading activity with a fixed amount.

6. **Warmup Mode**

   - **How it works**: Buys and sells recently traded tokens with a random SOL amount to avoid detection as a new wallet.
   - **When to use**: To simulate activity from fresh wallets, avoiding blockchain scanners.

7. **Stagger Mode**
   - **How it works**: Delays each buy with a defined time interval and uses JITO for optimized transactions.
   - **When to use**: For staggered volume generation with precise delays between buys.

---

### 2️⃣ **Sell Modes**

1. **Sell All (JITO)**

   - **How it works**: Sells all tokens in each wallet.
   - **When to use**: To sell the entire token balance across all wallets.

2. **Single Sell**

   - **How it works**: Sells 100% of the tokens from a selected wallet.
   - **When to use**: When you want to sell tokens from a specific wallet.

3. **Cleanup Mode**
   - **How it works**: Sells all tokens in your wallets, essentially cleaning up all your Pump.Fun tokens.
   - **When to use**: After finishing your trading activity, to clean up your wallets.

---

### 3️⃣ **Wallet Modes**

1. **Gen Wallets**

   - **How it works**: Generates a specified number of wallets and stores them in `/keypairs` along with `wallets.txt`.
   - **When to use**: To generate multiple wallets for volume generation.

2. **Check Balances**

   - **How it works**: Checks the SOL and SPL token balance of each wallet.
   - **When to use**: To monitor wallet balances.

3. **Close Token Accounts**

   - **How it works**: Closes unused SPL Token Accounts to reclaim rent fees.
   - **When to use**: To clean up unnecessary token accounts.

4. **Create Profiles**
   - **How it works**: Creates profiles (username + bio) on Pump.Fun.
   - **When to use**: When you want to create profiles for your wallets.

---

### 4️⃣ **Transfer Modes**

1. **Transfer SOL to Sub Wallets**

   - **How it works**: Transfers SOL from your main wallet to every sub-wallet in `wallets.txt` or `/keypairs`.
   - **When to use**: To fund your sub-wallets for transaction fees.

2. **Transfer SOL Back to Main Wallet**

   - **How it works**: Sends SOL from each sub-wallet back to your main wallet.
   - **When to use**: To consolidate SOL back to the main wallet.

3. **Transfer Tokens to Wallet**

   - **How it works**: Transfers 100% of the token balance from your sub-wallets to a specified wallet.
   - **When to use**: To consolidate tokens into a main wallet.

4. **Quit**
   - **How it works**: Exits the application.
   - **When to use**: To safely stop the bot.

---

## 📚 **BlockEngine URLs**

Select the **BlockEngine URL** closest to your location for optimized performance:

- **AMSTERDAM**: `amsterdam.mainnet.block-engine.jito.wtf`
- **FRANKFURT**: `frankfurt.mainnet.block-engine.jito.wtf`
- **NEW YORK**: `ny.mainnet.block-engine.jito.wtf`
- **TOKYO**: `tokyo.mainnet.block-engine.jito.wtf`

---

## 💖 Support the Developer

If you found this bot helpful and would like to support the development of more resources like this, consider tipping! If you need full source code, please contact me. I will give you source code anytime. Your contributions help keep the project alive and thriving.

**Solana Wallet Address:** `27uqtpRjpnDEiQ9SFJQKN2fEBQLEx3ptvJgGhV8AV83U`
**ETH Wallet Address:** `0xd64EA7D33dd5a96A6522fc6b6621b515f5a11EE7`

Thank you for your support!

Happy swapping! If you have any questions or run into issues, please open an issue in the GitHub repository.

## 📞 Author

Telegram: [@g0drlc](https://t.me/g0drlc)
