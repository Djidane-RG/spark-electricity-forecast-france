# Prédiction de la consommation électrique française avec Spark et Cassandra.

## Contexte :

Ce projet a été réalisé dans le cadre du projet final de la certification de spécialisation 'Analyste de données massives' du Conservatoire National des Arts et Métiers (Cnam).
Depuis janvier 2024, toutes les données publiques de Météo-France disposent d'une possibilité d'accès sans aucun frais et sont gratuitement réutilisables. Météo France met notamment à disposition gratuitement via une API dédiée les données climatologiques générées par des stations situées en métropole et outre-mer. 
Ces centaines de stations génèrent différents types de données comme la température, la quantité et la durée des précipitations ou encore la force du vent à intervalle régulier (toutes les heures voire toutes les six minutes pour les données concernant les précipitations). 
Ces données sont également historisées et il est possible de remonter plusieurs années auparavant afin d’obtenir des informations sur le climat dans différentes zones données.
Open Data Réseaux Énergies (ODRE) met pour sa part à disposition plusieurs jeux de données sur la consommation électrique en France. L’un des jeux de données présente les courbes de consommation régionale électrique (mis à jour toutes les 15 minutes en Mégawatt) 
Ce jeu de données peut également être téléchargé via une API qui autorise la recherche selon différents paramètres. Les données sont également historisées et il est possible de récupérer la consommation électrique régionale depuis janvier 2023 



## Objectifs poursuivis / Livrables : 

Il existe déjà de nombreux travaux sur la prédiction de la consommation électrique, ce projet propose avec modestie une approche prenant appui sur les données mises à disposition du grand public.
Les principaux objectifs du projet sont donc les suivants : 
* Une étude de la corrélation entre les variables climatiques et la consommation électrique nationale et régionale française. Est-elle significative ? Est-ce que certaines variables climatiques ont un impact plus ou moins important sur la consommation électrique.
* La création d’un modèle permettant de prédire à partir de différentes variables dont les variables climatiques générées par les stations la consommation électrique potentielle régionale française.


## Etapes : 

Afin de répondre à ces différents objectifs, les étapes du projet ont été les suivants : 
* Analyse d’un échantillon de données provenant des API de météo France et ODRE afin de confirmer qu’il existe un lien entre la consommation électrique et les variables des capteurs climatiques.
* Identification des correspondances possibles entre les variables des capteurs climatiques et celles du modèle atmosphérique AROME.
* Création de la base de données qui sera utilisée pour stocker les différentes variables, pour créer le modèle et l’appliquer aux données. 
* Création du modèle prédictif de la consommation et test des performances. 
* Récupération des données AROME et application du modèle prédictif.

## Architecture : 

Les détails sur l'architecture de stockage utilisée ou encore les résultats obtenus sont disponibles dans le rapport projet situé à la racine de ce repository
