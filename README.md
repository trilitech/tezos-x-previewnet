# Tezos X Previewnet

Long-running preview network for [Tezos X](https://tezos.com). Runs both the **EVM interface** and the **Michelson interface** on the same rollup, enabling cross-runtime development and testing.

> **Network portal:** `https://previewnet.tezosx.nomadic-labs.com/`

---

## Network identifiers

| Interface | CAIP-2 | Chain ID |
|-----------|--------|----------|
| EVM interface | `eip155:128064` | `128064` |
| Michelson interface | `tezos:NetXY2oPPvjhUxP` | `NetXY2oPPvjhUxP` (TBC) |

---

## Endpoints

| Service | URL |
|---------|-----|
| EVM JSON-RPC | `https://previewnet.tezosx.nomadic-labs.com/rpc` |
| Tezos RPC | `https://previewnet.tezosx.nomadic-labs.com/rpc/tezlink` |
| Smart Rollup Node | `https://previewnet.tezosx.nomadic-labs.com/rollup` |
| Blockscout (EVM explorer) | `https://<PREVIEWNET_BLOCKSCOUT_DOMAIN>` |
| TzKT (Tezos indexer) | `https://<PREVIEWNET_TZKT_DOMAIN>` |
| Faucet | `https://<PREVIEWNET_FAUCET_DOMAIN>` |

---

## Get tokens

Use the faucet to fund your accounts on both interfaces:

> **Faucet:** `https://<PREVIEWNET_FAUCET_DOMAIN>`

---

## Add to your wallet

### MetaMask (EVM interface)

| Field | Value |
|-------|-------|
| Network name | Tezos X Previewnet |
| RPC URL | `https://previewnet.tezosx.nomadic-labs.com/rpc` |
| Chain ID | `128064` |
| Currency symbol | `XTZ` |
| Block explorer | `https://<PREVIEWNET_BLOCKSCOUT_DOMAIN>` |

### Temple / octez-client (Michelson interface)

| Field | Value |
|-------|-------|
| RPC URL | `https://previewnet.tezosx.nomadic-labs.com/rpc/tezlink` |
| Chain ID | `NetXY2oPPvjhUxP` (TBC) |

```bash
octez-client --endpoint https://previewnet.tezosx.nomadic-labs.com/rpc/tezlink \
  config update
```

---

## Quick connectivity check

```bash
# EVM chain ID
curl -s -X POST https://previewnet.tezosx.nomadic-labs.com/rpc \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":1}'

# Tezos chain ID
curl -s https://previewnet.tezosx.nomadic-labs.com/rpc/tezlink/chains/main/chain_id
```
