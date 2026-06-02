# ⚔️ Faërun — Jeu de stratégie en Java

> **Module R2.01 — Développement Orienté Objet** | BUT Informatique (1ère année) — IUT2 Grenoble.

---

## 📝 Description du projet

Faërun est un jeu de stratégie au tour par tour développé en Java, s'exécutant intégralement dans le terminal avec un rendu en art ASCII. 

Le concept repose sur l'affrontement linéaire de deux armées (l'armée Bleue 🔵 et l'armée Rouge 🔴) situées aux extrémités opposées d'un plateau configurable. Chaque faction possède un château qui entraîne et déploie des guerriers dotés de caractéristiques spécifiques. Les unités avancent case par case et s'affrontent dès qu'elles se croisent. La partie prend fin lorsqu'une des deux armées est totalement exterminée.

Le moteur de jeu intègre des fonctionnalités avancées telles que la gestion des coups critiques divins (via des exceptions personnalisées), un mode pas-à-pas ou continu, et une option d'accumulation stratégique des troupes sur une même case avant le déclenchement des combats.

---

## 🎯 Objectifs du projet

L'objectif principal de ce projet était de mettre en pratique les concepts fondamentaux de la **Programmation Orientée Objet (POO)** en Java à travers un cas d'usage ludique mais complexe. 

Plus spécifiquement, les objectifs techniques étaient :
* Maîtriser les concepts d'**héritage** et de **polymorphisme** à travers la modélisation des différentes classes de guerriers.
* Implémenter une architecture logicielle propre et découpée en packages (modèle, logique de jeu, utilitaires).
* Gérer la robustesse du code à l'aide des **exceptions Java**.
* Manipuler les structures de données (listes, tris personnalisés) pour ordonner les combats et gérer l'état du plateau.

---

## 🛠️ Compétences développées

Ce projet s'inscrit dans la validation des compétences du BUT Informatique, notamment :
* **Compétence 1 : Réaliser un développement d'application**
    * Conception d'une architecture orientée objet respectant les principes de responsabilité unique.
    * Codage, test et débogage d'un algorithme de jeu en mode continu et pas-à-pas.
* **Compétence 2 : Travailler dans une équipe informatique**
    * Utilisation d'outils de versioning (Git) et répartition équitable des tâches.
    * Communication technique pour l'intégration des différents modules du jeu.

---

## 👥 Travail en groupe

Le projet a été réalisé en équipe, ce qui a nécessité une phase de conception commune essentielle :
* **Conception initiale** : Modélisation conjointe du diagramme de classes UML pour s'accorder sur les relations entre le Plateau, les Châteaux et les Guerriers.
* **Méthodologie** : Utilisation de Git pour fusionner le code et d'échanges réguliers pour s'assurer de la compatibilité entre l'affichage (plateau) et la logique métier (combats).
* **Bilan collectif** : Cette collaboration a permis d'aboutir à un code modulaire où l'ajout d'un nouveau type de guerrier ou d'une nouvelle règle de combat n'impactait pas le reste du système.

---

## 👤 Travail individuel dans le groupe

*En tant que membre de l'équipe, j'ai pris en charge des aspects clés de l'application :*
*(👉 **Note à l'étudiant** : Personnalise cette liste selon ce que tu as fait. Voici des exemples basés sur ton code) :*

* **Modélisation et Cycle de vie des Guerriers** : Conception de la classe abstraite `Guerrier` et implémentation des mécanismes d'héritage pour les classes dérivées (`Elf`, `Nain`, `ChefElf`, `ChefNain`).
* **Algorithme de Tri** : Développement du comparateur personnalisé `ComparaisonGuerrierDefense` pour trier les guerriers selon leur statistique de défense lors des phases critiques du jeu.
* **Gestion des Erreurs** : Création et intégration de l'exception personnalisée `CoupDivinException` afin d'isoler la logique des événements aléatoires majeurs lors des attaques.
* **Refactoring et Utilitaires** : Structuration des classes `GuerrierUtilitaire` et `CarreauUtilitaire` afin de séparer proprement les calculs mathématiques et algorithmiques de l'état des objets.

---

## 🧠 Techniques et savoir-faire acquis

Ce projet m'a permis d'acquérir et de consolider plusieurs compétences techniques majeures en Java :
* **Abstraction & Polymorphisme** : Utilisation d'une classe de base abstraite `Guerrier` permettant de manipuler des listes d'unités hétérogènes de manière uniforme lors des déplacements et des combats.
* **Gestion des Exceptions Professionnelle** : Implémentation de blocs `try-catch` et levée d'exceptions métiers (`CoupDivinException`) pour gérer les comportements d'attaque maximum sans polluer la boucle de jeu principale.
* **Encapsulation & Énumérations** : Utilisation stricte des modificateurs d'accès (`private`, `protected`) et des `enum` (`Couleur.java`) pour sécuriser les données de l'application.
* **Rendu sur Terminal Avancé** : Gestion des flux d'affichage ASCII pour simuler une interface graphique dynamique en mode console (classe `PlateauUtilitaire`).

---

## 🏗️ Structure technique du projet

L'application est découpée en packages spécialisés :

src/jeu/
├── Application.java                 # Point d'entrée — initialisation et boucle de jeu
├── guerrier/
│   ├── Guerrier.java                # Classe abstraite de base pour tous les guerriers
│   ├── GuerrierUtilitaire.java      # Initialisation des armées dans les châteaux
│   ├── type/
│   │   ├── Elf.java                 # Guerrier Elfe (force ×2)
│   │   ├── Nain.java                # Guerrier Nain (dégâts reçus / 2)
│   │   ├── ChefElf.java             # Chef Elfe (force ×4)
│   │   └── ChefNain.java            # Chef Nain (dégâts reçus / 4)
│   └── miscellaneous/
│       ├── ComparaisonGuerrierDefense.java   # Comparateur pour trier par défense
│       └── CoupDivinException.java           # Exception pour les coups spéciaux
└── plateauDeJeu/
├── Plateau.java                 # Gestion du plateau et de la progression des guerriers
├── PlateauUtilitaire.java       # Affichage et saisie des paramètres du plateau
├── carreau/
│   ├── Carreau.java             # Une case du plateau (champ de bataille potentiel)
│   └── CarreauUtilitaire.java   # Logique algorithmique du combat sur une case
└── chateau/
├── Chateau.java             # Château qui entraîne et produit des guerriers
└── Couleur.java             # Énumération BLEU / ROUGE


---

## 🎮 Aperçu du déroulement d'une partie

╔════════════════════════════════════════════════════════╗
║                        JEU DE FAËRUN                   ║
╚════════════════════════════════════════════════════════╝

Longueur du plateau : 10
Mode accumulation : non
Mode continu : oui

╔════════════════════════════════════════════════════════╗
║                        DÉBUT DU JEU                    ║
╚════════════════════════════════════════════════════════╝

[🔵🔵🔵] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [🔴🔴🔴]
... tour 4 ...
[  ] [ ] [🔵⚔️🔴] [ ] [ ] [ ] [ ] [ ] [ ] [  ]


---

## 🔧 Prérequis & Installation

* **Java JDK 11** ou version supérieure.
* Environnement de développement recommandé : **IntelliJ IDEA** (les fichiers de configuration `.iml` et `conf/debug-logging.properties` sont inclus pour faciliter le débogage).
