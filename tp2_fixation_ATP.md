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
```

---

# Garder uniquement la chaîne A

```pml
remove not chain A
```

---

#### 2️⃣ Affichage propre de la protéine

```pml
de everything
show cartoon, chain A
color slate, chain A
```

--- 

#### 3️⃣ Identifier et afficher la charnière (hinge)

Pour ABL, la charnière correspond classiquement aux résidus 312–318
(adapté à 2G1T – zone de liaison de l’adénine)

```pml
select hinge, chain A and resi 312-318
show sticks, hinge
color yellow, hinge
label hinge and name CA, "hinge"



```

---

4️⃣ Identifier et afficher le motif DFG

Dans ABL, le motif DFG est 381–383.

select DFG, chain A and resi 381-383
show sticks, DFG
color red, DFG
label DFG and name CA, "DFG"


👉 Rôle à expliquer :

D (Asp) : coordination Mg²⁺

Position du DFG → état actif / inactif

5️⃣ (Option pédagogique) Montrer le nucléotide s’il existe

⚠️ Sans supposer son nom

select ligands, chain A and hetatm
show sticks, ligands
color orange, ligands
zoom (hinge or DFG or ligands), 12


👉 S’il n’y a pas de nucléotide visible, ce n’est pas une erreur :

on localise quand même le site ATP grâce à la charnière + DFG

---

