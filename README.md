# Le Projet

## Préambule
Le projet se déroulera sur toute la période par équipe de deux. Tout comme le cours, le projet sera découpé en 4 jalons (voir Readme du repository Cours).
La notation se fera sur les critères suivants :

<ul>
<li>Les fonctionnalités implémentées (et leurs bons fonctionnements).</li>
<li>La qualité du code (commentaires, tests, normes de développement, nommage des variables, etc.).</li>
<li>Le respect des consignes et de l'architecture du projet.</li>
<li>La compilation (pas d’erreur, le moins de warning possible).</li>
<li>L'ergonomie des interfaces.</li>
</ul>

Le projet sera à rendre à la fin de la période avec la base de données.

## Problématique : 
Monsieur X se lance dans la création d’une entreprise destinée à vendre et à livrer des denrées alimentaires (produits frais) aux restaurateurs locaux. Son objectif est de proposer à ces clients potentiels des produits frais achetés chez les producteurs locaux avec lesquels il est en contact. Afin de vendre ses produits frais dans les meilleures conditions, il  souhaiterait mettre en place un système complet pour démarrer son entreprise avec les éléments suivants :
<ul>
<li>Une base de données permettant de stocker tous ses produits, ses commandes, ses clients, etc.</li>
<li>Une application installable sous forme d’un exécutable pour gérer les stocks c’est-à-dire les entrées et sorties de produit. Cette application sera installée sur plusieurs postes dans ses entrepôts et accédera à la base de données.</li>
<li>Une application web pour permettre à ses futurs clients de passer commande rapidement et facilement et de suivre l’évolution de la commande.</li>
<li>Un service web pour « communiquer » avec les personnes en charge des livraisons qui sont équipées d’un PDA. Ce service connecté à la base permettra à Monsieur X de suivre le livreur et de déterminer les commandes livrées et à livrer.</li>
</ul>

## Solution envisagée :

Afin de répondre à tous les besoins de Monsieur X en utilisant exclusivement des technologies Microsoft, voici la solution à mettre en place :
<ul>
<li>Une base de données SQL Server.</li>
<li>Une bibliothèque de classe pour gérer la couche d’accès aux données (J1).</li>
<li>Des tests unitaires pour ajouter des cas de test à la couche de données (J1) et assurer la pérennité de la couche de données.</li>
<li>Une application WPF pour concevoir une application client lourd permettant de gérer les stocks de marchandises (J2).</li>
<li>Un service WCF pour gérer la synchronisation entre la base de données et une application mobile « virtuelle » (J3).</li>
<li>Une application Web pour offrir au grand public un portail permettant la commande de produit (J4).</li>
</ul>

## La base de données :
Afin de faciliter le développement et le déploiement de l’application, la base de données sera volontairement au format « mdf ». Nous ne travaillerons pas sur une base de données hébergée sur un serveur SQL. Cette méthode ne change en rien la méthode de développement et surtout évite l’installation et la configuration d’un serveur SQL. Ce fichier au format mdf sera à rendre avec la solution complète à la fin du TP.

## Le schéma de la base de données :
Voici la base de données que Monsieur X a imaginée :

![alt tag](https://coursdotnetiut.files.wordpress.com/2016/05/bdd.png)

NB : Ce schéma pourra être amené à être complété au fur et à mesure du projet mais représente une base de travail indispensable à réaliser pour la suite du projet.

## L’architecture de la solution :
A des fins de maintenance, Monsieur X souhaite que l’ensemble du projet soit stocké dans une seule et unique solution Visual Studio. La solution comprendra donc plusieurs « sous-projets ». Le découpage des sous-projets conseillé est le suivant :
<ul>
<li>Un projet de type Bibliothèque pour la couche d’accès aux données.</li>
<li>Un projet de type application WPF pour l’application permettant de gérer les stocks.</li>
<li>Un projet de type application WCF pour créer le service permettant la synchronisation de ses données.</li>
<li>Un projet de type ASP.NET MVC pour créer l’application web permettant de vendre les produits sur internet.</li>
<li>Autant de projet de type Test Unitaire qu’il y aura de test à réaliser.</li>
</ul>

D’autres projets peuvent être ajoutés à cette solution pour compléter certains projets (exemple : un projet de type console pour tester la couche d’accès aux données dans un premier temps). La base de données au format présenté précédemment se placera dans le projet de la <u>couche d’accès<u>.
