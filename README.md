## Langage ubiquitaire :
    Ticket : Est une demande d'assistance créée par un Employé pour signaler un problème informatique. Il est traité par un Technicien et peut évoluer à travers plusieurs statuts.
    Analyser les performances du support : Permet de mesurer l’efficacité du support IT et d'optimiser son fonctionnement.
    Employé : Est un utilisateur du système de support IT. Il soumet des tickets pour signaler des incidents et suit l’évolution de leur résolution.
    Technicien : Est un membre de l’équipe IT chargé de résoudre les incidents signalés par les Employés.
    Responsable IT : Supervise le support technique et s’assure de son bon fonctionnement.
    Directeur des Opérations : Surveille l’impact du support IT sur la productivité de l’entreprise.
    Chef de Projet IT : Coordonne le déploiement de nouveaux outils et suit les problèmes liés à ces changements.
    Responsable de la Sécurité Informatique : S’assure que les incidents liés à la sécurité sont bien identifiés et traités avec rigueur.
    Document : Regroupe l’ensemble des procédures, guides et solutions recensées pour faciliter la résolution des incidents.

## Les sous-domaines : 
    -	Gestion du ticket (Core)
    -	Analyse des performances (Generic)
    -	Gestion du Personnel (Supporting)
    -	Documentation (Generic)

## Bounded Contexts :
    -	Gestion du ticket
        o	Création du ticket 
        o	Gestion du ticket 
        o	Commentaires

    -	Analyse des performances
        o	Satisfaction des utilisateurs
        o	Génération de rapport (stats)
        o	Temps moyen de résolution

    -	Gestion du Personnel
        o	Gestion des profils
        o	Attribution des tickets
        o	Gestion des performances individuel

    -	Documentation
        o	Historique des tickets
        o	Moyen de résolution
        o	Intégration avec les outils de gestions de tickets

##  Entités :
    -	Ticket 
    -	Employé 
    -	Technicien 
    -	Responsable IT 
    -	Chef de Projet IT 
    -	Documentation 


## Objets de valeur :

    - Statut du ticket (ouvert, en cours, résolu, fermé)
    - Priorité du ticket (basse, moyenne, haute, critique)
    - Type d’incident (logiciel, matériel, réseau, autre)
    - Délai de résolution estimé

## Agrégats :
    -	Tickets (crée, traité ou analyser par des employés)
        o	Id
        o	Description
        o	Statut
        o	Priorité
        o	Date de création
        o	Créateur
        o	Technicien
        o	Historique 

    -	Employé (créer, traite ou analyse un ticket)
        o	Id 
        o	Nom
        o	Prénom
        o	Département
        o	Liste des Tickets créés
        o	Rôle (technicien)
            	Spécialité
            	Tickets assignés
            	Historique des interventions
        o	Rôle (Responsable IT)
            	Liste des Tickets
            	Rapports de performances
        o	Rôle (Chef de projet IT)
            	Projets en cours
            	Tickets liés aux déploiements
            	Retours du support sur les nouveaux outils
        o	Rôle (Directeur des Opérations)
            	Temps de résolution

    -	Documentation (créer, accéder, modifier par des employées) 
        o	 Id
        o	Titre
        o	Contenu
        o	Catégorie
        o	Historique

    -	Statistique
        o	Id
        o	Nbr_ticket_resolu
        o	Nbr_ticket_creer
        o	Temps_moyen



## Modélisation d'un service de support informatique

    Appli ticket/
    ├── Presentation/
    │   └── Vue/
    │       ├── Vue_Ticket/
    │       ├── Vue_Documentation/
    │       └── Vue_Statistiques/              
    │
    ├── Application/
    │   ├── Controleurs/
    │   │   ├── Controleur_Ticket
    │   │   ├── Controleur_Employe
    │   │   ├── Controleur_Statistiques
    │   │   └── Controleur_Documentation
    │   │
    │   └── Services/
    │       ├── Implémentations/
    │       │   ├── Service_Ticket_Impl
    │       │   ├── Service_Employe_Impl
    │       │   ├── Service_Statistiques_Impl
    │       │   └── Service_Documentation_Impl
    │       │
    │       └── Interfaces/
    │           ├── Service_Ticket
    │           ├── Service_Employe
    │           ├── Service_Statistiques
    │           └── Service_Documentation
    │
    ├── Domaine/
    │   └── Model/
    │       ├── Ticket
    │       ├── Employe
    │       ├── Document
    │       └── Statistiques
    │
    ├── Infrastructure/
    │   ├── DTOs/
    │   │   ├── Dto_Ticket
    │   │   ├── Dto_Employe
    │   │   ├── Dto_Statistiques
    │   │   └── Dto_Documentation
    │   │
    │   └── Repository/
    │       ├── Repository_Ticket
    │       ├── Repository_Employe
    │       ├── Repository_Statistiques
    │       └── Repository_Documentation
    │    
    │
    └── README.md
