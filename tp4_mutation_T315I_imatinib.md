# TP 4 — Effet de la mutation T315I sur la fixation de l’imatinib
## Compréhension structurale d’un mécanisme de résistance thérapeutique

---

## 🎯 Objectif du TP

L’objectif de ce TP est de **comprendre pourquoi la mutation T315I de la kinase ABL entraîne une résistance à l’imatinib**, en comparant :

- la structure **ABL sauvage (WT) + imatinib**,
- la structure **ABL mutée T315I + imatinib (modélisée)**.

À l’issue du TP, l’étudiant doit être capable de relier :
- une **mutation ponctuelle**,
- à une **perte d’interaction médicament–protéine**,
- et à une **résistance clinique**.

---

## 🧬 Rappel biologique (essentiel)

Le résidu **Thr315** est appelé **gatekeeper** :
- il contrôle l’accès à une **poche hydrophobe adjacente** au site ATP,
- il permet la fixation correcte de plusieurs inhibiteurs, dont l’imatinib.

La mutation **T315I** :
- remplace une **thréonine (petite, polaire)**,
- par une **isoleucine (volumineuse, hydrophobe)**.

👉 Cette substitution :
- supprime une liaison hydrogène,
- crée un encombrement stérique,
- empêche l’imatinib d’accéder à sa poche de liaison.

---

## 📁 Fichier PDB utilisé

### Structure de référence (WT)
- **PDB : 2HYY**
- Domaine kinase d’ABL
- Complexé avec **imatinib**

👉 Le mutant sera généré **in silico** avec PyMOL.

---

## 🧰 Manipulation PyMOL — Préparation de la structure WT

### 1️⃣ Charger la structure
```pml
reinitialize
fetch 2HYY, async=0
remove solvent
remove not chain A

hide everything
show cartoon, chain A
color slate, chain A

select ligands, hetatm
show sticks, ligands
color orange, ligands
zoom ligands, 12
```

### 2️⃣ Afficher l'imatinib
```pml
select ligands, hetatm
show sticks, ligands
color orange, ligands
zoom ligands, 12
```

### 3️⃣ Mettre en évidence le gatekeeper WT (Thr315)
```pml
select gatekeeper_WT, chain A and resi 315
show sticks, gatekeeper_WT
color green, gatekeeper_WT
label gatekeeper_WT and name CA, "T315 (WT)"
```

---

## 🧪 Génération de la mutation T315I (in silico)

### 1️⃣ Lancer l’outil de mutagenèse

Dans PyMOL :

- Wizard → Mutagenesis
- Sélectionner le résidu 315
- Choisir Isoleucine (I)
- Appliquer la mutation
- Choisir un rotamère sans clash majeur

👉 Le résidu muté apparaît en rouge.

### 2️⃣ Mettre en évidence l’encombrement stérique

```pml
set cartoon_transparency, 0.4
zoom (gatekeeper_WT or gatekeeper_MUT or ligands), 10
```

👉 L’isoleucine occupe l’espace normalement utilisé par l’imatinib.

---

## 👀 Observations attendues

En WT :

- T315 est petit
- l’imatinib s’insère correctement

En mutant :

- I315 est volumineux
- la poche hydrophobe est obstruée
- l’imatinib ne peut plus se positionner

