# Quiz Pegaso — Preparazione Esami

Sito unico di autoesercitazione a risposta multipla (4 opzioni) per più esami universitari Pegaso. È un **unico file HTML autonomo**: nessuna installazione, nessun server, funziona anche solo aprendolo nel browser.

## Novità di questa versione

- **Tre livelli di difficoltà** (🟢 Facile, 🟡 Media, 🔴 Difficile) su ogni domanda della banca fissa, filtrabili dalla schermata di scelta modalità.
- **Modalità progressiva**: un nuovo modo di esercitarsi che percorre l'intera banca di domande partendo dalle più facili e arrivando gradualmente alle più difficili.
- **+60 domande nuove** (10 per materia), scritte a mano e bilanciate per lunghezza delle opzioni, concentrate soprattutto sui livelli medio/difficile.
- **Correzione del bias "risposta più lunga = corretta"**: in precedenza la risposta esatta era anche l'opzione più lunga in oltre l'85% dei casi in ogni materia — un pattern facilmente individuabile senza sapere davvero la risposta. Ora, dopo un ribilanciamento automatico dei distrattori (resi più articolati dove erano troppo corti) e la riscrittura delle nuove domande, la risposta corretta risulta la più lunga in meno del 15% dei casi per materia, in linea con quanto ci si aspetterebbe per puro caso (25% con 4 opzioni).
- **Correzione del bias di posizione**: nella versione precedente la risposta corretta si trovava nell'opzione "B" in circa l'80% delle domande della banca fissa, e non compariva mai in "D". Ora, ad ogni tentativo, le 4 opzioni di ogni domanda a banca fissa vengono mescolate casualmente prima di essere mostrate (le domande generate al volo lo facevano già).

## Materie incluse (banca fissa aggiornata)

| Materia | Domande teoriche | Esercizi infiniti generati |
|---|---|---|
| 📊 Statistica | 59 (22 facili · 20 medie · 17 difficili) | ✅ calcolo (12 modelli: media, mediana, probabilità, z-score, regressione, IC...) |
| 🏢 Economia Aziendale | 46 (16 facili · 17 medie · 13 difficili) | ✅ definizioni (40 termini, generate con distrattori casuali) |
| ⚖️ Diritto Privato | 45 (15 facili · 16 medie · 14 difficili) | ✅ definizioni (41 termini) |
| 📈 Economia Politica | 44 (15 facili · 16 medie · 13 difficili) | ✅ definizioni (40 termini) |
| 📜 Storia Economica | 43 (15 facili · 14 medie · 14 difficili) | ✅ definizioni (40 termini) |
| 🏛️ Teoria e Governo dell'Impresa | 43 (15 facili · 14 medie · 14 difficili) | ✅ definizioni (40 termini) |

**Totale: 280 domande nella banca fissa** (erano 220), più gli esercizi infiniti generati al volo per ogni materia.

Per ogni materia, dalla home si sceglie la modalità: test completo, prova rapida (15 domande), **modalità progressiva** (facile → media → difficile), esercizi infiniti (generati al volo, senza mai finire) oppure una sessione mista infinita che alterna banca fissa ed esercizi generati. Il filtro per difficoltà si applica a test completo, prova rapida e sessione mista/infinita; la modalità progressiva usa sempre l'intera banca, in ordine crescente di difficoltà. Un pulsante "Termina e vedi il punteggio" permette di chiudere la sessione infinita quando si vuole.

Per Statistica il generatore crea veri calcoli con numeri casuali ogni volta (media, varianza, probabilità, punteggio z, regressione, intervalli di confidenza...). Per le altre 5 materie il generatore pesca un concetto da un glossario di termini chiave e costruisce la domanda (in una delle due direzioni: "cosa significa questo termine?" oppure "a quale termine corrisponde questa definizione?") con 3 distrattori casuali presi dallo stesso glossario: la combinazione di termine, direzione e distrattori cambia ad ogni domanda, dando una quantità molto elevata di combinazioni diverse pur partendo da un insieme di concetti finito (esattamente come càpita ripassando un vero esame).

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
{topic:"Nome argomento", q:"Testo della domanda?", options:["A","B","C","D"], correct:1, explain:"Spiegazione della risposta corretta.", difficulty:"media"}
```

- `options`: **esattamente 4** risposte
- `correct`: indice (0, 1, 2 o 3) della risposta esatta
- `explain`: breve spiegazione mostrata dopo la risposta
- `difficulty`: uno tra `"facile"`, `"media"`, `"difficile"` — determina in quale filtro e in che punto della modalità progressiva compare la domanda

Copia il formato di una riga esistente per aggiungerne di nuove, salva il file e ricarica la pagina (o fai un nuovo commit su GitHub). **Consiglio contro i bias**: prova a variare la lunghezza e la posizione "logica" della risposta corretta rispetto ai distrattori — non serve mescolare tu stesso l'ordine delle opzioni nel codice, perché il sito lo fa già automaticamente ad ogni tentativo, ma evita di scrivere sempre la risposta giusta come l'unica più dettagliata o articolata delle quattro.

### Aggiungere una nuova materia

In fondo al file, nella sezione `const SUBJECTS = { ... }`, aggiungi una nuova voce seguendo lo stesso schema delle altre (nome, icona, array di domande, `hasGenerators:false`).

### Aggiungere nuovi modelli di esercizio generato

- Per **Statistica**, nella sezione `const STAT_GENERATORS = [ ... ]`: copia il formato di una funzione esistente (es. `genMean`) per crearne una nuova con numeri casuali.
- Per le **altre 5 materie**, basta aggiungere nuove voci ai rispettivi glossari (es. `GLOSSARY_DIRITTO_PRIVATO`), nel formato `{term:"Nome del concetto", definition:"definizione del concetto"}`. Più termini ci sono, più combinazioni diverse potrà generare il quiz infinito.

## Funzionalità

- Selezione materia dalla home, poi scelta della modalità di esercitazione e del livello di difficoltà
- Modalità progressiva che accompagna dal livello facile al difficile
- Domande mostrate in ordine casuale ad ogni tentativo, **e ora anche le opzioni di ogni domanda vengono mescolate ad ogni visualizzazione**
- Feedback immediato con spiegazione dopo ogni risposta
- Etichetta di difficoltà colorata visibile su ogni domanda della banca fissa
- Pannello statistiche live (risposte, corrette, errate, accuratezza, serie di risposte corrette consecutive)
- Schermata finale con punteggio e riepilogo delle domande sbagliate, con possibilità di rifare il test, cambiare modalità o cambiare materia
- Nessuna dipendenza esterna oltre ai font Google (funziona anche offline se rimuovi il link ai font)

## Nota

Materiale di autoesercitazione creato come supporto allo studio: verifica sempre i contenuti su libri di testo, slide del corso e materiale ufficiale fornito dall'ateneo, specialmente per Diritto Privato dove i riferimenti agli articoli di legge vanno sempre controllati sul codice aggiornato.
