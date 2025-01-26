# Projet de Collecte de Données GitHub pour Node.js

## Contexte Général

Ce projet vise à collecter des données (issues, pull requests, etc.) depuis l’API REST de GitHub, à les convertir en fichiers Parquet, et à les charger dans DuckDB pour une analyse ultérieure.

## Étapes du Pipeline

1. **Récupération des Données via l’API REST de GitHub**
   - Utilisation d'un token personnel pour l'authentification.
   - Pagination pour récupérer toutes les données.
   - Points de terminaison visés : Issues, Pull Requests, Commits, Releases.

2. **Conversion des Données Brutes en Parquet**
   - Utilisation de Python et PyArrow pour convertir les données JSON en fichiers Parquet.

3. **Chargement dans DuckDB**
   - Création d'une base DuckDB locale.
   - Importation des fichiers Parquet dans des tables préfixées `raw_`.

4. **Organisation et Automatisation**
   - Hébergement des scripts dans un dépôt Git.
   - Utilisation de variables d'environnement pour le token GitHub.
   - Documentation et automatisation via un script principal.

## Prérequis

- Python 3.x
- Bibliothèques Python : `requests`, `pyarrow`, `duckdb`, `python-dotenv`
- Un token GitHub personnel pour l'authentification.

## Installation

1. Cloner le dépôt.
2. Installer les dépendances Python :
   ```bash
   pip install -r requirements.txt
   ```
3. Créer un fichier `.env` avec votre token GitHub :
   ```
   GITHUB_TOKEN=your_personal_access_token
   ```

## Exécution

Lancer le script principal pour exécuter le pipeline de collecte et de traitement des données :
```bash
python pipeline.py
```

## Recommandations

- Mettre en place un cron job pour lancer régulièrement la collecte.
- Surveiller les limites de l'API GitHub pour éviter les erreurs de dépassement de quota.

## Conclusion

Ce projet constitue une base solide pour la collecte, la conversion et le chargement de données GitHub, permettant une analyse approfondie des indicateurs clés pour le projet Node.js.
