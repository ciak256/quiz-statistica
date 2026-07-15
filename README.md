# Quiz Pegaso — Preparazione Esami

Sito unico di autoesercitazione a risposta multipla (4 opzioni) per più esami universitari Pegaso. È un **unico file HTML autonomo**: nessuna installazione, nessun server, funziona anche solo aprendolo nel browser.

## Novità di questa versione

- **56 nuove domande di Statistica basate sulla TUA dispensa** (Pasquale Pavone / Paolo Sciattella / Veronica Distefano, testo Borra-Di Ciaccio), ora con copertura completa di entrambe le parti del corso:
  - **Parte 1 (statistica descrittiva)**: media aritmetica/ponderata, media geometrica, trimmed mean, mediana, varianza, deviazione standard, coefficiente di variazione, teoremi di Chebyshev e Markov, standardizzazione, concentrazione e indice di Gini, curva di Lorenz, correlazione lineare, regressione ai minimi quadrati.
  - **Parte 2 (probabilità e inferenza)**: concetti di probabilità (classica/frequentista/soggettivista), algebra degli eventi, probabilità condizionata e indipendenza, teorema di Bayes, distribuzioni Binomiale/Poisson/Uniforme/Normale, teorema del limite centrale, proprietà degli stimatori (correttezza, errore quadratico medio), errori di I e II tipo, procedura di verifica delle ipotesi, test per la media, campionamento casuale semplice e stratificato.
  - Le domande usano **gli stessi esempi numerici, dataset ed esercizi presenti nelle tue slide** (es. l'esercizio dei copertoni A/B/C, il rapporto di concentrazione R=0,45, la retta di regressione ŷ=0,595+1,255X, l'esempio Bayes del test diagnostico con P=0,33, il centralino telefonico con la Poisson λ=2, il confronto tra stimatori T1/T2, l'esempio del farmaco per gli errori di I/II tipo).
- **Revisione errori**: controllo automatico su tutte le domande (campi mancanti, opzioni duplicate, indice della risposta corretta fuori range, difficoltà non valida) e ricerca di domande duplicate. Sono state trovate e corrette **6 domande ripetute per errore** in due lotti diversi (stesso testo, opzioni riformulate); sono state rimosse e sostituite con domande nuove su argomenti non ancora trattati.
- **Ulteriore ampliamento**: la banca fissa è cresciuta ancora, per un totale di **585 domande** (partite da 220).
- **Tre livelli di difficoltà** (🟢 Facile, 🟡 Media, 🔴 Difficile) su ogni domanda della banca fissa, filtrabili dalla schermata di scelta modalità.
- **Modalità progressiva**: un modo di esercitarsi che percorre l'intera banca di domande partendo dalle più facili e arrivando gradualmente alle più difficili.
- **Correzione del bias "risposta più lunga = corretta"**: in precedenza la risposta esatta era anche l'opzione più lunga in oltre l'85% dei casi in ogni materia — un pattern facilmente individuabile senza sapere davvero la risposta. Ora, dopo un ribilanciamento automatico dei distrattori (resi più articolati dove erano troppo corti), la risposta corretta risulta la più lunga in meno del 15% dei casi per materia, in linea con quanto ci si aspetterebbe per puro caso (25% con 4 opzioni).
- **Correzione del bias di posizione**: nella versione originale la risposta corretta si trovava nell'opzione "B" in circa l'80% delle domande della banca fissa, e non compariva mai in "D". Ora, ad ogni tentativo, le 4 opzioni di ogni domanda a banca fissa vengono mescolate casualmente prima di essere mostrate.
- Gli **esercizi infiniti non sono mai stati rimossi** e restano disponibili in ogni modalità: sono anzi stati ampliati con 3 nuovi modelli di calcolo per Statistica e +15 termini in ciascuno degli altri 5 glossari.

## Materie incluse (banca fissa aggiornata)

| Materia | Domande teoriche | Esercizi infiniti generati |
|---|---|---|
| 📊 Statistica | 176 (51 facili · 78 medie · 47 difficili, incluse 56 basate sulla tua dispensa, copertura completa parte 1 e 2) | ✅ calcolo (15 modelli: media, mediana, probabilità, z-score, regressione, IC, IQR, varianza campionaria, media ponderata...) |
| 🏢 Economia Aziendale | 88 (31 facili · 33 medie · 24 difficili) | ✅ definizioni (56 termini, generate con distrattori casuali) |
| ⚖️ Diritto Privato | 78 (24 facili · 29 medie · 25 difficili) | ✅ definizioni (56 termini) |
| 📈 Economia Politica | 74 (25 facili · 29 medie · 20 difficili) | ✅ definizioni (55 termini) |
| 📜 Storia Economica | 70 (21 facili · 26 medie · 23 difficili) | ✅ definizioni (55 termini) |
| 🏛️ Teoria e Governo dell'Impresa | 68 (23 facili · 23 medie · 22 difficili) | ✅ definizioni (55 termini) |

**Totale: 585 domande nella banca fissa** (partite da 220), più gli esercizi infiniti generati al volo per ogni materia, sempre disponibili in ogni modalità.

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
