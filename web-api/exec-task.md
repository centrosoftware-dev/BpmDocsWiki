# Avanzamento Processo
Questa chiamata è utilizzata per completare un'attività del processo e avanzare allo step successivo.

L'operazione avviene solo se l'attività è 'attiva' ovvero visibile nella todo-list di un utente.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**) e **activity**.
Durante l'avanzamento verranno controllate le condizioni di validazione e di obbligatorietà che potranno impedire la continuazione nel caso non verranno soddisfatte.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/exectask`
- METODO: `POST`

## Corpo
```
{
  autenticazione,

  "model": "modello",
  "documentName": "nome-univoco-processo",
  "instanceId": "codice-univoco-processo"
  "activity": "nome-attività"
  "comments": "note-avanzamento"
  "variables": { ... }
}
```

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
  "result": "true / false in base al risultato"
  "message": "messaggio in caso di errore"
}
```
