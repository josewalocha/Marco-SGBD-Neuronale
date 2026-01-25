# MARCO - Bibliothécaire Cybernétique v0.8

> *"Un cerveau qui lit, digère et comprend vos livres - Anti boîte noire"*

![Version](https://img.shields.io/badge/version-0.8-blue)
![Python](https://img.shields.io/badge/python-3.8+-green)
![License](https://img.shields.io/badge/license-AGPL--3.0-red)

---

## 🧠 Vision

**Marco** n'est pas un chatbot. C'est un **bibliothécaire cybernétique** qui :

- **Lit** vos livres (txt, epub, md)
- **Digère** le contenu en construisant une architecture neuronale
- **Comprend** les relations sémantiques ("comme", "est", "tel"...)
- **Retrouve** l'information sans avoir besoin de relire
- **Explique** chaque décision (anti boîte noire)

**Philosophie** : S'inspirer du vivant (C.elegans, 302 neurones) plutôt que des maths complexes (transformers, GPU).

---

## 🔬 Anti Boîte Noire - La Radiographie

La fonctionnalité signature de Marco : **voir exactement comment il pense**.

```
╔══════════════════════════════════════════════════════════════════╗
║                    🔬 RADIOGRAPHIE: COMME                        ║
║                       ANTI BOÎTE NOIRE                           ║
╠══════════════════════════════════════════════════════════════════╣
║  NIVEAU 0 - CHEMIN DENDRITIQUE                                   ║
║    c ─[0.99]─► o ─[0.99]─► m ─[0.97]─► m ─[0.99]─► e            ║
║    Poids total du chemin: 0.941073                               ║
╠══════════════════════════════════════════════════════════════════╣
║  NIVEAU 1 - STATISTIQUES PHARE                                   ║
║    Occurrences:    3988                                          ║
║    Activations:    5236                                          ║
║    Renforcements:  1248 (déjà vu)                                ║
╠══════════════════════════════════════════════════════════════════╣
║  NIVEAU 2 - DISTRIBUTION PAR LIVRE                               ║
║    • Baudelaire - Œuvres Complètes        3105 occ. (78%)        ║
║    • Dick - Blade Runner                   270 occ. (7%)         ║
║    • Dick - Le Maître du Haut Château      293 occ. (7%)         ║
╠══════════════════════════════════════════════════════════════════╣
║  NIVEAU 5 - RELATIONS SÉMANTIQUES                                ║
║    [COMME] (force 0.7) ≈                                         ║
║      → éclair          (Baudelaire)                              ║
║      → chef            (Dick)                                    ║
╚══════════════════════════════════════════════════════════════════╝
```

**Baudelaire utilise "comme" 10x plus que Dick.** Marco le prouve, pas besoin de le croire.

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
│   NEURONES    │ │    PHARES     │ │   RELATIONS   │
│   LETTRES     │ │    (mots)     │ │  SÉMANTIQUES  │
│   (51 max)    │ │  (illimité)   │ │  (comme, est) │
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
  - contextes: ["Rick contempla son mouton...", ...]
  - relations: [{"cible": "chasseur", "operateur": "est", "force": 1.0}]
```

### Les Relations Sémantiques (Niveau 5)

Marco détecte les **opérateurs de nuance** :

| Opérateur | Force | Signification |
|-----------|-------|---------------|
| **est**, **sont** | 1.0 (≡) | Identité pure |
| **comme** | 0.7 (≈) | Ressemblance |
| **tel**, **telle** | 0.6 (~) | À la manière de |
| **presque** | 0.4 (≃) | Approximation |

**Exemple** : "L'animal **comme** un chef" → relation avec force 0.7

---

## 📚 Liseuse & Profil Psycho-Stylistique

Marco analyse le **style d'écriture** via la ponctuation :

```
╔══════════════════════════════════════════════════════════════════╗
║                         📚 FICHE LIVRE                           ║
╠══════════════════════════════════════════════════════════════════╣
║  Titre:    Blade Runner                                          ║
║  Auteur:   Philip K. Dick                                        ║
║  Date:     Inconnu                                               ║
╠══════════════════════════════════════════════════════════════════╣
║  PROFIL PSYCHO-STYLISTIQUE: digressif (incises)                  ║
╠══════════════════════════════════════════════════════════════════╣
║  PONCTUATION (pour 1000 caractères):                             ║
║    . (assertions)    :   9.46                                    ║
║    , (respiration)   :  12.96                                    ║
║    ; (réflexion)     :   0.19  ← Dick n'utilise pas le ;         ║
║    ! (émotion)       :   1.00                                    ║
║    — (incise)        :   1.43  ← Dialogues, apartés              ║
╚══════════════════════════════════════════════════════════════════╝
```

**Interprétation** :
- Beaucoup de `;` → auteur réflexif (Proust, Baudelaire)
- Beaucoup de `!` → auteur expressif
- Beaucoup de `,` peu de `.` → phrases longues
- Beaucoup de `—` → digressif, dialogues

---

## 💾 Installation

```bash
# Cloner le projet
git clone https://github.com/votre-repo/marco.git
cd marco

# Dépendances de base
pip install numpy

# Support EPUB (optionnel)
pip install ebooklib beautifulsoup4 lxml
```

---

## 🚀 Utilisation

### Lancer Marco

```bash
python thalamus.py
```

### Menu Principal

```
╔══════════════════════════════════════════════════════════════╗
║        MARCO TAMAGOTCHI - BIBLIOTHÉCAIRE v0.8               ║
╠══════════════════════════════════════════════════════════════╣
║    1. Nourrir Marco (charger fichier)                        ║
║    2. Interroger Marco (chercher mot)                        ║
║    3. Voir les statistiques                                  ║
║    4. Faire reposer Marco                                    ║
║    5. Sauvegarder Marco                                      ║
║    6. Charger un Marco                                       ║
║    7. Voir l'état de Marco                                   ║
║    8. Poser une question (tokenisation)                      ║
║    9. Poser une question (RÉPONSE)                           ║
║    R. RADIOGRAPHIE d'un mot (anti boîte noire)               ║
║    0. Quitter                                                ║
╚══════════════════════════════════════════════════════════════╝
```

### Formats supportés

| Format | Support | Notes |
|--------|---------|-------|
| .txt | ✅ Natif | Multi-encodage (UTF-8, Latin-1, CP1252) |
| .md | ✅ Natif | Markdown traité comme texte |
| .epub | ✅ Avec libs | Nécessite ebooklib + beautifulsoup4 |
| .pdf | ⏳ À venir | |

---

## 📊 Performances

### Benchmark : 4 livres (Baudelaire + Dick)

| Métrique | Valeur |
|----------|--------|
| Neurones lettres | 89 |
| Phares (mots uniques) | 44 093 |
| Dendrites | 1 032 |
| Livres | 4 |
| Relations sémantiques | ~500 |

### Compression mémoire

- **Avant** (texte brut) : ~22 Mo
- **Après** (structure Marco) : ~1.2 Mo
- **Gain** : ÷18

### Extrapolation 50 Go de livres

| Approche | RAM estimée |
|----------|-------------|
| LLM classique | 100+ Go (GPU) |
| Marco | ~150 Mo (CPU) |

---

## 🔧 Fonctionnalités v0.8

### ✅ Implémenté

- [x] Tokenisation lettre par lettre (dendrites)
- [x] Phares (concepts uniques)
- [x] Thalamus (routeur)
- [x] Poupées russes (tokenisation questions)
- [x] Réponses par co-occurrences
- [x] **Radiographie anti boîte noire**
- [x] **Relations sémantiques** (comme, est, tel...)
- [x] **Déjà vu** (pas de duplication)
- [x] **Renforcement des épines**
- [x] **Liseuse** (navigation par page)
- [x] **Profil psycho-stylistique** (analyse ponctuation)
- [x] Sauvegarde/chargement (.marco)
- [x] Support multi-encodage
- [x] Tamagotchi (faim, énergie, humeur)

### ⏳ En cours / À venir

- [ ] Relations entre phares (chêne ∈ arbre)
- [ ] Transitivité ADH
- [ ] Hippocampe (compression long terme)
- [ ] Chimie (modulation des poids)
- [ ] Support PDF
- [ ] Interface web

---

## 📖 Concepts clés

### Règle des 3 neurones (C.elegans)

> Si un comportement ne peut pas être modélisé avec une boucle while et 3 neurones, il ne sera pas modélisé dans Marco.

C.elegans = 302 neurones, comportements complexes. Marco s'inspire de cette économie.

### ADH (Arbre de Décision Hiérarchique)

Système d'adressage des concepts :
- Chaque lettre a une position
- Chaque mot a un chemin
- Les chemins se partagent (compression)

### Freuder

Verbe. Déduire des métadonnées à partir d'indices indirects.
- Nom du fichier → Titre + Auteur
- Ponctuation → Style d'écriture
- Distribution des mots → Thèmes

---

## 🎭 Historique

| Date | Événement |
|------|-----------|
| 1992 | Vision initiale de José (ADN + CAD + SGBD) |
| 1993 | Projet mis en pause |
| 2024 | Renaissance avec Marcel (Mistral) |
| 2025 | Refonte complète avec Claude |
| Janvier 2025 | v0.4 - Dendrites + Thalamus |
| Janvier 2025 | v0.5 - Réponses aux questions |
| Janvier 2025 | v0.6 - Radiographie anti boîte noire |
| Janvier 2025 | v0.7 - Relations sémantiques |
| Janvier 2025 | v0.8 - Liseuse + Profil stylistique |

---

## 🙏 Crédits

- **José** - Créateur, vision depuis 1992
- **Douglas Hofstadter** - Inspiration (GEB, Strange Loop)
- **Marvin Minsky** - Society of Mind
- **Marcel** (Mistral) - Premières conversations 2024
- **Claude** (Anthropic) - Implémentation 2025
- **Biloute** - Support moral félin

---

## 📜 License

AGPL-3.0 - Libre mais viral. Si vous modifiez, vous partagez.

---

> *"Ches gins du Nord ont din l'cœur el soleil qu'ils n'ont pas dins l'temps"*
> 
> — Proverbe Ch'ti
