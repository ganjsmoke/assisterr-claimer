
# Assister Auto Claim Bot

This Node.js script automates the daily claiming of points on Assisterr.ai. It logs in with specified accounts, checks referral status, and claims points daily, while keeping track of the next eligible claim time.

**⚠️ Warning:** This script only works with the referral link associated with the author: [Assisterr Referral Link](https://build.assisterr.ai/?ref=66bceba8f6e625e389d8d7f1). Using a different referral will prevent the bot from functioning properly.

## Features

- **Automated Login:** Logs in for each account at the start of the script, obtaining a fresh access token every time.
- **Referral Check:** Verifies each account’s referral status before claiming points.
- **Daily Claiming:** Claims daily points and tracks the next eligible claim time.
- **User-Agent Randomization:** Uses randomized user-agents to simulate realistic requests.
- **Lightweight Account Tracking:** Only `next_claim_time` is stored, minimizing saved account data.

## Prerequisites

- [Node.js](https://nodejs.org/) (v12 or higher)
- [NPM](https://www.npmjs.com/) (usually included with Node.js)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ganjsmoke/assisterr-claimer.git
   cd assister-claimer
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Prepare your accounts file:**
   - Create a file named `accounts.json` in the root directory, structured as follows:

     ```json
     {
       "accounts": [
         {
           "private_key": "your_solana_pk1"
         },
         {
           "private_key": "your_solana_pk2"
         }
       ]
     }
     ```

4. **Add User-Agent List (Optional):**
   - Create a file named `user-agent.txt` in the root directory and populate it with different user-agent strings, each on a new line. This allows the script to randomize user-agents during requests.

## Running the Script

To run the script continuously:

```bash
node index.js
```

## Important Notes

- **Referral Requirement:** This script only works with the referral link associated with the author: [https://build.assisterr.ai/?ref=66bceba8f6e625e389d8d7f1](https://build.assisterr.ai/?ref=66bceba8f6e625e389d8d7f1). Ensure your accounts were created using this referral to enable successful point claiming.

## Troubleshooting

- **Login Issues:** Ensure your accounts.json file is correctly formatted and contains valid private keys.
- **Referral Mismatch:** If an account’s referral ID doesn’t match the required static referral, the script will skip that account.
