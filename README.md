# RilevApp

**RilevApp** è una PWA per rilievi in campo con codice identificativo, GPS, foto georeferenziata e mappa riservata.

## Funzioni

- Validazione codice tramite Supabase.
- Acquisizione coordinate GPS.
- Invio di una foto JPG ridimensionata.
- Scrittura coordinate GPS negli EXIF.
- Salvataggio dati su Supabase.
- Coda locale offline.
- Mappa riservata con login.
- Popup con anteprima e download foto.
- Filtro punti per codice identificativo.
- App Android sperimentale per accesso rapido al survey.

## Struttura

```text
index.html   # Home
survey.html  # Rilievo GPS + foto
map.html     # Mappa riservata
README.md    # Documentazione
```

## Survey

La pagina `survey.html` consente di:

1. inserire un codice identificativo;
2. acquisire il GPS;
3. scattare o caricare una foto;
4. inviare il rilievo a Supabase.

Le foto sono salvate nello Storage con questa struttura:

```text
survey-photos/CODICE/AAAAMMGG_HHMMSS_mmm.jpg
```

Esempio:

```text
survey-photos/TEST123/20260523_094512_384.jpg
```

## Mappa

La pagina `map.html` è riservata agli utenti abilitati tramite Supabase Auth.

Permette di:

* visualizzare i punti rilevati;
* consultare le foto associate;
* scaricare le immagini;
* filtrare i rilievi per codice identificativo.

## Supabase

Il progetto usa:

* Database PostgreSQL;
* Storage per le foto;
* Auth per l’accesso alla mappa.

Tabelle principali:

* `valid_codes`: codici autorizzati;
* `survey_points`: rilievi inviati.

## Note

- La geolocalizzazione richiede HTTPS e permesso dell’utente.
- In caso di modifiche al codice, può essere necessario svuotare cache/PWA.
- Su iPhone/Safari può essere necessario cancellare i dati del sito se viene caricata una vecchia versione.
- È disponibile una versione Android sperimentale dell’app, pensata come collegamento rapido al survey. Può essere soggetta a limitazioni o avvisi di sicurezza del sistema Android.
