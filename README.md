 Dataset Multi-Classe : Ransomware + DDoS
Description

Ce projet propose un dataset unifié pour la détection et la prévision d’attaques réseau, construit à partir de deux sources publiques :

CICANDMAL2017 → trafic Ransomware

CICDDOS2019 → trafic DDoS

L’objectif est de fournir un jeu de données multi-classe équilibré, adapté à la recherche en cybersécurité, aussi bien pour la classification instantanée que pour la prévision temporelle.

Méthodologie de construction
0. Prétraitement & sélection des features

Chaque dataset a été préparé séparément.

Les features retenues sont celles qui ont été sélectionnées par au moins 3 méthodes sur 4 :

ANOVA (test F)

Random Forest Feature Importance

RFE (Recursive Feature Elimination) avec régression logistique

Régression Lasso (L1)

1. Gestion des features

Features communes → conservées telles quelles.

Features spécifiques → ajoutées dans un squelette unifié pour assurer la compatibilité.

2. Imputation des valeurs manquantes

Pour le DDoS : features manquantes remplacées par des valeurs issues du trafic bénin DDoS.

Pour le Ransomware : idem avec le trafic bénin Ransomware.

3. Fusion & tri chronologique

Les deux datasets sont concaténés.

L’ensemble est trié par timestamp afin de préserver l’ordre temporel.

Classes finales
Label	Type	Nombre d’échantillons
0	Benign	111,033
1	Ransomware	117,500
2	DDoS	117,248

Distribution des classes :

Classe 0 (Benign) → 111,033 échantillons

Classe 1 (Ransomware) → 117,500 échantillons

Classe 2 (DDoS) → 117,248 échantillons

Granularité temporelle

1 seconde par échantillon

Adapté à la détection en temps réel et à la prévision quasi-réelle des attaques.

Récapitulatif de l’analyse du dataset

Taille totale : 345,781 lignes × 42 colonnes (41 features + 1 label)

Répartition équilibrée :

Classe 0 (Benign) → 32.1%

Classe 1 (Ransomware) → 34.0%

Classe 2 (DDoS) → 33.9%

Qualité :

Aucune valeur manquante

Pas de doublons

Ordre chronologique respecté

Applications possibles

Détection : classification multi-classe instantanée des flux réseau

Prévision : détection précoce d’attaques via analyse de séquences temporelles

## Datasets Kaggle

Les datasets complets sont disponibles sur Kaggle :

1. **Benign + Ransomware**  
[Benign + Ransomware Network Traffic Dataset](https://www.kaggle.com/datasets/tilleliider/benign-ransomware-network-traffic-dataset)

2. **Benign + Ransomware + DDoS**  
[Multi-class Dataset](https://www.kaggle.com/datasets/tilleliider/multiclass-dataset)

 

 
```bash
python create_unified_dataset.py
