# iscrypt-artikel

Fachartikel über ISCRIPT, geschrieben als ISCRIPT-Projekt.

## Was ist das?

Dieses Repository ist ein **konkreter Artikel** über ISCRIPT — die
Programmiersprache, die formale Code-Struktur mit freier Sprache
verbindet. Der Artikel wurde in ISCRIPT geschrieben und mit dem
ISCRIPT-Resolver in Markdown (Fachartikel) und HTML (Homepage)
aufgelöst.

## Zusammenhang mit iscrypt

Die **Sprache** und die **Werkzeuge** liegen in
[TheoTaat/iscrypt](https://github.com/TheoTaat/iscrypt). Dieses
Repository hängt davon ab:

```json
"dependencies": { "iscrypt": "github:TheoTaat/iscrypt" }
```

Beim `npm install` wird iscrypt als Dependency installiert.
Die Version ist im `package.json` gepinnt:

```json
"dependencies": { "iscrypt": "github:TheoTaat/iscrypt#v0.1.0" }
```

## Versionierung / Dependency

`iscrypt-artikel` ist an eine konkrete Version von iscrypt
g
ew=ebunden (#v0.1.0 im package.json + Commit in package-lock.json).
`npm install` holt immer exakt diesen Stand — reproduzierbarer
Build, kein stiller Bruch, wenn sich an iscrypt etwas ändert.

**Auf eine neue iscrypt-Version updaten:**

1. In `iscrypt`: Änderungen committen + neuer Tag (`v0.2.0`) + push
2. Hier:_dependency anpassen: `"iscrypt": "github:TheoTaat/iscrypt#v0.2.0"`
3. `npm install` → neuer `package-lock.json` → commit
4. Pipeline verifizieren: `npm run extract && npm run resolve`

## Struktur

```
iscrypt-artikel/
├── README.md                    # diese Datei
├── package.json                 # Abhängigkeit: iscrypt
├── code/
│   └── iscrypt.isc              # Artikel-Code (domänenneutral)
├── kontexte/
│   ├── iscrypt.inhalt.txt       # Kontext A: Inhalt (artefakt-unabhängig)
│   ├── fachartikel.form.txt     # Kontext B: Form des Fachartikels
│   ├── homepage.form.txt        # Kontext B: Form der Homepage
│   └── fachartikel.vorlage.txt  # Vorlage für neue Kontexte B
└── out/
    ├── artikel.generiert.md     # Fachartikel-Rohling (Markdown)
    ├── artikel.ueberarbeitet.md # menschliche Überarbeitung (bleibt)
    ├── artikel.generiert.html   # Homepage-Rohling (HTML)
    ├── artikel.ueberarbeitet.html
    └── artikel.diff.md          # was hat sich geändert?
```

## Kontext A und Kontext B

Der Kontext ist zweigeteilt:

- **Kontext A** (`kontexte/iscrypt.inhalt.txt`) — Alles über
  ISCRIPT an sich. Was es ist, was es leistet, welche Fakten
  gelten. Bleibt bei jedem Artefakt-Wechsel gleich.

- **Kontext B** (`fachartikel.form.txt` / `homepage.form.txt`)
  — Wie das Artefakt strukturiert, aufgebaut, getönt sein soll.
  Wird ausgetauscht, wenn das Artefakt-Wechsel.

## Der Artefakt-Wechsel

Um von Fachartikel zu Homepage zu wechseln:

1. Kontext B tauschen: `fachartikel.form.txt` → `homepage.form.txt`
2. Domänengrammatik: `--domaene fachpublikation` → `website`

Alles andere bleibt stabil: Kontext A, Code, Resolver.

## Generierung

Voraussetzung: Node.js ≥ 18, API-Key für einen LLM-Provider
(Mistral, Moonshot oder Anthropic).

```bash
# Installation (holt iscrypt aus dem GitHub-Repo)
npm install

# Fachartikel (Markdown)
npm run generate

# Homepage (HTML)
npm run extract:homepage && npm run resolve:homepage
```

**Zwei Stufen:**

1. **KI-Schicht (Stufe 2):** Kontext A + B (freie Sprache) →
   `out/parameter.json` (strukturierte Parameter).
   Provider-Chain: Mistral → Kimi → Claude. Fallback: regelbasiert.

2. **Resolver (Stufe 3):** Code + Parameter + Domänengrammatik →
   Rohling im Zielformat. Regelbasiert, deterministisch.

**Das Artefakt ist ein Entwurf, kein Endprodukt.** Der Mensch
überarbeitet `out/artikel.ueberarbeitet.md`. Beim nächsten Lauf
wird die generierte Schicht neu erzeugt, die überarbeitete Schicht
bleibt. Ein Diff zeigt, was sich geändert hat.

## Lizenz

MIT
