---
title: Verifica Dati Utente
description: Come recuperare le informazioni relative ad un utente bpm
published: true
date: 2024-08-08T08:30:46.651Z
tags: 
editor: markdown
dateCreated: 2024-08-08T08:30:42.374Z
---

# Descrizione
La chiamata è utilizzata per recuperare le informazioni relative ad un utente.

Non ci sono parametri da inserire in quanto l'utente recuperato sarà quello dell'autenticazione.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/getuser`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione
> }
{.is-info}

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato",
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore",
> &nbsp;&nbsp;&nbsp; "userName": "nome-utente",
> &nbsp;&nbsp;&nbsp; "isExternal": "true / false se è un utente di collaborazione esterna",
> &nbsp;&nbsp;&nbsp; "groups": [ ... ]
> }
{.is-info}

### Parametri

#### Groups
Lista con i gruppi ai quali l'utente appartiene