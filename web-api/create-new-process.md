# Avviamento Nuovo Processo
Questa chiamata è utilizzata per creare una nuova istanza di un processo o di un documento.

E' concepita per eseguire le stesse regole e controlli che verrebbero eseguiti dall'utente che crea un nuovo processo su client.

I parametri obbligatori sono **model** e **startObject**.
Mentre **variables** è un oggetto composto da chiave - valore che serve per valorizzare le variabili all'interno del processo creato.
Nel caso di una variabile di gruppo basterà utilizzare come chiave il gruppo e come valore una lista di oggetti chiave - valore per ogni riga che si vuole aggiungere al gruppo.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/createnewprocess`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "model": "modello-processo",
  "startObject": "oggetto-di-avvio",
  "variables": { ... }
}
```

### Parametri

#### Variables
```
{
  "nome": "valore",
  "gruppo": {
    "nome": "valore"
  }
}
```

## Risposta
```
{
  "result": "true / false in base al risultato",
  "message": "messaggio in caso di errore",
  "documentName": "nome-univoco-processo",
  "documentDescription": "descrizione-processo",
  "instanceId": "codice-univoco-processo",
  "isDuplicate": "true / false se il processo esiste già",
  "duplicateDocumentName": "nome-processo-duplicato"
}
```
