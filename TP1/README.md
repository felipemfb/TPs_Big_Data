# TP1 - Word Count : Comparaison des approches de traitement Big Data

## Objectif

Ce TP s'appuie sur le matériel développé pour le cours de Big Data du 13 octobre 2026. Les résultats seront utilisés pour effectuer l'analyse des performances et formuler la conclusion. Les tests analysant l'implémentation avec PySpark figurent à la fin du document, en complément de ce qui a été réalisé pendant la matinée. Toutes les expériences ont été réalisées dans un environnement Ubuntu.

L'objectif de ce travail est de mettre en œuvre quatre approches visant à compter le nombre d'occurrences de chaque mot dans un fichier `.txt`, tout en comprenant le fonctionnement de chacune d'elles.

Les quatre versions proposées sont :

- Version simple utilisant Python
- Pseudo-MapReduce
- Hadoop MapReduce
- PySpark

Pour évaluer chaque approche, le temps d'exécution sera mesuré à l'aide de fichiers texte contenant différents nombres de mots.

Quatre fichiers `.txt` contenant des mots aléatoires, avec un mot par ligne, ont été créés. Chaque fichier contient dix fois plus de mots que le précédent, afin d'évaluer les performances de chaque approche pour différentes tailles de fichiers d'entrée.

- `mots_taille_1.txt` : 1 000 lignes, 6 309 octets
- `mots_taille_10.txt` : 10 000 lignes, 62 711 octets
- `mots_taille_100.txt` : 100 000 lignes, 626 776 octets
- `mots_taille_1000.txt` : 1 000 000 lignes, 6 265 995 octets

## Bibliothèques utilisées

- PySpark
- Pandas
- Time
- Random
- Collections
- Pathlib

## Configuration de Hadoop

HDFS et YARN ont été configurés et démarrés pour permettre l'exécution de Hadoop. Les fichiers de données ont également été transférés vers HDFS.

Le programme Hadoop MapReduce a ensuite été exécuté sur chaque fichier afin de compter les occurrences des mots et de mesurer le temps d'exécution.

## Résultats des performances

Les temps d'exécution obtenus pour chaque approche sont présentés dans le tableau suivant :

| Fichier | Python simple (s) | Pseudo-MapReduce (s) | Hadoop MapReduce (s) | PySpark (s) |
|---|---:|---:|---:|---:|
| mots_taille_1.txt | 0.000249 | 0.001191 | 13.03 | 0.159902 |
| mots_taille_10.txt | 0.003138 | 0.006758 | 14.08 | 0.178647 |
| mots_taille_100.txt | 0.013275 | 0.040867 | 14.29 | 0.205684 |
| mots_taille_1000.txt | 0.114798 | 0.386150 | 15.01 | 0.618949 |

## Analyse des performances et conclusion

L'approche simple utilisant Python est la méthode la plus rapide parmi celles évaluées pour les volumes de données utilisés. Le pseudo-MapReduce présente des temps d'exécution légèrement plus élevés en raison des étapes supplémentaires de Map, Shuffle et Reduce.

PySpark présente également des temps d'exécution supérieurs à ceux de Python simple. Cela s'explique notamment par les coûts d'initialisation et de préparation nécessaires à l'exécution des opérations Spark.

Hadoop MapReduce présente les temps d'exécution les plus élevés dans cette expérience. Ce résultat est principalement lié au coût initial de lancement des tâches et à la complexité de l'infrastructure. Cependant, Hadoop est conçu pour traiter de très grands volumes de données de manière distribuée.

Ce TP a permis de comprendre et de comparer quatre approches de traitement de données de complexités différentes. Le choix de la méthode dépend directement du volume de données et des besoins du traitement.

Pour les petits jeux de données, l'approche simple utilisant Python est la plus adaptée en raison de sa rapidité et de sa simplicité. Pour des volumes plus importants, les solutions distribuées comme PySpark et Hadoop MapReduce peuvent devenir pertinentes. PySpark constitue notamment une alternative intéressante grâce à ses capacités de traitement distribué et à des temps d'exécution inférieurs à ceux observés avec Hadoop MapReduce dans cette expérience.

Les résultats montrent ainsi que les infrastructures Big Data impliquent des coûts supplémentaires qui ne sont pas nécessairement justifiés pour de petits volumes de données, mais qui peuvent devenir intéressants lorsque les besoins de traitement augmentent.