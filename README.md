# SandClaw Plugin Registry

> **Beta** — This registry is currently in beta. Feedback and bug reports are welcome via [GitHub Issues](https://github.com/kokogo100/sandclaw/issues).

Public plugin registry for [SandClaw](https://sandclaw.io), an AI-powered trading IDE.
Plugins listed here are automatically available in the SandClaw IDE **Settings > Store**.

---

## Plugins (30)

### Bundled (included with IDE)

| Plugin | Region | Asset Class | Features |
|--------|--------|-------------|----------|
| **Web Search** | — | — | DuckDuckGo market monitoring, no API key |

### Store — Base Plugins (18)

| Plugin | Region | Asset Class | Auth | Features |
|--------|--------|-------------|------|----------|
| **Upbit** | KR | Crypto | API Key | 200+ KRW pairs, Limit Order |
| **Alpaca** | US | Stock, Crypto | API Key | Paper Trading, Fractional Shares, Limit Order |
| **LS Securities** | KR | Stock (KRX) | OAuth | 13 markets, WebSocket, Limit Order |
| **KIS Securities** | KR | Stock (KRX) | API Key | WebSocket, Limit Order |
| **Kraken** | Global | Crypto | HMAC-SHA512 | 300+ pairs, WebSocket, Limit Order |
| **Interactive Brokers** | Global | Multi-Asset | CDP Cookie | 150+ markets, 33 countries, Limit Order |
| **Kalshi API** | US | Prediction Market | RSA-PSS | 38 tools, all orders are limit |
| **Angel One** | IN | Stock (NSE/BSE) | API Key | WebSocket, Limit Order `*` |
| **Zerodha** | IN | Stock (NSE/BSE) | API Key | WebSocket, Limit Order `*` |
| **Upstox** | IN | Stock (NSE/BSE) | OAuth | WebSocket, Limit Order `*` |
| **bitFlyer** | JP | Crypto | HMAC-SHA256 | WebSocket, Limit Order `*` |
| **kabu STATION** | JP | Stock (TSE) | API Key | WebSocket, Limit Order `*` (VIEW ONLY) |
| **Kalshi** (Browser) | US | Prediction Market | Browser Login | CDP browser automation |
| **Robinhood** (Browser) | US | Stock, Crypto, Events | Browser Login | CDP browser automation |
| **Web Browsing CDP** | — | — | None | General browser automation skill |
| **SBI Securities** | JP | Stock (TSE) | Browser | CDP automation `*` |
| **Rakuten Securities** | JP | Stock (TSE) | Browser | CDP automation `*` |
| **Kraken Equities** | US | Stock, ETF | — | VIEW ONLY (API not yet available) |

### Store — Extension Plugins (11)

Extensions require their base plugin to be installed.

| Extension | Base | Asset Class | Features |
|-----------|------|-------------|----------|
| **LS Futures** | LS Securities | KOSPI200 Futures/Options | Limit Order |
| **LS Night** | LS Securities | Night Session Futures | Limit Order |
| **LS Overseas** | LS Securities | US Stocks (NYSE/NASDAQ) | Limit Order |
| **LS Overseas Futures** | LS Securities | Global Futures (CME, ICE...) | Limit Order |
| **Kraken Futures** | Kraken | Crypto Perpetuals | Up to 50x leverage, Limit Order |
| **Kraken xStocks** | Kraken | Tokenized US Equities | Fractional shares, 24/5, Limit Order |
| **IBKR Options** | Interactive Brokers | Options | Greeks, Limit Order |
| **IBKR Futures** | Interactive Brokers | Futures | Global markets, Limit Order |
| **IBKR Forex** | Interactive Brokers | Forex | Currency pairs, Limit Order |
| **IBKR Bonds** | Interactive Brokers | Fixed Income | Bond trading, Limit Order |
| **IBKR Events** | Interactive Brokers | Event Contracts | Prediction market, Limit Order |

> `*` **Community Testing**: The developer does not reside in these countries and could not test with real accounts. These plugins are implemented based on official API documentation. If you encounter issues, please provide feedback via [GitHub Issues](https://github.com/kokogo100/sandclaw/issues).

### Coverage Summary

| | Count |
|---|---|
| Total Plugins | 30 |
| API Trading Plugins | 22 |
| Limit Order Support | 22 |
| Regions | KR, US, JP, IN, Global |
| Asset Classes | Stocks, Crypto, Futures, Options, Forex, Bonds, Prediction Markets |

---

## Security

- All credentials are encrypted via **Windows Credential Manager** (never stored in plain text)
- Plugin ZIPs are verified with **SHA-256** checksums
- Registry is signed with **Ed25519** (`registry/index.json.sig`)
- AST-based security scan on install (no `eval`, `exec`, `subprocess`, etc.)

## Repository Structure

```
registry/
  index.json          <- Master plugin list (fetched by SandClaw IDE)
  index.json.sig      <- Ed25519 signature
icons/                <- Plugin icons (PNG)
releases/             <- Plugin ZIP packages
```

## For Plugin Developers

1. Build your plugin following the [Plugin SDK docs](https://sandclaw.io/docs/plugins)
2. Package as ZIP: `manifest.json` + `main.py` + modules
3. Open a [GitHub Issue](https://github.com/kokogo100/sandclaw/issues) with your plugin
4. After review, your plugin appears in the Store for all users

## For SandClaw Users

Open **Settings > Store** in your SandClaw IDE to browse, install, and manage plugins.
