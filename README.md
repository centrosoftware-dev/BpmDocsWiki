# Introduzione
Il BPM mette a disposizione dei servizi per l'interazione con software di terze parti.

I servizi comprendo una varietà di azioni eseguibili o di recupero dati.

## Autenticazione
Le funzioni esterne richiamabili tramite API necessitano di autenticazione principalmente basata sul sistema delle API KEY.

All’interno di BPM è necessario generare un nuovo token casuale da associare univocamente all’applicazione esterna che fa eseguire i comandi richiesti. 

Si considera che una applicazione esterna, una volta dotata di un api key specifico, sia autorizzata ad eseguire qualunque attività per conto di qualunque utente.
&nbsp;

### Utente BPM
```
{
  "authorization": {
    "authenticationToken": "bpm-api-token",
    "userName": "utente-bpm"
  }
}
```

### Utente SAM
```
{
  "authorization": {
    "authenticationToken": "bpm-api-token",
    "samUser": "id-utente-sam"
  }
}
```

### Utente Portali SAM
```
{
  "authorization": {
    "authenticationToken": "bpm-api-token",
    "samPortalUser": "id-utente-portali-sam",
    "samPortalCompany": "azienda-utente-portali-sam"
  }
}
```

# Web Services

- [Creazione Processo](./web-api/create-new-process.md)

- [Avanzamento Processo](./web-api/exec-task.md)

- [Aggiornamento Processo](./web-api/update-process.md)

- [Caricamento Allegato](./web-api/upload-attachmnet.md)

- [Aggiornamento Processo](./web-api/update-process.md)

- [Dati di un Processo / Documento](./web-api/get-process.md)

- [Caricamento TodoList](./web-api/get-todo-list.md)

- [Verifica Dati Utente](./web-api/get-user.md)

- [Struttura di una Attività](./web-api/get-schema.md)

- [Aggiornamento Task](./web-api/update-task.md)

- [Download Documento](./web-api/download-document.md)

- [Ricerca Documento](./web-api/search-documents.md)

> [Lista Modelli](./web-api/document-sets.md)
