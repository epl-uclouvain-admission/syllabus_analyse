# AGENTS.md — Guide pour les Agents IA (Syllabus d'Analyse UCLouvain)

Ce dépôt contient les sources $\LaTeX$ du **Syllabus d'Analyse** destiné à la préparation de l'épreuve d'analyse de l'examen spécial d'admission aux études d'ingénieur civil à l'**UCLouvain** (École Polytechnique de Louvain — EPL).

## 1. Architecture du projet

- `main.tex` : Fichier maître $\LaTeX$ (classe `book`, `11pt`, `a4paper`, `oneside`, marges de `2.5cm`). Définit les couleurs institutionnelles UCLouvain (`uclblue`, `ucllightblue`, `uclaccent`, etc.), les environnements `tcolorbox` (`theoreme`, `definition`, `exemple`, `attention`, `astuce`) et inclut tous les chapitres.
- `chap1_fonctions.tex` : Chapitre 1 — Fonctions réelles, domaines et fonctions transcendantes ($\ln$, $\exp$, fonctions réciproques, Lambert $W_0$).
- `chap2_limites.tex` : Chapitre 2 — Limites, continuité et asymptotes (définition $\varepsilon$-$M$, TVI, AV, AH, AO).
- `chap3_derivees.tex` : Chapitre 3 — Dérivées et grands théorèmes d'analyse (règles de dérivation, L'Hospital, Rolle, TAF).
- `chap4_etude_fonctions.tex` : Chapitre 4 — Étude complète de fonctions (méthodologie Question 1, tableaux de variations et tracés sans calculatrice).
- `chap5_optimisation.tex` : Chapitre 5 — Problèmes d'optimisation appliquée (méthodologie Question 2, mise en équation et paramétrisation).
- `chap6_primitives.tex` : Chapitre 6 — Calcul intégral et primitives (Question 3 : primitives immédiates, substitution, IPP, fractions simples, trigonométrie).
- `chap7_integrales_volumes.tex` : Chapitre 7 — Intégrales définies, inégalités, aires et volumes de révolution ($V = \pi \int R^2(x)\,\mathrm{d}x$).
- `chap8_formulaire.tex` : Chapitre 8 — Formulaire synthétique imprimable en 4 pages A4 (marges réduites à `1.4cm`, 2 colonnes).
- `annexe_logique.tex` : Annexe A — Logique et méthodes de démonstration en analyse (quantificateurs, implication, négation, contre-exemples).
- `chap9_correctifs.tex` : Chapitre 9 — Corrigés détaillés de tous les exercices de fin de chapitre.
- `.github/workflows/build-pdf.yml` : Workflow GitHub Actions compilant `main.tex` à chaque push/PR sur `main`, publiant l'artefact PDF et mettant à jour la release `latest` (`main.pdf` et `syllabus_analyse_uclouvain.pdf`).

## 2. Règles d'édition et de mise en page ($\LaTeX$)

1. **Zéro débordement (`Overfull \hbox`)** :
   - Après toute modification d'un fichier `.tex`, compilez avec `pdflatex -interaction=nonstopmode -file-line-error main.tex` (ou `latexmk -pdf main.tex`) et vérifiez dans `main.log` qu'aucun avertissement `Overfull \hbox` n'apparaît (`grep "Overfull" main.log`).
   - Si une équation hors texte (`\[ ... \]`) est trop longue ou comporte un `\boxed{...}` large, découpez-la sur plusieurs lignes avec `\begin{align*} ... \end{align*}` ou réduisez les espacements (`\quad` au lieu de `\qquad`).
   - Le Chapitre 8 (`chap8_formulaire.tex`) doit impérativement tenir sur **exactement 4 pages A4** (1 page par fiche récapitulative).
2. **Figures TikZ / PGFPlots** :
   - Toutes les figures sont dessinées directement en TikZ/PGFPlots (aucune image externe requise).
   - Veillez à ce que la largeur totale d'une figure ne dépasse jamais `\textwidth` ($16\text{ cm}$ dans les chapitres standards).
3. **Conventions mathématiques UCLouvain** :
   - Les fonctions cyclométriques se notent exclusivement `\arcsin`, `\arccos`, `\arctan` (jamais `\sin^{-1}`).
   - Le logarithme népérien se note `\ln(x)` et l'exponentielle `e^x` ou `\exp(x)`.
   - L'épreuve se déroule sans calculatrice : privilégiez toujours les valeurs exactes, l'analyse asymptotique et la vérification explicite des conditions d'existence (CE).
   - Chaque nouvel exercice ajouté à la fin d'un chapitre (`chap1` à `chap7`) doit avoir son corrigé complet correspondant dans `chap9_correctifs.tex`.
4. **Fichiers suivis par Git** :
   - Seuls les fichiers sources (`.tex`, `README.md`, `AGENTS.md`, `.gitignore`, `.github/workflows/build-pdf.yml`) doivent être suivis par Git. Ne commitez pas les fichiers auxiliaires (`.aux`, `.log`, `.out`, `.toc`) ni les `.pdf` générés localement.
