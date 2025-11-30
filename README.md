💡 Projet Hybride LLM-RO : Optimisation Prescriptive du Chargement Logistique 

Ce projet démontre un pipeline d'Intelligence Artificielle complet qui combine les Large Language Models (LLM) et la Recherche Opérationnelle (RO) pour transformer des données non structurées en décisions économiques optimales.L'objectif est de maximiser la priorité (valeur) des colis chargés dans un camion, tout en respectant strictement les contraintes de poids et de volume.

❓ Description Détaillée du Problème (Knapsack Multi-Contraintes)
Ce cas d'usage logistique est une variante du Problème du Sac à Dos (Knapsack Problem), où un ensemble d'articles doit être sélectionné pour un transport. La difficulté est double :Extraction de Données : Les informations essentielles (poids, volume, priorité) sont initialement noyées dans des notes de commandes en texte brut. Le LLM est utilisé pour normaliser et structurer cette donnée d'entrée.Double Contrainte : La sélection doit respecter simultanément deux limites physiques du véhicule (poids maximal et volume maximal).Le modèle de Recherche Opérationnelle cherche la combinaison parfaite de colis qui maximise la priorité totale sans violer les capacités du camion, fournissant ainsi une décision prescriptive à l'entreprise.

⚙️ Architecture et Flux de TravailLe pipeline est divisé en deux phases distinctes, simulant une chaîne de valeur complète :
    1. Phase LLM (Extraction et Structuration)Outils Clés : OpenAI API (GPT-3.5-Turbo), LangChain, Pydantic.Action : Le LLM extrait les 4 variables clés (ID_Colis, Poids_kg, Volume_m3, Priorite) via un schéma Pydantic.
    2. Phase RO (Optimisation Prescriptive)Outil Clé : Google OR-Tools (Solveur CP-SAT).
        Modèle : Problème du Sac à Dos Multi-Contraintes.
        Contraintes : Poids total  300 kg et Volume total  70 m^3.
        Objectif : Maximiser la somme de la variable Priorite.

🛠️ Technologies UtiliséesLangage : Python 3.9+Librairies :Data Science : PandasLLM/NLP : LangChain, Pydantic, python-dotenv Recherche Opérationnelle : Google OR-Tools

📊 Résultats Clés de l'Optimisation
Les résultats suivants démontrent la solution optimale trouvée par l'algorithme :
Capacités du CamionPoids Maximum : 300 kgVolume Maximum : 70 m^3
Performance et UtilisationPriorité Maximale Totale (Valeur Maximisée) : 295.0Poids 
Total Chargé : 246 kg (82% de la capacité utilisée)Volume Total Chargé : 69 m^3 (98.6% de la capacité utilisée)
📦 Colis Sélectionnés (Décision Prescriptive)Le solveur OR-Tools a déterminé que les 7 colis suivants doivent être chargés :M-BetaG-DeltaS-EpsilonA-EtaB-ThetaX-IotaY-Kappa

graph LR
    A[Texte Brut<br>(Notes de commandes)] --> B{LLM<br>(Extraction / Pydantic)}
    B --> C[Données Structurées<br>(Poids, Volume, Priorité)]
    C --> D{Recherche Opérationnelle<br>(Modèle Knapsack Multi-Contraintes)}
    D --> E[Décision Optimale<br>(Liste de colis à charger)]