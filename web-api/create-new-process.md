---
title: Avviamento Nuovo Processo
description: Come creare una nuova istanza di un modello di processo o classe documentale
published: true
date: 2024-08-07T14:49:10.175Z
tags: 
editor: markdown
dateCreated: 2024-08-07T09:27:17.444Z
---

# Descrizione
Questa chiamata è utilizzata per creare una nuova istanza di un processo o di un documento.

E' concepita per eseguire le stesse regole e controlli che verrebbero eseguiti dall'utente che crea un nuovo processo su client.

I parametri obbligatori sono **model** e **startObject**.
Mentre **variables** è un oggetto composto da chiave - valore che serve per valorizzare le variabili all'interno del processo creato.
Nel caso di una variabile di gruppo basterà utilizzare come chiave il gruppo e come valore una lista di oggetti chiave - valore per ogni riga che si vuole aggiungere al gruppo.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/createnewprocess`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "startObject": "oggetto-di-avvio",
> &nbsp;&nbsp;&nbsp; "variables": { ... }
> &nbsp;&nbsp;&nbsp; }
> }
{.is-info}

#### Variables
> {
> &nbsp;&nbsp;&nbsp; "nome": "valore",
> &nbsp;&nbsp;&nbsp; "gruppo":
> &nbsp;&nbsp;&nbsp; {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; }
> }

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "documentDescription": "descrizione-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "isDuplicate": "true / false se il processo esiste già",
> &nbsp;&nbsp;&nbsp; "duplicateDocumentName": "nome-processo-duplicato",
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato",
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore",
> }
{.is-info}
