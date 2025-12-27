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

## 🧠 Organisation générale du domaine kinase

### 🔹 Le domaine kinase est structuré en :
- Lobe N-terminal → fixation de l’ATP
- Lobe C-terminal → catalyse et interaction avec le substrat

---

### 🔹 Domaines et motifs structuraux à identifier
#### 1️⃣ La charnière (hinge)

- Relie les lobes N et C
- Permet la fixation de l’adénine de l’ATP
- Cible majeure des inhibiteurs de kinases

👉 Sans interaction avec la charnière → pas d’activité kinase.

(Elle sera étudiée plus en détail lors de la fixation de l’ATP et de l’imatinib.)

2️⃣ La boucle P (P-loop ou glycine-rich loop)

Rôle biologique

Stabilise les groupes phosphates de l’ATP

Apporte de la flexibilité au site catalytique

Riche en résidus glycine

👉 Essentielle au bon positionnement de l’ATP.

3️⃣ Le motif DFG (Asp-Phe-Gly)

Rôle biologique

Contrôle l’état actif ou inactif de la kinase

L’aspartate (D) coordonne le Mg²⁺ nécessaire à la catalyse

Conformations

DFG-in → compatible avec l’activité

DFG-out → kinase inactive

4️⃣ L’hélice αC

Rôle biologique

Positionne les résidus catalytiques

Formation d’un pont salin indispensable à l’activité

Conformations

αC-in → kinase active

αC-out → kinase inactive

5️⃣ La boucle d’activation (A-loop)

Rôle biologique

Régule l’accès du substrat au site catalytique

Peut bloquer partiellement le site actif en conformation inactive
