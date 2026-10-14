# Dashboard ordini materiale d'ufficio

Dashboard single-file (HTML + JavaScript, nessun backend) per monitorare gli ordini di materiale d'ufficio e di consumo per punto vendita, a partire dalle conferme d'ordine in PDF.

> **Versione dimostrativa:** nomi dei punti vendita, ordini, prezzi e indirizzi sono tutti **fittizi**.

## Funzioni
- Semaforo per punto vendita in base ai giorni dall'ultimo ordine (soglie configurabili)
- Dettaglio per PV: spesa mensile, spesa per categoria, prodotti acquistati, storico ordini
- Import dei PDF di conferma d'ordine (estrazione con PDF.js, tutto in locale nel browser)
- Esportazione/importazione backup JSON ed export CSV

## Uso
Apri `index.html` nel browser (oppure pubblicalo con GitHub Pages). Al primo avvio vengono caricati dati dimostrativi; con **Svuota archivio** si parte da zero e con **Carica dati demo** si ripristinano.

I dati restano nel `localStorage` del browser: nulla viene inviato a server. Unica dipendenza esterna: PDF.js da cdnjs.

## Personalizzazione
Modifica l'array `PV_LIST` in `index.html` con i tuoi punti vendita.
