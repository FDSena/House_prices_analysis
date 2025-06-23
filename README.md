# House_price_analysis

Ce projet vise à prédire les prix de vente des maisons à Ames, Iowa, à partir de données fournies dans le cadre de la compétition Kaggle **"House Prices - Advanced Regression Techniques"**.

## 📂 Données

Le jeu de données est composé de 79 variables expliquant chaque vente résidentielle en détail (surface, qualité des matériaux, nombre de garages, présence de piscine, etc.).

- `train.csv` : données d'entraînement (1460 lignes avec le prix de vente connu)
- `test.csv` : données de test (sans `SalePrice`, utilisé pour la soumission Kaggle)
- `submission.csv` : fichier de soumission contenant les prédictions

## 🔧 Prétraitement

- Analyse des valeurs manquantes  
- Remplissage des colonnes avec des valeurs `"None"` ou `0` selon le type de variable  
- Création de nouvelles variables comme `HasPool` (présence ou non d'une piscine)  
- Encodage des variables catégorielles avec `LabelEncoder`  
- Suppression des variables très faiblement corrélées avec le prix (`corr < 0.05`)

## 📊 Modélisation

Le modèle utilisé est un **Gradient Boosting Regressor** avec les paramètres suivants :

python
GradientBoostingRegressor(n_estimators=100, learning_rate=0.1, random_state=42)

## 📌 Score
Le fichier submission.csv a été soumis sur Kaggle, et le score public obtenu est :

🏆 RMSLE (Root Mean Squared Log Error) : 0.13954

Ce score reflète une bonne capacité de généralisation du modèle sur les données test.
