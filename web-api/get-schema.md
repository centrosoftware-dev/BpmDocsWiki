# Struttura di una Attività
La chiamata è utilizzata per visualizzare lo schema di un'attività di un modello, che comprende le variabili richieste dall'attività stessa.

I parametri obbligatori sono **modelName** e **activityName**.

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/getschema`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "modelName": "modello-processo",
> &nbsp;&nbsp;&nbsp; "activityName": "nome-attività"
> }
{.is-info}

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato",
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore",
> &nbsp;&nbsp;&nbsp; "model": "modello-processo",
> &nbsp;&nbsp;&nbsp; "activity": "nome-attività",
> &nbsp;&nbsp;&nbsp; "properties": [ { ... } ]
> }
{.is-info}

### Parametri

#### Properties
Informazioni delle variabili dell'attività
> {
> &nbsp;&nbsp;&nbsp; "propertyName": "nome-variabile",
> &nbsp;&nbsp;&nbsp; "propertyType": "tipo-variabile",
> &nbsp;&nbsp;&nbsp; "required": "true / false se obbligatoria",
> &nbsp;&nbsp;&nbsp; "readOnly": "true / false se solo lettura",
> &nbsp;&nbsp;&nbsp; "hasDefault": "true / false se presente formula default",
> &nbsp;&nbsp;&nbsp; "variablesType": "tipo-variabile-bpm",
> &nbsp;&nbsp;&nbsp; "description": "descrizione-variabile",
> &nbsp;&nbsp;&nbsp; "availableValues": [ ... ]
> }

##### AvailableValues
Se la variabile e di tipo lista contiene i valori che può assumere.
