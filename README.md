# SmartFarm — Gestion des capteurs d'une ferme intelligente

Application de bureau en **C / GTK+** pour gérer le parc de capteurs d'une exploitation agricole : ajout, consultation, modification, suppression et contrôle de l'état de fonctionnement des capteurs.

Projet académique réalisé à ESPRIT (module Programmation C).

## Fonctionnalités

- **Ajouter un capteur** : nombre, emplacement, lieu, type, marque et date de mise en service
- **Afficher** la liste des capteurs dans une vue tabulaire GTK (`GtkTreeView`)
- **Modifier** les informations d'un capteur existant
- **Supprimer** un capteur
- **Contrôle technique** : marquer un capteur comme *Fonctionne* ou *En panne*
- **Disponibilité** : vérifier les capteurs disponibles pour un emplacement et une date
- Persistance des données dans des fichiers texte (`capteur.txt`, `capused.txt`)

## Stack technique

| Élément | Technologie |
|---|---|
| Langage | C |
| Interface graphique | GTK+ 2, conçue avec **Glade** (`yosradab.glade`) |
| Build | Autotools (`autogen.sh`, `configure`, `Makefile`) |
| Stockage | Fichiers texte |

## Structure

```
src/
├── main.c         # Point d'entrée, création de la fenêtre principale
├── interface.c/h  # Fenêtres générées par Glade (Ajouter, Afficher, Modifier, Supprimer, Contrôle, Date)
├── callbacks.c/h  # Gestion des événements (boutons, validations)
├── capteur.c/h    # Logique métier : structure capteur, CRUD, contrôle, disponibilité
└── support.c/h    # Utilitaires GTK
pixmaps/           # Images de l'interface
yosradab.glade     # Description de l'interface Glade
```

## Lancer le projet (Linux)

Prérequis : `gcc`, `make`, `autoconf`, `automake` et les bibliothèques de développement GTK+ 2 (`libgtk2.0-dev`).

```bash
./autogen.sh      # génère configure et les Makefiles
./configure
make
./src/yosradab    # lance l'application
```

## Auteur

**Yosra Dab** — Ingénieure logiciel Full Stack · [Portfolio](https://yosradab.vercel.app) · [GitHub](https://github.com/yosradab) · [LinkedIn](https://linkedin.com/in/yosradab)
