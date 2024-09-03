# Caricamento di un Allegato
La chiamata inseriesce un nuovo allegato oppure aggiorna un allegato già esistente. 
(la chiave dell'allegato è composta da *filename*, *root*, *path*, *revision*)

I parametri obbligatori sono molteplici:
- **model** e **documentName** (o **instanceId**): per identificare il modello
- **fileName** e **content**: per il file e il suo contenuto
- **root**: destinazione dell'allegato

# Interfaccia
- ENDPOINT: `http(s)://<url-bpm-web>/api/ext/uploadattachment`
- METODO: `POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione
>
> &nbsp;&nbsp;&nbsp; "model": "modello",
> &nbsp;&nbsp;&nbsp; "documentName": "nome-univoco-processo",
> &nbsp;&nbsp;&nbsp; "instanceId": "codice-univoco-processo",
> &nbsp;&nbsp;&nbsp; "fileName": "nome-file",
> &nbsp;&nbsp;&nbsp; "fileDescription": "descrizione-file",
> &nbsp;&nbsp;&nbsp; "content": "valore-base64-file"
> &nbsp;&nbsp;&nbsp; "root": "nome-cartella-allegati",
> &nbsp;&nbsp;&nbsp; "path": "percorso-file-allegati",
> &nbsp;&nbsp;&nbsp; "group": "valore-gruppo-file",
> &nbsp;&nbsp;&nbsp; "type": "valore-tipo-file",
> &nbsp;&nbsp;&nbsp; "revision": "valore-revisione-file",
> &nbsp;&nbsp;&nbsp; "state": "valore-stato-file",
> &nbsp;&nbsp;&nbsp; "variables": { ... }
> }
{.is-info}

#### Variables
In questo caso le variabili fanno riferimento alle **variabili dell'allegato**
> {
> &nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; "gruppo":
> &nbsp;&nbsp;&nbsp; {
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "nome": "valore"
> &nbsp;&nbsp;&nbsp; }
> }

#### State
> (vuoto) - Allegato attivo ed editabile
> A - Allegato approvato e non editabile
> O - Allegato obsoleto e non editabile

## Risposta
> {
> &nbsp;&nbsp;&nbsp; "result": "true / false in base al risultato"
> &nbsp;&nbsp;&nbsp; "message": "messaggio in caso di errore"
> }
{.is-info}
