# Song raten

Partyspiel für **ein** Handy, das im Kreis weitergegeben wird. Der DJ sucht einen Song, Spotify spielt ihn über die Bluetooth-Box, alle anderen raten den Titel.

Der Ton läuft in der installierten Spotify-App (App Remote), nicht im WebView. Diese Mini-App streamt nichts, nutzt kein `preview_url` und kein Web Playback SDK.

## In EveryApp hinzufügen

1. EveryApp auf dem Android-Gerät öffnen. Es muss ein **SrvEveryApp-** oder **EveryApp-Build** sein, der die Spotify-Bridge schon enthält (`com.everyapp.container.dev` bzw. `com.everyapp.container`).
2. Auf „App hinzufügen“ tippen.
3. Diese URL einfügen:

```
https://github.com/Krust3nKaese3/evryGuessTheSong
```

4. Die Berechtigungen bestätigen:
   - **spotify** — Suche und Wiedergabe über die Spotify-App
   - **vibration** — kurzes haptisches Feedback, wenn der DJ auf den roten Stopp-Buzzer tippt

5. Die Box (Bluetooth-Lautsprecher) wie gewohnt mit dem Handy koppeln. Song raten verbindet sich nicht selbst mit dem Lautsprecher.

## Spotify vorbereiten

1. Spotify installieren und mit einem **Premium**-Account anmelden. Einen bestimmten Track (`spotify:track:…`) abspielen geht nur mit Premium.
2. Die **Client ID** in EveryApp auf dem Startbildschirm unter **Spotify** eintragen und speichern. Sie steht absichtlich nicht in diesem Repository und wird hier nicht abgefragt.
3. Im Spiel auf „Erneut prüfen“, „Anmelden“ und „Verbinden“ tippen, falls der Status das noch verlangt.

Ohne gespeicherte Client ID meldet die Bridge: „Keine Spotify Client ID hinterlegt. Bitte in den EveryApp-Einstellungen eintragen.“ Song raten zeigt diesen Hinweis und verweist auf die EveryApp-Einstellungen. Die Mini-App bekommt keinen Access-Token.

Dashboard, Redirect-URI und SHA1 stehen in der EveryApp-Doku: [SPOTIFY.md](https://github.com/Krust3nKaese3/EveryApp/blob/main/SPOTIFY.md).

## Regeln

Alle sitzen im Kreis. Ein Handy geht reihum. Gespielt wird, bis jemand auf **Spiel beenden** tippt. Danach kommt der Endstand. Punkte gelten nur für diese Runde im Speicher, sie werden nicht gespeichert.

Jede Runde:

1. Wer das Handy hält, ist DJ. Zu Beginn jeder Runde wählt sich die Person aus der Liste und bestätigt das. Nach der Auflösung heißt es, das Handy weiterzugeben und den nächsten DJ ausdrücklich zu wählen.
2. Der DJ sucht einen Track und tippt auf **Los**. Der Song startet von vorne. Jeder Track darf in diesem Spiel nur einmal gestartet werden.
3. Die anderen hören über die Box und rufen „Stopp“, wenn sie den Titel kennen. Der DJ tippt sofort auf den roten Buzzer. Die Wiedergabe pausiert.
4. Danach wird zuerst gewählt, **wer** geraten hat (alle außer dem aktuellen DJ), und dann **Ja** oder **Nein**.
5. Richtig: diese Person bekommt **+1**. Titel und Interpret werden aufgelöst. Danach das Handy weitergeben.
6. Falsch: diese Person bekommt **−1**, der Song läuft an der Pausestelle weiter. Es darf wieder auf Stopp geraten werden.
7. **Überspringen** (während der Song läuft, auch nach einem Fehlversuch): **−3** für den DJ, der den Song aufgelegt hat. Danach Auflösung und Handy weitergeben.
8. Endet der Track von selbst, ohne richtigen Tipp und ohne Überspringen: „Wurde der Song erraten?“ Bei Ja: wer? (ohne den DJ) und **+1** für diese Person. Bei Nein: **−3** für den DJ. Danach Auflösung und Handy weitergeben.

War der Buzzer ein Versehen, kann der DJ „Versehentlich gedrückt“ tippen. Dann läuft der Song weiter und niemand bekommt Punkte.

Ein Spiel zählt vom ersten gestarteten Song bis **Spiel beenden**. „Nochmal, gleiche Namen“ beginnt ein neues Spiel. In einem Spiel darf jeder Track nur einmal über **Los** starten. Tippt der DJ **Los** bei einem Track, der in diesem Spiel schon gestartet wurde, bleibt die Suchseite offen, Spotify spielt nicht, und es erscheint genau „Song war schon an.“ Titel und Interpret dürfen dabei sichtbar bleiben. Andere Schreibweisen derselben Track-URI zählen als derselbe Song. Läuft der Song nach **Los** nie an und der DJ tippt **Zurück zur Suche**, darf derselbe Track erneut versucht werden. Überspringen, ein falscher Tipp mit Weiterlaufen, das natürliche Songende und ein späterer DJ lassen die Sperre bestehen.

## Empfehlungen

Auf der Suchseite des DJ gibt es den Button **Empfehlungen**. Es wird nichts geladen und nichts angezeigt, solange der DJ nicht darauf tippt. Während des Ladens zeigt der Button einen kurzen Ladezustand. Danach erscheinen höchstens drei Vorschläge, weniger wenn der Vorrat dünn ist. Gibt es keinen, steht ein kurzer Hinweis.

Die Vorschläge stammen aus allen Tracks, die in diesem Spiel schon gestartet wurden, vom ersten Song bis **Spiel beenden** oder „Nochmal, gleiche Namen“. Vor dem ersten gestarteten Song gibt es noch keine Empfehlungen. Der Hinweis erscheint, ohne Spotify zu fragen.

Die Liste gilt nur für den aktuellen DJ. Geht das Handy weiter (der nächste DJ wird bestätigt), ist sie weg. Ein späterer DJ sieht keine Tracks, die einem früheren DJ in diesem Spiel schon als Empfehlung angezeigt wurden. Ein angezeigter, aber nicht gestarteter Vorschlag darf weiter über die Suche und **Los** laufen. Nur ein echtes **Los** sperrt den Track. Tippt derselbe DJ im selben Suchgang noch einmal auf **Empfehlungen**, bleiben dieselben Vorschläge stehen.

## Spoiler

Nur der DJ schaut während der Suche aufs Handy. In den Suchergebnissen und in den Empfehlungen stehen Titel, Interpret und Album, weil der DJ den Song aussucht.

Ab **Los** bis zur Auflösung (richtig, übersprungen oder nach dem Songende) zeigen Buzzer, Tipp und die Frage nach dem Songende weder Titel, Interpret, Albumname noch Cover. Empfehlungen stehen dort nicht. Der Spielerstatus aus Spotify wird auf diesen Schirmen nicht angezeigt.

## Im Browser

Ohne EveryApp-Bridge erscheint ein kurzer Hinweis. Das Spiel startet dort nicht und bricht nicht ab. Ton gibt es nur in EveryApp mit Spotify.

## Aufbau

```
evryGuessTheSong/
├── everyapp.json    # Manifest
├── index.html       # App, CSS und JavaScript inline
└── README.md
```

Benötigte Berechtigungen: `spotify`, `vibration`.
