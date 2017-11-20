### Meccanica Quantistica

Questo libretto è la trascrizione degli appunti del corso di **Fisica Moderna e Meccanica Quantistica** nel periodo marzo 2015 - gennaio 2016 tenuto dal professor Sergio Caracciolo.

Correzioni e consigli sono *sempre* benvenuti.

Buona lettura!

### Informazioni tecniche
##### Struttura dei file
I file `.tex` dei capitoli si trovano in file separati, nella cartella `chapters`, e sono inclusi nel file principale tramite il comando `\include`.
Il codice di ogni grafico è tenuto separato dal corpo principale, e si può trovare nella cartella `grafici`.

##### Come compilare
Nel menu [releases](https://github.com/phaerrax/analisi-matematica/releases) nella barra superiore potete trovare una versione già compilata del documento, che verrà aggiornata di tanto in tanto, oppure se sono stati introdotti grossi cambiamenti.
Se volete compilarlo sul vostro computer, in modo da ottenere la versione più aggiornata, ecco i passi da seguire (per una distribuzione Linux con le applicazioni necessarie installate).
I file dei singoli capitoli non possono essere compilati separatamente.
Si consiglia l'uso di `latexmk` per automatizzare i processi di compilazione.

Alla prima compilazione, bisogna generare i file della bibliografia di `biblatex`, perciò serve compilare più volte.
È necessario anche creare una sottocartella chiamata `tex` nella cartella principale: `pgfplots`, con l'opzione `externalize` impostata nel preambolo del file principale, compila i grafici solo alla prima occasione, e li salva in formato PDF nella cartella `tex`, per riutilizzarli le volte successive (salvo modifiche al loro codice).
Una compilazione senza aver creato `tex` dovrebbe arrestarsi in breve tempo con qualche errore.
Trovandosi nella cartella principale, eseguire

```bash
mkdir -p tex
pdflatex -shell-escape meccanica-quantistica
biber meccanica-quantistica
pdflatex -shell-escape meccanica-quantistica
pdflatex -shell-escape meccanica-quantistica
```

Le volte successive, se il file `meccanica-quantistica.bib` non è stato modificato e non sono state aggiunte citazioni (in tal caso, ripetere i passaggi precedenti), è sufficiente un unico passaggio:

```bash
pdflatex -shell-escape meccanica-quantistica
```

ripetuto eventualmente una seconda volta per sistemare riferimenti interni.

##### Requisiti
Per poter compilare il documento è necessario ovviamente avere installato tutti i pacchetti di LaTeX elencati nel file di stile e le applicazioni di base per compilare.
Se usate una distribuzione TeX Live è sufficiente installare i pacchetti

```
texlive-base
texlive-bibtex-extra
texlive-binaries
texlive-fonts-recommended
texlive-lang-italian
texlive-latex-base
texlive-latex-extra
texlive-latex-recommended
texlive-pictures
texlive-science
biber
gnuplot
```

(i nomi si riferiscono ai pacchetti disponibili per Arch Linux).
