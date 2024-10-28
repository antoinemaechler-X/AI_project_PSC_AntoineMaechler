Ce projet a pour objectif d'utiliser le Machine Learning pour optimiser la taxation carbone appliquée aux véhicules en France.

Il s'articule en 2 parties :

**Améliorer l'estimation du CO2 émis**

Dans un premier temps, il s'agissait de mieux estimer les émissions des véhicules. La taxation se base aujourd'hui sur le CO2 théorique émis, une mesure effectuée en laboratoire et peu fiable (RMSE de 29 pour un CO2 moyen de 141g/km). L'idée était alors d'utiliser les caractéristiques intrinsèques du véhicule (poids, coefficient d'aérodynamisme, cylindrée... - jusqu'à 25 dans nos modèles) afin de calculer plus finement les émissions. On utilisera pour cela une régression Lasso et un modèle KNN, entraînés sur une base de données retravaillée de plus de 180000 véhicules.
On trouvera cette première partie dans le fichier PSC_ML.

On obtient les estimations des émissions suivantes (en noir vs l'estimation de l'État en bleu) avec un RMSE final de 3.38 contre 29.04 pour l'État :

![knn](https://github.com/user-attachments/assets/331ccfc5-4535-455c-a31a-6dafc487fc4a)

**Taxer plus efficacement pour réduire les émissions**

Dans un second temps, il s'agissait de modéliser la demande à l'aide d'un modèle économique et d'ensuite en déduire le malus optimal à appliquer (en fonction du nouveau CO2 calculé précédemment) pour maximiser l'utilité des consommateurs sous la contrainte de rester sous un certain seuil d'émissions. Le résultat final est un malus composite qui prend en compte les résultats de l'optimisation ainsi que des contraintes de croissance/convexité sur la taxe.
On trouvera les données transformées dans p3_donnees_optimisation et les résultats finaux des malus à appliquer dans p4_optimisation.

Cette méthodologie se révèle très efficace car en gardant les mêmes niveaux de satisfaction consommateur (et des montants de taxe en moyenne moins élevés), on parvient à baisser le CO2 émis de 141.4g/km à 130g/km (notre cible).

On obtient la taxe suivante (en rouge), mise en perspective de celle de l'État en 2021 (jaune) et 2024 (vert).

![all_composite](https://github.com/user-attachments/assets/40eae4a9-d17c-494f-90e4-5cf397fa6920)

Ce projet a été récompensé du prix du meilleur PSC d'économie de l'année (2024).

On trouvera le rapport dans les fichiers du projet.
