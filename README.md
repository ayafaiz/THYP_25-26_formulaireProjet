

# THYP_25-26_formulaireProjet



##  Liens

- Formulaire :[Lien Google Form](https://forms.gle/xn75ezMgWPH2jMib9)


Titre du projet : Plateforme de gestion des ressources culturelles

Description du projet :
Ce projet a pour objectif de concevoir et développer une plateforme web dédiée à la gestion et à la valorisation des ressources culturelles. Elle permet de centraliser et d’organiser différents types de ressources, telles que les événements, lieux, projets, documents et utilisateurs, tout en offrant une navigation claire et des liens entre ces éléments.
Cette application s'adresse à deux types d'utilisateurs :
Les professionnels et chercheurs en culture et patrimoine, qui peuvent créer, modifier et consulter des ressources, gérer des projets et documenter des événements.
Le grand public intéressé par le patrimoine culturel, qui peut explorer les ressources disponibles et découvrir les événements et projets culturels.
Objectif général :
Développer une plateforme web permettant d’organiser, structurer et valoriser les ressources culturelles tout en facilitant leur consultation et leur interconnexion.
Objectifs spécifiques :
Centraliser et structurer les informations culturelles (Événements, Lieux, Projets, Documents, Utilisateurs).
Créer des vocabulaire et modèles de ressources pour normaliser les données.
Permettre l’importation de données via des fichiers CSV et leur gestion dans Omeka S.
Offrir une interface intuitive pour la consultation et la gestion des ressources.
Valoriser les relations entre les ressources pour mieux comprendre les liens entre événements, lieux et projets.
Technologies utilisées :
Frontend : HTML, CSS, JavaScript
Backend : PHP
Base de données : MySQL
Outils : Omeka S, GitHub, VS Code



   ```mermaid
erDiagram
    UTILISATEUR {
        int id_utilisateur PK
        string nom
        string prenom
        string email
        string mot_de_passe
        string role
    }

    DOCUMENT {
        int id_document PK
        string titre
        string type_document
        string url_document
        string statut_validation
        int id_utilisateur FK
    }

    LIEU {
        int id_lieu PK
        string nom
        string adresse
        string description
    }

    EVENEMENT {
        int id_evenement PK
        string nom
        date date_debut
        date date_fin
        string description
        int id_lieu FK
        int id_projet FK
    }

    PROJET {
        int id_projet PK
        string nom
        string description
        string responsable
    }

    HISTORIQUE_ACTION {
        int id_action PK
        datetime date_action
        string type_action
        int id_utilisateur FK
    }

    UTILISATEUR ||--o{ DOCUMENT : "crée"
    UTILISATEUR ||--o{ HISTORIQUE_ACTION : "effectue"
    LIEU ||--o{ EVENEMENT : "accueille"
    PROJET ||--o{ EVENEMENT : "contient"
    EVENEMENT ||--o{ DOCUMENT : "associe"
  ```

       

      ```

>>>>>>> b963ffa02fb6c4513bb0693b4db64dba627e3e3b
