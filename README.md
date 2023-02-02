# Cosmos Analytics Registry

The Cosmos Analytics Registry is home the Analytics interfaces supporting the Cosmos Ecosystem. It can be used for things like price aggregator api providers, like CoinGecko; for block explorers, like Mintscan, or many other analytics or data interface.

E.g., CoinGecko
```
{
  "provider": "CoinGecko",
  "website": "https://www.coingecko.com",
  "interfaces": [
    {
      "type": "browser",
      "parameters": {
        "base_url": "https://www.coingecko.com/",
        "asset_id": true
      },
      "requests": {
        "asset": "{base_url}/coins/{asset_id}"
      }
    },
    {
      "type": "rest_api",
      "parameters": {
        "base_url": "https://www.coingecko.com/api/v3",
        "asset_id": true,
        "fiat_currency_id": true
      },
      "requests": {
        "ping": "{base_url}/ping",
        "asset_ids": "{base_url}/coins/list",
        "asset": "{base_url}/coins/{id}",
        "asset_price": "{base_url}/simple/price?ids={asset_id}&vs_currencies={fiat_currency_id}",
        "market_cap": "{base_url}/simple/price?ids={asset_id}&vs_currencies={fiat_currency_id}&include_market_cap=true",
        "volume_24h": "{base_url}/simple/price?ids={asset_id}&vs_currencies={fiat_currency_id}&include_24hr_vol=true",
        "price_change_percent_24h": "{base_url}/simple/price?ids={asset_id}&vs_currencies={fiat_currency_id}&include_24hr_change=true"
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
