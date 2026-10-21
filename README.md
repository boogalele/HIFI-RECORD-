[README.md](https://github.com/user-attachments/files/33763066/README.md)
# HIFI TOOL

Interfaccia mobile-first per l’identificazione e la valutazione preliminare di vinili usati per HI-FI RECORDS PADOVA.

## Stato reale del progetto

`index.html` è un prototipo frontend statico. Fotografie, barcode/codici manuali e controlli fotocamera sono interfaccia di acquisizione; **non identificano automaticamente un’edizione e non interrogano Discogs o altre fonti live**. Il risultato della scansione resta quindi “Non stimabile / APPROFONDIRE” finché non vengono collegati un servizio di identificazione e dati di mercato verificabili. Il banco prova usa esclusivamente valori inseriti manualmente ed è etichettato “NON LIVE”.

## Metodo di valutazione fissato

1. **Identificare l’edizione esatta**: artista, titolo, etichetta, numero di catalogo, paese/anno, formato e matrice/runout quando disponibile. Una corrispondenza incompleta deve essere segnalata, non presentata come certa.
2. **Separare condizioni e edizioni**: confrontare VG+, NM e altre condizioni solo con vendite comparabili della stessa edizione; non mescolare ristampe o varianti diverse.
3. **Usare le vendite concluse come prova principale del valore**. Riportare periodo, numero di vendite e distribuzione dei prezzi (minimo, mediana, massimo) quando disponibili. La mediana è preferibile a una singola vendita estrema.
4. **Trattare le inserzioni attive come concorrenza, non come vendite**. La disponibilità di più copie comparabili a un prezzo inferiore è un limite pratico alla stima suggeribile, salvo vendite concluse che dimostrino un premio per una specifica variante. Non usare il prezzo richiesto come prova autonoma del valore.
5. **Valutare la liquidità separatamente**: frequenza delle vendite e recenza dell’ultima vendita aiutano a stimare la velocità di realizzo. Non confondere prezzo alto con facilità di vendita.
6. **Want/Have e interesse collezionistico/DJ sono indicatori di contesto**: non generano automaticamente un sovrapprezzo.
7. **Tenere distinta la valutazione di mercato dal prezzo d’acquisto**. Il prezzo massimo d’acquisto si calcola solo quando valore atteso, costi, margine obiettivo e rischio/rotazione sono espliciti. Non applicare un 40% fisso del VG+, un minimo arbitrario di €10 o soglie automatiche di premio.
8. **Decisione prudente**: `ACQUISTARE` solo quando identità, vendite comparabili, condizione e margine sono sufficientemente documentati; `APPROFONDIRE` quando mancano prove o c’è ambiguità; `NON CONVIENE` quando il prezzo richiesto supera il massimo economicamente sostenibile. Se i dati non bastano, mostrare “Non stimabile”, non inventare un prezzo.
9. **Dati tracciabili**: ogni valutazione reale deve conservare fonte, data di consultazione, mercato/valuta, condizione e criteri di selezione. Europa e USA vanno separati; eventuali conversioni di valuta devono indicare il cambio usato.

## Banco prova

Il banco prova consente di controllare la logica con dati manuali. Non è una fonte di mercato. La stima base viene dalle vendite concluse comparabili VG+; se non sono disponibili, il valore resta non stimabile. Il prezzo minimo delle inserzioni può limitare prudenzialmente la stima solo quando sono presenti più copie comparabili. Il prezzo d’acquisto indicativo è calcolato separatamente con margine e costi inseriti dall’utente.

Le soglie di liquidità nel banco prova sono indicatori operativi provvisori, non verità statistiche universali. Prima dell’uso commerciale vanno validate su un campione storico di dischi effettivamente acquistati e rivenduti.

## Funzioni del prototipo

- Selezione di una o più foto e acquisizione tramite fotocamera, dove supportata.
- Controlli zoom 0,5×/1× e torcia, se esposti dal dispositivo/browser. Il valore 0,5× è richiesto come impostazione predefinita ma non tutti i browser consentono di selezionare fisicamente il grandangolo.
- Inserimento facoltativo di codice catalogo, matrice e altri identificativi.
- Schermata risultato con stato esplicitamente preliminare quando non esistono dati verificati.
- Banco prova manuale.

Cronologia e impostazioni non costituiscono ancora un sistema persistente completo.

## Architettura necessaria per la versione reale

- Frontend statico ospitato su GitHub Pages.
- Backend/serverless per gestire credenziali e richieste alle API, senza inserire token segreti nel browser o nel repository.
- Servizio di identificazione dell’edizione e normalizzazione dei dati.
- Adattatori per fonti di mercato autorizzate, con rispetto di termini, limiti e licenze delle API. Non presumere che lo storico vendite sia accessibile tramite qualsiasi API.
- Motore di regole separato dall’interfaccia, con test automatici per edizioni ambigue, assenza di vendite, prezzi attivi inferiori, vendite estreme, valute e condizioni differenti.

## Pubblicazione GitHub Pages

Nel repository `boogalele/HIFI-RECORD-`, sostituire il contenuto di `index.html` con il file `index.html` fornito e il contenuto di `README.md` con questo file. Mantenere GitHub Pages configurato sulla branch `main`, cartella `/ (root)`. Dopo il commit, attendere la pubblicazione e verificare l’app in una finestra privata o con cache aggiornata.

**Avvertenza:** questa versione migliora la logica del banco prova e rende espliciti i limiti, ma non equivale ancora a un servizio live di quotazione.
