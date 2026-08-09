# Glyph Distance Toy — Nothing Phone (3)

Glyph Toy per mostrare sulla Glyph Matrix la distanza giornaliera registrata da **Google Fit**, in chilometri.

## Versione 0.2 — Google Fit only
- Legge `DistanceRecord.DISTANCE_TOTAL` da Health Connect.
- Filtra i dati esclusivamente per l'origine `com.google.android.apps.fitness` (Google Fit).
- Intervallo: dalle **00:00 locali del giorno corrente** all'istante corrente.
- A mezzanotte non cancella dati: la query passa automaticamente al nuovo giorno, quindi il valore visualizzato torna a `0.0 km` al successivo aggiornamento.
- Aggiornamento ogni 60 secondi mentre il Toy è selezionato.
- Pressione lunga del Glyph Button: aggiornamento immediato.
- Nessun permesso Internet e nessun invio di dati.

## Requisito importante
Google Fit deve scrivere/sincronizzare il dato **Distanza** in Health Connect. Se Health Connect non contiene record di distanza con origine Google Fit per la giornata corrente, il Toy mostra `0.0 KM`.

## Nothing Glyph Matrix
- Phone (3): `Glyph.DEVICE_23112`, matrice 25×25.
- Servizio registrato con action `com.nothing.glyph.TOY`.
- Permesso Nothing: `com.nothing.ketchum.permission.ENABLE`.
- Pressione lunga abilitata tramite metadata del Toy.

## APK
Vedi `BUILD_APK.md`. La GitHub Action `.github/workflows/build-apk.yml` produce `GlyphDistanceToy.apk` come artifact installabile.

## SDK Nothing
`glyph-matrix-sdk-2.0.aar` non è incluso nel pacchetto. La build automatica lo preleva dal repository ufficiale Nothing durante la compilazione.
