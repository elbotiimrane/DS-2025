🔥 COMPTE RENDU : Analyse du Dataset “Online Retail”


Introduction

L’analyse du dataset “Online Retail”, issu du UCI Machine Learning Repository, constitue une étude de cas complète pour comprendre les dynamiques réelles d’un site de commerce électronique. Le jeu de données regroupe plus d’une année de transactions, permettant d’examiner les comportements d’achat, la distribution des produits, la géographie des commandes et les modèles de ventes dans un contexte commercial international. L’objectif de cette étude est de préparer, nettoyer et explorer ces données afin d’en dégager des tendances utiles pour l’analyse marketing et commerciale.

1. Le Contexte Métier et la Mission

Le dataset provient d’une entreprise spécialisée dans la vente en ligne de produits décoratifs et d’articles variés. Le contexte métier est directement lié à l’activité e-commerce : gérer les transactions, suivre les clients, analyser la performance des produits et optimiser les ventes.
La mission assignée dans ce projet consiste à :

Inspecter et nettoyer les données brutes afin de les rendre exploitables.

Comprendre les patterns d’achat grâce à des analyses exploratoires.

Produire des visualisations descriptives autour des produits, des clients et des ventes.

Structurer les données pour une éventuelle analyse avancée (RFM, clustering, prédiction).

Ce projet ne vise pas encore un modèle prédictif supervisé : l’objectif ici est d’établir une base propre et analysée, qui pourra ensuite servir à la modélisation.

2. Le Code Python (Laboratoire)

Le laboratoire Python s’articule autour de quatre blocs essentiels :

Chargement des données
Le dataset est extrait via ucimlrepo puis inspecté à l’aide de head() et info().
Cette étape confirme la présence de valeurs manquantes, d’anomalies sur les quantités et d’un besoin urgent de nettoyage.

Nettoyage initial
Les transformations majeures sont :

Conversion de InvoiceDate en format datetime.

Suppression des lignes avec CustomerID ou StockCode manquants.

Filtrage des quantités et prix unitaires négatifs ou nuls.

Calcul de TotalPrice (Quantity × UnitPrice).

Construction d’indicateurs
Ajout de la variable InvoiceMonth pour permettre une analyse temporelle mensuelle des ventes.

Visualisations
Création de plusieurs graphiques clés :

Distribution logarithmique des prix unitaires

Classement des pays par volume de transactions

Série temporelle des ventes mensuelles

Top produits générant le plus de revenus

Distribution des quantités vendues

Ce laboratoire permet de transformer un dataset brut en une structure exploitable et visuellement analysée.

3. Analyse Approfondie : Nettoyage (Data Wrangling)

Le dataset brut présente plusieurs problèmes typiques des données réelles : quantités négatives (retours), prix aberrants, valeurs manquantes.
Le nettoyage a permis de :

Réduire fortement le bruit : suppression de toutes les lignes inutilisables.

Rétablir la cohérence métier : Quantity > 0 et UnitPrice > 0 garantissent l’analyse de ventes réelles.

Éliminer les biais : CustomerID manquant implique impossibilité d’analyses clients fiables.

Créer une variable clé : TotalPrice permettant d’effectuer des analyses financières.

On note que le nettoyage réduit significativement la taille du dataset, ce qui montre à quel point les données commerciales peuvent être imparfaites dans leur état brut.

4. Analyse Approfondie : Exploration (EDA)

L’exploration exploratoire met en lumière plusieurs enseignements :

Les prix unitaires sont extrêmement asymétriques, justifiant l’utilisation d’une transformation logarithmique pour stabiliser la distribution.

Certains pays dominent largement les transactions, notamment le Royaume-Uni, ce qui suggère un marché très concentré.

Les tendances mensuelles révèlent des pics saisonniers, cohérents avec les ventes saisonnières d’articles décoratifs (fin d’année notamment).

Une faible proportion de produits génère une forte part du revenu, confirmant la loi de Pareto dans le e-commerce.

L’EDA met en évidence des comportements typiques du marché digital : forte long tail de produits, importance des best-sellers, saisonnalité forte.

5. Analyse Approfondie : Méthodologie (Split)

Dans ce projet, aucun modèle prédictif supervisé n’a été entraîné, donc aucun split Train/Test n’a été mis en place.
Cependant, si le dataset devait servir à une modélisation en Machine Learning, la méthodologie de split serait la suivante :

Split temporel (Time Series Split) et non random, car les données sont chronologiques.

Entraînement sur les mois 2010–2011, test sur la fin 2011.

Validation croisée par blocs temporels pour éviter les fuites de données.

Cette précision méthodologique est importante car un simple train_test_split serait incorrect compte tenu de la structure temporelle des transactions.

6. Focus Théorique : L’Analyse Descriptive (pas d’algorithme ML utilisé)

Dans ce projet, aucun algorithme de Machine Learning n’a été appliqué.
Le focus théorique se concentre donc sur l’analyse descriptive et les concepts associés :

Distribution : comprendre les formes des variables (skewness, outliers).

Séries temporelles : construction d’indicateurs mensuels.

Analyse géographique : concentration par pays.

Analyse produit : identification des best-sellers.

Si un modèle devait être intégré plus tard, le choix le plus cohérent serait :

Clustering (KMeans ou HDBSCAN) pour segmenter les clients

Random Forest pour prédire des patterns d’achat ou détecter des anomalies

Apriori pour analyser les associations de produits

Mais ce n’était pas l’objectif de ce projet.

7. Analyse Approfondie : Évaluation (L’Heure de Vérité)

Dans un projet sans apprentissage automatique, l’évaluation ne porte pas sur des métriques de ML mais sur :

La qualité du nettoyage : les anomalies ont-elles été correctement traitées ?

La pertinence des visualisations : permettent-elles de conclure ?

La cohérence métier : les insights reflètent-ils la réalité e-commerce ?

Les visualisations montrent clairement :

des distributions asymétriques,

des ventes très concentrées,

une saisonnalité forte,

des comportements clients hétérogènes.

L’analyse est donc fiable, cohérente, et exploitée correctement pour un contexte débutant–intermédiaire.

Conclusion du Projet

Le projet Online Retail a permis de transformer un dataset brut en un ensemble structuré, nettoyé et analysé de manière professionnelle. Cette étude met en évidence les défis classiques des données e-commerce (retours, valeurs aberrantes, données manquantes) ainsi que les grandes tendances du marché (saisonnalité, concentration des produits, domination géographique). L’analyse descriptive constitue une base solide pour toute extension future vers des modèles prédictifs tels que le clustering clients ou l’analyse des paniers. Le travail réalisé prépare efficacement le terrain pour une modélisation avancée et offre une compréhension approfondie d’un dataset commercial réel.
