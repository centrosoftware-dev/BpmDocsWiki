# Caricamento TodoList
La chiamata è utilizzata per visualizzare la todo list di un utente, che comprende tutte le attività attive, completate e pianificate relative ad un utente bpm.

Non ci sono parametri obbligatori e nel caso non venga specificato un utente verrà utilizzato quello con cui avviene l'autenticazione.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/gettodolist`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "fromDate": "data-inizio-filtro",
  "toDate": "data-fine-filtro",
  "filterByUser": "utente-filtro",
  "filterByText": "testo-filtro",
  "filterByPriority": "priorità-filtro",
  "includeCompleted": "true / false",
  "includePlanned": "true / false",
  "includeCC": "true / false"
}
```

### Parametri

#### FilterByUser
Utente per il quale verranno visualizzate le attività.

Può essere un utente bpm o un utente collegato a sam
```
{
  "samUser": "codice-sam"
}
```

---

```
{
  "samPortalUser: "codice-sam",
  "samPortalCompany": "azienda-sam"
}
```

## Risposta
```
{
  "result": "`true / false in base al risultato`",
  "message": "`messaggio in caso di errore`",
  "todolist": [ { ... } ]
}
```

### Parametri

#### TodoList
```
{
  "assignedUsers: [ { ... } ],
  "activityName": "nome-attività",
  "activityDescription": "descrizione-attività",
  "instanceId": "codice-univoco-processo",
  "model": "modello-processo",
  "documentName": "nome-univoco-processo",
  "documentDescription": "descrizione-processo",
  "isCC": "true / false",
  "startDate": "data-inizio-attività",
  "endDate": "data-fine-attività",
  "dueDate": "data-scadenza-attività",
  "state": "stato-attività",
  "priority": "priorità-attività",
  "processHeaders": [ { ... } ],
  "activityLink": "link-web-attività",
  "processLink": "link-web-processo",
}
```

##### AssignedUsers
```
{
  "userName: "utente-bpm",
  "samUser": "codice-sam"
}
```

##### State
- active - Attività attiva
- completed - Attività completata
- planned - Attività pianificata

##### Priority
- suspended - Attività sospesa
- none - Attività senza priorità
- high - Attività con alta priorità
- medium - Attività con media priorità
- low - Attività con bassa priorità

##### ProcessHeaders
Variabili di intestazione del processo.
