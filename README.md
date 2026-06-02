<div align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Terminal-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white" alt="Terminal" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Status" />

  <h1>⚔️ Jeu Faërun 🏰</h1>
  <p>
    <i>Un jeu de stratégie au tour par tour développé en Java, conçu pour le terminal.</i>
  </p>
</div>

<br />

## 📖 Table des matières
- [À propos du projet](#-à-propos-du-projet)
- [Objectifs et Compétences](#-objectifs-et-compétences)
- [Architecture du Code](#-architecture-du-code)
- [Prérequis et Installation](#-prérequis-et-installation)
- [Mécaniques de Jeu](#-mécaniques-de-jeu)
- [Cadre du Projet (PPP)](#-cadre-du-projet-ppp)

---

## 🚀 À propos du projet

**Faërun** est un mini-jeu de stratégie en Java s'exécutant dans le terminal. L'univers oppose deux factions rivales, les **Rouges** et les **Bleus**, luttant pour la suprématie. Chaque équipe contrôle un château fortifié. 

L'objectif principal est d'entraîner stratégiquement des unités (Elfes, Chefs Elfes, Nains, Chefs Nains) et de les déployer sur un plateau de jeu constitué de carreaux. La victoire est remportée lorsqu'un guerrier parvient à infiltrer le château adverse.

---

## 🎯 Objectifs et Compétences

La conception de Faërun a été un excellent moyen de mettre en pratique et de consolider des concepts avancés de développement logiciel en Java.

### Objectifs Techniques
- **Modélisation d'une logique complexe** : Conception du système de combat au tour par tour, de la gestion de l'économie (ressources) et du système de déplacement sur le plateau.
- **Mécaniques asymétriques** : Implémentation d'un équilibrage via des ratios de force, de dégâts et de points de vie variables selon les classes.
- **Gestion des interactions** : Mise en place des rôles (attaquant/défenseur) et d'un séquençage strict des priorités de combat.

### Compétences, Techniques et Savoir-faire Acquis
- **Programmation Orientée Objet (POO)** : Structuration du code avec des responsabilités claires entre les objets.
- **Héritage et Polymorphisme** : Utilisation intensive pour gérer la hiérarchie des guerriers (classe parente et classes spécifiques) pour factoriser les comportements communs tout en spécialisant les attaques.
- **Robustesse et Gestion d'erreurs** : Sécurisation du flux d'exécution via la gestion des exceptions Java.
- **Algorithmique et Structures de données** : Utilisation experte des listes et conception d'algorithmes de tri personnalisés pour dicter le déroulement des combats, l'état du plateau et l'ordre des tours.

---

## 📂 Architecture du Code

Le projet suit une architecture modulaire pour séparer clairement les responsabilités (Logique de jeu, Entités, Plateau).

```text
src/
└── jeu/
    ├── Application.java               # Point d'entrée principal et boucle de jeu
    ├── guerrier/                      # Package dédié aux unités combattantes
    │   ├── Guerrier.java              # Classe de base (Abstraite / Parente)
    │   ├── GuerrierUtilitaire.java    # Logique utilitaire pour les combats
    │   ├── type/                      # Classes spécialisées des guerriers
    │   │   ├── Elf.java / ChefElf.java
    │   │   └── Nain.java / ChefNain.java
    │   └── miscellaneous/
    │       ├── ComparaisonGuerrierDefense.java # Logique de tri personnalisée (défense)
    │       └── CoupDivinException.java         # Exception liée aux événements de combat
    ├── plateauDeJeu/                  # Package gérant l'environnement spatial
    │   ├── Plateau.java / PlateauUtilitaire.java
    │   ├── carreau/                   # Gestion des cases individuelles du plateau
    │   │   └── Carreau.java / CarreauUtilitaire.java
    │   └── chateau/                   # Gestion des bases d'équipes et ressources
    │       └── Chateau.java / Couleur.java
    └── test/                          # Scénarios de tests d'intégration et de validation
        ├── TestGuerrier.java
        ├── TestEtape2.java
        └── TestEtape3.java
```

---

## 🛠️ Prérequis et Installation

### Prérequis
- **Java Development Kit (JDK)** version 8 ou supérieure.
- Un terminal d'invite de commandes (CMD, PowerShell, Bash...).

### Compilation et Exécution
1. Ouvrez votre terminal et placez-vous dans le répertoire source racine `src`.
2. Compilez l'ensemble des fichiers Java :
   ```bash
   javac jeu/Application.java
   ```
3. Lancez le jeu :
   ```bash
   java jeu.Application
   ```

---

## ⚙️ Mécaniques de Jeu

- **Entraînement** : Chaque tour, les châteaux génèrent des ressources permettant de former de nouvelles unités.
- **Déplacement** : Les unités avancent de carreau en carreau vers le château adverse.
- **Combat** : Lorsqu'une unité alliée rencontre une unité ennemie sur un même carreau, le combat s'engage. Les dégâts sont calculés selon la force de frappe, la classe du personnage (Elfe, Nain...) et les probabilités intégrées dans les calculs (Coup Divin).

---

## 🎓 Cadre du Projet

Ce projet s'inscrit dans un contexte académique, dont voici les détails de réalisation :

- **Travail en groupe** : Ce projet a été réalisé en **autonomie complète** (travail en solo).
- **Travail individuel dans le groupe** : L'intégralité du projet, de la conception à l'implémentation finale, a été réalisée individuellement. Cela inclut :
  - **La modélisation des classes** (Guerriers, Châteaux, Plateau).
  - **La gestion de la boucle de jeu** (entraînement, déplacement, résolution des combats).
  - **L'implémentation des algorithmes de combat et de calcul de dégâts**.
