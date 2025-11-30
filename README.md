💡 Projet Hybride LLM-RO : Optimisation Prescriptive du Chargement LogistiqueCe projet démontre un pipeline d'Intelligence Artificielle complet qui combine les Large Language Models (LLM) et la Recherche Opérationnelle (RO) pour transformer des données non structurées en décisions économiques optimales.L'objectif est de maximiser la priorité (valeur) des colis chargés dans un camion, tout en respectant strictement les contraintes de poids et de volume.

⚙️ Architecture et Flux de TravailLe pipeline est divisé en deux phases distinctes, simulant une chaîne de valeur complète :

    1. Phase LLM (Extraction et Structuration)Cette phase gère l'input non structuré et garantit la qualité des données.Outils Clés : OpenAI API (GPT-3.5-Turbo), LangChain, Pydantic.Action : Le LLM extrait de manière fiable quatre variables clés pour chaque colis : ID_Colis, Poids_kg, Volume_m3, et Priorite.Sortie : Un fichier de données structuré (donnees_propres_RO.csv) prêt pour le calcul.
    2. Phase RO (Optimisation Prescriptive)Cette phase utilise les données structurées pour générer la décision la plus rentable.Outil Clé : Google OR-Tools (Solveur CP-SAT).Modèle : Problème du Sac à Dos Multi-Contraintes.Contraintes : Poids total $\le 300$ kg et Volume total $\le 70$ $m^3$.Objectif : Maximiser la somme de la variable Priorite.

🛠️ Technologies UtiliséesLangage : Python 3.9+Librairies :Data Science : PandasLLM/NLP : LangChain, Pydantic, python-dotenvRecherche Opérationnelle : Google OR-Tools

📊 Résultats Clés de l'OptimisationLes résultats suivants démontrent la solution optimale trouvée par l'algorithme :Capacités du CamionPoids Maximum : 300 kgVolume Maximum : 70 $m^3$Performance et UtilisationPriorité Maximale Totale (Valeur Maximisée) : 295.0Poids Total Chargé : 246 kg (82% de la capacité utilisée)Volume Total Chargé : 69 $m^3$ (98.6% de la capacité utilisée)
📦 Colis Sélectionnés (Décision Prescriptive)Le solveur OR-Tools a déterminé que les 7 colis suivants doivent être chargés pour atteindre la priorité maximale tout en respectant les contraintes :M-BetaG-DeltaS-EpsilonA-EtaB-ThetaX-IotaY-Kappa
