# projet-fils-rouge
# 🚗 Plateforme de Location de Voitures

##  Présentation du Projet

###  Nom du projet
**Plateforme de Location de Voitures**

###  Description
Ce projet consiste à développer une plateforme web permettant aux agences de location de voitures de s’inscrire afin de publier leurs services et leurs voitures disponibles à la location.

Chaque agence doit respecter certaines conditions avant d’être validée et affichée sur la plateforme.

Après validation par l’administrateur, l’agence sera affichée sous forme de carte contenant :
- Les informations de l’agence
- Les photos des voitures
- Les prix de location par jour

---

# 🎯 Objectifs du Projet

- Réunir plusieurs agences de location dans une seule plateforme
- Faciliter la recherche de voitures pour les clients
- Permettre aux agences de publier leurs voitures
- Offrir une interface moderne et simple d’utilisation

---

# 👥 Types d’Utilisateurs

##  Administrateur
L’administrateur peut :
- Valider ou refuser les agences
- Gérer les utilisateurs
- Supprimer les contenus non conformes
- Contrôler les voitures publiées

---

##  Agence de Location
L’agence peut :
- Créer un compte
- Se connecter
- Ajouter ses informations
- Ajouter plusieurs voitures
- Modifier ou supprimer ses voitures
- Ajouter des photos des voitures

---

# ✅ Conditions de Validation des Agences

Pour être acceptée sur la plateforme, une agence doit :

- Fournir toutes les informations demandées
- Ajouter au minimum 5 voitures
- Ajouter des photos réelles des voitures
- Indiquer le prix de location par jour pour chaque voiture

Une fois validée par l’administrateur, l’agence sera visible sur le site.

---

#  Fonctionnalités Principales

##  Inscription des Agences
L’agence doit remplir :
- Nom de l’agence
- Email
- Téléphone
- Ville
- Adresse
- Description
- Logo ou photo

---

## 🚗 Gestion des Voitures

Chaque agence peut :
- Ajouter une voiture
- Modifier une voiture
- Supprimer une voiture
- Afficher ses voitures

### Informations des voitures
- Marque
- Modèle
- Année
- Prix par jour
- Photo de la voiture

---

## 🖼️ Affichage des Agences

Les agences validées seront affichées sous forme de cartes contenant :
- Logo de l’agence
- Nom de l’agence
- Ville
- Informations de contact
- Photos des voitures
- Prix par jour des voitures

---

##  Recherche

Le site permet la recherche selon :
- Ville
- Marque de voiture
- Prix par jour

---

#  Base de Données

## Table `agences`

CREATE DATABASE location_voitures;

USE location_voitures;

-- =====================================
-- TABLE AGENCES
-- =====================================

CREATE TABLE agences (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    telephone VARCHAR(20) NOT NULL,
    ville VARCHAR(50) NOT NULL,
    adresse TEXT NOT NULL,
    description TEXT NOT NULL,
    logo VARCHAR(255) NOT NULL,
    statut VARCHAR(20) DEFAULT 'en attente'
);

-- =====================================
-- TABLE VOITURES
-- =====================================

CREATE TABLE voitures (
    id INT AUTO_INCREMENT PRIMARY KEY,
    agence_id INT NOT NULL,
    marque VARCHAR(50) NOT NULL,
    modele VARCHAR(50) NOT NULL,
    annee INT NOT NULL,
    prix_jour DECIMAL(10,2) NOT NULL,
    image VARCHAR(255) NOT NULL,

    FOREIGN KEY (agence_id)
    REFERENCES agences(id)
    ON DELETE CASCADE
);

---

# 🖥️ Interfaces du Site

- Page d’accueil
- Page d’inscription
- Page de connexion
- Tableau de bord agence
- Liste des agences
- Liste des voitures
- Interface administrateur

---

# Technologies Utilisées

- HTML
- CSS
- Bootstrap
- JavaScript
- PHP
- MySQL
- XAMPP

---

#  Design

- Interface moderne et responsive
- Utilisation des cartes Bootstrap
- Affichage des voitures avec images
- Navigation simple et claire

---

# ✅ Résultat Attendu

Développer une plateforme web moderne permettant aux agences de location de voitures de publier leurs services et leurs voitures après validation par l’administrateur.

Chaque agence affichera plusieurs voitures avec leurs photos et leurs prix de location par jour dans une interface moderne et professionnelle.
