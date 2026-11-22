# CLAUDE.md – Dorf-App (Arbeitstitel)

## Inhalt dieses Ordners (Stand: 22.11.2026)
- `index.html` – spielbarer **Web-Prototyp** in einer einzigen Datei (HTML/CSS/JavaScript mit Three.js). Er zeigt den aktuellen Stand von Spielidee, Balance und Bedienung und läuft im Browser, z. B. mit der VS-Code-Erweiterung „Live Server“. Er ist zweisprachig (Deutsch/Englisch). Schritte, Trainingsminuten usw. werden dort über einen Testmodus simuliert.
- `Spieldesign-Dorf-App.md` – vollständiges Spieldesign: Ressourcen, Kosten, Gebiete, Aufgaben, Bewohner, Schule, Erzählhaus, Sprachen. **Bei Fragen zu Regeln und Zahlen gilt dieses Dokument.**
- `Prompt-Fahrplan.md` – Schritt-für-Schritt-Prompts für den Bau der iPhone-App in Xcode.
- `CLAUDE.md` – diese Datei mit den Regeln für die iPhone-App.

**Wer am Web-Prototyp weiterarbeitet:** Änderungen direkt in `index.html` machen und Struktur und Stil beibehalten. Neue Texte in beiden Sprachen anlegen: den deutschen Text im Code (mit `t('…')` oder `` tt`…` ``), die englische Übersetzung im `EN`-Objekt bzw. in `EN_DATA`. Danach das Spieldesign-Dokument aktualisieren.

**Die iPhone-App** wird nach den Regeln unten gebaut. Der Web-Prototyp dient als Vorlage für Aussehen und Spielgefühl, die erste iPhone-Version (MVP) bleibt aber bewusst kleiner.

## Worum es geht
Ein gemütliches Dorfaufbau-Spiel für das iPhone im Indie-Stil. Die Ressourcen zum Bauen kommen aus echter Bewegung: Die App liest Schritte aus Apple Health (HealthKit) und rechnet sie in Münzen um. Mit den Münzen baut man Gebäude in einem kleinen Dorf.

Der Ideengeber (Jan) hat keine Programmiererfahrung. Der Code wird mit Claude Code auf einem Mac gebaut. Erkläre deshalb jede Änderung kurz und verständlich, ohne Fachjargon.

## Technik
- Swift und SwiftUI, Mindestversion iOS 17
- SwiftData für das Speichern
- HealthKit, **nur lesend** (`HKQuantityType(.stepCount)`)
- Keine Fremd-Bibliotheken, kein Server, keine Netzwerkzugriffe, kein Tracking, keine Werbung
- Die Oberfläche ist auf Deutsch. Englisch kommt später über String Catalogs (Localizable.xcstrings) dazu.

## Wirtschaftsregeln (wichtig, bitte genau so umsetzen)
- **Startdatum:** Das Startdatum wird beim ersten Start der App gespeichert. Gezählt werden nur Schritte ab diesem Zeitpunkt. Schritte aus der Zeit vor der Installation zählen nicht.
- **Lebensschritte:** Die Summe aller Schritte seit dem Startdatum. Sie wird immer frisch aus HealthKit berechnet und nicht hochgezählt, damit nichts doppelt gezählt wird.
- **Münzen:** Lebensschritte minus ausgegebene Münzen. 1 Schritt entspricht 1 Münze. Gespeichert wird nur die Summe der ausgegebenen Münzen.
- **Kein Verfall:** Das Dorf verfällt nie, und es gibt keine Strafen für Inaktivität.
- **Ressourcen im MVP:** Holz und Stein gibt es in der ersten Version noch nicht. Es gelten nur die Münzkosten.

## Umfang der ersten Version (MVP)
1. Health-Berechtigung anfragen, heutige Schritte und Münzstand anzeigen
2. Dorf als Raster mit 8 × 8 Feldern. Gebäude sind vorerst Platzhalter, zum Beispiel farbige Formen oder Emoji
3. Bau-Menü: Gebäude kaufen und auf ein freies Feld setzen
4. Gebäude der Stufen 1 und 2 (siehe Katalog unten)
5. Freischaltung: Stufe 2 ist offen, sobald 4 Objekte aus Stufe 1 gebaut sind

**Nicht im MVP** (bitte nicht vorab einbauen): Holz, Stein, Wahrzeichen, Bewohner, Dialoge, Widgets, Apple Watch, In-App-Käufe, Mehrspieler.

## Gebäudekatalog (MVP)
Als eine zentrale, leicht änderbare Datei anlegen, z. B. `BuildingCatalog.swift`.

| id | Name | Stufe | Münzen | Größe |
|---|---|---|---|---|
| path | Kleiner Pfad | 1 | 300 | 1×1 |
| fence | Holzzaun | 1 | 500 | 1×1 |
| campfire | Lagerfeuer | 1 | 500 | 1×1 |
| bench | Holzbank | 1 | 1.000 | 1×1 |
| lantern | Laterne | 1 | 1.500 | 1×1 |
| flowerbed | Blumenbeet | 1 | 2.000 | 1×1 |
| garden | Gemüsegarten | 2 | 8.000 | 1×1 |
| hut | Hütte | 2 | 10.000 | 1×1 |
| pond | Teich mit Steg | 2 | 12.000 | 1×1 |
| well | Brunnen | 2 | 15.000 | 1×1 |
| guesthouse | Gästehaus | 2 | 20.000 | 1×1 |

Pfad und Zaun darf man beliebig oft bauen, alle anderen Gebäude je einmal.

## Ordnerstruktur (Vorschlag)
- `Models/` – Datenmodelle (gebaute Gebäude, Spielstand)
- `Health/` – alles rund um HealthKit
- `Game/` – Wirtschaftslogik, Gebäudekatalog, Freischaltung
- `Views/` – Bildschirme und UI-Bausteine

## Arbeitsweise
- Arbeite in kleinen Schritten. Pro Auftrag nur das umsetzen, was verlangt ist.
- Vor größeren Änderungen erst kurz den Plan nennen, dann umsetzen.
- Die Wirtschaftslogik (Münzen, Kauf, Freischaltung) gehört getrennt von der UI und wird mit Unit-Tests abgesichert.
- HealthKit über ein Protokoll kapseln, damit es in Tests und in der Vorschau eine Fake-Version mit Beispielwerten gibt.
- Fehlende Berechtigung freundlich behandeln. Die App darf nie abstürzen, wenn keine Health-Daten verfügbar sind.
- Nach jedem abgeschlossenen Schritt sicherstellen, dass das Projekt fehlerfrei baut, und dann einen Git-Commit mit kurzer deutscher Nachricht machen.
- Am Ende jedes Auftrags kurz zusammenfassen: was geändert wurde und wie man es testet.
