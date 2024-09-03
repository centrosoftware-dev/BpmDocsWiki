# Lista Modelli
La chiamata è utilizzata per ottenere la lista di tutte i modelli di processo o le classi documentali.

Non ci sono parametri obbligatori da passare nel corpo della chiamata.

# Interfaccia
- ENDPOINT MODELLI DI PROCESSO: `http(s)://<url-bpm-web>/api/ext/processmodels`
- ENDPOINT CLASSI DOCUMENTALI: `http(s)://<url-bpm-web>/api/ext/documentsets`
- METODO:	`POST`

## Corpo
> {
> &nbsp;&nbsp;&nbsp; autenticazione
> }
{.is-info}

## Risposta
Verrà restituito una lista con nome e descrizione di tutti i modelli di processo o delle classi documentali.

> {
> &nbsp;&nbsp;&nbsp; "nome": "nome-processo"
> &nbsp;&nbsp;&nbsp; "descrizione": "descrizione-processo"
> }
{.is-info}
