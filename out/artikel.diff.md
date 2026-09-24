# Diff: neue Generierung vs. bestehende Überarbeitung

**Die generierte Ausgabe hat sich geändert.**
Die bestehende Überarbeitung (artikel.ueberarbeitet.md) bleibt erhalten.
Der Mensch entscheidet, ob er die neue Generierung übernimmt oder seine Überarbeitung behält.

## Geändert (in der neuen Generierung, nicht in der Überarbeitung)

```markdown
> Eine Sprache, die Mehrdeutigkeit als Feature behandelt
**Zitation:** Weinmann, Rudolf Alexander. ISCRIPT — Code und Kontext. Schwerzenbach: lyrx GmbH, 2026.
## was-ist-iscrypt
Die zentrale These.  Wie wird sie präsentiert?
## code-ebene
Die Code-Ebene von ISCRIPT ist formales JavaScript plus markierte kontextabhängige Stellen (?{...}). Sie trägt die Struktur, die Relationen und die invariante Fakten. Sie sagt WAS.
Abgrenzung zur Kontext-Ebene: Code sagt WAS (Struktur, Fakten), Kontext sagt WIE (Präsentation, Ton, Fokus).  Beispiel: Im Lebenslauf-Beispiel trägt der Code die Stationen (was, wann, wo) als invariante Fakten.
## kontext-ebene
## auflösung
## faktum-und-rahmung
## javascript-basis
## beispiel-lebenslauf
## beispiel-narration
## doemänengrammatiken
Die Domänengrammatik wird nicht erfunden — sie wird aus bestehenden Ontologien abgeleitet. Das ist der Kern des ISCRIPT-Ansatzes: Standards dem Selbsterfinden vorziehen.
Der generische Prozess: 1.  Ontologie für die Domäne finden oder erstellen 2.
## syntax-elemente
ISCRIPT erweitert JavaScript um zwei Bausteine: ?{} für kontextabhängige Stellen und domain für die Domänengrammatik. Alles andere ist JavaScript.
| Schlüssel | Wert | Einheit |
|---|---|---|
| `?{...}` | Markiert eine kontextabhängige Stelle. Der Inhalt wird bei der Auflösung anhand der Kontextparameter bestimmt. | Syntax |
| `domain` | Definiert eine Domänengrammatik. Enthält Struktur, Invarianzen und Auflösungsregeln. | Deklaration |
| `meta` | Invariante Metadaten (Autor, Titel, Zitation). Unabhängig vom Artefakt-Typ. | Metadaten |
| `inhalte` | Liste der inhaltlichen Blöcke. Jeder Block hat id, fakten und kontext (?{}). | Struktur |
| `invarianzen` | Liste der faktum-Felder, die der Kontext nicht verändern darf. | Sicherheitsmechanismus |
| `kontextparameter` | Die vier Parametergruppen, die aus der Kontext-Prosa extrahiert werden: publikum, ton, laenge, fokus. | Schnittstelle |
Für fachpublikum: Die Syntax ist bewusst minimal.  ISCRIPT erfindet keine neuen Konstrukte — es erweitert JavaScript um zwei Dinge: ?
## abgrenzung-typescript
TypeScript beseitigt Mehrdeutigkeit im Programmtext durch statische Typisierung. ISCRIPT löst sie kontextuell auf bei der Auflösung.
Je nach Publikum: - Fachpublikum: Ausführliche Abgrenzung mit Beispiel - Allgemein: Ein Satz - Homepage: Kein eigener Abschnitt, nur ein Satz im Fließtext
## abgrenzung-dsl
DSLs sind domänenspezifisch und starr; ISCRIPT ist domänenspezifisch, aber durch den Kontext erweiterbar, ohne die Grammatik zu ändern.
Je nach Publikum: - Fachpublikum: Ausführliche Abgrenzung - Allgemein: Ein Satz - Homepage: Kein eigener Abschnitt
## abgrenzung-template
Templates variieren Ausgabe durch Parameter; ISCRIPT variiert Ausgabe durch Prosa, nicht durch strukturierte Parameter.
Je nach Publikum: - Fachpublikum: Ausführliche Abgrenzung - Allgemein: Ein Satz - Homepage: Kein eigener Abschnitt
## offene-fragen
Fünf Fragen bleiben offen: 1. Wie läuft die Auflösung konkret ab? 2. Wer verantwortet den Kontext? 3. Wie verhindert man, dass freie Sprache Invarianten des Codes verletzt? 4. Wie viel Struktur muss im Code stecken, damit neue Kontexte ohne neuen Code funktionieren? 5. Wer definiert Domänengrammatiken — vorgegeben, abgeleitet oder deklariert?
## fazit
ISCRIPT behandelt Mehrdeutigkeit als Feature, nicht als Bug. Die Code-Ebene trägt Struktur und Fakten, die Kontext-Ebene trägt Präsentation und Absicht. Die Auflösung verbindet beide — nachvollziehbar, prüfbar, revidierbar.
Für fachpublikum (gewicht 5): Der Meta-Aspekt: Dieser Artikel ist nicht nur über ISCRIPT — er ist ein Beispiel für ISCRIPT.  Der Code + der Kontext + die Auflösung = dieses Artefakt.
```

## Entfernt (in der Überarbeitung, nicht in der neuen Generierung)

```markdown
> ISCRIPT verbindet formale Code-Struktur mit freier Sprache und löst Mehrdeutigkeit kontextuell auf — nicht durch Eliminierung im Programmtext, sondern durch kontrollierte Auflösung bei der Generierung.
## ISCRIPT
Kontextabhängige Begriffsabgrenzung: - Abgrenzung zu TypeScript: TypeScript beseitigt Mehrdeutigkeit im Programmtext; ISCRIPT löst sie kontextuell auf bei der Auflösung.  - Abgrenzung zu DSLs: DSLs sind domänenspezifisch und starr; ISCRIPT ist domänenspezifisch, aber durch den Kontext erweiterbar, ohne die Grammatik zu ändern.
## Code-Ebene
Die Code-Ebene von ISCRIPT ist formales JavaScript plus markierte kontextabhängige Stellen (?{...}). Sie trägt die Struktur, die Relationen und die invariante Fakten.
Abgrenzung zu "Kontext-Ebene": Code sagt WAS (Struktur, Fakten), Kontext sagt WIE (Präsentation, Ton, Fokus).  Beispiel: Im Lebenslauf-Beispiel trägt der Code die Stationen (was, wann, wo) als invariante Fakten.
## Kontext-Ebene
## Auflösung
## Die drei Ebenen
ISCRIPT operiert auf drei Ebenen: Code (Struktur und Fakten), Kontext (Präsentation und Absicht) und Auflösung (Verbindung beider). Jede Ebene hat eine eigene Fehlerlogik.
Tabelle der drei Ebenen: Ebene     | Rolle                        | Fehler möglich?  ----------|------------------------------|------------------ Code      | Struktur, Relationen, Fakten | Ja (Syntax, Logik) Kontext   | Situation, Publikum, Absicht | Nein Auflösung | Verbindet beide              | Ja (Fehlinterpretation) Diese Tabelle ist das Kernstück des Artikels.
## Faktum und Rahmung
## JavaScript als Basis
## Auflösung ausführen
**Voraussetzung:** Es existiert ein .isc-Datei mit Artikel-Code und eine .txt-Datei mit Kontext.
**Hinweise:**
Kontextabhängige Bemerkung zur Syntax: Für fachpublikum: Die Syntax ist bewusst minimal.  ISCRIPT erfindet keine neuen Konstrukte — es erweitert JavaScript um zwei Dinge: ?
## Kontext schreiben
**Voraussetzung:** null
**Hinweise:**
Für fachpublikum: Der Generische Prozess: 1.  Ontologie für die Domäne finden oder erstellen 2.
## ISCRIPT-Syntax-Elemente
## Etablierte Ontologien für ISCRIPT-Domänen
Für fachpublikum (gewicht 5): Der Meta-Aspekt: Dieser Artikel ist nicht nur über ISCRIPT — er ist ein Beispiel für ISCRIPT.  Der Code (artikel/iscrypt.
Fünf Fragen bleiben offen: Wie läuft die Auflösung konkret ab? Wer verantwortet den Kontext? Wie verhindert man, dass freie Sprache Invarianten des Codes verletzt? Wie viel Struktur muss im Code stecken, damit neue Kontexte ohne neuen Code funktionieren? Wer definiert Domänengrammatiken — vorgegeben, abgeleitet oder deklariert?
ISCRIPT behandelt Mehrdeutigkeit als Feature, nicht als Bug. Die Code-Ebene trägt Struktur und Fakten, die Kontext-Ebene trägt Präsentation und Absicht. Die Auflösung verbindet beide — nachvollziehbar, prüfbar, revidierbar. Der Artikel selbst ist der Prototyp: Er wurde in ISCRIPT geschrieben und mit der beschriebenen Auflösung in dieses Artefakt transformiert.
```

## Aktion

Entscheidung: 
- **Übernehmen:** Die neue Generierung ist besser → `artikel.generiert.md` in `artikel.ueberarbeitet.md` kopieren
- **Behalten:** Die bestehende Überarbeitung ist besser → `artikel.ueberarbeitet.md` bleibt so
- **Mischen:** Manuell auswählen, was aus der neuen Generierung übernommen wird