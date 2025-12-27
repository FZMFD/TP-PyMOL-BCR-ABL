# TP 1 — Domaines structuraux de la kinase ABL
## Identification des éléments clés du domaine kinase avec PyMOL

---

## 🎯 Objectif du TP

L’objectif de ce TP est de **visualiser le domaine kinase d’ABL en 3D** et d’identifier les **principaux domaines et motifs structuraux impliqués dans son activité enzymatique**.

Cette étape est indispensable pour comprendre ensuite :
- les conformations active / inactive,
- la fixation de l’ATP,
- l’action des inhibiteurs (imatinib),
- et les mécanismes de résistance.

---

## 🧬 Rappel biologique (essentiel)

ABL est une **tyrosine kinase**, c’est-à-dire une enzyme capable de transférer un groupement phosphate de l’ATP vers une protéine cible.

Son **domaine kinase** :
- est conservé chez toutes les kinases,
- est composé d’environ **250–300 acides aminés**,
- est organisé en **deux lobes** :
  - **Lobe N-terminal** (riche en feuillets β)
  - **Lobe C-terminal** (riche en hélices α)

👉 Le **site catalytique** se situe **entre les deux lobes**.

---

## 📁 Fichier PDB utilisé

### Structure de référence
- **PDB : 2HYY**
- Domaine kinase d’ABL
- Complexé avec l’inhibiteur **imatinib**

👉 Ce PDB est utilisé ici **comme modèle structural** du domaine kinase.

---

## 🧰 Manipulation PyMOL — Chargement et affichage général

### 1️⃣ Charger la structure
Dans la console PyMOL :

```pml
fetch 2HYY, async=0
remove solvent
```

---

### 2️⃣ Affichage de base
Dans la console PyMOL :

```pml
hide everything
show cartoon, polymer
color slate, polymer
```

👉 Le mode cartoon permet de visualiser la structure secondaire
(hélices α et feuillets β).

---

##
