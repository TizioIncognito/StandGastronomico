# Configurazione delle categorie

Stand Gastronomico permette di personalizzare le etichette delle categorie senza modificare il programma.

Le impostazioni si trovano nella cartella `Config` dell'applicazione. Dopo una modifica, chiudi e riapri il programma per applicare le nuove etichette.

## File `Config/categories.json`

Le categorie sono sempre cinque e il loro ordine non cambia. Il file modifica soltanto il nome mostrato: non crea, elimina, sposta o nasconde categorie.

Le chiavi indicano la posizione della categoria, non il tipo di cibo:

```json
{
  "cat1": "Pizzeria",
  "cat2": "Bomboloni",
  "cat3": "Primi",
  "cat4": "Secondi",
  "cat5": "Griglia"
}
```

| Chiave | Categoria predefinita |
|---|---|
| `cat1` | Bar |
| `cat2` | Primi |
| `cat3` | Secondi |
| `cat4` | Fritti |
| `cat5` | Griglia |

## Regole da rispettare

- Usa esattamente le cinque chiavi `cat1`, `cat2`, `cat3`, `cat4` e `cat5`.
- Ogni etichetta deve essere diversa dalle altre, non vuota e lunga al massimo 40 caratteri.
- Gli spazi iniziali e finali vengono ignorati; i caratteri `{` e `}` non sono ammessi.
- Se il file manca, l'applicazione usa le etichette predefinite.
- Se il file contiene un errore, all'avvio viene mostrato un avviso e vengono usate le etichette predefinite.

Le etichette scelte compaiono nel Listino, nella Cassa e nelle intestazioni di stampa. Se una categoria non serve, lasciala senza prodotti: rimane comunque disponibile nel Listino.

Per modificare la stampa degli ordini, consulta [Personalizzazione dei template di stampa](TEMPLATE_STAMPA.md).
