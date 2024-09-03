# Dati di un Processo / Documento
La chiamata recupera i dati e lo stato di avanzamento di un processo esistente.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**).

# Interfaccia
- ENDPOINT PROCESSO: `http(s)://<url-bpm-web>/api/ext/getprocess`
- ENDPOINT DOCUMENTO: `http(s)://<url-bpm-web>/api/ext/getdocument`
- METODO: `POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione
>
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "includeVariables": [ ... ],
> &nbsp;&nbsp;&nbsp; "includeGraph": true/false
> }
{.is-info}

### Parametri

#### IncludeVariables
Restituisce le variabili appartenenti al processo.
> (vuoto) - Nessuna variabile
> "*" - Tutte le variabili
> Lista con i nomi delle variabili visualizzate

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato"
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore"
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "documentDescription": "descrizione-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "state": "stato-processo",
> &nbsp;&nbsp;&nbsp; "activeTasks: [ { ... } ],
> &nbsp;&nbsp;&nbsp; "links": [ { ... } ],
> &nbsp;&nbsp;&nbsp; "variables: { ... }
> }
{.is-info}

Per il documento si avranno i seguenti campi in più

> {
> &nbsp;&nbsp;&nbsp; "documentDate": "data-documento",
> &nbsp;&nbsp;&nbsp; "documentDueDate": "data-scadenza-documento",
> &nbsp;&nbsp;&nbsp; "barcode": "barcode",
> &nbsp;&nbsp;&nbsp; "versions": [ { ... } ],
> }
{.is-info}

### Parametri

#### ActiveTasks
Task attualmente attivi
> {
> &nbsp;&nbsp;&nbsp; "activity": "attività-processo",
> &nbsp;&nbsp;&nbsp; "activityDescription": "descrizione-attività",
> &nbsp;&nbsp;&nbsp; "userName": "utente-attività"
> }

#### Links
Processi collegati
> {
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "documentDescription": "descrizione-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo"
> }

#### Variables
Variabili del processo
> {
> &nbsp;&nbsp;&nbsp; "nome": "valore",
> &nbsp;&nbsp;&nbsp; "gruppo":
> &nbsp;&nbsp;&nbsp; {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; }
> }

#### Versions
Versioni del documento
> {
> &nbsp;&nbsp;&nbsp; "fileName": "nome-file-documento",
> &nbsp;&nbsp;&nbsp; "version": "numero-versione",
> &nbsp;&nbsp;&nbsp; "description": "descrizione-versione",
> &nbsp;&nbsp;&nbsp; "uploadDate": "data-caricamento",
> &nbsp;&nbsp;&nbsp; "username": "utente-versione",
> &nbsp;&nbsp;&nbsp; "state": "stato-versione",
> &nbsp;&nbsp;&nbsp; "extension": "estensione-documento"
> }

##### Version State
Stato delle versioni del documento
- 0 - Attivo
- 1 - Storico
- 2 - Bozza
