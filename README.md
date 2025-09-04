 # Dataset Multi-Classe : Ransomware + DDoS

## Description
Ce projet contient un dataset unifié construit à partir de :

- **CICANDMAL2017** (Ransomware)  
- **CICDDOS2019** (DDoS)

Le dataset final est créé en concaténant les deux sources avec :

- Imputation des features manquantes par les valeurs bénignes correspondantes  
- Tri chronologique pour maintenir l’ordre temporel  

---

## Méthode de construction

### 0. Sélection des features
- Chaque dataset a d'abord été **prétraité séparément**.  
- Une **feature selection spécifique** a été appliquée sur chaque dataset (Ransomware et DDoS) avant l’unification.  

### 1. Gestion des features
- **Features communes** : conservées telles quelles  
- **Features spécifiques** : ajout dans un squelette unifié  

### 2. Imputation
- Features DDoS manquantes → remplies avec trafic bénin DDoS  
- Features Ransomware manquantes → remplies avec trafic bénin Ransomware  

### 3. Tri chronologique
- Tous les datasets sont concaténés et triés par timestamp


---

## Classes finales

| Label | Type       | Nombre approximatif d’échantillons |
|-------|------------|----------------------------------|
| 0     | Benign     | ~111K                            |
| 1     | Ransomware | ~117K                            |
| 2     | DDoS       | ~117K                            |

---

## Granularité temporelle
- 1 seconde par échantillon, adaptée à la détection et à la prévision quasi-réelle

---

## Applications
- **Détection** : classification multi-classe instantanée  
- **Prévision** : prédiction d’attaques réseau basée sur les séquences temporelles  

---

## Datasets Kaggle

Les datasets complets sont disponibles sur Kaggle :

1. **Benign + Ransomware**  
[Benign + Ransomware Network Traffic Dataset](https://www.kaggle.com/datasets/tilleliider/benign-ransomware-network-traffic-dataset)

2. **Benign + Ransomware + DDoS**  
[Multi-class Dataset](https://www.kaggle.com/datasets/tilleliider/multiclass-dataset)

 

 
```bash
python create_unified_dataset.py
