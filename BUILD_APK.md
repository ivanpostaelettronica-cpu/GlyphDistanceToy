# Come ottenere l'APK installabile

Il progetto include una GitHub Action che genera automaticamente un APK Android firmato con chiave di debug, installabile manualmente sul Nothing Phone (3).

## Metodo GitHub
1. Crea un repository GitHub e carica il contenuto di questa cartella mantenendo la struttura dei file, inclusa `.github`.
2. Apri **Actions** nel repository.
3. Seleziona **Build installable APK**.
4. Premi **Run workflow**.
5. Al termine scarica l'artifact **GlyphDistanceToy-APK**.
6. Estrai `GlyphDistanceToy.apk` e aprilo sul Nothing Phone (3).
7. Autorizza l'installazione dalla sorgente usata solo quando Android lo richiede.
8. Apri l'app e concedi l'accesso Health Connect a **Distanza** e, se richiesto, la lettura in background.
9. Verifica con **Leggi distanza di oggi**: il valore deve corrispondere ai dati Google Fit disponibili in Health Connect.
10. Premi **Apri gestione Glyph Toys** e aggiungi **Distanza oggi** ai Toy attivi.

## Comportamento della versione 0.2
Il Toy considera esclusivamente i record di distanza provenienti da Google Fit (`com.google.android.apps.fitness`) e solo quelli compresi tra mezzanotte locale e l'ora corrente. In questo modo il conteggio riparte ogni giorno senza cancellare lo storico.
