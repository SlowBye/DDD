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
