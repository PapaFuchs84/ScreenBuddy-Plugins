<p align="center"><img src="https://raw.githubusercontent.com/PapaFuchs84/ScreenBuddy/main/docs/logo/fuchslabs-logo.png" alt="FuchsLabs" width="96"></p>

# ScreenBuddy-Plugins

**Deutsch** · [English](README.en.md)

Der signierte Plugin-Store für [ScreenBuddy](https://github.com/PapaFuchs84/ScreenBuddy). Ein Plugin ist **eine JSON-Datei ohne Programmcode** (`plugins/<id>/<id>.flplugin.json`). Dieses Repository enthält nur Daten.

## Wie der Store funktioniert

1. Autoren reichen ein Plugin per **Pull Request** ein ([Autorenleitfaden](https://github.com/PapaFuchs84/ScreenBuddy/blob/main/docs/PLUGIN-AUTOREN.md)).
2. Die CI prüft es mit dem Validator der App (`fl-plugin-validate --store`): Pflichtfelder, MIT/CC0-1.0, nur HTTPS-Hosts, keine lokalen Adressen.
3. Ein Maintainer prüft Zweck, Hosts und Lizenz und nimmt es auf.
4. Der Maintainer erzeugt `docs/index.json` neu und **signiert** sie **offline** mit dem FuchsLabs-Schlüssel (Ed25519). Der private Schlüssel liegt nie in GitHub.
5. ScreenBuddy lädt Index und Sperrliste höchstens einmal am Tag (GitHub Pages), prüft die Signatur und die SHA-256-Summe jedes Plugins und zeigt vor der Installation die Hosts an.

Die CI lehnt jede Änderung ab, bei der `plugins/` und der signierte Index nicht zusammenpassen.

Regeln, Lizenz und Datenschutz: [Store-Bedingungen](https://github.com/PapaFuchs84/ScreenBuddy/blob/main/docs/PLUGIN-STORE-BEDINGUNGEN.md) (Entwurf). Ein Plugin melden: [Issue „Plugin melden“](https://github.com/PapaFuchs84/ScreenBuddy/issues/new?template=plugin-melden.yml).

**Stand:** Der Store ist im Aufbau. Solange `docs/index.json` fehlt oder ScreenBuddy keinen Signaturschlüssel eingebaut hat, zeigt die App „nicht verfügbar“.

© 2026 FuchsLabs · MIT, Name und Logo ausgenommen ([TRADEMARKS.md](TRADEMARKS.md)).
