# 🔥 Prédiction du risque d’incendie agricole par Machine Learning

## 📌 Présentation du projet

Ce projet a été réalisé dans le cadre d’un **projet tutoré en Data Science**.

L’objectif est d’étudier et de prédire la survenue de sinistres incendie en milieu agricole à partir de caractéristiques issues d’un portefeuille d’assurance et de variables climatiques.

Le projet met en œuvre une démarche complète de Data Science, allant de la préparation et de l’exploration des données jusqu’à la construction, l’évaluation et l’interprétation de plusieurs modèles de Machine Learning.

---

## 🎯 Objectif

L’objectif principal est de construire un modèle capable d’estimer le risque de survenue d’un incendie agricole.

La variable cible est définie de la manière suivante :

* `Y = 1` : au moins un sinistre incendie a été observé ;
* `Y = 0` : aucun sinistre incendie n’a été observé.

L’une des principales difficultés du projet réside dans le **fort déséquilibre des classes**, les sinistres incendie représentant une faible proportion des observations.

---

## 📊 Données

Le jeu de données initial contient environ :

* **383 000 observations** ;
* **374 variables initiales** ;
* des variables climatiques ;
* des informations géographiques ;
* des caractéristiques agricoles ;
* des informations relatives aux contrats d’assurance.

Compte tenu de la dimension importante du jeu de données, un travail de sélection, de nettoyage et de transformation des variables a été réalisé avant la phase de modélisation.

---

## 🧹 Préparation des données

Plusieurs étapes de preprocessing ont été mises en œuvre :

* fusion des différentes sources de données ;
* analyse des valeurs manquantes ;
* nettoyage des données ;
* sélection des variables pertinentes ;
* transformation des variables numériques ;
* encodage des variables catégorielles ;
* standardisation de certaines variables ;
* séparation des données en ensembles d’entraînement et de test ;
* stratification selon la variable cible ;
* prise en compte du déséquilibre des classes ;
* utilisation de méthodes telles que **SMOTE** et la pondération des classes.

Des indicateurs climatiques synthétiques ont également été construits afin de mieux représenter certains phénomènes environnementaux, notamment :

* les épisodes de forte chaleur ;
* les vents forts ;
* les conditions de sécheresse ;
* les amplitudes thermiques.

---

## 🔎 Analyse exploratoire des données

Une analyse exploratoire a été réalisée afin d’étudier les relations entre les sinistres incendie, les caractéristiques des contrats et les conditions climatiques.

Les analyses comprennent notamment :

* statistiques descriptives ;
* étude de la distribution des variables ;
* analyse du taux de sinistres ;
* comparaison des profils climatiques ;
* analyse des corrélations ;
* tests statistiques de **Mann-Whitney** ;
* visualisations graphiques.

Certaines variables liées notamment au **vent** et aux **précipitations** présentent des relations significatives avec la survenue des incendies.

---

## 📉 Réduction de dimension

### Analyse en Composantes Principales — ACP

Une **Analyse en Composantes Principales (ACP)** a été appliquée afin de réduire la redondance entre les nombreuses variables climatiques corrélées.

Environ **9 composantes principales permettent d’expliquer près de 80 % de la variance climatique**.

### t-SNE

La méthode **t-SNE** a également été utilisée afin d'explorer la structure des observations dans un espace de dimension réduite.

---

## 🧩 Apprentissage non supervisé

Deux approches de clustering ont été étudiées.

### K-Means

L’algorithme **K-Means** a été utilisé afin d’identifier des groupes d’observations présentant des profils climatiques similaires.

### Classification Ascendante Hiérarchique

Une approche de **clustering hiérarchique agglomératif** a également été appliquée afin de comparer la structure des groupes obtenus.

La comparaison des deux méthodes a conduit à un **Adjusted Rand Index (ARI) d’environ 0,89**, indiquant une forte concordance entre les partitions obtenues.

---

## 🤖 Modèles de Machine Learning

Plusieurs algorithmes de classification supervisée ont été entraînés et comparés :

* Régression logistique ;
* Arbre de décision CART ;
* Random Forest ;
* XGBoost ;
* LightGBM.

Les performances des modèles ont été étudiées à l’aide de plusieurs métriques :

* ROC-AUC ;
* F1-score ;
* Average Precision ;
* précision ;
* rappel ;
* matrice de confusion ;
* courbe ROC ;
* courbe Precision-Recall.

---

## 🏆 Principaux résultats

Parmi les modèles testés, le **Random Forest** présente les meilleures performances globales dans les analyses réalisées, avec un :

**ROC-AUC ≈ 0,727**

L’arbre de décision CART atteint une AUC d’environ **0,705**, tandis que les modèles de régression logistique se situent autour de **0,70**.

Les performances de **XGBoost** et **LightGBM** se sont révélées plus faibles sur les configurations testées dans ce projet.

Compte tenu du fort déséquilibre entre les classes, une attention particulière a également été portée au **choix du seuil de classification**, le seuil classique de 0,5 n’étant pas nécessairement le plus approprié pour la détection d’événements rares.

---

## 🔍 Interprétation des modèles

La méthode **SHAP (SHapley Additive exPlanations)** a été utilisée afin d’améliorer l’interprétabilité des prédictions.

L’analyse permet d’identifier les variables contribuant le plus aux prédictions du modèle.

Parmi les variables importantes figurent notamment :

* le capital assuré ;
* la surface agricole ;
* la zone géographique.

Certaines variables climatiques liées au **vent**, aux **précipitations** et aux **températures** présentent également des relations avec la survenue des sinistres.

---

## 💡 Principaux enseignements

Ce projet met notamment en évidence :

1. **L'importance du déséquilibre des classes** dans la prédiction d'événements rares comme les incendies agricoles.

2. **L'intérêt de comparer plusieurs familles d'algorithmes** plutôt que de se limiter à un seul modèle.

3. **L'importance de l'interprétabilité** des modèles lorsque le Machine Learning est appliqué à des problématiques de risque.

4. Le potentiel de l'association entre **données agricoles, données contractuelles et informations climatiques** pour développer des outils d'aide à l'évaluation du risque.

---

## 🛠️ Technologies et méthodes utilisées

### Langage

`Python`

### Principales bibliothèques

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Imbalanced-learn
* Statsmodels
* XGBoost
* LightGBM
* SHAP

### Méthodes

`Machine Learning` · `Classification` · `Random Forest` · `Régression logistique` · `CART` · `XGBoost` · `LightGBM` · `ACP` · `t-SNE` · `K-Means` · `Clustering hiérarchique` · `SMOTE` · `SHAP` · `Tests statistiques`

---

## 📂 Organisation du dépôt

```text
climate-risk-machine-learning/
│
├── README.md
├── Projet_Risque_Climatique_Machine_Learning.ipynb
├── requirements.txt
└── .gitignore
```

Le notebook principal contient les différentes étapes de l'analyse, depuis l'exploration des données jusqu'à l'évaluation et l'interprétation des modèles.

---

## 👥 Auteurs

**Mame Cheikh Anta CASSET**
**Moussa HANNE**

Projet tutoré — Data Science / Machine Learning.

---

## 🚀 Perspectives

Plusieurs améliorations peuvent être envisagées pour poursuivre ce travail :

* approfondir le feature engineering des variables climatiques ;
* optimiser davantage les hyperparamètres ;
* tester d'autres stratégies adaptées aux événements rares ;
* améliorer la calibration des probabilités ;
* étudier différentes méthodes de sélection de variables ;
* approfondir l'interprétation des prédictions avec SHAP ;
* tester la robustesse du modèle sur de nouvelles données.

---

## 📌 Conclusion

Ce projet illustre la mise en œuvre d'une **chaîne complète de Machine Learning appliquée à une problématique agricole et climatique** : préparation des données, analyse statistique, réduction de dimension, clustering, classification supervisée, gestion du déséquilibre des classes, comparaison des modèles et interprétation des prédictions.

Il met également en évidence les difficultés propres à la **prédiction d'événements rares** et l'intérêt d'associer méthodes statistiques et Machine Learning pour l'analyse du risque agricole.
