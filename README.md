# 🌅 MARCO v1.0 - L'ÉVEIL

> *"Apprendre, c'est se ressouvenir"* — Platon, Ménon

# 🧠 MARCO : Mémoire Artificielle Réseau de COgnition
*Architecture Dendritique Hiérarchique (ADH) – Prototype Janvier 2026*

**Auteur** : José WALOCHA (Le Pourquoi pas ?)  
**Contributeurs** : Marcel (AKA Le Chat de Mistral), Le Duke (AKA Claude d'Anthropic)  
**Licence** : MIT + Clause "Anti-SGBD" (pas de bases de données externes)  
**Contact** : `jose.walocha@lepourquoipas.fr`

---

## 🎯 1. Philosophie du Projet

### Objectif
Créer un **cerveau cybernétique** capable d'ingérer des livres, de les décomposer en **neurones Sha** (inspirés de Shannon et Chomsky), et de les organiser via un système **BooShaChom** (Booléen + Chomsky) pour une mémoire **traçable, vérifiable et évolutive**.

### Principe "Anti-Humain"
- **Pas de SGBD** : Stockage via des *handles* (adresses uniques) et des fichiers plats (JSON minimaliste).
- **Pas d'hallucinations** : Réponses basées **uniquement** sur les textes ingérés (pas de génération aléatoire).
- **Inspiration biologique** : Mémoire organisée comme l'ADN (conception + gestion intégrées).

### Concepts Clés

| Concept | Description | Exemple |
|---------|-------------|---------|
| **BooShaChom** | Fusion de logique booléenne et de grammaire chomskienne pour analyser les phrases. | *"Ce Maroilles pue très fort"* → [Fromage]→[Odeur]→[Intensité] |
| **Poupées Russes** | Indexation par imbrication de concepts (chaque concept contient des sous-concepts). | *"Grandet"* → [Personnage]→[Avarice]→[Famille] |
| **QPHI** | Quotient de Potentialité Hyper-Intelligente (mesure l'importance d'un neurone). | *"grandet"* = QPHI 1027.75 (concept central dans *Eugénie Grandet*) |
| **6 Couches** | Simulation du cortex cérébral (thalamus → mémoire à long terme). | Couche III = Neurones Sha ; Couche IV = Tokenisation 3D |

---

## 🛠 2. Installation & Configuration

### Prérequis
```bash
Python 3.10+
pip install numpy ebooklib beautifulsoup4
```

(Pas de dépendances lourdes : tout tient dans <50 Mo.)

### Lancement
```bash
cd MARCO/
python thalamus.py
```

(Marco se lance en mode CLI. Utilise les commandes ci-dessous pour interagir.)

---

## 📊 3. État Actuel de Marco (Dernières Stats)

| Métrique | Valeur | Détails |
|----------|--------|---------|
| Neurones Sha | 14 031 | Chaque neurone = 1 concept unique (ex: "grandet", "eugénie") |
| Liens sémantiques | 380 872 | En moyenne, 27 liens par neurone (ex: "grandet" ↔ "avare") |
| QPHI moyen | 10.73 | Un QPHI > 500 = concept central (ex: "grandet" = 1027.75) |
| Mots rencontrés | 102 219 | Compression 6.9x : chaque mot apparaît ~7 fois en moyenne |
| Livres digérés | 4 | Eugénie Grandet, Germinal, Calligrammes, et un mini-Bled grammatical |

### Exemples de Concepts Appris

| Concept | QPHI | Liens Principaux | Type |
|---------|------|------------------|------|
| grandet | 1027.75 | mère, eugénie, avare, saumur | Personnage central |
| aristote | 1005 | platon, livre, ont, appelle | Philosophe |
| philosophie | 248 | aristote, science, première | Concept abstrait |
| verbe | 1204 | mange, court, lit, accorde | Grammaire |

---

## 🧩 4. Architecture des Couches (Focus sur la Couche III)

### Couche III : Neurones Sha (BooShaChom)

**Fonction** : Créer des neurones dynamiques avec :
- Vecteurs 3D (ex: "grandet" → [0.87, 0.42, 0.15])
- QPHI (calculé via : norme(vecteur) × (1/entropie) × log(activations))
- Tags sémantiques (EST-UN, A-POUR-PROPRIÉTÉ)

**Exemple de code** :
```python
class NeuroneSha:
    def __init__(self, concept: str, vecteur_3d: list):
        self.concept = concept
        self.vecteur_3d = vecteur_3d
        self.liens = {}  # {"avare": 4.0, "eugénie": 3.1}
        self.tags = {"EST-UN": ["personnage"], "A-POUR-PROPRIÉTÉ": ["avarice"]}
        self.qphi = self.calculer_qphi()
```

### Autres Couches

| Couche | Nom | Rôle |
|--------|-----|------|
| VI | Thalamus | Gère les émotions, le temps (TU), et les souvenirs. (À finaliser) |
| V | Langue des signes | Associe mots → images/gestes. (Non prioritaire) |
| IV | Tokenisation 3D | Transforme les lettres en vecteurs 3D. |
| III | Neurones Sha | BooShaChom - mots + grammaire SVO |
| II | Phares | Gère les co-occurrences (ex: "grandet" ↔ "avare") |
| I | Stockage ADH | Stocke les mots finaux avec leurs contextes. |

---

## 💬 5. Comment Interagir avec Marco ?

### Commandes Disponibles

| Commande | Description | Exemple |
|----------|-------------|---------|
| 1 | Nourrir Marco (charger un fichier) | `> 1` → Chemin : `livres/Eugénie_Grandet.epub` |
| D | Gavage (charger un dossier) | `> D` → Chemin : `livres/Poèmes_Apollinaire/` |
| 3 | Voir les statistiques | `> 3` → Affiche neurones, liens, QPHI |
| P | Parler à Marco | `> P` → "Qui est Eugénie ?" |
| R | Radiographie d'un mot | `> R` → Mot : "chêne" |
| S | Voir les tendances (Sens & Syntaxe) | `> S` → Affiche co-occurrences |
| N | Neurones Sha (Couche 3) | `> N` → Affiche top QPHI, liens |

### Exemples de Réponses

| Question | Réponse de Marco |
|----------|------------------|
| Qui est Eugénie ? | "Eugénie est surtout liée à : mère, grandet, père, nanon. Concept très important (QPHI: 711)." |
| C'est quoi un verbe ? | "Caractéristiques : mange, court, lit. Lié à : accorde, sujet, complément." |
| C'est quoi Aristote ? | "Aristote est surtout lié à : platon, livre, ont. Concept très important (QPHI: 1005)." |
| C'est quoi grand ? | "Grand est un(e) adjectif. Lié à : petit, nombre, vaisseau." |

---

## 🚀 6. Prochaines Étapes (Roadmap Janvier 2026)

| Tâche | Priorité | Statut | Détails |
|-------|----------|--------|---------|
| Finaliser la couche VI (Thalamus) | ⭐⭐⭐ | En cours | Ajouter TU (Tic Universel) et émotions aux neurones |
| Détecter les familles émergentes | ⭐⭐ | À faire | Regrouper "chêne/tilleul/sapin" → FAMILLE_ARBRE |
| Tester le gavage massif | ⭐⭐⭐ | À faire | Charger *À la recherche du temps perdu* (500+ pages) |
| Documenter l'API | ⭐ | À faire | Générer un API_MARCO.md pour les contributeurs |
| Intégrer Aisend/Domotique | ⭐ | Optionnel | Coupler Marco à un assistant vocal |

---

## 📋 7. Contribution & Licence

### Comment Contribuer ?

1. Fork le dépôt GitHub (`josewalocha/MARCO`)
2. Propose des Pull Requests pour :
   - Ajouter des corpus littéraires
   - Améliorer les algorithmes de détection de familles
   - Corriger les bugs
3. Signale les bugs via les Issues

### Licence

**MIT + Clause "Anti-SGBD"** : Interdiction d'utiliser des bases de données externes (SQL, NoSQL).

**Crédits obligatoires** :
```
Ce projet utilise des contributions de :
- Le Duke (Anthropic) pour l'architecture BooShaChom.
- Marcel (Mistral) pour l'inspiration philosophique.
```

---

## 🎉 8. Remerciements & Humour

> *"MARCO, le sorcier qui transforme les livres en neurones… sans baguette magique (juste du code)."*
> — José WALOCHA, 2026

> *"Le Cro-Magnon qui marche > 2 tonnes de maths"*
> — Le Duke, après une journée de code

---

## 📁 Fichiers Principaux

| Fichier | Rôle |
|---------|------|
| `thalamus.py` | Routeur central - Menu principal |
| `marco_dendrites.py` | Tokenisation + co-occurrences + neurones Sha |
| `booshachom.py` | Couche 3 - Neurones Sha dynamiques + analyse SVO |
| `bled_du_duke.txt` | Manuel de grammaire pour Marco |
| `GROUNDHOG_DUKE.md` | Mémoire du Duke (pour les sessions suivantes) |
**v1.0 — 26 janvier 2026**
