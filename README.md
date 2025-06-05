OpenOrderFramework
==================

Please note that this uses Asp.net Identity Code First migration which means the database is generated from the code. To do this the first time simply compile the app and run: 

    update-database
    
From the package manager console and then run the app. 

To login as an admin try the following

    user: admin@gmail.com
    password: abc123
    
(Please change that password if your going to do anything other than use this for fun.)


A lightweight ASP.NET MVC 5 cart/order framework. It can be customized to handel any type of online shopping. Users can place an order and that order is sent via e-mail to the store's owners

Find out more at http://louiebacaj.com/a-lightweight-shopping-cart-web-application-in-asp-net-mvc-5/#

Most local shops don’t have the fancy infrastructure of say Amazon, but they still want to setup a simple online order system. They want an email with an order that they ship or deliver and they want to actually just charge the order in their own store and don’t want some fancy credit card integration (although I will add that option at some point and is easy enough to add). This web application provides the features needed to place an order online and emails it out with the very basic information about that order. 


Although it was originally designed for local restaurants to receive orders from their website and receive an email with the order it has many other uses and in actuality any type of store can be setup to work with this. 


Key Features:

    1)	Designed as an easy way to setup an ASP.NET MVC 5 website/store that can easily take orders. 
    
    2)	Users can place order as a guest or signup and their info will be saved to a SQL Server express database.
    
    3)	Uses bootstrap framework for the UI with a Boostwatch.com theme configured.
    
    4)	Uses Asynchronous controllers in most cases so the app remains responsive.
    
    5)	Uses code first migration to generate the database and setup the models and configure an admin and guest account for maintenance. (admin@gmail.com with pass abc123 for your local testing)
    
    6)	Authentication and authorization system is provided via Identity 2.0 and is simple and secure.
    
    7)	Admin accounts can add groups of items that will be sold.
    
    8)	Admin accounts can modify and add new items for sale 
    
    9)	Admin accounts can view lists of orders track some analytics via D3 charts (work in progress).
    
    10)	Guest account provided out of the box for quick checkout.
    
    11)	Roles available via Identity.
    
    12)	External account login supported such as Google, Facebook, etc. (Work in progress)
    
    13)	Emailing system leverages Mailgun.com but other cloud email services should work fine.
    
    14)	Paging of items on the UI and many other UI libraries such as jQuery used to add UI.

Ce projet s’inscrit dans la démarche de modernisation continue des solutions qui soutiennent les processus de compensation gouvernementale à la LGR. Le système en place, E3CG — partiellement codé en COBOL et mis en production en 1994 — arrive au terme de son cycle de vie.

L’initiative comporte deux axes majeurs :
	1.	Mise à niveau technologique
– Conversion des chaînes différées COBOL exécutées au central vers des services web ou des chaînes différées bâties sur le Framework .NET du départemental.
	2.	Harmonisation de la nomenclature
– Refonte complète des noms de tables, règles métiers et variables portant le préfixe « E3 », afin de les aligner sur l’architecture du nouveau système FX.

Cette dernière phase de modernisation ouvrira la voie au retrait définitif d’E3CG, offrant ainsi une plateforme plus pérenne, agile et cohérente avec les standards technologiques actuels.



Ce projet poursuit l’effort de modernisation des solutions qui soutiennent les processus de compensation gouvernementale à la LGR. Le système existant, E3CG—partiellement développé en COBOL et déployé en 1994—atteint désormais la fin de son cycle de vie.

L’initiative se décline en deux volets :
	1.	Renouvellement technologique
• Migrer les chaînes différées COBOL du centre vers des services Web ou des chaînes différées bâtis sur le Framework .NET du secteur départemental.
	2.	Uniformisation de la nomenclature
• Revoir intégralement les noms de tables, règles métiers et variables comportant le préfixe « E3 » afin de les harmoniser avec l’architecture du nouveau système FX.

Cette modernisation mènera au déclassement complet d’E3CG et dotera l’organisation d’une plateforme durable, souple et conforme aux standards technologiques actuels.

Ce projet s’inscrit dans la continuité des travaux de modernisation qui appuient les processus de compensation gouvernementale à la LGR. Le système E3CG, déployé en 1994 et partiellement développé en COBOL, demeure opérationnel ; l’initiative vise donc son adaptation plutôt qu’une refonte complète.

Le mandat se décline en deux volets :
	1.	Évolution technologique
• Transposer les chaînes différées COBOL exécutées au central vers des services Web ou des chaînes différées conçus sur le Framework .NET, hébergés au départemental.
	2.	Harmonisation de la nomenclature
• Actualiser l’ensemble des noms de tables, règles métier et variables comportant le préfixe « E3 » afin de les aligner sur l’architecture du nouveau système FX.

Ces travaux permettront de réduire la dépendance à E3CG tout en assurant une transition fluide vers des standards technologiques plus modernes et mieux intégrés à l’écosystème FX.
