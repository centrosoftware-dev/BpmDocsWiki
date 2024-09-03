# Aggiornamento Task
La chiamata è utilizzata per aggiornare le informazioni relative ad una attività.

I parametri obbligatori sono **model** e **documentName** o (**instanceId**) e **activityName**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/updatetask`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "model": "modello-processo",
  "documentName": "nome-univoco-processo",
  "instanceId": "codice-univoco-processo",
  "activityName": "nome-attività",
  "assignedUser": [ { ... } ],
  "ccUser": [ { ... } ],
  "respUser": [ { ... } ],
  "priority": "priorità",
  "durationDays": "durata-attività",
  "scope": "ambito-attività",
  "startDate": "data-di-inizio",
  "actualStartDate": "data-inizio-attuale",
  "plannedStartDate": "data-inizio-pianificata",
  "updatedStartDate": "data-inizio-aggiornata",
  "dueDate": "data-di-scadenza",
  "ignoreCalendar": "true / false se utilizzato il calendario dei giorni lavorativi"
}
```

### Parametri

#### AssignedUser & CcUser & RespUser
```
{
  "userName: "utente-bpm",
  "samUser": "codice-sam"
}
```

#### Priority
- 1 - 10 - Priorità bassa, medio e alta
- 0 - Priorità non specificata
- -99 - Priorità sospesa

## Risposta
```
{
  "result": "true / false in base al risultato",
  "message": "messaggio in caso di errore"
}
```
