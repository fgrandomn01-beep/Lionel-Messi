# MESSI · Criteri di progettazione del progetto

Autori: Filippo Girolami e Alex Amadio.
Framework recepito il 9 ottobre 2026, fuso di riferimento UTC+2.

## Regole condivise
- Una CTA dominante per contesto. Azioni secondarie subordinate.
- Pattern di navigazione familiari, etichette concrete, nessun gergo tecnico nei flussi.
- Informazioni correlate vicine e gruppi diversi separati chiaramente.
- Informazioni complesse mostrate progressivamente; gruppi di massimo 5–7 elementi.
- Scala di spaziatura: 8, 16, 24, 32, 48, 64, 96 px.
- Scala dei titoli basata sul rapporto 1,25; corpo di lettura minimo 16 px, interlinea 1,5–1,6.
- Contrasto del testo normale almeno 4,5:1; testo grande almeno 3:1.
- Palette con fondo dominante, superfici/testi secondari e accento funzionale. Obiettivo compositivo 60–30–10.
- Spazio negativo significativo; obiettivo compositivo 30–40%, da giudicare anche sul contenuto reale.
- Stato del sistema comunicato subito; obiettivo di feedback locale entro 100 ms.
- Default, hover, pressed, focus, disabled, loading, success, error definiti quando pertinenti.
- Chiudere i dialoghi facilmente, supportare Escape e ripristinare il focus.
- Contenuti accessibili da tastiera e con tecnologie assistive.
- Zoom, ridistribuzione del testo e preferenze di movimento rispettati.
- Le fotografie devono essere autentiche e associate al soggetto, periodo e momento corretto.
- Il glassmorphism conserva una base scura leggibile e un fallback senza blur.

## Desktop, sopra 1024 px
- Layout a 12 colonne, allineamenti coerenti, navigazione estesa.
- Apertura progettata per mostrare messaggio e azione principale entro 700 px.
- Spaziature multiple di 8 px; testo con lunghezza di riga controllata.
- Ogni controllo cliccabile ha feedback al passaggio del mouse.

## Smartphone e tablet, fino a 1024 px
- Colonna unica, inclusi i gruppi secondari; margini laterali di 24 px.
- Nessuno scorrimento orizzontale richiesto per leggere i contenuti.
- Target di tocco del progetto almeno 48×48 px, separati da almeno 8 px.
- Navigazione compatta e azione inferiore nella zona del pollice.
- Apertura progettata per mostrare messaggio e prima azione entro 600 px.
- Le foto hanno il proprio blocco; i testi non dipendono dalla leggibilità sopra una foto.
- Moduli, se introdotti: una colonna, label sopra il campo, errori descrittivi, prevenzione invii incompleti.

## Verifica
I criteri non equivalgono a una certificazione automatica. I controlli CSS e DOM sono documentati nel README. La verifica visiva su browser reali, lo zoom reale e la valutazione completa WCAG richiedono un ambiente di test disponibile. Eventuali limiti di verifica vanno dichiarati senza trasformarli in risultati superati.
