<p align="center"><img src="https://raw.githubusercontent.com/PapaFuchs84/ScreenBuddy/main/docs/logo/fuchslabs-logo.png" alt="FuchsLabs" width="96"></p>

# ScreenBuddy-Plugins

[Deutsch](README.md) · **English**

The signed plugin store for [ScreenBuddy](https://github.com/PapaFuchs84/ScreenBuddy). A plugin is **one JSON file without program code** (`plugins/<id>/<id>.flplugin.json`). This repository contains data only.

## How the store works

1. Authors submit a plugin as a **pull request** ([author guide](https://github.com/PapaFuchs84/ScreenBuddy/blob/main/docs/PLUGIN-AUTHORS.md)).
2. CI checks it with the app's validator (`fl-plugin-validate --store`): required fields, MIT/CC0-1.0, HTTPS hosts only, no local addresses.
3. A maintainer reviews purpose, hosts and license and accepts it.
4. The maintainer regenerates `docs/index.json` and **signs** it **offline** with the FuchsLabs key (Ed25519). The private key is never in GitHub.
5. ScreenBuddy fetches index and revocation list at most once a day (GitHub Pages), checks the signature and the SHA-256 of every plugin and shows the hosts before installation.

CI rejects every change where `plugins/` and the signed index do not match.

Rules, license and privacy: [store terms](https://github.com/PapaFuchs84/ScreenBuddy/blob/main/docs/PLUGIN-STORE-TERMS.md) (draft). Report a plugin: [issue "Report a plugin"](https://github.com/PapaFuchs84/ScreenBuddy/issues/new?template=plugin-melden.yml).

**Status:** the store is being set up. While `docs/index.json` is missing or ScreenBuddy has no signing key built in, the app shows "not available".

© 2026 FuchsLabs · MIT, name and logo excluded ([TRADEMARKS.md](TRADEMARKS.md)).
