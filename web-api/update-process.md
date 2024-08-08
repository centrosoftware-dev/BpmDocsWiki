---
title: Aggiornamento Processo esistente
description: Come modificare e forzare uno stato in un processo esistente
published: true
date: 2024-08-08T08:29:04.254Z
tags: 
editor: markdown
dateCreated: 2024-08-07T10:51:16.832Z
---

# Descrizione
La chiamata è utilizzata per aggiornare le variabili o forzare lo stato ad un processo già esistente.

Lo stato verrà modificato a seconda della raggiungibilità dello stato stesso o nel caso dello stato libero.

I parametri obbligatori sono **model** e **documentName** (o **instanceId**).

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/updateprocess`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "state": "nuovo-stato-processo",
> &nbsp;&nbsp;&nbsp; "variables": { ... }
> &nbsp;&nbsp;&nbsp; "resetGroups": [ ... ]
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

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato",
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo"
> }
{.is-info}
