# SandClaw Plugin Registry

Public registry for [SandClaw](https://sandclaw.io) plugins.

## Structure

```
registry/
├── index.json              ← Master plugin list (fetched by SandClaw IDE)
└── plugins/
    ├── upbit/icon.png
    ├── alpaca/icon.png
    ├── kalshi/icon.png
    └── robinhood/icon.png
```

## For Plugin Developers

Want to publish your plugin to the SandClaw Store?

1. Build your plugin following the [Plugin SDK docs](https://sandclaw.io/docs/plugins)
2. Package as ZIP: `manifest.json` + `main.py` + dependencies
3. Open a [GitHub Issue](https://github.com/kokogo100/sandclaw/issues) with your plugin ZIP
4. After review, your plugin will appear in the Store for all users

## For SandClaw Users

Plugins listed here are automatically available in your SandClaw IDE Store.
Open **Settings > Store** to browse, install, and manage plugins.
