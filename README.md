# Tezos X Previewnet

Long-running preview network for [Tezos X](https://tezos.com). Runs both the **EVM interface** and the **Michelson interface** on the same rollup, enabling cross-runtime development and testing.

> **Network portal:** `https://<PREVIEWNET_DOMAIN>/`

---

## Network identifiers

| Interface | CAIP-2 | Chain ID |
|-----------|--------|----------|
| EVM interface | `eip155:127124` | `127124` (`0x1f094`) |
| Michelson interface | `tezos:NetXH12Aer3be93` | `NetXH12Aer3be93` |

---

## Endpoints

| Service | URL |
|---------|-----|
| EVM JSON-RPC | `https://<PREVIEWNET_DOMAIN>/rpc` |
| Tezos RPC | `https://<PREVIEWNET_DOMAIN>/rpc/tezlink` |
| Smart Rollup Node | `https://<PREVIEWNET_DOMAIN>/rollup` |
| Blockscout (EVM explorer) | `https://<PREVIEWNET_BLOCKSCOUT_DOMAIN>` |
| TzKT (Tezos indexer) | `https://<PREVIEWNET_TZKT_DOMAIN>` |
| Faucet | `https://<PREVIEWNET_FAUCET_DOMAIN>` |

---

## Add to your wallet

### MetaMask (EVM interface)

| Field | Value |
|-------|-------|
| Network name | Tezos X Previewnet |
| RPC URL | `https://<PREVIEWNET_DOMAIN>/rpc` |
| Chain ID | `127124` |
| Currency symbol | `XTZ` |
| Block explorer | `https://<PREVIEWNET_BLOCKSCOUT_DOMAIN>` |

### Temple / octez-client (Michelson interface)

| Field | Value |
|-------|-------|
| RPC URL | `https://<PREVIEWNET_DOMAIN>/rpc/tezlink` |
| Chain ID | `NetXH12Aer3be93` |

```bash
octez-client --endpoint https://<PREVIEWNET_DOMAIN>/rpc/tezlink \
  config update
```

---

## Bootstrap accounts

Pre-funded accounts available on the network. **For testing only — do not use in production.**

### EVM interface

| Address | Private key |
|---------|-------------|
| `0x6ce4d79d4E77402e1ef3417Fdda433aA744C6e1c` | `0x9722f6cc9ff938e63f8ccb74c3daa6b45837e5c5e3835ac08c44c50ab5f39dc0` |
| `0xB53dc01974176E5dFf2298C5a94343c2585E3c54` | `0x3a6a6ca30c1ef1ce605a63a7a1a4ff4c689f8414ca0838bca29423f0ec280ff5` |
| `0x9b49c988b5817Be31DfB00F7a5a4671772dCce2B` | `0x0eb9bfa77d6cd145cdc0e3d6f902ee1464aeb5f62b02e38f111c9b60cd3adab5` |

### Michelson interface

| Alias | Public key | Secret key |
|-------|------------|------------|
| bootstrap1 | `edpkuBknW28nW72KG6RoHtYW7p12T6GKc7nAbwYX5m8Wd9sDVC9yav` | `edsk3gUfUPyBSfrS9CCgmCiQsTCHGkviBDusMxDJstFtojtc1zcpsh` |
| bootstrap2 | `edpktzNbDAUjUk697W7gYg2CRuBQjyPxbEg8dLccYYwKSKvkPvjtV9` | `edsk39qAm1fiMjgmPkw1EgQYkMzkJezLNewd7PLNHTkr6w9XA2zdfo` |
| bootstrap3 | `edpkuTXkJDGcFd5nh6VvMz8phXxU3Bi7h6hqgywNFi1vZTfQNnS1RV` | `edsk4ArLQgBTLWG5FJmnGnT689VKoqhXwmDPBuGx3z4cvwU9MmrPZZ` |
| bootstrap4 | `edpkuFrRoDSEbJYgxRtLx2ps82UdaYc1WwfS9sE11yhauZt5DgCHbU` | `edsk2uqQB9AY4FvioK2YMdfmyMrer5R8mGFyuaLLFfSRo8EoyNdht3` |
| bootstrap5 | `edpkv8EUUH68jmo3f7Um5PezmfGrRF24gnfLpH3sVNwJnV5bVCxL2n` | `edsk4QLrcijEffxV31gGdN2HU7UpyJjA8drFoNcmnB28n89YjPNRFm` |

```bash
octez-client --endpoint https://<PREVIEWNET_DOMAIN>/rpc/tezlink \
  import secret key bootstrap1 unencrypted:edsk3gUfUPyBSfrS9CCgmCiQsTCHGkviBDusMxDJstFtojtc1zcpsh
```

---

## Quick connectivity check

```bash
# EVM chain ID
curl -s -X POST https://<PREVIEWNET_DOMAIN>/rpc \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":1}'
# → {"result":"0x1f094",...}

# Tezos chain ID
curl -s https://<PREVIEWNET_DOMAIN>/rpc/tezlink/chains/main/chain_id
# → "NetXH12Aer3be93"
```
