# Exercice Data Science Niveau Entretien : Prédiction et Analyse des Ventes

## Contexte
Tu es en entretien technique pour un stage de Data Scientist. Le recruteur te fournit ce jeu de données de ventes de chocolats et souhaite évaluer ta capacité à nettoyer, explorer et modéliser des données réelles.

**Objectif** : Construire un pipeline complet allant du nettoyage des données à la modélisation prédictive du montant des ventes (`Amount`).

---

## Consignes

### 1. Ingénierie des Données (Data Engineering & Cleaning)
*   **Environnement** : Charge le chemin du fichier CSV via un fichier `.env` (bonne pratique de sécurité).
*   **Nettoyage Monétaire** : La colonne `Amount` est sale (`$`, `,`). Nettoie-la et convertis-la en `float`.
*   **Gestion des Dates** : Convertis la colonne `Date` en format `datetime`.
*   **Contrôle Qualité** : Vérifie s'il y a des valeurs aberrantes ou négatives dans `Boxes Shipped` et `Amount`. Si oui, traite-les (suppression ou imputation).

### 2. Feature Engineering
Crée de nouvelles variables pertinentes pour l'analyse :
*   **`Month`** et **`Year`** : Extraits de la date.
*   **`Product_Category`** : Crée une catégorie simplifiée à partir du nom du produit (`Product`).
    *   Si le nom contient "Dark" -> Catégorie "Dark Choco".
    *   Si le nom contient "Nut", "Peanut", "Almond" -> Catégorie "Nut Choco".
    *   Si le nom contient "White" -> Catégorie "White Choco".
    *   Sinon -> "Other".
*   **`Price_Per_Box`** : Calcule le prix unitaire moyen par boîte pour chaque ligne (`Amount` / `Boxes Shipped`).

### 3. Analyse Exploratoire (EDA)
Produis au moins 3 visualisations (avec Matplotlib ou Seaborn) pour répondre aux questions suivantes :
*   **Saisonnalité** : Y a-t-il une tendance des ventes au cours de l'année (somme des ventes par mois) ?
*   **Distribution** : Quelle est la distribution des prix unitaires (`Price_Per_Box`) ? Est-ce qu'elle varie selon le pays ? (Utilise un Boxplot).
*   **Corrélation** : Y a-t-il une corrélation entre `Boxes Shipped` et `Amount` ? (Affiche un Scatter plot et le coefficient de corrélation de Pearson).

### 4. Modélisation (Machine Learning)
L'objectif est de prédire le montant total d'une vente (`Amount`).

*   **Préparation** :
    *   Les variables explicatives (Features) seront : `Boxes Shipped`, `Country`, `Product_Category`.
    *   La variable cible (Target) est : `Amount`.
    *   Encode les variables catégorielles (`Country`, `Product_Category`) avec du **One-Hot Encoding** (`pd.get_dummies`).
*   **Split** : Divise ton jeu de données en ensemble d'entraînement (80%) et de test (20%) avec `train_test_split`.
*   **Entraînement** : Entraîne une **Régression Linéaire** simple (`LinearRegression` de Scikit-Learn).
*   **Évaluation** :
    *   Calcule le **R²** (coefficient de détermination) sur le jeu de test.
    *   Calcule le **RMSE** (Root Mean Squared Error) pour estimer l'erreur moyenne de tes prédictions en dollars.
*   **Interprétation** : Affiche les coefficients du modèle. Quel Pays ou Catégorie de produit impacte le plus positivement le montant de la vente ?

---

## Critères d'évaluation (Checklist)
*   [ ] Le code est structuré, commenté et utilise des fonctions si nécessaire.
*   [ ] Les graphiques sont titrés et lisibles.
*   [ ] La gestion des erreurs (chemins fichiers, types de données) est robuste.
*   [ ] L'interprétation des résultats du modèle est claire.
