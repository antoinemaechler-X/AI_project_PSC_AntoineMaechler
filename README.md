Ce projet, mené sous la tutelle de Clément Malgouyres (économiste au CREST) a pour objectif d'utiliser le Machine Learning pour optimiser la taxation carbone appliquée aux véhicules en France.

Il s'articule en 2 parties :

Dans un premier temps, cette taxation se base sur le CO2 théorique émis par les véhicules (mesuré en laboratoire). Alors que Clément Malgouyres avait observé une grande différence entre ce CO2 théorique et le CO2 réel, il s'agissait dans un premier temps de prédire à l'aide de 25 caractéristiques intrinsèques du véhicule (poids, coefficient d'aérodynamisme, cylindrée...) les émissions de façon beaucoup plus précise pour rendre la taxe plus juste et efficace.
On trouvera cette première partie dans le fichier PSC_ML.

Dans un second temps, il s'agissait de modéliser la demande et d'ensuite en déduire le malus optimal à appliquer (en fonction du nouveau CO2 calculé en partie 1) pour maximiser l'utilité des consommateurs sous la contrainte de rester sous un certain seuil d'émissions. Pour ce faire on divise les véhicules en tranches d'émissions sur lesquelles on calcule un prix moyen.
On trouvera les données transformées dans p3_donnees_optimisation et les résultats finaux des malus à appliquer dans p4_optimisation. 
