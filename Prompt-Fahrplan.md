# Prompt-Fahrplan für Claude Code – Dorf-App

Für: den Mac-Helfer · Stand: 28.10.2026

## Vorbereitung (einmalig, von Hand)
1. **Xcode** aus dem Mac App Store installieren und einmal öffnen, damit es die Zusatzkomponenten installiert.
2. **Claude Code** installieren. Dafür braucht es ein Claude-Abo (Pro oder höher). Die Anleitung steht unter code.claude.com/docs/en/quickstart.
3. **Projekt in Xcode anlegen:** File → New → Project → iOS → App
   - Product Name: `Dorf` (später änderbar)
   - Interface: SwiftUI · Language: Swift · Storage: SwiftData · „Include Tests“ anhaken
4. **HealthKit freischalten:** Projekt anklicken → Target „Dorf“ → *Signing & Capabilities* → *+ Capability* → **HealthKit**. Bei *Team* die eigene Apple-ID auswählen.
5. Die Datei **`CLAUDE.md`** in den obersten Projektordner legen, also dorthin, wo die `.xcodeproj`-Datei liegt.
6. Im Terminal in diesen Ordner wechseln und `claude` starten.

## So arbeitest du mit den Prompts
- Die Prompts **nacheinander** geben, immer nur einen zur Zeit.
- Nach jedem Prompt in Xcode bauen und starten (⌘R) und den **Test** am Ende des Schritts durchführen.
- Wenn Xcode einen Fehler zeigt: die Fehlermeldung kopieren und Claude Code geben, mit dem Satz „Beim Bauen kommt dieser Fehler: …“.
- Erst wenn der Test klappt, mit dem nächsten Prompt weitermachen.

---

### Prompt 0 – Kennenlernen
> Lies die CLAUDE.md und schau dir das bestehende Xcode-Projekt an. Fasse in einfachen Worten zusammen, was die App werden soll, und schlage die Dateien vor, die du für das MVP anlegen würdest. Noch nichts ändern. Richte außerdem ein Git-Repository ein, falls noch keins existiert, und mache einen ersten Commit.

**Test:** Die Zusammenfassung passt zur Idee.

### Prompt 1 – Schritte aus Apple Health
> Baue die HealthKit-Anbindung laut CLAUDE.md: Ein Protokoll für den Schritte-Dienst, eine echte HealthKit-Version und eine Fake-Version mit Beispielwerten für Vorschau und Tests. Trage die nötige Beschreibung für die Health-Berechtigung (NSHealthShareUsageDescription) auf Deutsch ein. Zeige auf einem einfachen Startbildschirm die heutigen Schritte an. Wenn die Berechtigung fehlt, soll ein freundlicher Hinweis mit Erklärung erscheinen.

**Test:** Im Simulator die Health-App öffnen → Durchsuchen → Aktivität → Schritte → Daten hinzufügen. Dann die Dorf-App starten: Die eingetragenen Schritte werden angezeigt.

### Prompt 2 – Münzen und Spielstand
> Setze die Wirtschaftsregeln aus der CLAUDE.md um: Startdatum beim ersten Start speichern, Lebensschritte seit dem Startdatum aus HealthKit berechnen, Münzen = Lebensschritte minus ausgegebene Münzen. Speichere den Spielstand mit SwiftData. Halte die Logik getrennt von der UI und schreibe Unit-Tests dafür (auch für Randfälle wie 0 Schritte oder fehlende Berechtigung). Zeige Münzstand und heutige Schritte oben auf dem Startbildschirm.

**Test:** Die Unit-Tests laufen grün (⌘U). Schritte im Simulator hinzufügen → der Münzstand steigt.

### Prompt 3 – Gebäudekatalog
> Lege den Gebäudekatalog aus der CLAUDE.md als zentrale Datei an. Jedes Gebäude bekommt id, Name, Stufe, Kosten, ein Platzhalter-Symbol (Emoji) und die Angabe, ob man es mehrfach bauen darf. Schreibe Tests, die prüfen, dass alle ids eindeutig sind.

**Test:** Die Tests laufen grün.

### Prompt 4 – Die Dorf-Ansicht
> Baue die Dorf-Ansicht: ein Raster mit 8 × 8 Feldern in einem gemütlichen, warmen Farbschema (Grüntöne für die Wiese). Gebaute Gebäude erscheinen mit ihrem Platzhalter-Symbol auf ihrem Feld. Speichere die gebauten Gebäude mit Position in SwiftData. Füge zum Testen vorübergehend einen Debug-Knopf ein, der ein Beispielgebäude platziert.

**Test:** Mit dem Debug-Knopf ein Gebäude setzen, die App schließen und neu öffnen: Das Gebäude steht noch da.

### Prompt 5 – Bau-Menü
> Baue ein Bau-Menü als Sheet: eine Liste aller Gebäude mit Symbol, Name und Kosten. Gebäude, die man sich nicht leisten kann, werden ausgegraut angezeigt. Nach Auswahl tippt man auf ein freies Feld im Dorf, um das Gebäude zu platzieren. Erst dann werden die Münzen abgezogen. Beachte die Regel einmalig/mehrfach. Entferne den Debug-Knopf aus Prompt 4. Sichere den Kauf mit Unit-Tests ab.

**Test:** Ein Gebäude kaufen und setzen → die Münzen sinken um den richtigen Betrag. Ein zu teures Gebäude lässt sich nicht kaufen.

### Prompt 6 – Freischaltung von Stufe 2
> Setze die Freischaltregel um: Stufe 2 wird offen, sobald 4 Objekte aus Stufe 1 gebaut sind. Gesperrte Gebäude zeigt das Bau-Menü mit Schloss-Symbol und dem Hinweis, was noch fehlt. Beim Freischalten erscheint eine kleine, freundliche Meldung. Mit Unit-Tests absichern.

**Test:** 4 Objekte aus Stufe 1 bauen → Stufe 2 wird freigeschaltet.

### Prompt 7 – Erster Start und Feinschliff
> Baue einen kurzen Willkommensbildschirm für den ersten Start (2–3 Seiten): was die App macht, dass nur Schritte ab heute zählen, warum die Health-Berechtigung nötig ist und dass die Daten auf dem Gerät bleiben. Prüfe danach die ganze App auf Abstürze und Sonderfälle. Achte dabei besonders auf diese Fälle: keine Berechtigung, 0 Schritte, Dorf voll. Behebe alle Warnungen in Xcode.

**Test:** App im Simulator löschen und neu installieren → der Willkommensbildschirm erscheint, und alles läuft ohne Absturz.

---

## Auf Jans iPhone testen
iPhone per Kabel an den Mac anschließen, in Xcode als Ziel auswählen und starten (⌘R). Mit einer kostenlosen Apple-ID läuft die App nur begrenzte Zeit (in der Regel 7 Tage) und muss danach neu aufgespielt werden. Für TestFlight und den App Store braucht es das Apple Developer Program (99 USD/Jahr). Das lohnt sich erst, wenn das MVP fertig ist.

## Nach dem MVP (spätere Prompts)
Holz und Stein (Trainingsminuten, Stockwerke) · Stufe 3 · Wahrzeichen mit Bauphasen · Bewohner und Dialoge · echte Grafik statt Emoji · Homescreen-Widget · TestFlight
