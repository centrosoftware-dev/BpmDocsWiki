# Download Documento
La chiamata è utilizzata per scaricare il file originale di un documento creato.
E' possibile ricevere il documento sia in formato binario sia in base64, in base all'endpoint a cui si effettua la chiamata.

I parametri obbligatori sono **model** e **name** (o **instanceId**).

# Interfaccia
- ENDPOINT BINARIO: `http(s)://<url-bpm-web>/api/ext/downloaddocument`
- ENDPOINT JSON: `http(s)://<url-bpm-web>/api/ext/downloaddocumentjson`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione,
>
> &nbsp;&nbsp;&nbsp; "model": "modello",
> &nbsp;&nbsp;&nbsp; "name": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "version": versione-documento
> }
{.is-info}

### Parametri

#### Version
E' possibile indicare la versione del documento se supportata dalla classe documentale.
Non specificandola o valorizzandola con 0 verrà restituita il documento attivo.

## Risposta
In base alla chiamata può essere restituito il documento in formato binario, che potrà essere scaricato, oppure un json con le informazioni del documento e il file in formato base64.

