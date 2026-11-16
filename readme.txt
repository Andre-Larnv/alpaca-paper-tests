# Alpaca Trading API: Postman tests

API tests for the [Alpaca Trading API](https://docs.alpaca.markets/) (paper account, US stocks), written in Postman.

## Scope

- Auth & Account
- Assets & Market (in progress)
- Orders (in progress)
- Positions (in progress)
- End-to-end trading flow (in progress)

## Tech stack

- Postman
- Newman (planned)

## How to run

1. Create a free Alpaca account and switch to **Paper Trading**.
2. Generate API keys (key ID and secret).
3. In Postman, import the files from the `postman/` folder:
   - `alpaca-trading.postman_collection.json`
   - `alpaca-paper.postman_environment.json`
4. Open the `alpaca-paper` environment and fill in `key` and `secret_key`.
5. Select the environment (top right) and run the collection with Collection Runner.

## Test cases

### Auth & Account

| ID | Test case | Expected result |
|----|-----------|-----------------|
| AUTH-01 | Get account with valid keys | 200; status ACTIVE; currency USD; trading not blocked; balance fields are numeric strings; equity matches cash + market values |
| AUTH-02 | Get account with invalid key | 401; error message present; no account data returned |
| AUTH-03 | Get account without auth headers | 401; error message present; no account data returned |

## Out of scope

Crypto, options, watchlists, websocket streaming.