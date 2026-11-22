# Spieldesign: Cozy-Dorf-App (Arbeitstitel)

Stand: 22.11.2026 · Version 0.4

## Kernidee
Ein gemütliches Dorfaufbau-Spiel im Indie-Stil. Die Ressourcen zum Bauen kommen aus echter Bewegung, ausgelesen aus Apple Health (HealthKit, nur lesend). Das Spiel belohnt Bewegung und bestraft nie Inaktivität: Das Dorf verfällt nicht.

## Ressourcen (im Web-Prototyp umgesetzt)

| Ressource | Quelle (HealthKit) | Umrechnung | Typischer Tag* | Wofür vor allem |
|---|---|---|---|---|
| Münzen | Schritte | 1 Schritt = 1 Münze | ~7.000 | alles |
| Holz | Trainingsminuten (Apple-Trainingsring, zählt auch zügiges Gehen) | 1 Minute = 1 Holz | ~20 | Häuser, Zäune, Bänke, Boote |
| Stein | Stockwerke / Treppen | 1 Stockwerk = 1 Stein | ~8 | Wege, Brunnen, Teich, Kapelle |
| Kräuter | Ruhe-Übungen im Dorf (für alle) + Achtsamkeitsminuten (Apple Watch oder Meditations-App) | 3 pro Übungsminute, 1 pro Achtsamkeitsminute | ~9–27 | Blumen, Gärten, Pflanzen |
| Lebensschritte | alle jemals gesammelten Schritte | wird **nicht verbraucht** | wächst stetig | Wahrzeichen (geplant) |

*Referenzspieler für die Balance: 7.000 Schritte, 20 Trainingsminuten, 8 Stockwerke und 5 Achtsamkeitsminuten pro Tag.

**Hinweis:** Mit dem iPhone allein bekommt man sicher nur Schritte und Stockwerke. Trainings- und Achtsamkeitsminuten kommen in der Regel von der Apple Watch oder aus anderen Apps. Deshalb gibt es die Ruhe-Übungen im Spiel und den Tauschstand.

**Tauschstand** (ein festes 2 × 2-Gebäude im Dorf mit Händler Emil): 100 Münzen pro Holz, Stein oder Kraut, in Paketen zu 5, 10 oder 25. Der Kurs ist bewusst ungünstig, damit Vielfalt sich lohnt, aber niemand festhängt. Startausstattung für ein neues Dorf: 20 Holz, 20 Stein, 10 Kräuter.

**Baukosten im Prototyp** (Münzen + Rohstoffe):

| Gebäude | Kosten | Gebäude | Kosten |
|---|---|---|---|
| Kleiner Pfad | 50 Münzen, 1 Stein | Schilf | 300, 2 Kräuter |
| Holzzaun | 300, 2 Holz | Ruderboot | 2.500, 20 Holz |
| Lagerfeuer | 400, 3 Holz, 2 Stein | Bootssteg | 5.000, 35 Holz |
| Holzbank | 800, 4 Holz | Muschelstand | 7.000, 20 Holz, 5 Stein |
| Laterne | 1.200, 1 Holz, 2 Stein | Fischerhütte | 11.000, 50 Holz, 15 Stein |
| Blumenbeet | 1.500, 2 Holz, 3 Kräuter | Tanne | 500, 3 Kräuter |
| Gemüsegarten | 6.000, 15 Holz, 5 Kräuter | Pilzkreis | 2.000, 8 Kräuter |
| Hütte | 8.000, 40 Holz, 10 Stein | Holzfällerhütte | 14.000, 40 Holz, 20 Stein |
| Teich mit Steg | 9.000, 5 Holz, 25 Stein | Baumhaus | 18.000, 70 Holz |
| Brunnen | 12.000, 10 Holz, 30 Stein | Försterhaus | 24.000, 60 Holz, 30 Stein, 10 Kräuter |
| Gästehaus | 16.000, 60 Holz, 20 Stein | Lavendel | 700, 4 Kräuter |
| Aussichtsbank | 3.000, 10 Holz, 15 Stein | Ziegenstall | 16.000, 60 Holz, 20 Stein |
| Steinbruch | 20.000, 10 Holz, 60 Stein | Bergkapelle | 32.000, 30 Holz, 100 Stein |

## Freischaltlogik
- **Dorfstufe 1:** Von Anfang an offen.
- **Dorfstufe 2:** Wird offen, sobald 4 Gebäude/Objekte aus Stufe 1 gebaut sind.
- **Dorfstufe 3:** Wird offen, sobald die Hütte und 3 weitere Gebäude aus Stufe 2 stehen.
- **Wahrzeichen:** Von Tag 1 an als Baustelle sichtbar. Sie wachsen automatisch mit den Lebensschritten, nacheinander (eine aktive Baustelle zur Zeit), in sichtbaren Bauphasen.

## Gebäudeliste

### Stufe 1 – Ankommen (Tag 1–2)

| Objekt | Münzen | Holz | Stein | Wirkung |
|---|---|---|---|---|
| Zelt | gratis | – | – | Startunterkunft |
| Kleiner Pfad (je Feld) | 300 | – | – | Wege anlegen |
| Holzzaun (je Feld) | 500 | – | – | Deko, Grundstück abgrenzen |
| Lagerfeuer | 500 | – | – | Abendszene, erster Treffpunkt |
| Holzbank | 1.000 | – | – | Deko |
| Laterne | 1.500 | – | – | Licht bei Nacht |
| Blumenbeet | 2.000 | – | – | Deko, erste Farbe im Dorf |

### Stufe 2 – Erste Siedlung (ca. Woche 1–2)

| Gebäude | Münzen | Holz | Stein | Wirkung |
|---|---|---|---|---|
| Gemüsegarten | 8.000 | – | – | Saisonale Pflanzen |
| Hütte (eigenes Haus) | 10.000 | 50 | – | Ersetzt das Zelt, Inneneinrichtung möglich |
| Teich mit Steg | 12.000 | 20 | – | Angeln als Mini-Beschäftigung |
| Brunnen | 15.000 | – | 30 | Dorfmittelpunkt |
| Gästehaus | 20.000 | 60 | – | Erster Bewohner zieht ein |

### Stufe 3 – Dorfleben (ca. Woche 3–10)

| Gebäude | Münzen | Holz | Stein | Wirkung |
|---|---|---|---|---|
| Bäckerei | 40.000 | 100 | 50 | Neuer Bewohner (Bäckerin) |
| Taverne | 60.000 | 150 | 80 | Abendliche Dialoge, Geschichten |
| Schmiede | 70.000 | 100 | 120 | Werkzeug-Upgrades, Deko aus Metall |
| Marktplatz | 80.000 | – | 150 | Wechselnde Händler mit Deko |
| Bibliothek | 90.000 | 150 | 100 | Dorfchronik (Statistik der eigenen Bewegung) |
| Windmühle | 100.000 | 200 | 100 | Wahrzeichen der Landschaft |

### Stufe 4 – Wahrzeichen (Monate, über Lebensschritte)

| Wahrzeichen | Lebensschritte | Bauphasen | Dauer beim Referenzspieler |
|---|---|---|---|
| Leuchtturm | 200.000 | 4 à 50.000 | ca. 1 Monat |
| Uhrturm | 400.000 | 8 à 50.000 | ca. 2 weitere Monate |
| Kleiner Palast | 1.000.000 | 10 à 100.000 | ca. 4,5–5 weitere Monate |

Bauphasen des Palasts: Fundament → Mauern → Tor → Turm 1 → Turm 2 → Dach → Fenster → Innenhof → Garten → Fahnen und Einweihungsfest. Jede Phase ist im Dorf sichtbar und bringt eine kleine Belohnung (Deko, Dialog oder Bewohner).

## Gesamtrechnung (Referenzspieler)
- Stufe 1: rund 6.000 Münzen, also etwa 1 Tag
- Stufe 2: 65.000 Münzen, also etwa 9 Tage
- Stufe 3: 440.000 Münzen, also etwa 63 Tage
- Die Gebäude aus Münzen sind nach ungefähr **2,5 Monaten** fertig. Der Palast ist erst nach ungefähr **7,5 Monaten** fertig.

**Offenes Problem:** Zwischen Monat 2,5 und 7,5 fehlt ein Ziel, für das man Münzen ausgibt. Mögliche Lösungen dafür sind ein Deko-Shop mit Jahreszeiten-Sets, Wünsche der Bewohner (kleine Aufträge), Upgrades für bestehende Gebäude in 2–3 Stufen und Erweiterungen des Dorfgebiets. Die täglichen Aufgaben bringen zusätzliche Münzen ins Spiel. Dadurch wird diese Lücke etwas früher erreicht, und das sollte man bei der Balance berücksichtigen.

## Wachsende Dorffläche (im Web-Prototyp umgesetzt, 3D)
Das Dorf ist **eine zusammenhängende Fläche**, die an den Rändern wächst (Endgröße 32 × 32 Felder). Man startet auf der Lichtung (16 × 16 Felder). Neue Gebiete schließen sich an und haben eine eigene Gestaltung und eigene Gebäude. Noch nicht erschlossene Gebiete sind als dunkle Fläche zu sehen. Ein Gebiet kommt hinzu, sobald **eine** von zwei Bedingungen erfüllt ist: genug Gebäude oder genug ausgegebene Münzen. Deko zählt dabei nicht als Gebäude. Die Gebäude aus Stufe 1 und 2 kann man überall bauen, die Gebietsgebäude nur in ihrem eigenen Gebiet.

| Gebiet | Lage und Größe | Kommt hinzu bei | Gestaltung | Eigene Gebäude (Münzen) |
|---|---|---|---|---|
| Lichtung | Mitte, 16 × 16 | Start | Wiese | – |
| Seeufer | Osten, 8 × 16 | 6 Gebäude oder 20.000 ausgegeben | Sand, See am Rand | Schilf (400, Deko), Ruderboot (3.000), Bootssteg (6.000), Muschelstand (9.000), Fischerhütte (14.000) |
| Waldrand | Norden, 24 × 8 | 11 Gebäude oder 60.000 ausgegeben | Moosgrün, alte Tannen | Tanne (700, Deko), Pilzkreis (2.500), Holzfällerhütte (18.000), Baumhaus (24.000), Försterhaus (30.000) |
| Bergwiese | Westen, 8 × 24 | 16 Gebäude oder 150.000 ausgegeben | Helle Almwiese, Felsen | Lavendel (900, Deko), Aussichtsbank (4.000), Ziegenstall (20.000), Steinbruch (28.000), Bergkapelle (40.000) |
| Sonnenfelder | Süden, 32 × 8 | 21 Gebäude oder 300.000 ausgegeben | Goldgrüne Felder, Apfelbäume am Rand | Acker (300, beliebig oft, siehe unten), Sonnenblumen (800, 3 Kräuter, Deko), Bienenstöcke (5.000, 12 Holz, 8 Kräuter), Hofladen (9.000, 30 Holz, 5 Stein), Bauernhof (22.000, 70 Holz, 25 Stein, 5 Kräuter), Windmühle (36.000, 60 Holz, 60 Stein, 10 Kräuter) |

**Grundflächen:**

| Größe | Gebäude |
|---|---|
| 1 × 1 | Pfad, Zaun, Laterne, Schilf, Tanne, Lavendel, Sonnenblumen |
| 2 × 2 | Lagerfeuer, Holzbank, Blumenbeet, Brunnen, Pilzkreis, Ruderboot, Bootssteg, Muschelstand, Aussichtsbank, Bienenstöcke, Hofladen, Acker |
| 3 × 3 | Gemüsegarten, Hütte, Teich, Gästehaus, Fischerhütte, Holzfällerhütte, Baumhaus, Försterhaus, Ziegenstall, Steinbruch, Bergkapelle, Bauernhof, Windmühle |
| 4 × 4 | Dein Zuhause |

Die Flügel der Windmühle drehen sich, um die Bienenstöcke schwirren Bienen. Gesperrte Gebiete zeigen nur ein kleines Schloss-Symbol. Die Bedingungen erscheinen erst, wenn man mit der Maus darüberfährt oder es antippt. Einmal erschlossene Gebiete bleiben offen, auch wenn später Gebäude ins Lager wandern.

**Äcker auf den Sonnenfeldern:** Auf den Sonnenfeldern kann man beliebig viele Äcker anlegen (300 Münzen je 2 × 2 Felder, auch durch Ziehen „malbar“). Ein leerer Acker wird angetippt, dann wählt man eine Pflanze. Pflanzen wachsen in **echter Zeit**, auch wenn das Spiel geschlossen ist, und zeigen drei Stadien: Keimling, wachsend, reif. Über reifen Äckern erscheint ein Korb-Symbol. Ein Tipp darauf (oder auf den Acker) erntet und bringt Kräuter. Im Acker-Menü gibt es „Alle bepflanzen“ und „Alles ernten“. Wandert ein bepflanzter Acker ins Lager, geht die Pflanze verloren. Im Testmodus spult „Äcker: +1 Std“ das Wachstum vor.

| Pflanze | Kosten beim Pflanzen | Wachstum | Ernte |
|---|---|---|---|
| Radieschen | 200 Münzen | 3 Minuten | 4 Kräuter |
| Karotten | 500 Münzen | 15 Minuten | 8 Kräuter |
| Kartoffeln | 4 Kräuter | 45 Minuten | 14 Kräuter |
| Kürbisse | 10 Kräuter | 2 Stunden | 32 Kräuter |
| Erdbeeren | 2.000 Münzen, 5 Kräuter | 6 Stunden | 60 Kräuter |

Die Werte stehen im Code zentral in der Liste `CROPS` und lassen sich dort leicht anpassen.

**Dein Zuhause (4 × 4 Felder):** Es ist von Anfang an da und wird mit jedem neuen Gebiet gemütlicher: Zelt → Blockhütte (mit Seeufer) → Fachwerkhaus (mit Waldrand) → Landhaus (mit Bergwiese) → Gutshof (mit Sonnenfeldern). Die Stufe richtet sich nach der Zahl der erschlossenen Gebiete. Man kann es verschieben, aber nicht ins Lager legen.

**Bearbeiten-Modus und Lager:** Über den Stift-Knopf neben „Bauen“ wählt man ein Gebäude aus. Dann kann man es **verschieben** oder **ins Lager** legen. Aus dem Lager lassen sich Gebäude kostenlos wieder platzieren (im Bau-Menü ganz oben). Gelagerte Gebäude zählen weiter für Freischaltungen. Einmal-Gebäude kann man nicht doppelt kaufen. Platzieren aus dem Lager zählt nicht für Bau-Aufgaben.

**Wasser-Gebäude:** Bootssteg und Ruderboot kann man nur auf Wasserfeldern am Seeufer bauen. Das Ruderboot schaukelt auf dem Wasser.

**Bewohner:** Wohngebäude bringen Bewohner mit, die durchs Dorf laufen. Sie bevorzugen Pfade und gehen nicht durch Gebäude oder Wasser. Wer sie antippt, bekommt einen kurzen Satz zu hören, und das zählt für die Aufgabe „Dorfrundgang“. Liegt ein Gebäude im Lager, verschwinden auch seine Bewohner.

| Gebäude | Bewohner |
|---|---|
| Dein Zuhause | Minka, deine Katze |
| Tauschstand | Emil, Händler |
| Erzählhaus | Wilma, Geschichtenerzählerin |
| Dorfschule | Konrad, Lehrer |
| Hütte | Lotte, Nachbarin |
| Gästehaus | Paul und Ida, Gäste |
| Fischerhütte | Greta, Fischerin |
| Holzfällerhütte | Bruno, Holzfäller |
| Försterhaus | Hanne, Försterin |
| Baumhaus | Mo, Baumhaus-Kind |
| Ziegenstall | Rosa, Ziegenhirtin, mit den Ziegen Flocke und Kiesel |
| Hofladen | Lene, Hofladen-Verkäuferin |
| Bauernhof | Frieda, Bäuerin, mit den Hühnern Henni und Pünktchen |
| Windmühle | Anton, Müller |

**Darstellung:** Low-Poly-3D mit Three.js. Die Kamera lässt sich verschieben, drehen und zoomen, damit kein Gebäude dauerhaft verdeckt wird. Steuerung: Ziehen verschiebt die Karte, die rechte Maustaste (oder Shift + Ziehen) dreht, das Mausrad zoomt zum Mauszeiger hin. Auf dem Handy: ein Finger verschiebt, zwei Finger zoomen und drehen. Ein Knopf setzt die Ansicht zurück. Gebäude lassen sich beim Platzieren, beim Verschieben und im Bearbeiten-Modus in 90°-Schritten drehen (Knopf oder Taste R). Bewohner treten immer an der Vorderseite aus ihrem Haus. Beim Platzieren zeigt eine halbtransparente Vorschau, wo das Gebäude landet.

## Tägliche Aufgaben (im Web-Prototyp umgesetzt)
Jeden Tag gibt es **vier** Aufgaben: eine zu Schritten, eine zu Treppen, Training oder Achtsamkeit (im Wechsel), eine zum Bauen und eine im Dorf. Belohnungen sind Münzen und passende Rohstoffe. Bonus-Münzen zählen nicht zu den Lebensschritten. Es gibt keine Strafen und keine Streaks.

| Art | Aufgabe | Ziel | Belohnung |
|---|---|---|---|
| Schritte | Morgenrunde / Spaziergang / Ausflug / Langer Weg | 2.000 / 5.000 / 8.000 / 10.000 Schritte | 200 / 500 / 1.000 / 1.500 Münzen |
| Treppen | Treppenläufer / Gipfelstürmer / Turmbesteigung | 5 / 10 / 15 Stockwerke | 150 + 5 Stein / 300 + 10 Stein / 500 + 15 Stein |
| Training | In Bewegung / Kraftpaket / Ausdauer-Held | 15 / 30 / 45 Minuten | 150 + 8 Holz / 300 + 15 Holz / 500 + 25 Holz |
| Achtsamkeit | Durchatmen / Ruhepol | 4 Achtsamkeitsminuten / 2 Ruhe-Übungen | 100 + 5 Kräuter / 200 + 8 Kräuter |
| Bauen | Baumeister / Fleißige Hände | 1 / 2 Objekte bauen | 300 / 600 Münzen |
| Bauen | Wegebauer / Pflasterer | 3 / 8 Wegfelder | 200 + 3 Stein / 400 + 6 Stein |
| Bauen | Verschönerung | 2 Deko-Objekte | 250 + 3 Kräuter |
| Dorf | Dorfrundgang | 3 Orte antippen | 150 Münzen |
| Dorf | Plauderstunde | mit 2 Bewohnern sprechen | 200 + 2 Kräuter |
| Dorf | Sparfuchs | 5.000 Münzen auf einmal | 300 Münzen |

**Tagesbonus:** Wer alle vier Belohnungen abholt, öffnet eine Truhe mit 500 Münzen, 5 Holz, 5 Stein und 5 Kräutern.

## Ruheorte (im Web-Prototyp umgesetzt)
Jeden Tag lädt das Spiel an bis zu drei Orten im Dorf zu einer kurzen Übung ein. Dort schwebt dann ein Blatt-Symbol. Jede Übung wird geführt (animierter Atemkreis oder Schritt-für-Schritt-Text) und **läuft automatisch bis zu 3 Minuten**. Ein sanfter Klang markiert jede volle Minute und das Ende. So kann man die Augen geschlossen lassen. Beenden geht jederzeit, angerechnet werden die geschafften vollen Minuten: 3 Kräuter und 1 Achtsamkeitsminute pro Minute. Wer in der ersten Minute abbricht, bekommt nichts, aber auch keinen Hinweis oder eine Strafe, und der Ruheort bleibt offen. Ob man sie wirklich macht, prüft das Spiel nicht. Man spielt ja für sich. Später könnte die iOS-App diese Minuten selbst in Apple Health eintragen.

| Ort | Übung |
|---|---|
| Zuhause | Morgendehnung |
| Lagerfeuer | Atmen mit dem Feuer (4 ein, 6 aus) |
| Teich | Box-Atmung (4-4-4-4) |
| Brunnen | Tiefes Atmen (4-7-8) |
| Holzbank | Schultern lockern |
| Aussichtsbank | Blick in die Ferne (5-4-3-2-1) |
| Blumenbeet | Drei schöne Dinge |
| Bootssteg | Wellen-Atmung (5 ein, 5 aus) |
| Bergkapelle | Eine stille Minute |
| Baumhaus | Körperreise |
| Bienenstöcke | Summende Atmung (4 ein, 6 summend aus) |

## Erzählhaus (im Web-Prototyp umgesetzt)
Das Erzählhaus ist ein Stufe-2-Gebäude (3 × 3 Felder, 10.000 Münzen, 30 Holz, 15 Stein, 5 Kräuter). Dort wohnt die Geschichtenerzählerin **Wilma**. Jeden Tag trägt sie ein Gedicht vor. Ein Buch-Symbol über dem Haus zeigt, dass das heutige Gedicht noch ungelesen ist. Antippen von Haus, Wilma oder Symbol öffnet das Gedicht, und auf Wunsch liest das Gerät es vor (Sprachausgabe des Browsers bzw. später von iOS). Beim ersten Lesen am Tag gibt es 100 Münzen und 2 Kräuter.

**Rechtliches:** In Deutschland erlischt das Urheberrecht 70 Jahre nach dem Tod des Urhebers (§ 64 UrhG). Deshalb enthält das Spiel nur Gedichte von Dichtern, die lange vor 1956 gestorben sind und deren Gedichte vor 1929 erschienen sind. So sind sie auch nach der US-Regel gemeinfrei (dort ist seit dem 1.1.2026 alles frei, was 1930 oder früher veröffentlicht wurde). Vorsicht bei Übersetzungen, modernen Bearbeitungen, Illustrationen und Hörbuch-Aufnahmen, denn diese können eigene Rechte haben. Vor der Veröffentlichung im App Store sollte das noch einmal fachkundig geprüft werden.

**Gedichte im Prototyp (12, Wechsel täglich):** Goethe (Wandrers Nachtlied, Gefunden), Mörike (Er ist's), Morgenstern (Das ästhetische Wiesel, Die Trichter), Eichendorff (Mondnacht, Wünschelrute), Busch (Es sitzt ein Vogel auf dem Leim), Heine (Leise zieht durch mein Gemüt), Rilke (Herbsttag), Claudius (Abendlied, erste Strophe), Hoffmann von Fallersleben (Ein Männlein steht im Walde).

## Dorfschule und Rätselspiele (im Web-Prototyp umgesetzt)
Die Dorfschule ist ein Stufe-1-Gebäude (3 × 3 Felder, 1.200 Münzen, 15 Holz, 5 Stein) mit Lehrer **Konrad**. Antippen von Schule oder Konrad öffnet die Spielauswahl. Die Spiele sind auch über den Bereich „Aufgaben“ erreichbar. Pro Tag bringt die erste Runde jedes Spiels eine Belohnung, danach kann man beliebig oft üben. Wer eine belohnte Runde vorzeitig beendet, bekommt die schon beantworteten Fragen gutgeschrieben.

**Quizrunde:** 5 Allgemeinwissensfragen mit je 4 Antworten, 20 Sekunden pro Frage (Tasten 1–4 oder A–D). Pro richtiger Antwort gibt es 80 Münzen und 2 Holz, Stein oder Kräuter im Wechsel. Bei 5 von 5 kommen je 3 Rohstoffe dazu. Fragenpool im Prototyp: 42 Fragen, täglich neu gemischt.

**Seltene Funde** (Prinzip angelehnt an Krillion, aber mit eigenen Fragen und eigenem Namen): 5 offene Fragen („Nenne eine Obstsorte“), 25 Sekunden pro Frage. Jede richtige Antwort hat eine Seltenheitsstufe: Häufig (10 Punkte), Bekannt (30), Selten (60), Rarität (100). Antworten, die nicht in der Liste stehen, zählen nicht, und man darf es innerhalb der Zeit noch einmal versuchen. Kleine Tippfehler, Umlaute und Artikel werden toleriert. Nach jeder Frage zeigt das Spiel Beispiele für häufige Antworten und Raritäten. Belohnung: Punkte × 2 Münzen und je 1 Holz, Stein und Kraut pro 30 Punkte.

**Einschränkung im Prototyp:** Ohne Server gibt es keine echten Spielerdaten. Die Seltenheit ist deshalb vorab festgelegt, und die Antwortlisten (10 Fragen) sind begrenzt. In der App könnte ein Server die echte Seltenheit aus allen Spielerantworten berechnen, wie bei Krillion.

## Einstellungen (im Web-Prototyp umgesetzt)
Über das Zahnrad neben dem Tag erreichbar: Spielsprache (Deutsch/Englisch), Klänge an/aus, Lautstärke, Gedichte automatisch vorlesen, Animationen reduzieren, Steuerungs-Hinweis ein-/ausblenden, Übersicht über Maus-, Touch- und Tastatursteuerung sowie „Dorf zurücksetzen“ (mit Sicherheitsabfrage). Die Einstellungen werden im Browser gespeichert.

## Komfort und Spielgefühl (im Web-Prototyp umgesetzt)
- **Abbrechen:** Rechtsklick oder Esc schließt Menüs, beendet Bauen oder Verschieben und hebt eine Auswahl auf.
- **Tastenkürzel:** B Bauen, M Bearbeiten, R Gebäude drehen, Entf ins Lager, Q/E Ansicht drehen, WASD oder Pfeiltasten verschieben, +/− zoomen.
- **Wege und Deko malen:** Mit gedrückter Maustaste (oder dem Finger) über die Felder ziehen.
- **Doppelklick auf ein Gebäude** öffnet es direkt im Bearbeiten-Modus. Im Bearbeiten-Modus werden Gebäude unter dem Mauszeiger hervorgehoben.
- **Kurze Übergänge** (unter 0,25 s) für Menüs, Leisten, Ansichten und das Übungsfenster sowie Klick-Feedback auf Knöpfen. Wer in den Systemeinstellungen reduzierte Bewegung eingestellt hat, sieht keine Animationen.
- **Kleine Effekte:** Staubwölkchen beim Bauen, sanftes Schrumpfen beim Einlagern.
- **Leise Klänge** beim Bauen, Belohnen, Tauschen und Wachsen des Dorfs. Ein Lautsprecher-Knopf neben dem Tag schaltet sie aus, auch den Klang der Ruhe-Übungen.
- Das Bau-Menü merkt sich, wo man zuletzt gescrollt hat.

## Bewusste Designentscheidungen
- Das Dorf verfällt nie und wird nie bestraft.
- Ressourcen werden nicht verkauft. Bezahlt wird höchstens für Kosmetik oder einmalig für die App.
- Gesundheitsdaten bleiben auf dem Gerät und werden nicht für Werbung genutzt.
- Die erste Version (MVP) enthält nur Schritte und Münzen, Stufe 1 und 2 sowie einen Bildschirm.

## Sprachen (Deutsch / Englisch)

Das Spiel ist komplett zweisprachig. Beim ersten Start richtet sich die Sprache nach der Gerätesprache (Deutsch bei deutschem Gerät, sonst Englisch); in den Einstellungen lässt sie sich jederzeit umstellen, der Spielstand bleibt dabei erhalten. Übersetzt sind alle Oberflächentexte, Gebäude, Gebiete, Aufgaben, Ruhe-Übungen und Bewohner-Sätze. Die Inhalte sind nicht wörtlich übersetzt, sondern an den Sprachraum angepasst: Das englische Quiz fragt etwa nach den US-Bundesstaaten statt den deutschen Bundesländern, nach der Themse statt dem Rhein und nach Shakespeare statt Goethe. „Seltene Funde“ hat eigene englische Antwortlisten (u. a. alle 50 US-Bundesstaaten in Seltenheitsstufen), und Artikel wie „the/a/an“ werden bei der Eingabe ignoriert. Wilma trägt auf Englisch zwölf eigene gemeinfreie Gedichte vor (Tennyson, Rossetti, Dickinson, Wordsworth, Carroll, Stevenson, Blake, Yeats, Shakespeare, Keats); Robert Frost wurde bewusst ausgelassen, weil er in der EU noch geschützt ist. Die Vorlesefunktion nutzt dann eine englische Stimme. Für die iOS-Version sollten die Texte in Apples String Catalogs (Localizable.xcstrings) überführt werden.
