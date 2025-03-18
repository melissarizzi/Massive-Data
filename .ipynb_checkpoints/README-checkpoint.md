# Massive-Data

[![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/melissarizzi/Massive-Data/blob/main/project.ipynb)

Uso questo per segnarmi le cose che sto guardando cosi rimangono:
(poi capiamo insieme cosa ha senso).

Guardando i 'titoli' degli argomenti affrontati a lezione, quello che potrebbe essere 
più utile a noi potrebbe essere **'Insieme di elementi frequenti'**.

Questo rimanda a capitolo 6 del libro e quindi sono partita a dare un'occhiata da li.
- Il libro inizia proprio il capitolo 6 parlando del market-basket model.

Algoritmi trattati dal libro:
- A-Priori algorithm (citato da chat quando chiesto di market basket analysis)

Invece da quello che ho capito, per un campionamento per scegliere un subsample sensato, 
potrebbe servire quel **'Spark'** che bisogna cercare che è. forse anche **'Map reduce'**.
(queste info le ho cercate molto molto brevemente su chatty, quindi da prendere ancora con 
le pinze).

Qualche info che mi ha dato:
- Spark è ideale per lavorare con dataset enormi, come nel tuo caso con oltre un milione di righe.
- Esempio di utilizzo : 
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("MarketBasket").getOrCreate()
df = spark.read.csv("Books_rating.csv", header=True, inferSchema=True)

df.show(5)  # Visualizza le prime 5 righe
```
- Nel contesto di market-basket analysis, Spark è uno strumento molto potente per l'elaborazione di dati su larga scala, specialmente se il tuo dataset è davvero grande, come quello che stai trattando. Puoi utilizzare Spark per caricare, manipolare, e analizzare i tuoi dati in modo distribuito, 
senza preoccuparti troppo della memoria del singolo computer.

Se hai già caricato il tuo dataset in Spark come nell'esempio che abbiamo visto prima, possiamo proseguire con operazioni come:

1. Pulizia e trasformazione dei dati (es. rimozione di valori nulli, creazione di nuove colonne).
2. Esecuzione di analisi statistiche (es. calcolo delle frequenze delle parole o degli item nei vari "cestini").
3. Creazione di un modello di analisi di market-basket (come l'algoritmo Apriori o FP-Growth).
 
