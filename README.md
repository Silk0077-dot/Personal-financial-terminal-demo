# Terminale finanziario

Un terminale finanziario personale in stile professionale che gira in locale, nel browser. In un'unica schermata scura e densa riunisce quotazioni, grafici, analisi tecnica e fondamentale, notizie dal mondo con mappamondo interattivo, portafoglio titoli e bilancio personale.

> 🔒 **Il codice sorgente è in un repository privato.** Questa pagina è una vetrina del progetto. Se vuoi vedere il codice, scrivimi e ti do accesso.

![Home](screenshot/home.png)

_Tutti gli screenshot usano dati di prova inventati: nessun dato personale e nessun prezzo reale._

## In breve

- **Zero dipendenze**: server in Python 3 con la sola libreria standard e interfaccia in un singolo file HTML con JavaScript puro. Grafici, mappamondo e ciambelle sono disegnati a mano su `<canvas>`, senza librerie esterne.
- **Oltre 5.000 righe** fra backend (Python) e frontend (HTML/CSS/JS), sette pagine e più di 40 riquadri.
- **Privacy prima di tutto**: il server ascolta solo su `127.0.0.1`. Portafoglio, spese e chiavi restano in file locali, e i file Excel dell'utente sono letti in sola lettura.
- **Fonte dati intercambiabile**: il terminale non è legato a un fornitore. Un piccolo connettore (`fonte.py`) collega qualsiasi API di mercato; le funzioni che l'API non offre vengono semplicemente segnalate come non disponibili.
- **Funziona anche offline**: ogni risposta viene salvata su disco e riusata senza rete, con una barra che indica la data dei dati.

## Pagine

| Tasto | Pagina | Cosa fa |
|---|---|---|
| **F1** | Home | Patrimonio netto con grafico nel tempo, mese in corso con budget, obiettivi di risparmio, avvisi di prezzo, prossimi eventi (macro, dividendi, cedole), heatmap di mercati e watchlist |
| **F2** | Entrate & Uscite | Entrate e spese per categoria e sotto categoria, tasso di risparmio, budget mensili con indicatore di ritmo, confronto con l'anno precedente, obiettivi di risparmio, proiezione del patrimonio a tre scenari, andamento e riepilogo mensile con filtri, operazioni modificabili |
| **F3** | Portafoglio | Posizioni riprezzate in tempo reale, P&L realizzato e non realizzato anche per anno, allocazione per strumento, area, settore e valuta, storico del valore con confronto con un indice, rendimento TWR e MWR, ribilanciamento, dividendi e cedole, simulazione delle tasse di vendita, zainetto fiscale |
| **F4** | Notizie | Mappamondo interattivo con gli indici, regioni (Globale, Stati Uniti, Europa, Asia-Pacifico), variazioni per periodo, migliori e peggiori titoli, indici, valute e materie prime della regione, notizie su tre livelli |
| **F5** | Agenda | Avvisi di prezzo con notifiche, calendario macro (BCE, Fed, inflazione), prossimi dividendi e cedole con importi lordi e netti |
| **F6** | Mercato | Watchlist (lista o heatmap), grafico a candele o a linea, confronto fra due titoli, analisi tecnica, descrizione e composizione degli ETF, fondamentali in breve, monitor dei mercati |
| **F7** | Fondamentali | Punteggio fondamentale 0–10 su cinque aree, valore di Graham, consenso e storico dei giudizi degli analisti, bilanci, dividendi per anno, storico prezzi con export CSV |

### F1 · Home

- **Patrimonio netto** con grafico a 3M / 6M / YTD / 1A / 5A: il passato è ricostruito dai movimenti del portafoglio, da oggi in poi il valore reale viene salvato ogni giorno.
- Mese in corso: entrate, spese, differenza, risparmio medio e barre dei budget.
- Avanzamento degli obiettivi di risparmio, con la cifra mensile che serve per arrivarci in tempo.
- Avvisi di prezzo, prossimi eventi macro, dividendi e cedole, heatmap di indici, valute, materie prime e watchlist.

### F2 · Entrate & Uscite

![Entrate e uscite](screenshot/entrate_uscite.png)

- Riepilogo del periodo scelto (mese, anno o date libere): entrate, spese, differenza, tasso di risparmio, quota investita.
- Spese per categoria e per sotto categoria con barre proporzionali.
- **Budget mensili** per categoria, sotto categoria o totale, colorati in base alla soglia, con una linea che mostra il ritmo di spesa atteso per quel giorno del mese.
- Confronto con lo stesso periodo dell'anno precedente.
- **Obiettivi di risparmio** (su risparmio, su una voce o sul patrimonio netto) con data di scadenza.
- **Proiezione del patrimonio netto** a 5, 10 e 20 anni con tre scenari di rendimento e nota sull'inflazione.
- Andamento mensile e riepilogo per mese filtrabili per anno e categoria; elenco delle operazioni modificabile e aggiunta manuale di entrate e uscite.

### F3 · Portafoglio

![Portafoglio](screenshot/portafoglio.png)

- Posizioni lette dall'Excel del broker e **riprezzate in tempo reale**, con P&L in euro e percentuale, peso e scorciatoie per aprire grafico, notizie e fondamentali.
- Liquidità e voci del patrimonio modificabili direttamente dalla pagina, senza toccare l'Excel.
- **Allocazione** in quattro ciambelle: tipo di strumento, area geografica, settore e valuta.
- **Storico del valore** su più periodi o date libere, confrontabile con un indice.
- **P&L** da sempre e per anno, realizzato e non realizzato.
- **Rendimento vero del periodo**: time-weighted (TWR) e money-weighted (MWR/XIRR), calcolati da zero.
- Acquisti e vendite registrabili e annullabili, **simulazione di vendita** con tasse stimate (26% e 12,5%).
- **Ribilanciamento** verso pesi obiettivo, anche con soli acquisti.
- Dividendi e cedole incassati e attesi, obbligazioni con calendario delle cedole, **zainetto fiscale** con la scadenza delle minusvalenze.

### F4 · Notizie

![Notizie](screenshot/notizie.png)

- **Mappamondo interattivo** disegnato su canvas: si trascina, si fa lo zoom e funziona offline. Le etichette degli indici mostrano la variazione e aprono grafico e notizie.
- Quattro regioni (Globale, Stati Uniti, Europa, Asia-Pacifico), ognuna con i propri indici, coppie di valute e materie prime.
- **Variazione per periodo** (1G, 1S, 1M, 3M, 6M, YTD, 1A) per tutti i riquadri.
- **Migliori e peggiori**: i titoli delle grandi società della regione che salgono o scendono di più nel periodo scelto.
- Notizie su tre livelli: mercati della regione, titolo selezionato e titoli della watchlist, con ricerca e filtro.

### F5 · Agenda

![Agenda](screenshot/agenda.png)

- **Avvisi di prezzo** (sopra o sotto una soglia) controllati in background, con notifica a schermo e distanza dalla soglia.
- **Calendario macro**: riunioni BCE e Fed, inflazione USA e area euro, con il conto alla rovescia.
- **Prossimi dividendi e cedole** dei prossimi 12 mesi, con importi lordi e netti stimati.

### F6 · Mercato

![Mercato](screenshot/mercato.png)

- Watchlist in lista o **heatmap**, con ritardo del dato (tempo reale o 15 minuti) per ogni titolo.
- Testata con prezzo, variazione, massimo, minimo, volume e freschezza dell'ultimo scambio.
- **Grafico** a candele o a linea da 1 giorno a 5 anni o su date libere, con **tooltip al passaggio del mouse**, volumi e confronto in percentuale con un secondo titolo.
- **Analisi tecnica** su più intervalli (15m, 1h, 4h, 1g, 1s): giudizio complessivo, medie mobili e oscillatori, RSI, MACD, stocastico, ADX, CCI, ATR, Bollinger.
- **Descrizione** del titolo e, per ETF, fondi e indici, **composizione**: tipo di attività, paesi, settori e prime 10 partecipazioni, con ISIN, costi e tipo di replica.
- Fondamentali e giudizio degli analisti in breve per le azioni.
- Monitor di indici, valute, materie prime, cripto e tassi, più un nastro scorrevole in alto.

![Composizione di un ETF](screenshot/composizione.png)

### F7 · Fondamentali

![Fondamentali](screenshot/fondamentali.png)

- **Punteggio fondamentale 0–10** su cinque aree (valutazione, redditività, crescita, solidità, dividendo) con semafori per ogni indicatore e **valore di Graham**.
- **Raccomandazioni degli analisti**: giudizio medio, prezzi obiettivo minimo, medio e massimo, andamento dei giudizi negli ultimi mesi e ultimi cambi di giudizio.
- Valutazione, redditività e crescita, solidità finanziaria, dividendi e utili, dati di mercato, profilo.
- Bilanci annuali, dividendi per anno e storico prezzi con export CSV.

## Interfaccia

- **Guidata da tastiera**: tasti funzione per le pagine e una riga di comando (`/`) per aprire titoli, gestire la watchlist, cambiare intervallo, registrare operazioni e creare avvisi (es. `AVVISO ENI.MI < 13`, `VS AAPL`).
- **Sezioni riducibili**: ogni riquadro si chiude con una freccia e la scelta viene ricordata.
- Tooltip sui grafici, orologi delle principali borse, avviso quando il server acceso è più vecchio della pagina.
- Spegnimento automatico dopo un periodo di inattività configurabile.

## Aspetti tecnici

- **Backend**: `http.server` multithread con API JSON, cache in memoria con scadenza, cache persistente su disco per l'uso offline, limitazione delle richieste verso il fornitore, elaborazioni in parallelo con un pool di thread.
- **Dati**: lettura di file Excel (`.xlsx`) con il parser XML della libreria standard, salvataggi JSON atomici (file temporaneo e `fsync`) con recupero automatico dei file danneggiati.
- **Finanza**: TWR e XIRR calcolati da zero, ricostruzione storica del portafoglio e del patrimonio dai movimenti, variazioni per periodo, calendario delle cedole obbligazionarie, tassazione italiana (26% e 12,5%) e scadenza delle minusvalenze.
- **Frontend**: grafici a candele, ad area, a barre e a ciambella e mappamondo ortografico con rotazione e zoom, tutti su canvas; layout a griglia responsive; tema scuro ad alto contrasto.
- **Analisi**: indicatori tecnici calcolati in locale e punteggio fondamentale basato su multipli, redditività, crescita, solidità e dividendo.

## Stack

Python 3 · HTML · CSS · JavaScript (vanilla) · Canvas API

---

Progetto personale. Non è consulenza finanziaria e non è affiliato ad alcun fornitore di dati.

<details>
<summary>🇬🇧 English summary</summary>

A personal, Bloomberg-style financial terminal that runs locally in the browser. Built with a dependency-free Python 3 standard-library server and a single vanilla-JS HTML front end with hand-drawn canvas charts and an interactive globe (5,000+ lines). Seven keyboard-driven pages cover: a home dashboard with a net-worth chart; personal budgeting with monthly budgets, savings goals and net-worth projection; a portfolio tracker (live repricing, allocation, TWR/XIRR, benchmark comparison, rebalancing, dividends, bond coupons, Italian tax handling); world news with an interactive globe, regional markets, multi-period performance and top gainers/losers; an agenda with price alerts and the macro calendar; a market page with candlestick charts, hover tooltips, technical analysis and ETF composition; and fundamental analysis with a 0–10 score, Graham value and analyst consensus. Data providers are pluggable through a small connector module, and everything stays on the user's machine (localhost only, read-only Excel input, offline disk cache).

**The source code is private: contact me for access.**
</details>
