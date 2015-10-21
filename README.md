### Meccanica Quantistica

Questo libretto è la trascrizione degli appunti del corso di **Fisica Moderna e Meccanica Quantistica** nel periodo marzo 2015 - gennaio 2016 tenuto dal professor Sergio Caracciolo.

Spero di riuscire a mantenerlo aggiornato nel tempo man mano che le lezioni procedono. Correzioni e consigli sono *sempre* benvenuti.

Buona lettura!

### Informazioni tecniche
##### Struttura dei file
I file `.tex` dei capitoli si trovano, suddivisi per corso, nelle tre cartelle numerate; sono inclusi nel file principale tramite il comando `\include`.
Il codice di ogni grafico è tenuto separato dal corpo principale, e si può trovare nella cartella `grafici`.

##### Come compilare
Se volete compilare i file di LaTeX sul vostro computer, ecco i passi da seguire (per una distribuzione Linux con le applicazioni necessarie installate).
I file dei singoli capitoli non possono essere compilati separatamente.
Si consiglia l'uso di `latexmk` per automatizzare i processi di compilazione.

È necessario anche creare una sottocartella chiamata `tex` nella cartella principale: `pgfplots`, con l'opzione `externalize` impostata nel preambolo del file principale, compila i grafici solo alla prima occasione, e li salva in formato PDF nella cartella `tex`, per riutilizzarli le volte successive (salvo modifiche al loro codice).
Una compilazione senza aver creato `tex` dovrebbe arrestarsi in breve tempo con qualche errore.
Trovandosi nella cartella principale, eseguire

```bash
mkdir -p tex
pdflatex -shell-escape meccanica-quantistica
pdflatex -shell-escape meccanica-quantistica
```

Le volte successive è sufficiente un unico passaggio:

```bash
pdflatex -shell-escape meccanica-quantistica
```

ripetuto eventualmente una seconda volta per sistemare riferimenti interni.

##### Requisiti
Per poter compilare il documento è necessario ovviamente avere installato tutti i pacchetti di LaTeX elencati nel file di stile e le applicazioni di base per compilare.
Se usate una distribuzione TeX Live per sistemi basati su Debian è sufficiente installare i pacchetti

```
texlive-base
texlive-binaries
texlive-extra-utils
texlive-font-utils
texlive-fonts-recommended
texlive-generic-recommended
texlive-lang-italian
texlive-latex-base
texlive-latex-extra
texlive-latex-recommended
texlive-pictures
texlive-plain-extra
texlive-science
gnuplot
```

