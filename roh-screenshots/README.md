# Visuelle Baseline der Rohfassung

Stand der Oberfläche: Commit `6437c5ddc7531679c78bb55a469595261e48e70f` auf Branch `roh`. `index.html`, `everyapp.json` und die Spiel-Doku im Repository-README sind dafür nicht verändert.

Die Bilder sind PNG-Aufnahmen der echten Seite in Chrome, nicht nachgezeichnet. Viewport etwa wie ein Pixel 7: **412×915 CSS-Pixel**, Pixeldichte 2 (PNG-Breite 824). Eine Bildschirmhöhe ist 1830 Pixel. Längere Seiten sind vollständig enthalten, also inklusive dem Bereich unter dem ersten Viewport.

Spotify lief nicht echt. Eine lokale Bridge hat die EveryApp-Schnittstelle nur für diese Aufnahme nachgebildet, ohne Client ID und ohne Geheimnisse im Repository. Titel, Interpreten und Alben in Suche und Empfehlungen sind Testdaten dieser Aufnahme. Die App selbst hat keine feste Songliste.

Mitspieler in den Spielbildern: Mina, Jonas, Lea.

## Bilder

| Datei | Was zu sehen ist |
| --- | --- |
| `01-lobby-namen.png` | Leere Lobby. Namensfeld, Spotify verbunden und Premium, noch niemand eingetragen, „Spiel starten“ deaktiviert. |
| `02-hinweis-name-fehlt.png` | Fehler „Bitte einen Namen eintragen.“ |
| `03-zu-wenige-spieler.png` | Nur Mina. „Spiel starten“ bleibt deaktiviert. Darunter der Hinweis, dass mindestens zwei Personen nötig sind. |
| `04-hinweis-name-doppelt.png` | Fehler „Diesen Namen gibt es schon.“ |
| `05-lobby-regeln.png` | Drei Namen, „Spiel starten“ aktiv, Regeln aufgeklappt. |
| `06-dj-auswahl-unbestaetigt.png` | „Wer ist der DJ?“ Niemand gewählt, „Ich bin der DJ“ deaktiviert. |
| `07-dj-auswahl-name-gewaehlt.png` | Mina ist markiert, „Ich bin der DJ“ ist aktiv. Die Suche kommt erst nach dem Bestätigen. |
| `08-dj-suche-leer.png` | DJ-Suche ohne Treffer. „Noch keine Treffer.“, „Los“ deaktiviert. |
| `09-empfehlungen-vor-erstem-song.png` | Hinweis „Empfehlungen erst nach dem ersten Song gehen.“ Es wird nichts bei Spotify angefragt. |
| `10-dj-suche-nichts-gefunden.png` | Suche ohne Ergebnis, Hinweis „Nichts gefunden.“ |
| `11-dj-suche-treffer.png` | Treffer mit Titel, Interpret, Album und Dauer. „Los“ noch deaktiviert. |
| `12-dj-suche-song-ausgewaehlt.png` | „99 Luftballons“ markiert, „Los“ aktiv. |
| `13-spielen-buzzer.png` | Laufender Song. Großer roter STOPP-Buzzer. Kein Titel, Interpret, Album oder Cover. |
| `14-raten-wer.png` | „Wer hat geraten?“ DJ fehlt in der Liste. „Ja, richtig“ und „Nein, falsch“ sind deaktiviert. |
| `15-raten-ja-nein.png` | Jonas ist gewählt. Ja und Nein sind aktiv. |
| `16-aufloesung-richtig.png` | Auflösung nach richtigem Tipp. Jonas +1, dann „Nächsten DJ wählen“. |
| `17-naechster-dj.png` | „Gib das Handy weiter.“ Nächster DJ noch nicht gewählt. |
| `18-empfehlungen.png` | Drei Empfehlungen, nachdem schon ein Song gestartet wurde. „Los“ deaktiviert, solange nichts gewählt ist. |
| `19-song-war-schon-an.png` | Fehler „Song war schon an.“ Der schon gestartete Track trägt die Markierung „Schon an“. Titel bleiben sichtbar. |
| `20-falscher-tipp-weiter.png` | Lea −1. Hinweis, dass der Song weiterläuft. Wieder der Buzzer, ohne Titel. |
| `21-versehentlich-gedrueckt.png` | „Stopp zurückgenommen.“ Niemand bekommt dafür Punkte, der Buzzer ist wieder da. |
| `22-aufloesung-uebersprungen.png` | Übersprungen. Jonas bekommt −3, danach die Auflösung. |
| `23-songende-frage.png` | „Der Song ist zu Ende.“ Frage „Wurde der Song erraten?“ ohne Titel, Interpret, Album oder Cover. |
| `24-songende-wer.png` | „Wer hat ihn erraten?“ „Punkt geben“ ist deaktiviert. |
| `25-songende-wer-ausgewaehlt.png` | Mina gewählt, „Punkt geben (+1)“ aktiv. |
| `26-aufloesung-songende-ja.png` | Natürliches Ende mit Ja. Mina +1 und Auflösung. |
| `27-spiel-beenden-dialog.png` | Dialog „Spiel beenden?“ über der Auflösung, mit „Weiter spielen“. |
| `28-aufloesung-songende-nein.png` | Natürliches Ende mit Nein. DJ Mina bekommt −3, danach die Auflösung. |
| `29-endstand.png` | Endstand nach vier gestarteten Songs und „Nochmal, gleiche Namen“. |
| `30-nochmal-gleiche-namen.png` | Neue Runde mit denselben Namen. Punkte sind zurückgesetzt, die Regeln sind wieder zugeklappt. |
| `31-hinweis-kein-premium.png` | Premium fehlt. Der Start bleibt in der Lobby und zeigt den Premium-Hinweis. |
| `32-hinweis-spotify-fehlt.png` | Spotify-App nicht installiert. |
| `33-hinweis-keine-client-id.png` | Keine Client ID. Angezeigt wird nur der Hinweis, kein ID-Wert. |
| `34-hinweis-ohne-bridge.png` | Seite ohne EveryApp-Bridge, wie im normalen Browser. |
| `35-start-ohne-bridge.png` | „Spiel starten“ ohne Bridge. Das Spiel bleibt in der Lobby und nennt den fehlenden Ton. |
| `36-spielen-song-startet-nicht.png` | Wiedergabe pausiert, Titel verdeckt. Hinweis, dass Spotify den Song noch nicht spielt, plus „Fortsetzen“, „Erneut von vorne starten“ und „Zurück zur Suche“. |

## Nicht als eigenes Bild

Der Satz „Mindestens zwei Personen. Sonst kann außer dem DJ niemand raten.“ steckt im Code, ist aber nicht anklickbar: „Spiel starten“ ist unter zwei Personen deaktiviert. Sichtbar ist der Hinweis direkt unter dem Button (`03-zu-wenige-spieler.png`).

„Der Name ist zu lang“ ist über das Namensfeld nicht erreichbar. Das Feld lässt höchstens 24 Zeichen zu.

„Lädt …“ am Button „Empfehlungen“ erscheint nur, während die Suche läuft, und ist hier kein eigenes Standbild. Der Zustand davor ist `09-empfehlungen-vor-erstem-song.png`, der Zustand danach `18-empfehlungen.png`.
