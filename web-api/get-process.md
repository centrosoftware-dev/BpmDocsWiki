# Dati di un Processo / Documento
La chiamata recupera i dati e lo stato di avanzamento di un processo esistente.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**).

# Interfaccia
- ENDPOINT PROCESSO: `http(s)://<url-bpm-web>/api/ext/getprocess`
- ENDPOINT DOCUMENTO: `http(s)://<url-bpm-web>/api/ext/getdocument`
- METODO: `POST`

## Corpo
```
{
  autenticazione

  "model": "modello-processo",
  "documentName": "nome-univoco-processo",
  "instanceId": "codice-univoco-processo",
  "includeVariables": [ ... ],
  "includeGraph": true/false
}
```

### Parametri

#### IncludeVariables
Restituisce le variabili appartenenti al processo.
- (vuoto) - Nessuna variabile
- "*" - Tutte le variabili
- Lista con i nomi delle variabili visualizzate

## Risposta
```
{
  "result": "true / false in base al risultato"
  "message": "messaggio in caso di errore"
  "model": "modello-processo",
  "documentName": "nome-univoco-processo",
  "documentDescription": "descrizione-processo",
  "instanceId": "codice-univoco-processo",
  "state": "stato-processo",
  "activeTasks: [ { ... } ],
  "links": [ { ... } ],
  "variables: { ... }
}
```

Per il documento si avranno i seguenti campi in più
```
{
  "documentDate": "data-documento",
  "documentDueDate": "data-scadenza-documento",
  "barcode": "barcode",
  "versions": [ { ... } ],
}
```

### Parametri

#### ActiveTasks
Task attualmente attivi
```
{
  "activity": "attività-processo",
  "activityDescription": "descrizione-attività",
  "userName": "utente-attività"
}
```

#### Links
Processi collegati
```
{
  "model": "modello-processo",
  "documentName": "nome-univoco-processo",
  "documentDescription": "descrizione-processo",
  "instanceId": "codice-univoco-processo"
}
```

#### Variables
Variabili del processo
```
{
  "nome": "valore",
  "gruppo": {
    "nome": "valore"
  }
}
```

#### Versions
Versioni del documento
```
{
  "fileName": "nome-file-documento",
  "version": "numero-versione",
  "description": "descrizione-versione",
  "uploadDate": "data-caricamento",
  "username": "utente-versione",
  "state": "stato-versione",
  "extension": "estensione-documento"
}
```

##### Version State
Stato delle versioni del documento
- 0 - Attivo
- 1 - Storico
- 2 - Bozza
