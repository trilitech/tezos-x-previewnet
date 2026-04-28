# Tezos X Previewnet

Long-running preview network for [Tezos X](https://tezos.com). Runs both the **EVM interface** and the **Michelson interface** on the same rollup, enabling cross-runtime development and testing.

> **Network portal:** `https://previewnet.tezosx.nomadic-labs.com/`

---

## Network identifiers

| Interface | CAIP-2 | Chain ID |
|-----------|--------|----------|
| EVM interface | `eip155:128064` | `128064` |
| Michelson interface | `tezos:NetXY2oPPzkxUW1` | `NetXY2oPPzkxUW1` |

---

## Endpoints

| Service | URL |
|---------|-----|
| EVM JSON-RPC | `https://evm.previewnet.tezosx.nomadic-labs.com` |
| Tezos RPC (Michelson interface) | `https://michelson.previewnet.tezosx.nomadic-labs.com` |
| Smart Rollup Node | `https://previewnet.tezosx.nomadic-labs.com/rollup` |
| Blockscout (EVM explorer) | `https://blockscout.previewnet.tezosx.nomadic-labs.com` |
| TzKT (Tezos indexer) | `https://tzkt.previewnet.tezosx.nomadic-labs.com` |
| Faucet | `https://faucet.previewnet.tezosx.nomadic-labs.com` |

---

## Get tokens

Use the faucet to fund your accounts on both interfaces:

> **Faucet:** `https://faucet.previewnet.tezosx.nomadic-labs.com`

---

## Add to your wallet

### MetaMask (EVM interface)

| Field | Value |
|-------|-------|
| Network name | Tezos X Previewnet |
| RPC URL | `https://evm.previewnet.tezosx.nomadic-labs.com` |
| Chain ID | `128064` |
| Currency symbol | `XTZ` |
| Block explorer | `https://blockscout.previewnet.tezosx.nomadic-labs.com` |

### Temple / octez-client (Michelson interface)

| Field | Value |
|-------|-------|
| RPC URL | `https://michelson.previewnet.tezosx.nomadic-labs.com` |
| Chain ID | `NetXY2oPPzkxUW1` |

```bash
octez-client --endpoint https://michelson.previewnet.tezosx.nomadic-labs.com \
  config update
```

---

## Quick connectivity check

```bash
# EVM chain ID
curl -s -X POST https://evm.previewnet.tezosx.nomadic-labs.com \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":1}'

# Tezos chain ID
curl -s https://michelson.previewnet.tezosx.nomadic-labs.com/chains/main/chain_id
```
