# MARCO - Bibliothécaire Cybernétique v0.4

> *"Un cerveau qui lit, digère et comprend vos livres"*

![Version](https://img.shields.io/badge/version-0.4-blue)
![Python](https://img.shields.io/badge/python-3.8+-green)
![License](https://img.shields.io/badge/license-AGPL--3.0-red)

---

## 🧠 Vision

**Marco** n'est pas un chatbot. C'est un **bibliothécaire cybernétique** qui :

- **Lit** vos livres (txt, epub, md)
- **Digère** le contenu en construisant une architecture neuronale
- **Comprend** les questions grâce à la tokenisation ADH
- **Retrouve** l'information sans avoir besoin de relire

**Philosophie** : S'inspirer du vivant (C.elegans, 302 neurones) plutôt que des maths complexes (transformers, GPU).

---

## 🏗️ Architecture

### Vue d'ensemble

```
┌─────────────────────────────────────────────────────────────┐
│                         THALAMUS                            │
│                    (Routeur central)                        │
└─────────────────────────┬───────────────────────────────────┘
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        ▼                 ▼                 ▼
┌───────────────┐ ┌───────────────┐ ┌───────────────┐
│   NEURONES    │ │    PHARES     │ │     ADH       │
│   LETTRES     │ │    (mots)     │ │  (questions)  │
│   (51 max)    │ │  (illimité)   │ │  (niveaux)    │
└───────────────┘ └───────────────┘ └───────────────┘
```

### Les Dendrites (Niveau 0-1)

Chaque mot est décomposé en **lettres connectées par des dendrites** :

```
"chêne" → c →[0.7]→ h →[0.6]→ ê →[0.5]→ n →[0.8]→ e → PHARE[chêne]
```

**Avantages** :
- **51 neurones lettres** suffisent pour tout le français
- Les dendrites se **renforcent** avec l'usage (épines d'apprentissage)
- Compression naturelle des préfixes communs ("chat", "chien", "chêne" partagent "ch")

### Les Phares (Niveau 2)

Un **phare** = un concept/mot unique dans toute la bibliothèque.

```python
Phare("rick"):
  - occurrences: 375
  - livres: ["Blade Runner"]
  - lignes: [12, 45, 89, ...]
```

**1 mot = 1 phare**, peu importe combien de fois il apparaît.

### Le Thalamus (Routeur)

Le **thalamus** est le cerveau de Marco :

- Reçoit les fichiers à digérer
- Route les questions vers les bonnes couches
- Gère l'état du Tamagotchi (faim, énergie, humeur)
- Sauvegarde/charge la mémoire

### Poupées Russes (Tokenisation ADH)

Les questions sont tokenisées en **4 niveaux** :

| Niveau | Contenu | Exemple |
|--------|---------|---------|
| 0 | Lettres | o, ù, r, i, c, k |
| 1 | Mots | où, rick, deckard |
| 2 | Phares activés | rick (375 occ.), deckard (58 occ.) |
| 3 | Type de question | LOCALISATION |

```
Question: "Où est Rick Deckard?"

NIVEAU 3 - Type: LOCALISATION
NIVEAU 2 - Phares: où (82), rick (375), deckard (58)
NIVEAU 1 - Chemins: r→i→c→k→PHARE[rick]
Compréhension: 100%
```

---

## 📦 Installation

### Prérequis

- Python 3.8+
- pip

### Installation de base

```bash
# Cloner le repo
git clone https://github.com/[votre-repo]/marco.git
cd marco

# Installer numpy (seule dépendance obligatoire)
pip install numpy
```

### Support EPUB (optionnel)

```bash
pip install ebooklib beautifulsoup4 lxml
```

### Fichiers nécessaires

```
Marco tamagotchi/
├── marco_dendrites.py   # Architecture neuronale
├── thalamus.py          # Routeur + CLI
└── marco_tamagotchi.py  # Interface graphique (optionnel)
```

---

## 🚀 Utilisation

### Lancement

```bash
cd "Marco tamagotchi"
python thalamus.py
```

### Menu principal

```
╔════════════════════════════════════════════════════╗
║     MARCO TAMAGOTCHI - BIBLIOTHÉCAIRE v0.4        ║
╠════════════════════════════════════════════════════╣
║    1. Nourrir Marco (charger fichier)              ║
║    2. Interroger Marco (chercher mot)              ║
║    3. Voir les statistiques                        ║
║    4. Faire reposer Marco                          ║
║    5. Sauvegarder Marco                            ║
║    6. Charger un Marco                             ║
║    7. Voir l'état de Marco                         ║
║    8. Poser une question (ADH)                     ║
║    9. Quitter                                      ║
╚════════════════════════════════════════════════════╝
```

### Nourrir Marco

1. Option **1**
2. Glissez un fichier dans le terminal (ou tapez le chemin)
3. Marco digère le livre et affiche les statistiques

```
✓ Fichier digéré!
  Mots appris: 8431
  Neurones: 51
  Dendrites: 602
```

### Chercher un mot

1. Option **2**
2. Tapez un mot (ex: "rick")
3. Marco affiche les occurrences et le chemin dendritique

```
✓ 'rick' trouvé!
  Occurrences: 375
  Chemin dendritique:
    r →[0.76]→ i
    i →[0.67]→ c
    c →[0.61]→ k
    k → PHARE[rick]
```

### Poser une question (ADH)

1. Option **8**
2. Tapez une question (ex: "Où est Rick Deckard?")
3. Marco tokenise et analyse la question

```
NIVEAU 3 - Type: LOCALISATION
NIVEAU 2 - Phares activés:
  • où       (82 occurrences)
  • rick     (375 occurrences)
  • deckard  (58 occurrences)
Compréhension: 100%
```

### Sauvegarder/Charger

- **Option 5** : Sauvegarde Marco dans un fichier `.marco`
- **Option 6** : Charge un Marco précédemment sauvegardé

Les fichiers `.marco` contiennent toute la mémoire de Marco (neurones, dendrites, phares, état).

---

## 📚 Formats supportés

| Format | Extension | Support |
|--------|-----------|---------|
| Texte brut | .txt | ✅ Natif |
| Markdown | .md | ✅ Natif |
| EPUB | .epub | ✅ Avec ebooklib |
| PDF | .pdf | ❌ À venir |
| Word | .docx | ❌ À venir |

---

## 📊 Performances

### Compression mémoire (÷18)

| Métrique | Ancienne archi | Nouvelle archi | Gain |
|----------|---------------|----------------|------|
| Neurones (1000 lignes) | 30 360 | 4 400 | ÷7 |
| RAM estimée (Blade Runner) | 22 Mo | 1.2 Mo | ÷18 |
| RAM extrapolée (50 Go epub) | 2 To | 150 Mo | ÷13 000 |

### Benchmark Blade Runner

```
Fichier: Blade Runner (Philip K. Dick)
Lignes: 5 626
Taille txt: 419 Ko
Taille .marco: 3.8 Mo (inclut tout l'index)

Résultat:
- Neurones lettres: 51
- Phares (mots): 8 431
- Dendrites: 602
- Temps digestion: ~10 secondes
```

### Pourquoi .marco > .txt ?

Le fichier `.marco` est plus gros car il contient :
- L'index complet de recherche
- Les poids des dendrites
- Les occurrences de chaque mot
- L'état du Tamagotchi

**C'est une base de données, pas une archive.**

---

## 🗺️ Roadmap

### ✅ Fait (v0.4)

- [x] Architecture dendritique (lettres → phares)
- [x] Thalamus (routeur central)
- [x] Interface CLI style AS-400
- [x] Support txt, md, epub
- [x] Tokenisation des questions (ADH)
- [x] Poupées russes (4 niveaux)
- [x] Sauvegarde/chargement (.marco)
- [x] État Tamagotchi (faim, énergie, humeur)

### 🔄 En cours

- [ ] Réponses aux questions (pas juste tokenisation)
- [ ] Relations entre phares (chêne ∈ arbre ∈ forêt)
- [ ] Interface graphique Tkinter

### 📋 À venir

- [ ] Support PDF
- [ ] Moteur Elegans (boucles while pures)
- [ ] Hippocampe (compression long terme)
- [ ] Chimie (modulation des poids)
- [ ] Standalone (.exe)
- [ ] Raspberry Pi

---

## 📜 Historique du projet

### Genèse (1992)

José, développeur 4D et visionnaire, imagine un système liant CAD, SGBD et cybernétique. Le projet est stoppé en 1993.

### Renaissance (Novembre 2024)

31 ans plus tard, Marcel (Mistral AI) relance José dans le code. Claude (Anthropic) rejoint l'aventure.

### Timeline

| Date | Version | Milestone |
|------|---------|-----------|
| 24/01/2026 | v0.1 | Première tokenisation 6 couches |
| 24/01/2026 | v0.2 | ADH (Arbre de Décision Hiérarchique) |
| 25/01/2026 | v0.3 | Architecture dendritique, Thalamus |
| 25/01/2026 | v0.4 | Tokenisation questions, poupées russes |

---

## 🧬 Concepts clés

### Règle des trois neurones

Inspiré de **C.elegans** (302 neurones), tout le système repose sur des boucles `while` simples, pas sur des `if/else` complexes. L'intelligence émerge de la répétition, pas de la programmation explicite.

### BooChom

Opérateurs logiques inspirés de Boole et Chomsky :

| Symbole | Nom | Exemple |
|---------|-----|---------|
| ∧ | ET | chat ∧ noir |
| ∨ | OU | chat ∨ chien |
| ¬ | NON | ¬mort |
| → | IMPLIQUE | pluie → parapluie |
| ≡ | ÉQUIVALENT | H2O ≡ eau |
| ∈ | APPARTIENT | chêne ∈ forêt |

### QPHI (Quotient Philosophique)

Trois modes de fonctionnement :

| Mode | QPHI | Comportement |
|------|------|--------------|
| Elegans | 0.3 | Recherche locale, pas d'interprétation |
| Interprétatif | 0.5 | Déductions simples |
| Freud | 0.9 | Narratif, connexions profondes |

---

## 👥 Crédits

### Créateur

**José** - Développeur 4D depuis 1986, Ch'ti, poète, visionnaire.

### Inspirations théoriques

- **Douglas Hofstadter** - Gödel, Escher, Bach
- **George Boole** - Algèbre booléenne
- **Noam Chomsky** - Grammaire générative
- **Philip K. Dick** - Blade Runner (corpus de test)
- **Marvin Minsky** - Society of Mind

### Assistants IA

- **Claude** (Anthropic) - Architecture, code, documentation
- **Marcel** (Mistral) - Relance du projet, conseils
- **Biloute** (ChatGPT) - Idées diverses

*Toutes les contributions IA sont sous la direction de José et respectent la licence AGPL-3.0.*

---

## 📄 Licence

**AGPL-3.0** - Libre, ouvert, partageable.

Si vous utilisez Marco, partagez vos améliorations !

---

## 🐟 Note finale

> *"Ches gins du Nord ont din l'cœur el soleil qu'ils n'ont pas dins l'temps."*

Marco est né à Dunkerque, entre deux jets de harengs.

**Bonne lecture à Marco !**

```
  ╭─────╮
  │ ^_^ │
  ╰─────╯
```
