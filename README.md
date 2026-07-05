# Quiz Statistica — Esame Pegaso

App di autoesercitazione a risposta multipla (4 opzioni) per l'esame di Statistica. È un **unico file HTML autonomo**: nessuna installazione, nessuna dipendenza da server, funziona anche solo aprendolo nel browser.

## Come metterlo online con un link GitHub (GitHub Pages)

1. Crea un nuovo repository su GitHub (es. `quiz-statistica`), pubblico.
2. Carica il file `index.html` (e questo `README.md` se vuoi) nella radice del repository.
   - Dal sito GitHub: **Add file → Upload files** → trascina `index.html` → **Commit changes**.
3. Vai su **Settings → Pages** (nel menu a sinistra del repository).
4. In **Source**, seleziona il branch `main` e la cartella `/ (root)`, poi **Save**.
5. Dopo circa 1 minuto, GitHub ti mostrerà il link pubblico, del tipo:
   `https://TUO-USERNAME.github.io/quiz-statistica/`

Quel link è la tua app: apribile da telefono, tablet o PC, condivisibile con chiunque.

## Come modificare o aggiungere domande

Apri `index.html` con un editor di testo e cerca la sezione:

```js
const QUESTIONS = [
  {topic:"...", q:"...", options:["...","...","...","..."], correct:0, explain:"..."},
  ...
];
```

Ogni domanda è un oggetto con:
- `topic`: l'argomento (mostrato come etichetta)
- `q`: il testo della domanda
- `options`: array di **esattamente 4** risposte
- `correct`: indice (0, 1, 2 o 3) della risposta esatta nell'array `options`
- `explain`: breve spiegazione mostrata dopo la risposta

Aggiungi nuove domande copiando il formato di una riga esistente. Salva il file e ricarica la pagina (o fai un nuovo commit su GitHub se è già online).

## Funzionalità

- **Banca fissa**: 45 domande teoriche a risposta multipla, in ordine casuale ad ogni tentativo
- **Generatore infinito di esercizi**: 12 "modelli" di esercizio (media, mediana, moda, range, varianza, probabilità su urna, probabilità con il dado, punteggio z, regola empirica della Normale, regressione lineare, coefficiente di variazione, intervallo di confidenza) che ad ogni domanda estraggono numeri casuali nuovi, calcolano la risposta esatta e generano 3 alternative plausibili basate su errori tipici (es. confondere media e mediana, dimenticare la radice quadrata, invertire numeratore e denominatore). Il risultato è un numero **praticamente illimitato** di esercizi diversi.
- **Sessione mista infinita**: alterna a caso domande teoriche della banca fissa ed esercizi di calcolo generati, senza mai finire, con un pulsante "Termina e vedi il punteggio" per chiudere quando vuoi
- Feedback immediato con spiegazione (compresi i passaggi del calcolo) dopo ogni risposta
- Pannello statistiche live (risposte, corrette, errate, accuratezza, serie di risposte corrette consecutive)
- Schermata finale con punteggio e riepilogo delle domande sbagliate
- Nessuna dipendenza esterna oltre ai font Google (funziona anche offline se rimuovi il link ai font)

### Aggiungere nuovi "modelli" di esercizio generato

Nella sezione `const GENERATORS = [ ... ]` ogni funzione genera una domanda con numeri casuali. Per aggiungerne una nuova, copia il formato di una funzione esistente (es. `genMean`): genera i dati casuali, calcola la risposta corretta, usa `buildOptions(valoreCorretto, funzioneDistrattori)` per ottenere le 4 opzioni mescolate, e restituisci `{ topic, q, options, correct, explain }`.

## Nota

Materiale di autoesercitazione creato come supporto allo studio: verifica sempre i contenuti su libri di testo, slide del corso e materiale ufficiale fornito dall'ateneo.
