# ⚔️ Faërun — Jeu de stratégie en Java

> Simulation d'un jeu de stratégie au tour par tour en Java. Deux armées (Bleue 🔵 et Rouge 🔴) s'affrontent sur un plateau, chacune composée de guerriers aux caractéristiques distinctes, entraînés depuis leurs châteaux respectifs.

---

## ✨ Fonctionnalités

- **Deux factions** qui s'affrontent sur un plateau linéaire configurable
- **4 types de guerriers** avec des statistiques différentes :
  - 🧝 **Elfe** — Force ×2 par rapport à la base
  - 🪨 **Nain** — Défense renforcée
  - 👑 **Chef Elfe** — Commandant elfique avec bonus de commandement
  - 🏰 **Chef Nain** — Commandant nain avec capacités spéciales
- **Système de combat** — les guerriers s'affrontent case par case lors de leurs rencontres
- **Coups divins** — événements aléatoires gérés via exception (`CoupDivinException`)
- **Mode continu ou pas-à-pas** — rejoue chaque tour automatiquement ou attend une validation
- **Mode accumulation** — les guerriers peuvent s'accumuler sur une même case avant de combattre
- **Affichage du plateau** dans le terminal avec rendu ASCII

---

## 🏗️ Structure du projet

```
src/jeu/
├── Application.java                    # Point d'entrée — initialisation et boucle de jeu
├── guerrier/
│   ├── Guerrier.java                   # Classe abstraite de base pour tous les guerriers
│   ├── GuerrierUtilitaire.java         # Initialisation des armées dans les châteaux
│   ├── type/
│   │   ├── Elf.java                    # Guerrier Elfe (force ×2)
│   │   ├── Nain.java                   # Guerrier Nain
│   │   ├── ChefElf.java                # Chef Elfe
│   │   └── ChefNain.java               # Chef Nain
│   └── miscellaneous/
│       ├── ComparaisonGuerrierDefense.java   # Comparateur pour trier par défense
│       └── CoupDivinException.java           # Exception pour les coups spéciaux
└── plateauDeJeu/
    ├── Plateau.java                    # Gestion du plateau et de la progression des guerriers
    ├── PlateauUtilitaire.java          # Affichage et saisie des paramètres du plateau
    ├── carreau/
    │   ├── Carreau.java                # Une case du plateau (peut être un champ de bataille)
    │   └── CarreauUtilitaire.java      # Logique de combat sur une case
    └── chateau/
        ├── Chateau.java                # Château qui entraîne et produit des guerriers
        └── Couleur.java                # Énumération BLEU / ROUGE
```

---

## 🔧 Prérequis

- **Java JDK 11+**
- IntelliJ IDEA (le projet inclut le fichier `.iml` et la config `conf/debug-logging.properties`)

---

## 🚀 Lancement

```bash
# 1. Cloner le dépôt
git clone https://github.com/Ghost-Lake/rajalun.git
cd rajalun

# 2. Ouvrir dans IntelliJ et lancer Application.java dans src/jeu/
```

> ⚠️ Le fichier `conf/debug-logging.properties` doit être accessible depuis le répertoire de travail pour que le système de logging fonctionne.

---

## 🎮 Déroulement d'une partie

```
╔════════════════════════════════════════════════════════╗
║                      JEU DE FAËRUN                     ║
╚════════════════════════════════════════════════════════╝

Longueur du plateau : 10
Mode accumulation : non
Mode continu : oui

╔════════════════════════════════════════════════════════╗
║                      DÉBUT DU JEU                      ║
╚════════════════════════════════════════════════════════╝

[🔵🔵🔵] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [🔴🔴🔴]
                      ... tour 4 ...
[  ] [ ] [🔵⚔️🔴] [ ] [ ] [ ] [ ] [ ] [ ] [  ]
```

Le jeu se termine lorsqu'une des deux armées est entièrement éliminée.

---

## 🧩 Ce projet fait partie du module R2.01

Ce dépôt contient également deux autres exercices réalisés dans le cadre du même module :

| Dossier | Description |
|---|---|
| `src/exercice1/` | Gestion d'une carte de restaurant (plats, menus, prix) |
| `src/TPInstruments/` | Planification de séances d'instruments de musique pour enfants |

---

## 👤 Auteur

Projet réalisé dans le cadre du **module R2.01** — BUT Informatique 1ère année, IUT2 Grenoble.
