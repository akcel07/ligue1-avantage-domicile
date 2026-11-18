# Ligue 1 : jouer à domicile donne-t-il un avantage ?

Analyse de données en Python sur 5 saisons de Ligue 1 (2021/22 à 2025/26, soit 1 678 matchs) pour vérifier si les équipes qui jouent à domicile gagnent réellement plus souvent.

## Résultat principal

Jouer à domicile donne un avantage net, dans chacune des 5 saisons :

| Saison | Victoire extérieur | Nul | Victoire domicile |
|--------|-------------------:|----:|------------------:|
| 2021/22 | 30,5 % | 26,8 % | 42,6 % |
| 2022/23 | 32,9 % | 24,2 % | 42,9 % |
| 2023/24 | 34,3 % | 26,5 % | 39,2 % |
| 2024/25 | 33,0 % | 20,3 % | 46,7 % |
| 2025/26 | 29,4 % | 24,5 % | 46,1 % |

- Les équipes à domicile gagnent entre **39,2 % et 46,7 %** de leurs matchs, contre **29,4 % à 34,3 %** pour les équipes à l'extérieur.
- L'écart moyen est d'environ **11 points**. Il est le plus élevé en 2025/26 (16,7 points) et le plus faible en 2023/24 (4,9 points), sans que l'avantage disparaisse.

## Démarche

1. **Explorer et nettoyer** une saison : valeurs manquantes (colonne `Referee` vide, supprimée), types (conversion de `Date`), doublons et valeurs aberrantes (scores plausibles).
2. **Analyser** : répartition des victoires à domicile, des nuls et des victoires à l'extérieur, et buts moyens marqués dans chaque cas.
3. **Vérifier sur 5 saisons** : assemblage des fichiers avec `pd.concat`, tableau croisé par saison avec `pd.crosstab`, calcul de l'écart domicile / extérieur et graphique comparatif.
4. **Conclure**, en précisant les limites.

## Limites

- Seulement 5 saisons et une seule ligue.
- Aucun test statistique pour confirmer que les écarts ne sont pas dus au hasard.
- Les données ne permettent pas d'expliquer pourquoi 2023/24 se distingue.

## Contenu du dépôt

- `ligue1_avantage_domicile.ipynb` : le notebook complet (code, graphiques et conclusion)
- `season-2122.csv` à `season-2526.csv` : les résultats de chaque saison

## Outils

Python, Pandas, Matplotlib, Jupyter.

## Lancer le projet

```bash
pip install pandas matplotlib jupyter
python -m notebook
```

Ouvrir `ligue1_avantage_domicile.ipynb`, puis **Kernel → Restart & Run All**. Les fichiers CSV doivent être dans le même dossier que le notebook.

## Source des données

Résultats de matchs fournis par [football-data.co.uk](https://www.football-data.co.uk/) (via [datahub.io](https://datahub.io/core/french-ligue-1)).

## Auteur

Akcel Arab — [GitHub](https://github.com/akcel07) · [LinkedIn](https://www.linkedin.com/in/arab-akcel-07922a24a)
