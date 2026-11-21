# Syllabus d'Analyse — Examen d'admission UCLouvain (EPL)

[![Build LaTeX PDF](https://github.com/epl-uclouvain-admission/syllabus_analyse/actions/workflows/build-pdf.yml/badge.svg)](https://github.com/epl-uclouvain-admission/syllabus_analyse/actions/workflows/build-pdf.yml)

Bienvenue sur le dépôt officiel du **Syllabus d'Analyse** destiné à la préparation de l'épreuve d'analyse de l'**examen spécial d'admission aux études d'ingénieur civil** à l'[UCLouvain](https://uclouvain.be/fr/facultes/epl) (École Polytechnique de Louvain — EPL).

---

## 📥 Télécharger le syllabus (PDF)

Le document PDF est compilé automatiquement à chaque mise à jour du dépôt via GitHub Actions :

- 👉 **[Télécharger la dernière version du PDF (`syllabus_analyse_uclouvain.pdf`)](https://github.com/epl-uclouvain-admission/syllabus_analyse/releases/download/latest/syllabus_analyse_uclouvain.pdf)** *(lien direct issu de la dernière release)*
- 📄 Vous pouvez également consulter la page des **[Releases](https://github.com/epl-uclouvain-admission/syllabus_analyse/releases/tag/latest)** ou récupérer l'artefact généré dans l'onglet **[Actions](https://github.com/epl-uclouvain-admission/syllabus_analyse/actions)**.

---

## 📚 Contenu de l'ouvrage

Ce syllabus couvre l'ensemble de la matière d'analyse de 5e et 6e secondaire en Fédération Wallonie-Bruxelles (Communauté française de Belgique) nécessaire pour l'épreuve d'admission (qui se déroule **sans calculatrice**), ainsi que l'intégralité des exemples résolus et exercices issus des annales de l'examen d'entrée de l'UCLouvain (2021–2026) :

1. **Chapitre 1 — Fonctions réelles, domaines et fonctions transcendantes** (`chap1_fonctions.tex`) : domaine de définition, parité, périodicité, opérations et composition, fonctions réciproques (dont $\arcsin, \arccos, \arctan$ et la fonction de Lambert $W_0$), logarithme népérien $\ln(x)$ et exponentielle $e^x$.
2. **Chapitre 2 — Limites, continuité et asymptotes** (`chap2_limites.tex`) : définition formelle ($\varepsilon$-$M$ et $\varepsilon$-$\delta$), règles de calcul, formes indéterminées, théorème des gendarmes, limites fondamentales, continuité, prolongement par continuité, théorème des valeurs intermédiaires (TVI) et asymptotes (AV, AH, AO).
3. **Chapitre 3 — Dérivées et grands théorèmes d'analyse** (`chap3_derivees.tex`) : nombre dérivé, interprétation géométrique (tangente) et cinématique, règles de dérivation (produit, quotient, composition, fonction réciproque), règle de L'Hospital, théorème de Rolle et théorème des accroissements finis (TAF).
4. **Chapitre 4 — Étude complète de fonctions** (`chap4_etude_fonctions.tex`) : méthodologie en 6 étapes pour la Question 1 de l'examen, croissance, extrema locaux, concavité, points d'inflexion, tableaux de variations complets et esquisses graphiques sans calculatrice.
5. **Chapitre 5 — Problèmes d'optimisation appliquée** (`chap5_optimisation.tex`) : méthodologie de modélisation pour la Question 2 de l'examen, paramétrisation, élimination des contraintes, optimisation énergétique, géométrique, cinématique et économique.
6. **Chapitre 6 — Calcul intégral et primitives** (`chap6_primitives.tex`) : primitives immédiates, intégration par substitution (changement de variable), intégration par parties (IPP simples, doubles et cycliques), fractions rationnelles et primitives trigonométriques.
7. **Chapitre 7 — Intégrales définies, inégalités, aires et volumes de révolution** (`chap7_integrales_volumes.tex`) : théorème fondamental de l'analyse, valeur moyenne, démonstration d'inégalités par intégration ou par étude de différence, calcul d'aires planes et volumes de solides de révolution ($V = \pi \int R^2(x)\,dx$).
8. **Chapitre 8 — Formulaire récapitulatif** (`chap8_formulaire.tex`) : synthèse imprimable en 4 pages A4 de toutes les formules et méthodes essentielles d'analyse.
9. **Annexe — Raisonnement logique et méthodes de démonstration en analyse** (`annexe_logique.tex`) : quantificateurs, implication, équivalence, contre-exemples et pièges classiques.
10. **Chapitre 9 — Corrigés détaillés des exercices** (`chap9_correctifs.tex`) : solutions complètes et commentées de tous les exercices de fin de chapitre.

---

## 🛠️ Compilation locale

Pour compiler le syllabus sur votre machine, vous devez disposer d'une distribution $\LaTeX$ complète (par exemple **TeX Live** ou **MacTeX**) incluant `pdflatex`, `latexmk` ainsi que les packages standards (`tikz`, `pgfplots`, `tcolorbox`, `amsmath`, `babel`, etc.).

Exécutez simplement la commande suivante à la racine du dépôt :

```bash
latexmk -pdf -interaction=nonstopmode main.tex
```

Ou avec `pdflatex` (deux passes sont nécessaires pour générer la table des matières et les références croisées) :

```bash
pdflatex main.tex
pdflatex main.tex
```

Le fichier généré s'intitule `main.pdf`.

---

## 👥 Auteurs, direction et sources

- **Direction artistique & *Prompt Engineering*** : L'équipe de l'examen d'admission à l'EPL — UCLouvain (**Jean-François Remacle** et **Pierre Schaus**).
- **Rédaction et mise en forme $\LaTeX$ / TikZ** : assistée par Intelligence Artificielle sous la supervision des enseignants.
- **Sources** :
  - Le programme officiel de mathématiques (5e et 6e secondaire, 6h/semaine) de la Fédération Wallonie-Bruxelles (Communauté française de Belgique).
  - Les supports des cours préparatoires et les annales officielles avec solutionnaires de l'épreuve d'**Analyse** de l'examen d'admission de l'**UCLouvain** (2021 à 2026).

---

## 🤝 Signaler une coquille ou contribuer

Si vous repérez une coquille dans un énoncé, une figure ou un corrigé, n'hésitez pas à ouvrir une **[Issue](https://github.com/epl-uclouvain-admission/syllabus_analyse/issues)** ou à proposer une **[Pull Request](https://github.com/epl-uclouvain-admission/syllabus_analyse/pulls)**.
