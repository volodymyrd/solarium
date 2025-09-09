# solarium

Solarium blockchain

```
cargo run --package solarium-keygen -- new --no-passphrase -fso config/faucet.json
cargo run --package solarium-keygen -- new --no-passphrase -so config/leader/identity.json
cargo run --package solarium-keygen -- new --no-passphrase -so config/leader/stake-account.json
cargo run --package solarium-keygen -- new --no-passphrase -so config/leader/vote-account.json
```

```
cargo run --package solarium-genesis -- \
--max-genesis-archive-unpacked-size 1073741824  \
--enable-warmup-epochs \
--bootstrap-validator config/leader/identity.json config/leader/vote-account.json config/leader/stake-account.json \
--ledger config/leader \
--faucet-pubkey config/faucet.json \
--faucet-lamports 500000000000000000 \
--hashes-per-tick auto \
--cluster-type development
```

```
cargo run --package agave-ledger-tool -- -l config/leader accounts
```
