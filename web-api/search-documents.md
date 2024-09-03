# Ricerca Documento
La chiamata è utilizzata per ricercare i documenti in una classe documentale tramite dei filtri.

E' possibile effettuare la ricera su più modelli, prestando attenzione al fatto che i filtri vengono applicati sul primo modello elencato.

**N.B. Se nel modello non sono presenti le variabili filtrate il risultato sarà una lista vuota.**

L'unico parametro obbligatorio è **model**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/searchdocuments`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello",
> &nbsp;&nbsp;&nbsp; "filters": [ { ... } ]
> }
{.is-info}

### Parametri

#### Filters
> {
> &nbsp;&nbsp;&nbsp; "name": "nome-variabile"
> &nbsp;&nbsp;&nbsp; "value": "valore-variabile"
> &nbsp;&nbsp;&nbsp; "valueIn": [ ... ]
> }

## Risposta
> {
> &nbsp;&nbsp;&nbsp; variabili,
> &nbsp;&nbsp;&nbsp;
> &nbsp;&nbsp;&nbsp; "fix_data": "data-creazione-documento",
> &nbsp;&nbsp;&nbsp; "fix_name": "nome-univoco-documento",
> &nbsp;&nbsp;&nbsp; "fix_modificato": "modificato",
> &nbsp;&nbsp;&nbsp; "fix_text": "testo-documento",
> &nbsp;&nbsp;&nbsp; "fix_lifecycle": "modello-documento",
> &nbsp;&nbsp;&nbsp; "fix_owners": "propietari-documento",
> &nbsp;&nbsp;&nbsp; "fix_state": "stato-documento",
> &nbsp;&nbsp;&nbsp; "fix_descrizione": "descrizione-documento",
> &nbsp;&nbsp;&nbsp; "fix_utecreazione": "utente-creazione",
> &nbsp;&nbsp;&nbsp; "fix_documentdate": "data-documento",
> &nbsp;&nbsp;&nbsp; "fix_duedate": "data-scadenza-documento",
> &nbsp;&nbsp;&nbsp; "fix_barcode": "barcode-documento",
> &nbsp;&nbsp;&nbsp; "fix_currentversion": "versione-documento",
> &nbsp;&nbsp;&nbsp; "fix_filename": "nome-documento",
> &nbsp;&nbsp;&nbsp; "id": "codice-univoco-documento",
> &nbsp;&nbsp;&nbsp; "must_lifecycle": "modello-documento",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-documento",
> &nbsp;&nbsp;&nbsp; "must_checkedout": " "
> }
{.is-info}

### Parametri

##### Varibili
Per ogni variabile verrà generata una riga nell'oggetto json con chiave il nome della variabile e valore il valore della variabile.
