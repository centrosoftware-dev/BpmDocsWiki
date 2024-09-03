# Aggiornamento Processo
La chiamata è utilizzata per aggiornare le variabili o forzare lo stato ad un processo già esistente.

Lo stato verrà modificato a seconda della raggiungibilità dello stato stesso o nel caso dello stato libero.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**).

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/updateprocess`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "model": "modello",
  "documentName": "nome-univoco-processo",
  "instanceId": "codice-univoco-processo",
  "state": "nuovo-stato-processo",
  "variables": { ... }
  "resetGroups": [ ... ]
}
```

### Parametri

#### Variables
```
{
  "nome": "valore"
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
  "instanceId": "codice-univoco-processo"
}
```
