# Aggiornamento Task
La chiamata è utilizzata per aggiornare le informazioni relative ad una attività.

I parametri obbligatori sono **model** e **documentName** o (**instanceId**) e **activityName**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/updatetask`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "activityName": "nome-attività",
> &nbsp;&nbsp;&nbsp; "assignedUser": [ { ... } ],
> &nbsp;&nbsp;&nbsp; "ccUser": [ { ... } ],
> &nbsp;&nbsp;&nbsp; "respUser": [ { ... } ],
> &nbsp;&nbsp;&nbsp; "priority": "priorità",
> &nbsp;&nbsp;&nbsp; "durationDays": "durata-attività",
> &nbsp;&nbsp;&nbsp; "scope": "ambito-attività",
> &nbsp;&nbsp;&nbsp; "startDate": "data-di-inizio",
> &nbsp;&nbsp;&nbsp; "actualStartDate": "data-inizio-attuale",
> &nbsp;&nbsp;&nbsp; "plannedStartDate": "data-inizio-pianificata",
> &nbsp;&nbsp;&nbsp; "updatedStartDate": "data-inizio-aggiornata",
> &nbsp;&nbsp;&nbsp; "dueDate": "data-di-scadenza",
> &nbsp;&nbsp;&nbsp; "ignoreCalendar": "true / false se utilizzato il calendario dei giorni lavorativi"
> }
{.is-info}

### Parametri

#### AssignedUser & CcUser & RespUser
> {
> &nbsp;&nbsp;&nbsp; "userName: "utente-bpm",
> &nbsp;&nbsp;&nbsp; "samUser": "codice-sam"
> }

#### Priority
- 1 - 10 - Priorità bassa, medio e alta
- 0 - Priorità non specificata
- -99 - Priorità sospesa

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato",
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore"
> }
{.is-info}
