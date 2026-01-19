# Marco-SGBD-Neuronale
Un système léger de gestion de concepts sans SQL/JSON, inspiré des réseaux neuronaux.
# SGBD Neuronale Non-SQL / CCADH
*Un système léger pour organiser et manipuler des concepts sans bases de données classiques (SQL/JSON).*

---

## 📌 **Statut du Projet**
- **Phase actuelle** : Prototypage (objectif : 10 000 *handles*).
- **Licence** : [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.fr.html).
- **Auteur** : José Walocha.
- **Dernière mise à jour** : 19/01/2026.

---
## 🧠 **Architecture : 6 Couches (Inspiration Biologique)**
   Couche               | Rôle                                                                 | Analogies Biologiques          |
 |----------------------|----------------------------------------------------------------------|----------------------------------|
 | **1. Tic Universel** | Synchronisation temporelle (temps absolu/relatif).                | Horloge cellulaire.             |
 | **2. Phares/Handles**| Stockage des *handles* et de leurs liens.                          | Mémoire à long terme (ADN).     |
 | **3. BooChom**       | Validation logique/grammaticale (inspiré de Boole + Chomsky).      | Synapses (connexions neuronales).|
 | **4. Tokenisation**   | Décomposition des entrées en *handles*.                           | Transcription (ARN → protéines).|
 | **5. Traitement**    | Analyse sémantique (neurones miroirs).                           | Cortex sensoriel.               |
 | **6. Mémoire**       | Souvenirs et émotions associées aux *handles*.                     | Hippocampe (mémoire épisodique). |

*Flux* :
`Tokenisation → BooChom → Phares → Mémoire` (avec retour vers le Tic Universel).

## 🧠 **Concepts Clés**
### 1. **Les *Handles***
- **Définition** : Un *handle* est une **représentation unique** d’un concept (ex. : un mot, un livre, une idée).
- **Exemple** :
  ```python
  handle_Maroilles = {
      "id": "UI_001",
      "vecteur": ["ASCII_77", "ASCII_97", ...],
      "type": "nom",
      "liens": ["Fromages", "Doute"],
      "poids": {"Fromages": 0.9, "Doute": 0.7}
  }
2. Le BooChom
Mécanisme de calcul qui valide la cohérence entre les handles (grammaire + logique).
Formule :
boochom = (grammaire + logique) × (facteur_concept)^puissance
Exemple de calcul :
def calculer_boochom(sujet, verbe, complement):
    grammaire = 1 if est_SVC_valide(sujet, verbe, complement) else 0
    logique = 1 if sont_liens_coherents(sujet, verbe, complement) else 0
    return (grammaire + logique) * 0.9  # Facteur conceptuel
3. Hypervecteurs
Traces mémorielles des interactions entre handles.
Exemple :
hypervecteur_Maroilles = {
    "vecteur": ["M", "a", "r", ...],
    "contexte": {
        "phrase": "Ce Maroilles pue fort",
        "position": 2,  # 2ème mot de la phrase
        "émotion": {"nostalgie": 0.9}
    },
    "liens": ["Fromages_Puants"]
}
📂 Structure du projet
SGBD-Neuronale/
├── README.md          # Ce fichier
├── LICENSE            # Licence AGPL-3.0
├── requirements.txt    # Dépendances Python
├── sgbd/              # Code source
│   ├── handles.py     # Gestion des *handles*
│   ├── boochom.py     # Calcul du BooChom
│   └── adh.py         # Architecture hiérarchique
├── examples/          # Exemples d'utilisation
└── docs/              # Documentation

# Marco-SGBD-Neuronale
Un système léger de gestion de concepts sans SQL/JSON, inspiré des réseaux neuronaux.
# SGBD Neuronale Non-SQL / CCADH
*Un système léger pour organiser et manipuler des concepts sans bases de données classiques (SQL/JSON).*

---

## 📌 **Statut du Projet**
- **Phase actuelle** : Prototypage (objectif : 10 000 *handles*).
- **Licence** : [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.fr.html).
- **Auteur** : José Walocha.
- **Dernière mise à jour** : 19/01/2026.

---

## 🧠 **Concepts Clés**
### 1. **Les *Handles***
- **Définition** : Un *handle* est une **représentation unique** d’un concept (ex. : un mot, un livre, une idée).
- **Exemple** :
  ```python
  handle_Maroilles = {
      "id": "UI_001",
      "vecteur": ["ASCII_77", "ASCII_97", ...],
      "type": "nom",
      "liens": ["Fromages", "Doute"],
      "poids": {"Fromages": 0.9, "Doute": 0.7}
  }
2. Le BooChom
Mécanisme de calcul qui valide la cohérence entre les handles (grammaire + logique).
Formule :
boochom = (grammaire + logique) × (facteur_concept)^puissance
Exemple de calcul :
def calculer_boochom(sujet, verbe, complement):
    grammaire = 1 if est_SVC_valide(sujet, verbe, complement) else 0
    logique = 1 if sont_liens_coherents(sujet, verbe, complement) else 0
    return (grammaire + logique) * 0.9  # Facteur conceptuel
3. Hypervecteurs
Traces mémorielles des interactions entre handles.
Exemple :
hypervecteur_Maroilles = {
    "vecteur": ["M", "a", "r", ...],
    "contexte": {
        "phrase": "Ce Maroilles pue fort",
        "position": 2,  # 2ème mot de la phrase
        "émotion": {"nostalgie": 0.9}
    },
    "liens": ["Fromages_Puants"]
}
📂 Structure du projet
SGBD-Neuronale/
├── README.md          # Ce fichier
├── LICENSE            # Licence AGPL-3.0
├── requirements.txt    # Dépendances Python
├── sgbd/              # Code source
│   ├── handles.py     # Gestion des *handles*
│   ├── boochom.py     # Calcul du BooChom
│   └── adh.py         # Architecture hiérarchique
├── examples/          # Exemples d'utilisation
└── docs/              # Documentation

## 🚀 **Roadmap**

| Étape               | Objectif                                  | Statut      |
|---------------------|-------------------------------------------|-------------|
| Prototypage         | 10 000 *handles* fonctionnels            | En cours    |
| Couplage vocal      | Intégration avec un générateur de voix   | À venir     |
| Open Source         | Publication du code (licence AGPL)       | Prévu 2026 |
| Scalabilité         | Test avec 1 million de *handles*          | À venir     |

📜 Licence
Ce projet est sous licence AGPL-3.0 :

Utilisation libre, mais les modifications doivent rester open source.
Voir LICENSE pour les détails.


🎯 Pourquoi ce projet ?

"Un système où chaque concept est un handle interconnecté, sans boîte noire. L’objectif : une base de données neuronale, légère et transparente."
— José Walocha




