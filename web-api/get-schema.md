# Struttura di una Attività
La chiamata è utilizzata per visualizzare lo schema di un'attività di un modello, che comprende le variabili richieste dall'attività stessa.

I parametri obbligatori sono **modelName** e **activityName**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/getschema`
- METODO:	`POST`

## Corpo
```
{
  autenticazione,

  "modelName": "modello-processo",
  "activityName": "nome-attività"
}
```

## Risposta
```
{
  "result": "true / false in base al risultato",
  "message": "messaggio in caso di errore",
  "model": "modello-processo",
  "activity": "nome-attività",
  "properties": [ { ... } ]
}
```

### Parametri

#### Properties
Informazioni delle variabili dell'attività
```
{
  "propertyName": "nome-variabile",
  "propertyType": "tipo-variabile",
  "required": "true / false se obbligatoria",
  "readOnly": "true / false se solo lettura",
  "hasDefault": "true / false se presente formula default",
  "variablesType": "tipo-variabile-bpm",
  "description": "descrizione-variabile",
  "availableValues": [ ... ]
}
```

##### AvailableValues
Se la variabile e di tipo lista contiene i valori che può assumere.

