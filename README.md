# 🎾 App Torneo Mini Tennis (Vanilla JS Edition)

Questa Web App mobile-first (PWA) è progettata per gestire tornei di mini-tennis tra amici. In base ai requisiti stringenti, l'app è costruita interamente in **Vanilla JavaScript**, **CSS inline** e HTML in un **singolo file `index.html` autonomo**, senza alcun framework o libreria esterna.

Funziona al 100% offline grazie al Service Worker integrato.

## 🌟 Funzionalità Avanzate

1. **Gestione dei Bye (Riposi)**
   - Algoritmo del "Poligono" per generare i turni di gioco (girone all'italiana).
   - In caso di numero dispari di giocatori, l'app inserisce automaticamente un "BYE", assicurando che ogni giocatore riposi esattamente una volta per girone in modo equo.

2. **Andata e Ritorno**
   - Possibilità di duplicare e invertire le partite per fare gironi più lunghi.

3. **Determinismo della Classifica**
   - **Criterio 1**: Vittorie.
   - **Criterio 2**: Scontro diretto (solo se la parità coinvolge ESATTAMENTE due giocatori e si sono già affrontati).
   - **Criterio 3**: Differenza Punti totale (PF - PS).
   - **Criterio 4**: Punti Fatti totali.
   - **Criterio 5**: Ordine alfabetico.

4. **Offline & Robustezza Dati**
   - Salvataggio continuo nel `localStorage`.
   - **Schema Versioning**: Rileva se i vecchi dati sono incompatibili con l'algoritmo corrente per prevenire crash.
   - **Export / Import JSON**: Scarica e condividi i dati del torneo per backup o per passarli su un altro dispositivo.

5. **UX da Bordo Campo**
   - Evidenziazione dinamica ("Prossima!") della prima partita da giocare per non dover scorrere tutto il calendario.
   - Protezione da sovrascrittura accidentale dei punteggi.
   - Feedback aptico (vibrazione) al salvataggio (se supportato dal dispositivo).
   - **Modalità "Sole Fortissimo" (Alto Contrasto)**: Un toggle che rimuove i fronzoli estetici (sfondo del campo in erba) in favore di un estremo contrasto B/N perfetto per il sole diretto di mezzogiorno.
   - **Condivisione Natiiva**: Sfrutta la Web Share API per inviare al volo la classifica via WhatsApp/Telegram.

6. **Statistiche Globali**
   - Analisi di tutto l'archivio dei tornei storici per eleggere il vincitore assoluto di più tornei e il detentore del maggior numero di singole vittorie.

## 🛠 Come usare l'app
Essendo l'app racchiusa in un singolo file HTML autonomo:
1. Doppio clicca su `index.html` (o usa un qualsiasi live server).
2. Tutto il codice, CSS e logica risiedono lì.
3. Se servita tramite protocollo HTTP/HTTPS, l'app si installerà come PWA e il file `sw.js` ne garantirà l'uso perpetuo senza internet.
