# Analyse des ventes de café — Projet Data Science

Auteurs
Christie Féliza M. ANILUS
Woodt Chelly ALEXANDRE

Bootcamp Data Akademi — Phase 5
Tuteur : Wedter JEROME
Date de remise : Octobre 2025

## 1. Introduction

Le projet Coffee Sales Prediction vise à comprendre les facteurs influençant les ventes de café et à prévoir les revenus futurs à l’aide d’un modèle d’apprentissage automatique.
Grâce à une base de données issue de Kaggle, le modèle Random Forest Regressor a été entraîné pour prédire les ventes à partir de caractéristiques telles que :
 - Le type de café,
 - Le moment de la journée,
 - Le mode de paiement,
 - Le mois et le jour de la semaine.

Les compétences mobilisées incluent :
- Manipulation et nettoyage de données (pandas, numpy)
- Visualisation (matplotlib, seaborn)
- Analyse statistique et modélisation prédictive (scikit-learn)

![Image du café](IMAGES/expresso.jpeg)

### 2. Compréhension du contexte et des données

Les données proviennent du dataset Coffee Sales Dataset (Kaggle).
Elles contiennent :

 - Le nom du produit ;
 - La date et l’heure de la transaction ;
 - Le moment de la journée (Time_of_Day) ;
 - Le montant de la vente ;
 - Le mode de paiement (cash_type) ;
 - Des variables temporelles : jour, mois, etc.

Le café souhaite comprendre quels facteurs influencent ses ventes et anticiper les revenus futurs.
Un modèle de Machine Learning (Random Forest Regressor) a été développé pour prédire les ventes et aider à la prise de décision concernant les promotions, stocks et planifications.

![Image](IMAGES/grain%20café.jpeg)

### 3. Objectifs du projet
#### 3.1. Objectif général
 - Construire un modèle capable de prédire le montant des ventes de café à partir des données historiques.
#### 3.2.  Objectifs spécifiques
   - Identifier les facteurs qui influencent les ventes.
   - Analyser les tendances selon le type de café, la période et le moment de la journée.
   - Évaluer la performance d’un modèle prédictif avec MAE, RMSE et R².
   - Fournir des recommandations commerciales exploitables.


### 4. Description du jeu de données
- Élément	Description
- Source	Kaggle
- Nom du fichier	- Coffee_sales.csv
- Volume	≈ 15 000 lignes / 8 colonnes
- Période couverte - Janv. 2019 – Déc. 2021
- Colonnes clés - Date, Store, Product, Units_Sold, Price, Revenue, Promo, Region.

### 5. Méthodologie

- Importation et exploration des données
- Nettoyage et transformation : traitement des valeurs manquantes, création de variables temporelles
- Analyse exploratoire (EDA) : histogrammes, heatmaps, comparaisons régionales
   - #### Vente Moyenne par type de café
   - Permet d’identifier les cafés les plus rentables.
   
![Vente de café](IMAGES/vente%20moyenne%20par%20type%20de%20café.jpeg)
   - #### Ditribution des ventes selon le moment de la journée
   - Montre les périodes (matin, midi, soir) où les ventes sont les plus fortes.

![Ditribution](IMAGES/distributions%20des%20ventes%20par%20moment%20de%20la%20journée.jpeg)
   - #### Répartition des types de paiement
   - Indique les modes de paiement les plus utilisés (espèces, carte, etc.)

![Paiement](IMAGES/nombre%20des%20transactions%20par%20type%20de%20paiement.jpeg)

   - #### Ventes totales par mois
   - Fait ressortir les variations saisonnières et les pics de ventes.

![Ventes mensuelles](IMAGES/ventes%20totales%20par%20mois.jpeg)
- Modélisation prédictive : test de plusieurs modèles (Régression linéaire, Random Forest)
- Évaluation des performances et analyse de l’importance des variables.

### 6. Modélisation et Evaluation

- Performance du modèle Random Forest :
    - MAE = 0.28
    - RMSE = 0.73
    - R² = 0.98

 - Facteurs les plus influents :
    - Type de café 
    - Mois de l’année 

 - Variables les moins influentes : mode de paiement, heure de la journée
 - Visualisations générées : courbes de tendances, boxplots, heatmaps.
 - Ces résultats montrent que le modèle prédit les ventes avec une précision remarquable.

 ### 7. Visualisation des performances du modèle
 #### Valeurs réelles vs. prédites
 - Les points proches de la diagonale indiquent une excellente précision.

![Valeurs reelles et predites](IMAGES/Capture%20d’écran_26-10-2025_224425_.jpeg)

#### Distribution des erreurs (résidus)
 - Confirme la stabilité et la symétrie des erreurs autour de zéro.

![Distribution des erreurs](IMAGES/Capture%20d’écran_26-10-2025_224447_.jpeg)

#### Importance des variables
 - Met en évidence les facteurs les plus déterminants pour les ventes.

![Importance des variables](IMAGES/Capture%20d’écran_26-10-2025_224553_.jpeg)

 ### 7. Résultats et interprétation

Les variables les plus influentes sont :

Variable	Importance	Interprétation
 - coffee_name	/0.87	/Type de café : facteur dominant des ventes
 - Monthsort	/0.11	/Impact saisonnier modéré
 - hour_of_day, Weekdaysort	/0.01	/Impact faible
 - cash_type	/ 0.00	/Aucun effet significatif
 - Variable cible : money

 ### 8. Optimisation du modèle (Grid Search)

 - Une recherche par grille (Grid Search CV) a permis d’ajuster les hyperparamètres pour maximiser le score R² :

    - Meilleurs paramètres : max_depth=10, n_estimators=200, min_samples_split=10
    - Score R² : 0.978

#### Visualisation des performances selon les paramètres
![heatmap des peroformances du modele](IMAGES/Capture%20d’écran_26-10-2025_224725_.jpeg)

 ### 8. Recommandations

 - Mettre l’accent sur les cafés les plus rentables
 - Adapter les stocks et le personnel aux périodes de forte demande
 - Organiser des promotions ciblées durant les périodes creuses
 - Mettre en place un tableau de bord Power BI / Tableau pour le suivi en temps réel.

 ### 9. Conclusion
 - Le projet démontre la puissance du Machine Learning dans la prédiction des ventes.
 - Le modèle Random Forest offre une fiabilité exceptionnelle (R² ≈ 0.98).
 - Les ventes dépendent principalement du type de café et du mois, tandis que les autres facteurs ont un effet moindre.
 - L’exploitation intelligente des données permet donc d’améliorer la performance commerciale et d’orienter les décisions stratégiques.

### 10. Références
 - Kaggle — Coffee Sales Dataset
 - Wes McKinney (2018), Python for Data Analysis, O’Reilly Media
 - Géron, A. (2022), Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow
 - Documentation officielle : pandas, matplotlib, seaborn, scikit-learn
 - Articles de Medium et Towards Data Science sur les analyses EDA et la visualisation de données.

 ## Remerciements
Nous remercions :
 - Dieu Tout-Puissant, pour Sa guidance et Sa force
 - Wedter Jérôme, pour son accompagnement constant
 - Madame Castelline, pour son encadrement bienveillant
 - Djovany et mes collègues du Bootcamp pour leur soutien et leur esprit d’équipe.
 - Enfin, nous remercions tous ceux qui, directement ou indirectement, contribué à ce parcours d’apprentissage, et sans qui ce projet n’aurait pas vu le jour.