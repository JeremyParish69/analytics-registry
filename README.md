# Cosmos Interface Registry

The Cosmos Interface Registry is the registry for data and analytics interfaces supporting any of the Cosmos Ecosystem. It can be used for many data providers, such as price aggregators (e.g., CoinGecko), block explorers (e.g., Mintscan), chain endpoints (e.g., Keplr's chain endpoints), and many other analytics or data interfaces.

E.g., CoinGecko
```
{
  "provider": "CoinGecko",
  "website": "https://www.coingecko.com",
  "interfaces": [
    {
      "type": "browser",
      "base_url": "https://www.coingecko.com",
      "requests": {
        "asset": "${base_url}/coins/${asset_id}"
      }
    },
    {
      "type": "rest_api",
      "base_url": "https://www.coingecko.com/api/v3",
      "requests": {
        "ping": "${base_url}/ping",
        "asset_ids": "${base_url}/coins/list",
        "asset": "${base_url}/coins/${id}",
        "price": "${base_url}/simple/price?ids=${asset_id}&vs_currencies=${fiat_currency_id}",
        "market_cap": "${base_url}/simple/price?ids=${asset_id}&vs_currencies=${fiat_currency_id}&include_market_cap=true",
        "volume_24h": "${base_url}/simple/price?ids=${asset_id}&vs_currencies=${fiat_currency_id}&include_24hr_vol=true",
        "price_change_24h_percent": "${base_url}/simple/price?ids=${asset_id}&vs_currencies=${fiat_currency_id}&include_24hr_change=true"
      }
    }
  ],
  "ids": {
    "fiat_currencies": [
      {
        "name": "USD",
        "id": "usd"
      }
    ],
    "assets": [
      {
        "chain_name": "cosmoshub",
        "base_denom": "uatom",
        "id": "atom"
      },
      {
        "chain_name": "osmosis",
        "base_denom": "uosmos",
        "id": "osmosis"
      },
      {
        "chain_name": "osmosis",
        "base_denom": "uion",
        "id": "ion"
      }
    ]
  }
}
```

E.g., Mintscan Explorer
```
{
  "provider": "Mintscan",
  "website": "https://www.mintscan.io",
  "interfaces": [
    {
      "type": "browser",
      "base_url": "https://www.mintscan.io",
      "requests": {
        "chain": "${base_url}/${chain_id}",
        "chain_parameters": "${base_url}/${chain_id}/parameters",
        "txs": "${base_url}/${chain_id}/txs",
        "tx_hash": "${base_url}/${chain_id}/txs/${tx_hash}",
        "account_bech32": "${base_url}/${chain_id}/account/${account_address}",
        "validators": "${base_url}/${chain_id}/validators",
        "validator_bech32": "${base_url}/${chain_id}/validators/${validator_address}",
        "contracts": "${base_url}/${chain_id}/wasm/",
        "contract_bech32": "${base_url}/${chain_id}/wasm/contract/${contract_address}",
        "blocks": "${base_url}/${chain_id}/blocks",
        "block": "${base_url}/${chain_id}/blocks/${block_number}",
        "proposals": "${base_url}/${chain_id}/proposals",
        "proposal": "${base_url}/${chain_id}/proposals/${proposal_number}",
        "chain_assets": "${base_url}/${chain_id}/assets",
        "chain_asset": "${base_url}/${chain_id}/assets/${asset_id}",
        "ibc_connections": "${base_url}/${chain_id}/relayers",
        "ibc_connection": "${base_url}/${chain_id}/relayers/${channel_id}"
      }
    }
  ],
  "ids": {
    "chains": [
      {
        "chain_name": "cosmoshub",
        "id": "cosmos"
      },
      {
        "chain_name": "osmosis",
        "id": "osmosis"
      }
    ],
    "assets": [
      {
        "chain_name": "cosmoshub",
        "base_denom": "uatom",
        "id": "dWF0b20=?type=staking"
      },
      {
        "chain_name": "osmosis",
        "base_denom": "uosmo",
        "id": "dW9zbW8=?type=staking"
      },
      {
        "chain_name": "osmosis",
        "base_denom": "uion",
        "id": "dWlvbg==?type=native"
      }
    ]
  }
}
```
