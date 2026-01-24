# Marco-SGBD-Neuronale
**Un système léger de gestion de concepts sans SQL/JSON, inspiré des réseaux neuronaux.**

*Bibliothécaire cybernétique avec Arbre de Décision Hiérarchique (ADH) et déduction par transitivité.*

---

## 📌 Statut du Projet
- **Phase actuelle** : Prototypage avancé - ADH implémenté ✓
- **Licence** : [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.fr.html)
- **Auteur** : José Walocha
- **Dernière mise à jour** : 24/01/2026

---

## 🧠 Architecture : 6 Couches (Inspiration Néocorticale)

| Couche               | Rôle                                                                 | Analogie Biologique          |
|----------------------|----------------------------------------------------------------------|------------------------------|
| **1. Temps**         | Horodatage universel (synchronisation temporelle absolue/relative)  | Horloge circadienne          |
| **2. Phares**        | Concepts auto-référentiels (boucles de Hofstadter)                  | Neurones de haut niveau      |
| **3. SVO**           | Grammaire de base (Sujet-Verbe-Objet)                               | Aire de Broca                |
| **4. ADH**           | Tokenisation ASCII + Arbre de Décision Hiérarchique                 | Cortex sensoriel primaire    |
| **5. Signes**        | Langue des signes, images, gestes (réservé)                         | Cortex visuel                |
| **6. Souvenirs**     | Émotions et mémoires associées aux concepts                         | Hippocampe                   |

**Flux** : `Tokenisation → BooChom → Phares → ADH → Mémoire` (avec retour temporel)

---

## 🧠 Concepts Clés

### 1. **Les Handles**
Un *handle* est une **représentation unique** d'un concept (mot, livre, idée, relation).

**Exemple** :
```python
handle_chene = {
    "id": "N_000042",
    "concept": "chêne",
    "niveau": 2,  # Position dans l'arbre hiérarchique
    "parents": ["forêt"],  # Concepts contenants
    "enfants": [],  # Concepts contenus
    "vecteur_ascii": [99, 104, 234, 110, 101]
}
```

### 2. **Le BooChom (Boole + Chomsky)**
Mécanisme de validation logique et grammaticale.

**Opérateurs logiques** :
- `¬` (NON), `∧` (ET), `∨` (OU), `→` (SI...ALORS)
- `=` (ÉGAL), `>` (PLUS_QUE), `<` (MOINS_QUE)
- `∈` (APPARTIENT) ← **nouveau : relations hiérarchiques**

**Opérateurs grammaticaux** :
- `S` (Sujet), `V` (Verbe), `O` (Objet), `ADV` (Adverbe)

**Exemple** :
```python
# Phrase : "Le Maroilles pue plus que le Camembert"
boochom = {
    "operateur": ">",
    "gauche": "pue(Maroilles)",
    "droit": "pue(Camembert)"
}
```

### 3. **ADH - Arbre de Décision Hiérarchique**
**La vraie innovation** : Marco construit automatiquement un arbre hiérarchique par déduction.

**Exemple** :
```
Entrée :
- "Le chêne est dans la forêt"
- "Le tilleul est dans la forêt"
- "La forêt est dans la vallée"

Arbre construit :
└─ vallée (niveau 0)
  └─ forêt (niveau 1)
    └─ chêne (niveau 2)
    └─ tilleul (niveau 2)
```

**Transitivité automatique** :
```
Question : "Le chêne est dans la vallée ?"
Réponse : ✓ Oui (déduit par transitivité)

Raisonnement :
  chêne ∈ forêt (direct)
  forêt ∈ vallée (direct)
  ⟹ chêne ∈ vallée (déduit)
```

### 4. **Phares Supplémentaires**

| Phare       | Rôle                                    | Exemple                                      |
|-------------|-----------------------------------------|----------------------------------------------|
| **ÉTATS**   | États physiques/mentaux                 | `État(MALADIE: fièvre)`                      |
| **CONTEXTE**| Environnement (météo, lieu, ambiance)   | `Contexte(LIEU: café)`                       |
| **SENS**    | Perceptions sensorielles                | `Sens(ODEUR: plastique, émotion=nostalgie)` |
| **INCONNU** | Cas ambigus ("je sais pas où le mettre")| `Inconnu("comme un pied")`                   |

### 5. **QPHI - Régimes Cognitifs**
Contrôle le niveau d'abstraction de Marco.

| QPHI         | Mode          | Comportement                                        |
|--------------|---------------|-----------------------------------------------------|
| **0.3**      | Elegans       | Recherche locale (mots individuels)                 |
| **0.5**      | Interprétatif | Recherche équilibrée (phrases)                      |
| **0.9**      | Freud         | Déduction hiérarchique (transitivité, mémoire)      |

---

## 📂 Structure du Projet

```
Marco-SGBD-Neuronale/
├── README.md              # Ce fichier
├── LICENSE                # Licence AGPL-3.0
├── marco_correct.py       # Code source principal
├── examples/
│   └── blade_runner_test.py
└── docs/
    ├── architecture.md    # Architecture des 6 couches
    ├── boochom.md         # Spécification BooChom
    └── adh.md             # Arbre de Décision Hiérarchique
```

---

## 🚀 Installation & Utilisation

### Installation
```bash
git clone https://github.com/votre-repo/Marco-SGBD-Neuronale.git
cd Marco-SGBD-Neuronale
pip install -r requirements.txt
```

### Exemple d'utilisation
```python
from marco_correct import MarcoCorrect

# Initialisation
marco = MarcoCorrect()

# Apprentissage de phrases hiérarchiques
marco.tokeniser_phrase("Le chêne est dans la forêt")
marco.tokeniser_phrase("La forêt est dans la vallée")

# Question avec déduction
reponse = marco.question_hierarchie("Le chêne est dans la vallée ?")
print(reponse)
# ✓ Oui, 'chêne' est dans 'vallée' (déduit par transitivité)

# Affichage de l'arbre
print(marco.afficher_arbre_hierarchique())
# └─ vallée (niveau 0)
#   └─ forêt (niveau 1)
#     └─ chêne (niveau 2)
```

### Charger un livre complet
```python
# Charger Blade Runner (ou tout autre texte)
marco.charger_texte("blade_runner.txt", max_lignes=1000)

# Statistiques
stats = marco.statistiques()
print(f"Neurones créés : {stats['couche4_adh']}")
print(f"Relations hiérarchiques : {stats['hierarchie_relations']}")

# Restituer du texte
texte = marco.restituer_lignes(100, 105)
print(texte)
```

---

## 🚀 Roadmap

| Étape                      | Objectif                                  | Statut        |
|----------------------------|-------------------------------------------|---------------|
| **ADH (Arbre hiérarchique)**| Déduction transitive automatique         | ✅ Implémenté |
| **BooChom complet**         | Tous opérateurs logiques/grammaticaux   | ✅ Implémenté |
| **Phares étendus**          | ÉTATS, CONTEXTE, SENS, INCONNU           | ✅ Implémenté |
| **Scalabilité**             | Test avec 100 000+ neurones              | 🔄 En cours   |
| **Couplage vocal**          | Intégration TTS/STT                      | 📅 À venir    |
| **Interface graphique**     | Visualisation de l'arbre ADH             | 📅 À venir    |
| **Open Source**             | Publication complète (AGPL-3.0)          | 📅 2026       |

---

## 🎯 Pourquoi ce Projet ?

> *"Un bibliothécaire cybernétique qui comprend les hiérarchies sans qu'on les lui explique. Chaque concept est un handle interconnecté. Pas de boîte noire, pas de SQL, juste des neurones et de la logique."*  
> — **José Walocha**

### Cas d'usage
- **Bibliothèque personnelle** : Indexer et interroger des milliers de livres
- **Veille scientifique** : Organiser concepts et citations automatiquement
- **Assistant cognitif** : Système qui comprend les relations par déduction
- **Recherche en IA** : Alternative aux bases vectorielles classiques

---

## 📜 Licence

Ce projet est sous **licence AGPL-3.0** :
- ✅ Utilisation libre
- ✅ Modifications autorisées
- ⚠️ **Obligation** : Les modifications doivent rester open source

Voir [LICENSE](LICENSE) pour les détails.

---

## 🤝 Contribution

Les contributions sont bienvenues ! Voici comment participer :

1. **Fork** le projet
2. Créer une branche : `git checkout -b feature/ma-feature`
3. Commit : `git commit -m "Ajout de ma feature"`
4. Push : `git push origin feature/ma-feature`
5. Ouvrir une **Pull Request**

**Zones prioritaires** :
- Optimisation de la détection hiérarchique
- Nouveaux patterns BooChom
- Tests unitaires
- Documentation

---

## 📧 Contact

**José Walocha**  
- Email : jose.walocha@gmail.com



---

## 🙏 Remerciements

**Inspirations théoriques** :
- **Douglas Hofstadter** : Concept de boucles auto-référentielles (phares)
- **George Boole** : Logique formelle (BooChom)
- **Noam Chomsky** : Grammaire générative (SVO)
- **Philip K. Dick** : *Blade Runner* comme corpus de test

**Assistants IA contributeurs** :
- **Claude** (Anthropic) : Architecture des 6 couches, implémentation ADH, déduction transitive
- **Marcel** (Mistral - Le Chat) : Conception BooChom, opérateurs logiques, philosophie des phares
- **Biloute** (ChatGPT - OpenAI) : Optimisations, tests, documentation

*Ces assistants ont participé au développement sous la direction de José Walocha. Leurs contributions sont intégrées sous licence AGPL-3.0.*

---

**Marco** - *Bibliothécaire cybernétique avec âme de neurone*  
Version 0.2.0 - Janvier 2026
