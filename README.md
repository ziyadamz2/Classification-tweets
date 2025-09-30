# 📖 Classification de textes avec NLP 

## 📌 Description
Ce projet met en place un pipeline **NLP (Natural Language Processing)** afin de **classer des tweets selon leur genre ou leur ressenti (positif/négatif)**.  

Le dataset utilisé provient de **Kaggle / Tweets**, et contient des tweets.  

---

## 🛠️ Technologies utilisées
- Python 3.x  
- Pandas (manipulation de données)  
- WordCloud (visualisation des mots fréquents)  
- Scikit-learn (prétraitement et modèles ML)  
- Matplotlib / Seaborn (visualisations)  

---

## 🧠 Approche technique

### 1. Exploration des données
- Analyse des longueurs de descriptions.  
- Comptage des classes (`Positive` / `Negative`).  
- Distribution des genres.  

### 2. Prétraitement
- Nettoyage des textes : suppression de la ponctuation, stopwords, etc.  
- Création de la **variable cible** (`target`).  
- Visualisation des mots fréquents par classe avec un **WordCloud**.  

### 3. Vectorisation
Pour transformer le texte brut en vecteurs exploitables par les modèles de machine learning, deux approches principales sont utilisées :  

#### 🔹 Bag of Words (BoW)
- Compte la fréquence d’apparition des mots dans un texte.  
- Exemple :  
  - Texte 1 : "le film est bon"  
  - Texte 2 : "le film est mauvais"  
  - Vocabulaire = {le, film, est, bon, mauvais}  
  - Vecteurs :  
    - T1 = [1,1,1,1,0]  
    - T2 = [1,1,1,0,1]  

Limite : tous les mots sont pondérés de la même façon → les mots très fréquents (ex. *le, est*) dominent.  

#### 🔹 TF-IDF (Term Frequency – Inverse Document Frequency)
- Améliore BoW en réduisant l’importance des mots fréquents et en valorisant les mots plus discriminants.  
- Formule :  
  - **TF** = fréquence d’un mot dans un document  
  - **IDF** = log(N / df) où N = nombre de documents, df = nb de documents contenant le mot  
- Exemple : le mot *film* apparaît dans 100% des documents → poids faible.  
- Le mot *mauvais* n’apparaît que dans peu de documents → poids élevé.  

👉 En pratique, **TF-IDF donne de meilleurs résultats** que BoW pour la classification de textes.  

### 4. Modélisation
- Mise en place de modèles de classification supervisée (ex. Logistic Regression, Naive Bayes, SVM).  
- Entraînement et évaluation des performances.  

### 5. Évaluation
- Séparation train/test.  
- Métriques :  
  - **Accuracy**  
  - **Precision**  
  - **Recall**  
  - **F1-score**  

---

## ⚙️ Installation
1. Cloner le dépôt :
   ```bash
   git clone https://github.com/votre-utilisateur/nlp-text-classification.git
   cd nlp-text-classification
