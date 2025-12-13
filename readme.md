# Modélisation et Backtesting de la Value-at-Risk

## Description

Ce projet compare différentes méthodes de calcul de la Value-at-Risk (VaR) sur trois types de portefeuilles financiers : actions, cryptomonnaies et mixte. L'objectif est d'évaluer la performance et la stabilité de chaque approche à travers des tests statistiques rigoureux.

## Auteurs

- TOULBA Boubacar
- CHEMLAL Ismail
- IRAQI Hiba

Encadré par : Professeur HICHAM Jenati  
Institution : Institut National de Statistique et d'Économie Appliquée (INSEA)  
Année : 2025-2026

## Structure du Projet

### 1. Collecte des Données
- Période : 2017-2025
- Sources : Yahoo Finance (yfinance)
- Portefeuilles :
  - P_A : 10 actions tech (AAPL, MSFT, AMZN, GOOGL, NVDA, META, NFLX, AMD, TSLA, QCOM)
  - P_B : 2 cryptomonnaies (BTC, ETH)
  - P_C : Mix 50/50 (SPY + BTC)

### 2. Méthodes Implémentées

**Méthodes Classiques**
- Historical Simulation (HS)
- Variance-Covariance (VC)
- EWMA (Exponentially Weighted Moving Average)

**Modèles Économétriques**
- GARCH(1,1) avec distribution Student-t

**Méthodes Monte-Carlo**
- MVN (Multivariate Normal)
- MVT (Multivariate Student-t)
- Copule-t

**Machine Learning**
- Régression Quantile Linéaire
- Gradient Boosting Quantile

### 3. Tests de Backtesting
- Test de Kupiec (1995) - couverture inconditionnelle
- Test de Christoffersen (1998) - indépendance
- Test Conjoint
- Expected Shortfall (ES)
- Zones de Bâle (Traffic Light)

## Organisation des Fichiers

```
var_project/
├── data/
│   ├── raw/              # Données brutes
│   └── processed/        # Rendements calculés
├── results/              # Résultats et graphiques
└── var_project.py        # Code principal
```

## Dépendances

```
numpy
pandas
yfinance
matplotlib
scipy
scikit-learn
arch
```

Installation :
```bash
pip install numpy pandas yfinance matplotlib scipy scikit-learn arch
```

## Utilisation

Le notebook est organisé en sections numérotées. Exécutez les cellules dans l'ordre :

1. Collecte et préparation des données
2. Méthodes baselines (HS, VC, EWMA)
3. Modèles GARCH
4. Simulations Monte-Carlo
5. Méthodes Machine Learning
6. Comparaison et classement final

## Résultats

Les résultats incluent :
- Prédictions VaR pour chaque méthode et portefeuille
- Statistiques de backtesting (p-values, taux de dépassement)
- Graphiques de séries temporelles
- Classement des modèles par performance
- Identification du meilleur modèle par combinaison (portefeuille, alpha)

Fichiers générés dans `results/` :
- `backtest_summary_*.csv` - Résultats par méthode
- `compare_all_methods_ranked.csv` - Classement complet
- `winners_by_portfolio_alpha.csv` - Meilleurs modèles
- `plot_*.png` - Visualisations

## Paramètres Principaux

- Fenêtre d'estimation : 500-750 jours
- Niveaux VaR : 1% et 5%
- Simulations Monte-Carlo : 10,000 scénarios
- Refit périodique : 5-20 jours

## Références

- Kupiec, P. (1995). "Techniques for Verifying the Accuracy of Risk Measurement Models"
- Christoffersen, P. (1998). "Evaluating Interval Forecasts"
- Bollerslev, T. (1986). "Generalized Autoregressive Conditional Heteroskedasticity"
- Koenker, R. (2005). "Quantile Regression"

## Licence

Projet académique - INSEA 2025-2026
