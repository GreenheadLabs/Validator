# When the host arrives

The Linux machine is not here yet. validator.greenhead.io is not live. This is a checklist for later. It does not install rippled, create keys, or change DNS.

- [ ] Install rippled on the host.
- [ ] Create the validator keys on the host. Keep the key file out of this repo.
- [ ] Create the validator token on the host and install it only in the local `rippled.cfg`. Leave `[validator_token]` empty in git.
- [ ] Set DNS for validator.greenhead.io and serve `/.well-known/xrp-ledger.toml` over HTTPS. The public key in that file must match the validator manifest.
- [ ] Open peer port 51235. Keep admin and RPC on localhost.
- [ ] Watch agreement once the server is proposing: it should stay in step with the network.
