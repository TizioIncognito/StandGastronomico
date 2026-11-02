# Personalizzazione dei template di stampa

La stampa degli ordini può essere personalizzata intervenendo sui file della cartella `Config/Print` dell'applicazione:

- `OrderPrint.html` definisce struttura e testi della stampa;
- `OrderPrint.css` definisce l'aspetto grafico.

I file vengono riletti a ogni stampa: dopo averli salvati, non è necessario riavviare o ricompilare il programma. Il documento di stampa è locale e autosufficiente; non usa Internet, font remoti o script.

Prima di modificare i file, fanne una copia di sicurezza. Mantieni i segnaposto e gli elementi obbligatori descritti sotto: servono al programma per inserire i dati dell'ordine.

## Segnaposto disponibili

| Segnaposto | Significato |
|---|---|
| `{{ORDER_NUMBER}}` | Numero dell'ordine |
| `{{TIME}}` | Orario di salvataggio |
| `{{CUSTOMER_NAME}}` | Nome del cliente |
| `{{TOTAL}}` | Totale dell'ordine |
| `{{CSS}}` | Foglio di stile incorporato |
| `{{PAGE_CLASS}}` | `compact` per ordini con oltre 12 righe; altrimenti vuoto |
| `{{CATEGORY_1}}` … `{{CATEGORY_5}}` | Etichetta corrente della prima…quinta categoria |
| `{{DESCRIPTION}}`, `{{QUANTITY}}`, `{{UNIT_PRICE}}`, `{{SUBTOTAL}}` | Celle dei modelli di riga |

## Sezioni delle categorie

Ogni sezione di stampa è riconosciuta dalla chiave della categoria, non dall'etichetta visualizzata. Per esempio:

```html
<tbody data-print-category="cat2"></tbody>
```

Le chiavi sono le stesse di `categories.json`, da `cat1` a `cat5`. Se cambi il nome mostrato della categoria, non devi modificare la chiave del template. Puoi usare anche il segnaposto corrispondente nell'intestazione:

```html
<h2>{{CATEGORY_2}} - Ordine n. {{ORDER_NUMBER}}</h2>
```

Puoi mantenere solo le sezioni necessarie al tuo stand. Le righe delle categorie senza una sezione dedicata restano comunque nel riepilogo iniziale. Nel template predefinito `cat1` compare solo nel riepilogo; per aggiungere una sezione dedicata, inserisci un elemento con `data-print-category="cat1"` e la relativa intestazione.

## Elementi obbligatori

Non rimuovere questi elementi dall'HTML:

- il contenitore del riepilogo `data-print-rows="summary"`;
- il blocco `<template id="summary-row">`;
- il blocco `<template id="section-row">`.

Il programma usa questi elementi per ripetere le righe dell'ordine. Dopo ogni modifica, esegui una stampa di prova e controlla che riepilogo, categorie e totale siano presenti e leggibili.
