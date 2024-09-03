# Verifica Dati Utente
La chiamata è utilizzata per recuperare le informazioni relative ad un utente.

Non ci sono parametri da inserire in quanto l'utente recuperato sarà quello dell'autenticazione.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/getuser`
- METODO:	`POST`

## Corpo
```
{
  autenticazione
}
```

## Risposta
```
{
  "result": "true / false in base al risultato",
  "message": "messaggio in caso di errore",
  "userName": "nome-utente",
  "isExternal": "true / false se è un utente di collaborazione esterna",
  "groups": [ ... ]
}
```

### Parametri

#### Groups
Lista con i gruppi ai quali l'utente appartiene

