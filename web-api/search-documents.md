# Ricerca Documento
La chiamata è utilizzata per ricercare i documenti in una classe documentale tramite dei filtri.

E' possibile effettuare la ricera su più modelli, prestando attenzione al fatto che i filtri vengono applicati sul primo modello elencato.

**N.B. Se nel modello non sono presenti le variabili filtrate il risultato sarà una lista vuota.**

L'unico parametro obbligatorio è **model**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/searchdocuments`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "model": "modello",
  "filters": [ { ... } ]
}
```

### Parametri

#### Filters
```
{
  "name": "nome-variabile"
  "value": "valore-variabile"
  "valueIn": [ ... ]
}
```

## Risposta
```
{
  variabili,

  "fix_data": "data-creazione-documento",
  "fix_name": "nome-univoco-documento",
  "fix_modificato": "modificato",
  "fix_text": "testo-documento",
  "fix_lifecycle": "modello-documento",
  "fix_owners": "propietari-documento",
  "fix_state": "stato-documento",
  "fix_descrizione": "descrizione-documento",
  "fix_utecreazione": "utente-creazione",
  "fix_documentdate": "data-documento",
  "fix_duedate": "data-scadenza-documento",
  "fix_barcode": "barcode-documento",
  "fix_currentversion": "versione-documento",
  "fix_filename": "nome-documento",
  "id": "codice-univoco-documento",
  "must_lifecycle": "modello-documento",
  "instanceId": "codice-univoco-documento",
  "must_checkedout": " "
}
```

### Parametri

##### Varibili
Per ogni variabile verrà generata una riga nell'oggetto json con chiave il nome della variabile e valore il valore della variabile.

