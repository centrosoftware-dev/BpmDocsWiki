---
title: Avanzamento Processo
description: Come valorizzare le variabili e completare completare un task in corso
published: true
date: 2024-08-08T09:07:48.530Z
tags: 
editor: markdown
dateCreated: 2024-08-07T09:41:10.454Z
---

# Descrizione
Questa chiamata è utilizzata per completare un'attività del processo e avanzare allo step successivo.

L'operazione avviene solo se l'attività è 'attiva' ovvero visibile nella todo-list di un utente.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**) e **activity**.
Durante l'avanzamento verranno controllate le condizioni di validazione e di obbligatorietà che potranno impedire la continuazione nel caso non verranno soddisfatte.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/exectask`
- METODO: `POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo"
> &nbsp;&nbsp;&nbsp; "activity": "nome-attività"
> &nbsp;&nbsp;&nbsp; "comments": "note-avanzamento"
> &nbsp;&nbsp;&nbsp; "variables": { ... }
> }
{.is-info}

#### Variables
> {
> &nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; "gruppo":
> &nbsp;&nbsp;&nbsp; {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; }
> }
{.is-info}

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato"
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore"
> }
{.is-info}
