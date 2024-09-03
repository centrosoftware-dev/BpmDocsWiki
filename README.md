# Introduzione
Il BPM mette a disposizione dei servizi per l'interazione con software di terze parti.

I servizi comprendo una varietà di azioni eseguibili o di recupero dati.

## Autenticazione
Le funzioni esterne richiamabili tramite API necessitano di autenticazione principalmente basata sul sistema delle API KEY.

All’interno di BPM è necessario generare un nuovo token casuale da associare univocamente all’applicazione esterna che fa eseguire i comandi richiesti. 

Si considera che una applicazione esterna, una volta dotata di un api key specifico, sia autorizzata ad eseguire qualunque attività per conto di qualunque utente.
&nbsp;

### Utente BPM
> {
> &nbsp;&nbsp;&nbsp; "authorization": {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "authenticationToken": "bpm-api-token",
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "userName": "utente-bpm"
> &nbsp;&nbsp;&nbsp; }
> }

### Utente SAM
> {
> &nbsp;&nbsp;&nbsp; "authorization": {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "authenticationToken": "bpm-api-token",
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "samUser": "id-utente-sam"
> &nbsp;&nbsp;&nbsp; }
> }

### Utente Portali SAM
> {
> &nbsp;&nbsp;&nbsp; "authorization": {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "authenticationToken": "bpm-api-token",
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "samPortalUser": "id-utente-portali-sam",
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "samPortalCompany": "azienda-utente-portali-sam"
> &nbsp;&nbsp;&nbsp; }
> }

# Web Services

> [Creazione Processo](./web-api/create-new-process.md)
{.is-info}

> [Avanzamento Processo](./web-api/exec-task.md)
{.is-info}

> [Aggiornamento Processo](./web-api/update-process.md)
{.is-info}

> [Caricamento Allegato](./web-api/upload-attachmnet.md)
{.is-info}

> [Aggiornamento Processo](./web-api/update-process.md)
{.is-info}

> [Dati di un Processo / Documento](./web-api/get-process.md)
{.is-info}

> [Caricamento TodoList](./web-api/get-todo-list.md)
{.is-info}

> [Verifica Dati Utente](./web-api/get-user.md)
{.is-info}

> [Struttura di una Attività](./web-api/get-schema.md)
{.is-info}

> [Aggiornamento Task](./web-api/update-task.md)
{.is-info}

> [Download Documento](./web-api/download-document.md)
{.is-info}

> [Ricerca Documento](./web-api/search-documents.md)
{.is-info}

> [Lista Modelli](./web-api/document-sets.md)
{.is-info}

