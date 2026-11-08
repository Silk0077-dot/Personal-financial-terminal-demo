# Terminale finanziario

Un terminale finanziario personale in stile professionale che gira in locale, nel browser. In un'unica schermata scura e densa riunisce quotazioni, grafici, analisi tecnica e fondamentale, notizie, portafoglio titoli e bilancio personale.

> 🔒 **Il codice sorgente è in un repository privato.** Questa pagina è una vetrina del progetto. Se vuoi vedere il codice, scrivimi e ti do accesso.

![Home](screenshot/home.png)

_Tutti gli screenshot usano dati di prova._

## In breve

- **Zero dipendenze**: server in Python 3 con la sola libreria standard e interfaccia in un singolo file HTML con JavaScript puro. I grafici sono disegnati a mano su `<canvas>`, senza librerie esterne.
- **Circa 4.500 righe** fra backend (Python) e frontend (HTML/CSS/JS).
- **Privacy prima di tutto**: il server ascolta solo su `127.0.0.1`. Portafoglio, spese e chiavi restano in file locali, e i file Excel dell'utente sono letti in sola lettura.
- **Fonte dati intercambiabile**: il terminale non è legato a un fornitore. Un piccolo connettore (`fonte.py`) collega qualsiasi API di mercato.
- **Funziona anche offline**: ogni risposta viene salvata su disco e riusata senza rete, con una barra che indica la data dei dati.

## Funzionalità

| Tasto | Pagina | Cosa fa |
|---|---|---|
| **F1** | Home | Patrimonio netto, mese in corso con budget, obiettivi di risparmio, avvisi, prossimi eventi, heatmap di mercati e watchlist |
| **F2** | Entrate & Uscite | Spese per categoria, andamento mensile, budget, confronto con l'anno precedente, obiettivi di risparmio e proiezione del patrimonio a più scenari |
| **F3** | Portafoglio | Posizioni riprezzate in tempo reale, P&L, rendimento time-weighted e money-weighted (XIRR), confronto con un indice, allocazione, ribilanciamento, dividendi e cedole, simulazione delle tasse di vendita, zainetto fiscale |
| **F4** | Notizie | Notizie di mercato e del titolo selezionato |
| **F5** | Agenda | Avvisi di prezzo con notifiche, calendario macro (BCE, Fed, inflazione), prossimi dividendi |
| **F6** | Mercato | Watchlist (lista o heatmap), grafico a candele, confronto fra due titoli, analisi tecnica, monitor di indici, valute, materie prime, cripto e tassi |
| **F7** | Fondamentali | Punteggio fondamentale 0–10 su cinque aree, valore di Graham, raccomandazioni degli analisti, bilanci, storico prezzi con export CSV |

![Mercato](screenshot/mercato.png)
![Fondamentali](screenshot/fondamentali.png)
![Portafoglio](screenshot/portafoglio.png)
![Entrate e uscite](screenshot/entrate_uscite.png)

## Aspetti tecnici

- **Backend**: `http.server` multithread con API JSON, cache in memoria con scadenza, cache persistente su disco per l'uso offline, limitazione delle richieste verso il fornitore (circa 5–10 al minuto), spegnimento automatico dopo inattività.
- **Dati**: lettura di file Excel (`.xlsx`) con il parser XML della libreria standard, salvataggi JSON atomici (file temporaneo e `fsync`) con recupero automatico dei file danneggiati.
- **Finanza**: TWR e XIRR calcolati da zero, ricostruzione storica del portafoglio dai movimenti, calendario delle cedole obbligazionarie, tassazione italiana (26% e 12,5%) e scadenza delle minusvalenze.
- **Frontend**: interfaccia guidata da tastiera (tasti funzione e riga di comando), grafici a candele, ad area e a ciambella su canvas, layout responsive, tema scuro ad alto contrasto.
- **Analisi**: indicatori tecnici (RSI, MACD, stocastico, ADX, medie mobili, Bollinger) e punteggio fondamentale basato su multipli, redditività, crescita, solidità e dividendo.

## Stack

Python 3 · HTML · CSS · JavaScript (vanilla) · Canvas API

---

Progetto personale. Non è consulenza finanziaria e non è affiliato ad alcun fornitore di dati.

<details>
<summary>🇬🇧 English summary</summary>

A personal, Bloomberg-style financial terminal that runs locally in the browser. Built with a dependency-free Python 3 standard-library server and a single vanilla-JS HTML front end with hand-drawn canvas charts (~4,500 lines). It covers live quotes, candlestick charts, technical and fundamental analysis with analyst consensus, news, a portfolio tracker (TWR/XIRR, benchmark comparison, rebalancing, dividends, bond coupons, Italian tax handling), and personal budgeting with savings goals and net-worth projection. Data providers are pluggable through a small connector module, and everything stays on the user's machine (localhost only, read-only Excel input, offline disk cache).

**The source code is private: contact me for access.**
</details>
