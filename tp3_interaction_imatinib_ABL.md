# TP 3 — Interaction de l’imatinib avec la kinase ABL
## Visualisation du site de liaison et compréhension du mécanisme d’inhibition

---

## 🎯 Objectif du TP

L’objectif de ce TP est de **visualiser comment l’imatinib se fixe sur la kinase ABL** et de comprendre :

- où se situe le site de liaison de l’imatinib,
- quels domaines structuraux sont impliqués dans l’interaction,
- pourquoi l’imatinib est un inhibiteur efficace de la kinase ABL,
- le lien entre **conformation de la kinase** et **fixation du médicament**.

---

## 🧬 Rappel biologique (essentiel)

L’imatinib est un **inhibiteur de tyrosine kinase (PKI)** utilisé dans le traitement de la leucémie myéloïde chronique.

Il agit en :
- bloquant l’activité kinase de **BCR-ABL**,
- empêchant la fixation correcte de l’ATP,
- stabilisant la kinase dans une **conformation inactive**.

👉 L’imatinib est un **inhibiteur de type II** :
- il se fixe dans le site ATP,
- **et** dans une **poche hydrophobe adjacente**, accessible uniquement lorsque la kinase est inactive.

---

## 📁 Fichier PDB utilisé

### Structure de référence
- **PDB : 2HYY**
- Domaine kinase d’ABL
- Complexé avec **imatinib**

👉 Ce PDB est un modèle classique pour étudier l’inhibition d’ABL.

---

## 🧰 Manipulation PyMOL — Chargement et préparation

### Charger la structure
```pml
reinitialize
fetch 2HYY, async=0
remove solvent

remove not chain A

hide everything
show cartoon, chain A
color slate, chain A
```

--- 

## 🧪 Visualisation de l’imatinib

### Identifier l’imatinib précisément
```pml
select ligands, hetatm
show sticks, ligands
color yellow, ligands
zoom ligands, 12

select imatinib, resn STI
show sticks, imatinib
color orange, imatinib
zoom imatinib, 12
```

---

## 🧠 Site de liaison de l’imatinib

### 1️⃣ La charnière (hinge)
```pml
select hinge, chain A and resi 312-318
show sticks, hinge
color green, hinge
```

👉 Rôle
- Interaction avec la partie aromatique de l’imatinib
- Même région utilisée par l’adénine de l’ATP

### 2️⃣ Le motif DFG
```pml
select DFG, chain A and resi 381-383
show sticks, DFG
color red, DFG
```

👉 Dans le complexe avec imatinib :
- la kinase est en conformation inactive
- le motif DFG est déplacé par rapport au site ATP

### 3️⃣ La poche hydrophobe adjacente
```pml
select pocket, byres (chain A within 4 of imatinib)
show sticks, pocket
color cyan, pocket
```

➡️ **Prochaine étape :**  
[TP 4 — Effet de la mutation T315I sur la fixation de l’imatinib](tp4_mutation_T315I_imatinib.md)

👉 Cette poche n’existe que lorsque la kinase est inactive
