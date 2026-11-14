# Credits

## `assets/sounds/buzzer.mp3`

- **Name:** Game show wrong answer buzz (Mixkit ID 950)
- **Ersteller / Quelle:** [Mixkit](https://mixkit.co)
- **Seite:** https://mixkit.co/free-sound-effects/buzzer/
- **Originaldatei:** https://assets.mixkit.co/active_storage/sfx/950/950.wav
- **Lizenz:** [Mixkit Sound Effects Free License](https://mixkit.co/license/#sfxFree)

Namensnennung ist nach dieser Lizenz nicht erforderlich. Die Quelle steht hier trotzdem.

Bearbeitung gegenüber dem WAV-Original:

- Stille am Anfang und am Ende entfernt. Der hörbare Klang ist etwa 0,25 s lang, die Datei etwa 0,30 s.
- Lautstärke linear um 3,6 dB abgesenkt (`ffmpeg` `volume`), ohne Limiter und ohne Clipping, damit der Ton nicht lauter ist als der bisherige Buzzer. Sample-Peak und True Peak liegen darunter.
- Nach 48 kHz, Stereo, 256 kbit/s MP3 konvertiert und unter demselben Pfad abgelegt.

Die Abspiellautstärke in der App bleibt 0,4.
