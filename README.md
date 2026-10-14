# PokéDeck – Kartendaten

Dieses Repository veröffentlicht die Kartendaten für die iOS-App **PokéDeck**: Karten, Texte, Preise, Turnier-Decklisten und Legalitätsregeln für das Format Standard.

Ein GitHub-Workflow baut die Daten **jede Nacht** neu und hängt sie an das Release [`catalog`](../../releases/tag/catalog). Die App prüft einmal am Tag, ob es neuere Daten gibt. Neue Sets, Preise und Turnier-Listen kommen so ohne App-Update an.

| Datei | Inhalt |
|---|---|
| `manifest.json` | Stand, Anzahl der Drucke, SHA-256-Prüfsumme und Größe jeder Datei |
| `catalog.sqlite.lzfse` | Kartenkatalog als SQLite, LZFSE-komprimiert |
| `formats.json` | Formate, Regulierungszeichen, Kopien-Grenzen |
| `legality-overrides.json` | von Hand geprüfte Ausnahmen zur Reprint-Regel |
| `staples.json` | Rollen und Passt-Bedingungen für den Deck-Generator |

So schützt sich die App vor fehlerhaften Daten:
- Sie installiert ein Update nur, wenn alle Prüfsummen stimmen.
- Der Katalog muss sich öffnen lassen und genug Karten enthalten.
- Sonst bleiben die bisherigen Daten aktiv.

## Quellen

- **Karten, Texte, Bilder:** [TCGdex](https://tcgdex.dev) (MIT-Lizenz)
- **Turnier-Decklisten:** [Limitless TCG](https://limitlesstcg.com)
- **Preise:** Cardmarket-Trendpreise über TCGdex, ohne Gewähr

PokéDeck ist eine inoffizielle Fan-App. Sie steht in keiner Verbindung zu Nintendo, The Pokémon Company, Creatures oder GAME FREAK. Pokémon und alle zugehörigen Namen sind Marken ihrer jeweiligen Inhaber.
