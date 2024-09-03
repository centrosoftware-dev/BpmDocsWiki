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
```
{
  autenticazione

  "model": "modello",
  "documentName": "nome-univoco-processo",
  "instanceId": "codice-univoco-processo",
  "fileName": "nome-file",
  "fileDescription": "descrizione-file",
  "content": "valore-base64-file"
  "root": "nome-cartella-allegati",
  "path": "percorso-file-allegati",
  "group": "valore-gruppo-file",
  "type": "valore-tipo-file",
  "revision": "valore-revisione-file",
  "state": "valore-stato-file",
  "variables": { ... }
}
```

#### Variables
In questo caso le variabili fanno riferimento alle **variabili dell'allegato**
```
{
  "nome": "valore"
  "gruppo": {
    "nome": "valore"
  }
}
```

#### State
- (vuoto) - Allegato attivo ed editabile
- A - Allegato approvato e non editabile
- O - Allegato obsoleto e non editabile

## Risposta
```
{
  "result": "true / false in base al risultato"
  "message": "messaggio in caso di errore"
}
```
