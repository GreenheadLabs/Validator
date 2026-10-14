# Greenhead public XRPL validator

This is the Greenhead public XRP Ledger validator repository for [validator.greenhead.io](https://validator.greenhead.io).

**Status: not launched.** The Linux host has not arrived. The domain is not live, nothing in this repo is deployed, and validator keys have not been created.

More will be added after the machine shows up. Until then, this repo only holds templates and a later checklist.

## What this repo holds

- `config/rippled.cfg.example` — commented `rippled` config. Peer port `51235`. Admin and RPC bound to localhost. `[validator_token]` is present and empty.
- `config/validators.txt.example` — placeholder noting that a trusted validator list is still required to sync, and that the list is chosen when the host arrives.
- `well-known/xrp-ledger.toml.example` — template for `https://validator.greenhead.io/.well-known/xrp-ledger.toml`.
- `docs/when-host-arrives.md` — checklist of later work. It does not install or configure anything.

Copy the examples onto the host when it exists. Fill them in there. Do not commit the filled copies.

## Never commit

These stay on the host, or offline, and must never be committed:

- **Validator seed** — `validation_seed`, `node_seed`, and `validator-keys.json` (the key file holds the secret key).
- **Validator token** — the value under `[validator_token]` in the live config.
- **Manifest private material** — the private key that signs the validator manifest.
- **Node database** — `node_db`, `database_path`, NuDB or RocksDB files, and rippled debug logs.

Also keep out wallet files, `*.key`, and local secret env files. See `.gitignore`.
