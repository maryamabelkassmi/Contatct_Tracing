# Contatct_Tracing
**Introduction**

La recherche des contacts est le nom du processus utilisé pour identifier ceux qui entrent en contact avec des personnes qui ont été testées positives pour des maladies contagieuses - telles que la rougeole, le VIH et le COVID-19. Pendant une pandémie, effectuer correctement la recherche des contacts peut aider à réduire le nombre de personnes infectées ou à accélérer le processus de traitement des personnes infectées. Cela peut aider à sauver de nombreuses vies.

Le clustering est une sous-classe d'algorithmes d'apprentissage automatique utilisés pour diviser les données qui partagent certaines caractéristiques dans différents clusters en fonction de ces caractéristiques.

Pour la recherche des contacts, nous devons utiliser un algorithme de clustering basé sur la densité. La raison en est que les maladies sont transférées lorsqu'une personne infectée entre en contact avec d'autres. Ainsi, les zones plus encombrées - denses - auront plus de cas que les moins encombrées.

**Base de données**
Pour retracer le mouvement des personnes infectées, les scientifiques utilisent souvent des ensembles de données GPS qui contiennent des informations sur l'heure et l'emplacement d'une personne à une période donnée. Les données de localisation sont souvent représentées sous forme de coordonnées de longitude et de latitude.

Malheureusement, nous ne pouvons pas obtenir de données réelles à partir des emplacements GPS. Nous allons donc créer un ensemble de données simulé sur lequel appliquer notre algorithme. Pnous allons utiliser un générateur de données simulé pour générer un ensemble de données JSON contenant 100 entrées des emplacements de 10 utilisateurs. cette base de données peut eter télechargere du drive suivant:https://drive.google.com/file/d/1fYkBwXmDHLmRk_MCtiAOrcYwwyIqERbF/view

** l'algorithme DBSCAN**
L' algorithme DBSCAN considère les clusters comme des zones de haute densité séparées par des régions de faible densité. Pour cette raison, les clusters trouvés par DBSCAN peuvent être de n'importe quelle forme, par opposition aux k-means, qui suppose que tous les clusters sont de forme convexe.

eps: ce facteur indique la distance entre les différents points d'un même cluster. Dans notre cas, nous utiliserons la distance recommandée par le CDC, qui est de 6 pieds (ou 0,0018288 kilomètres).
min_samples: le nombre minimum d'échantillons dans le cluster. Dans le cas de grands ensembles de données bruyants, augmentez ce nombre.
metric: Ceci définit la métrique de distance entre les points de données. Sklearn a de nombreuses mesures de distance, telles que euclidienne, Manhattan et Minkowski. Pour notre cas, cependant, nous avons besoin d'une mesure de distance qui décrit la distance sur un chiffre (la Terre). La métrique pour cela s'appelle haversine.


