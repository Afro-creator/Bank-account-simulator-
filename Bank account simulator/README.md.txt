# Bank Account Simulation

Simple command-line bank account simulator in Python. Supports account creation, deposits, withdrawals, transfers, transaction histories, and JSON persistence.

## Features
- Create accounts with optional initial deposit
- Deposit and withdraw funds
- Transfer between accounts
- Per-account transaction history with timestamps
- Persist data to a JSON file for durability

## Requirements
- Python 3.8+
- No external packages required

## Usage (Windows)
1. Open PowerShell or CMD.
2. Change to the directory containing the script:
   cd "C:\path\to\folder"
3. Run the script:
   python bank_simulation.py
4. Follow the interactive menu.

## Data file
- The simulator saves accounts to `bank_db.json` (in the same directory as the script).
- The file is human-readable JSON containing account balances and transaction histories.

## Design notes
- Accounts and transactions are represented with dataclasses for clarity.
- The data store is an in-memory dict keyed by account ID; changes are saved to disk after each operation.
- Transaction history includes type, amount, timestamp, optional note, and related account for transfers.

## Known limitations & improvements
- Writes are not atomic; a power loss during save can corrupt the DB — consider write-to-temp-and-rename.
- No concurrency control; running multiple instances may cause lost updates.
- Validation is minimal (e.g., negative amounts prevented); add stricter checks (max transfer limits, account name validation).
- Tests and CLI input sanitization would improve reliability.

## License
Unlicensed — free to use and adapt for learning and experimentation.