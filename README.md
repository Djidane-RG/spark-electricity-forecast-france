# Prédiction de la consommation électrique française avec Spark et Cassandra.

<p align="center">
  <img src="https://github.com/user-attachments/assets/6e6da88b-7fe6-4250-93ad-870d7cf7eb47" alt="image" width="600">
</p>

## Contexte :

Ce projet a été réalisé dans le cadre du projet final du <a href="https://formation.cnam.fr/rechercher-par-discipline/certificat-de-specialisation-analyste-de-donnees-massives-669531.kjsp" target="_blank"> [certificat de spécialisation Analyste de données massives](https://www.cnam.fr/formation/electronique-informatique-telecommunication/informatique-systemes-dinformation-et-numerique/certificat-de-specialisation-analyste-de-donnees-massives-5) du Conservatoire National des Arts et Métiers (Cnam) dont le rapport projet est situé à cette [adresse](Rapport_Projet_UASB03_2025.pdf).
Depuis janvier 2024, toutes les données publiques de Météo-France disposent d'une possibilité d'accès sans aucun frais et sont gratuitement réutilisables. Météo France met notamment à disposition gratuitement via [une API dédiée](https://portail-api.meteofrance.fr/web/fr/api/DonneesPubliquesClimatologie) les données climatologiques générées par des stations situées en métropole et outre-mer. 
Ces centaines de stations génèrent différents types de données comme la température, la quantité et la durée des précipitations ou encore la force du vent à intervalle régulier (toutes les heures voire toutes les six minutes pour les données concernant les précipitations). 
Ces données sont également historisées et il est possible de remonter plusieurs années auparavant afin d’obtenir des informations sur le climat dans différentes zones données.
Open Data Réseaux Énergies (ODRE) met pour sa part à disposition plusieurs jeux de données sur la consommation électrique en France. L’un des jeux de données présente les courbes de consommation régionale électrique (mis à jour toutes les 15 minutes en Mégawatt) 
Ce jeu de données peut également être téléchargé [via une API](https://odre.opendatasoft.com/explore/dataset/eco2mix-regional-tr/table/?disjunctive.libelle_region&disjunctive.nature&sort=-date_heure) qui autorise la recherche selon différents paramètres.



## Objectifs poursuivis / livrables : 

Il existe déjà de nombreux travaux sur la prédiction de la consommation électrique, ce projet propose avec modestie une approche prenant appui sur les données mises à disposition du grand public.
Les principaux objectifs du projet sont donc les suivants : 
* Une étude de la corrélation entre les variables climatiques et la consommation électrique nationale et régionale française. Est-elle significative ? Est-ce que certaines variables climatiques ont un impact plus ou moins important sur la consommation électrique.
* La création d’un modèle permettant de prédire à partir de différentes variables dont les variables climatiques générées par les stations la consommation électrique potentielle régionale française.


## Étapes : 

Afin de répondre à ces différents objectifs, les étapes du projet ont été les suivantes : 
* Analyse d’un échantillon de données provenant des API de météo France et ODRE afin de confirmer qu’il existe un lien entre la consommation électrique et les variables des capteurs climatiques.
* Identification des correspondances possibles entre les variables des capteurs climatiques et celles du modèle atmosphérique AROME.
* Création de la base de données qui sera utilisée pour stocker les différentes variables, pour créer le modèle et l’appliquer aux données. 
* Création du modèle prédictif de la consommation et test des performances. 
* Récupération des données AROME et application du modèle prédictif.

|Nom du notebook |Objectifs | Lien |
|------|-------------|------|
|0-exploration-d-un-échantillon-de-données-2025.ipynb|Exploration des données météo et analyse des corrélations|[ici](notebooks/0-exploration-d-un-échantillon-de-données-2025.ipynb)|
|1-Sélection_des_données,_pré-traitement_et_stockage_dans_Cassandra_2025|Récupération des données des stations météo en région Grand Est et stockage de celles-ci dans Apache Cassandra|[ici](notebooks/1-Sélection_des_données,_pré-traitement_et_stockage_dans_Cassandra_2025.ipynb)|
|2-Création du modèle prédictif|Création du modèle avec la régression linéaire et les forêts aléatoires, tests des performances|[ici](notebooks/2-Création_du_modèle_prédictif_de_la_consommation_electrique-2025.ipynb)|
|3-Recuperation des cartes_AROME et calcul de haversine|Récupération des données du modèle atmosphérique AROME et stockage dans Cassandra|[ici](notebooks/3-Recuperation_des_cartes_AROME_et_calcul_de_haversine-2025.ipynb)|
|4- Application du modèle|Application du modèle sur les données|[ici](notebooks/4-Application_du_modèle.ipynb)|


## Architecture : 

Les détails sur l'architecture de stockage utilisée (Cassandra), le moteur de calcul distribué (Spark) ou encore les résultats obtenus sont disponibles dans le rapport projet situé à la racine du dépôt à cette [adresse](Rapport_Projet_UASB03_2025.pdf).
