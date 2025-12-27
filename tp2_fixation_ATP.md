# TP 2 — Fixation de l’ATP dans le domaine kinase d’ABL
## Visualisation du site catalytique et des interactions ATP–kinase avec PyMOL

---

## 🎯 Objectif du TP

L’objectif de ce TP est de **visualiser le site de fixation de l’ATP** dans le domaine kinase d’ABL et de comprendre :

- comment l’ATP se positionne entre les deux lobes de la kinase,
- quels **domaines structuraux** participent à sa fixation,
- pourquoi la fixation correcte de l’ATP est indispensable à l’activité enzymatique.

Cette étape est essentielle pour comprendre ensuite **comment les inhibiteurs de kinases bloquent ce site**.

---

## 🧬 Rappel biologique (essentiel)

Les protéines kinases catalysent le transfert d’un groupement phosphate (γ-phosphate) de l’ATP vers une protéine substrat.

Pour cela :
- l’ATP doit être **correctement positionné** dans le site catalytique,
- plusieurs **résidus conservés** assurent sa reconnaissance,
- le complexe **ATP–Mg²⁺** est indispensable à la réaction.

👉 Toute perturbation de la fixation de l’ATP empêche la phosphorylation.

---

## 📁 Fichiers PDB utilisés

Deux structures sont utilisées pour comparer :

### 🔹 Structure sans ATP (référence)
- **PDB : 2HYY** (https://www.rcsb.org/structure/2HYY)
- Domaine kinase d’ABL
- Complexé avec imatinib (ATP absent)

### 🔹 Structure avec ATP
- **PDB : 2G1T** (https://www.rcsb.org/structure/2G1T)
- Domaine kinase d’ABL
- Complexé avec **ATP**

👉 La comparaison permet de localiser précisément le site ATP.

---

## 🧰 Manipulation PyMOL — Chargement des structures

#### 1️⃣ Charger 2G1T et ne garder que la chaîne A

Dans la console PyMOL :

```pml
reinitialize
fetch 2G1T, async=0
remove solvent

hide everything
show cartoon, polymer
color slate, polymer

# 1) Afficher TOUS les ligands (HETATM)
select ligands, hetatm
show sticks, ligands
color yellow, ligands
zoom ligands, 12

select hinge, resi 315-320
show sticks, hinge
color orange, hinge
zoom hinge

select DFG, chain A and resi 381-383
show sticks, DFG
color red, DFG
```

---


