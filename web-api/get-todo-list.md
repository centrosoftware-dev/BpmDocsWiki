# Caricamento TodoList
La chiamata è utilizzata per visualizzare la todo list di un utente, che comprende tutte le attività attive, completate e pianificate relative ad un utente bpm.

Non ci sono parametri obbligatori e nel caso non venga specificato un utente verrà utilizzato quello con cui avviene l'autenticazione.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/gettodolist`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "fromDate": "data-inizio-filtro",
> &nbsp;&nbsp;&nbsp; "toDate": "data-fine-filtro",
> &nbsp;&nbsp;&nbsp; "filterByUser": "utente-filtro",
> &nbsp;&nbsp;&nbsp; "filterByText": "testo-filtro",
> &nbsp;&nbsp;&nbsp; "filterByPriority": "priorità-filtro",
> &nbsp;&nbsp;&nbsp; "includeCompleted": "true / false",
> &nbsp;&nbsp;&nbsp; "includePlanned": "true / false",
> &nbsp;&nbsp;&nbsp; "includeCC": "true / false"
> }
{.is-info}

### Parametri

#### FilterByUser
Utente per il quale verranno visualizzate le attività.

Può essere un utente bpm o un utente collegato a sam
> {
> &nbsp;&nbsp;&nbsp; "samUser": "codice-sam"
> }

---

> {
> &nbsp;&nbsp;&nbsp; "samPortalUser: "codice-sam",
> &nbsp;&nbsp;&nbsp; "samPortalCompany": "azienda-sam"
> }

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "`true / false in base al risultato`",
> &nbsp;&nbsp;&nbsp; "message": "`messaggio in caso di errore`",
> &nbsp;&nbsp;&nbsp; "todolist": [ { ... } ]
> }
{.is-info}

### Parametri

#### TodoList
> {
> &nbsp;&nbsp;&nbsp; "assignedUsers: [ { ... } ],
> &nbsp;&nbsp;&nbsp; "activityName": "nome-attività",
> &nbsp;&nbsp;&nbsp; "activityDescription": "descrizione-attività",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "documentDescription": "descrizione-processo",
> &nbsp;&nbsp;&nbsp; "isCC": "true / false",
> &nbsp;&nbsp;&nbsp; "startDate": "data-inizio-attività",
> &nbsp;&nbsp;&nbsp; "endDate": "data-fine-attività",
> &nbsp;&nbsp;&nbsp; "dueDate": "data-scadenza-attività",
> &nbsp;&nbsp;&nbsp; "state": "stato-attività",
> &nbsp;&nbsp;&nbsp; "priority": "priorità-attività",
> &nbsp;&nbsp;&nbsp; "processHeaders": [ { ... } ],
> &nbsp;&nbsp;&nbsp; "activityLink": "link-web-attività",
> &nbsp;&nbsp;&nbsp; "processLink": "link-web-processo",
> }

##### AssignedUsers
> {
> &nbsp;&nbsp;&nbsp; "userName: "utente-bpm",
> &nbsp;&nbsp;&nbsp; "samUser": "codice-sam"
> }

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
