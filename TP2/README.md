# TP2 - Étude de cas – Analyse Big Data de données d'accidents de la route à l'aide de PySpark

## Objectif

L'objectif de ce TP est de mettre en œuvre une analyse Big Data de données d'accidents de la route à l'aide d'Apache Spark et de PySpark, en suivant l'étude de cas présentée dans l'article suivant :

Nain, Rakesh. [Big Data Analysis of Road Crash Data Using PySpark](https://medium.com/rakesh-nain/big-data-analysis-of-road-crash-data-using-pyspark-with-pyspark-tutorial-c78ff2c35588).

## Concepts

### RDD (Resilient Distributed Dataset)
Un RDD (Resilient Distributed Dataset) constitue l'abstraction fondamentale de Spark pour le traitement des données. Il s'agit, en somme, d'une collection distribuée et immuable d'objets.

Spark répartit automatiquement les données contenues dans les RDD au sein du cluster et parallélise les opérations qui y sont appliquées. Chaque RDD est divisé en plusieurs partitions, lesquelles peuvent être traitées sur différents nœuds ou cœurs du cluster.

Dans Spark, tout travail se traduit soit par la création de nouveaux RDD, soit par la transformation de RDD existants, soit par l'exécution d'opérations sur des RDD afin d'obtenir un résultat.

### DataFrame

Un DataFrame est une collection distribuée de données organisées en colonnes nommées. Il équivaut à une table dans une base de données relationnelle, mais il bénéficie d’optimisations plus poussées en arrière-plan.

### SparkSQL

Spark SQL est un module d'Apache Spark qui permet de traiter et d'analyser des données structurées à l'aide de requêtes SQL. Il permet d'interroger des DataFrames via des commandes SQL classiques tout en tirant parti du traitement distribué et des optimisations de Spark.

## Technologies

- Python
- Apache Spark
- PySpark
- RDD (Resilient Distributed Dataset)
- DataFrame