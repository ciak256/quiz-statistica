# Quiz Pegaso — Preparazione Esami

Sito unico di autoesercitazione a risposta multipla (4 opzioni) per più esami universitari Pegaso. È un **unico file HTML autonomo**: nessuna installazione, nessun server, funziona anche solo aprendolo nel browser.

## Materie incluse

| Materia | Domande teoriche | Esercizi infiniti generati |
|---|---|---|
| 📊 Statistica | 49 | ✅ calcolo (12 modelli: media, mediana, probabilità, z-score, regressione, IC...) |
| 🏢 Economia Aziendale | 36 | ✅ definizioni (40 termini, generate con distrattori casuali) |
| ⚖️ Diritto Privato | 35 | ✅ definizioni (41 termini) |
| 📈 Economia Politica | 34 | ✅ definizioni (40 termini) |
| 📜 Storia Economica | 33 | ✅ definizioni (40 termini) |
| 🏛️ Teoria e Governo dell'Impresa | 33 | ✅ definizioni (40 termini) |

Per ogni materia, dalla home si sceglie la modalità: test completo, prova rapida (15 domande), esercizi infiniti (generati al volo, senza mai finire) oppure una sessione mista infinita che alterna banca fissa ed esercizi generati. Un pulsante "Termina e vedi il punteggio" permette di chiudere la sessione infinita quando si vuole.

Per Statistica il generatore crea veri calcoli con numeri casuali ogni volta (media, varianza, probabilità, punteggio z, regressione, intervalli di confidenza...). Per le altre 5 materie il generatore pesca un concetto da un glossario di 33-41 termini chiave e costruisce la domanda (in una delle due direzioni: "cosa significa questo termine?" oppure "a quale termine corrisponde questa definizione?") con 3 distrattori casuali presi dallo stesso glossario: la combinazione di termine, direzione e distrattori cambia ad ogni domanda, dando una quantità molto elevata di combinazioni diverse pur partendo da un insieme di concetti finito (esattamente come càpita ripassando un vero esame).

## Come metterlo online con un link GitHub (GitHub Pages)

1. Crea un nuovo repository su GitHub (es. `quiz-pegaso`), pubblico.
2. Carica il file `index.html` nella radice del repository (Add file → Upload files → Commit changes).
3. Vai su **Settings → Pages**.
4. In **Source**, seleziona il branch `main` e la cartella `/ (root)`, poi **Save**.
5. Dopo circa un minuto avrai il link pubblico:
   `https://TUO-USERNAME.github.io/quiz-pegaso/`

Quel link è il sito completo con tutte le materie, apribile da telefono, tablet o PC.

## Come aggiungere o modificare domande

Apri `index.html` con un editor di testo. Ogni materia ha il suo array di domande, ben identificabile all'inizio del file:

- `Q_STATISTICA`
- `Q_ECONOMIA_AZIENDALE`
- `Q_DIRITTO_PRIVATO`
- `Q_ECONOMIA_POLITICA`
- `Q_STORIA_ECONOMICA`
- `Q_TEORIA_GOVERNO_IMPRESA`

Ogni domanda è un oggetto con questo formato:

```js
{topic:"Nome argomento", q:"Testo della domanda?", options:["A","B","C","D"], correct:1, explain:"Spiegazione della risposta corretta."}
```

- `options`: **esattamente 4** risposte
- `correct`: indice (0, 1, 2 o 3) della risposta esatta
- `explain`: breve spiegazione mostrata dopo la risposta

Copia il formato di una riga esistente per aggiungerne di nuove, salva il file e ricarica la pagina (o fai un nuovo commit su GitHub).

### Aggiungere una nuova materia

In fondo al file, nella sezione `const SUBJECTS = { ... }`, aggiungi una nuova voce seguendo lo stesso schema delle altre (nome, icona, array di domande, `hasGenerators:false`).

### Aggiungere nuovi modelli di esercizio generato

- Per **Statistica**, nella sezione `const STAT_GENERATORS = [ ... ]`: copia il formato di una funzione esistente (es. `genMean`) per crearne una nuova con numeri casuali.
- Per le **altre 5 materie**, basta aggiungere nuove voci ai rispettivi glossari (es. `GLOSSARY_DIRITTO_PRIVATO`), nel formato `{term:"Nome del concetto", definition:"definizione del concetto"}`. Più termini ci sono, più combinazioni diverse potrà generare il quiz infinito.

## Funzionalità

- Selezione materia dalla home, poi scelta della modalità di esercitazione
- Domande ed opzioni mostrate in ordine casuale ad ogni tentativo
- Feedback immediato con spiegazione dopo ogni risposta
- Pannello statistiche live (risposte, corrette, errate, accuratezza, serie di risposte corrette consecutive)
- Schermata finale con punteggio e riepilogo delle domande sbagliate, con possibilità di rifare il test, cambiare modalità o cambiare materia
- Nessuna dipendenza esterna oltre ai font Google (funziona anche offline se rimuovi il link ai font)

## Nota

Materiale di autoesercitazione creato come supporto allo studio: verifica sempre i contenuti su libri di testo, slide del corso e materiale ufficiale fornito dall'ateneo, specialmente per Diritto Privato dove i riferimenti agli articoli di legge vanno sempre controllati sul codice aggiornato.
