# 📚 TP - Prétraitement des Données Textuelles en NLP

## 🎯 Objectifs du TP

Ce travail pratique vous guidera à travers toutes les étapes essentielles du prétraitement de texte pour le Natural Language Processing (NLP), de la base jusqu'aux techniques avancées de Deep Learning.

**À la fin de ce TP, vous saurez :**
- ✅ Nettoyer et normaliser des données textuelles brutes
- ✅ Tokeniser et créer des n-grammes
- ✅ Appliquer la réduction linguistique (stemming, lemmatisation)
- ✅ Utiliser les techniques POS tagging et NER
- ✅ Préparer des données pour le Deep Learning (padding, troncature)
- ✅ Augmenter artificiellement vos datasets textuels
- ✅ Comprendre les bases de la transformation numérique

---

## 📋 Prérequis

### Connaissances requises
- Python de base (variables, boucles, fonctions)
- Manipulation de données avec Pandas (niveau basique)
- Notions de base en Data Science

### Logiciels nécessaires
- Python 3.8 ou supérieur
- Jupyter Notebook ou JupyterLab
- Connexion internet (pour télécharger les ressources NLTK et spaCy)

---

## 🚀 Installation

### Étape 1 : Cloner ou télécharger le projet

```bash
# Si vous utilisez Git
git clone [URL_DU_REPO]
cd tp-nlp-preprocessing

# Ou téléchargez simplement le dossier ZIP et extrayez-le
```

### Étape 2 : Créer un environnement virtuel (recommandé)

```bash
# Sur Windows
python -m venv venv
venv\Scripts\activate

# Sur macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Étape 3 : Installer les dépendances

```bash
pip install -r requirements.txt
```

### Étape 4 : Télécharger les modèles et ressources

```bash
# Télécharger les ressources NLTK
python -c "import nltk; nltk.download('stopwords'); nltk.download('punkt'); nltk.download('wordnet'); nltk.download('averaged_perceptron_tagger'); nltk.download('omw-1.4')"

# Télécharger les modèles spaCy
python -m spacy download fr_core_news_sm
python -m spacy download en_core_web_sm
```

### Étape 5 : Lancer Jupyter Notebook

```bash
jupyter notebook
```

Ouvrez ensuite le fichier `tp_nlp_preprocessing.ipynb` dans votre navigateur.

---

## 📖 Structure du TP

Le notebook est organisé en **8 parties progressives** :

### 🔧 **Partie 1 : Nettoyage de Base**
- Suppression HTML, URLs, emails
- Gestion des émojis et émoticônes
- Suppression de la ponctuation
- **Bonus** : Méthodes alternatives professionnelles

### 📝 **Partie 2 : Normalisation et Harmonisation**
- Conversion en minuscules
- Gestion des contractions
- Détection de langue

### 🔤 **Partie 3 : Tokenisation et N-grammes**
- Segmentation en phrases
- Tokenisation en mots
- Génération de 1-grammes, 2-grammes, 3-grammes

### ✂️ **Partie 4 : Réduction Linguistique**
- Suppression des stop words
- Stemming (racinisation)
- Lemmatisation
- Comparaison des techniques

### 🎯 **Partie 5 : Techniques Avancées**
- POS Tagging (étiquetage grammatical)
- Reconnaissance d'Entités Nommées (NER)
- Gestion des mots à faible fréquence

### 🔄 **Partie 6 : Pipeline Complet**
- Classe `PreprocesseurTexte` réutilisable
- Pipeline end-to-end
- Exemple d'application pratique

### 🧠 **Partie 7 : Prétraitement Deep Learning**
- **Padding** : uniformiser les longueurs
- **Troncature** : limiter les séquences longues
- **Augmentation de données** :
  - Substitution de synonymes
  - Rétro-traduction
  - Insertion/suppression aléatoire
- Pipeline complet pour réseaux de neurones

### 📊 **Partie 8 : Transformation Numérique (Aperçu)**
- Introduction à Bag of Words
- Introduction à TF-IDF
- *(Word Embeddings seront couverts dans un cours dédié)*

---

## 💡 Conseils d'utilisation

### Pour les débutants
1. **Suivez l'ordre des cellules** : Le notebook est conçu pour être progressif
2. **Exécutez chaque cellule** : Utilisez `Shift + Enter` pour exécuter et passer à la suivante
3. **Lisez les commentaires** : Chaque section est bien documentée
4. **Expérimentez** : Modifiez les exemples avec vos propres textes

### Pour les utilisateurs avancés
- Explorez les **méthodes alternatives** présentées
- Testez les fonctions avec vos propres datasets
- Adaptez la classe `PreprocesseurTexte` à vos besoins spécifiques
- Combinez plusieurs techniques pour créer votre pipeline personnalisé

---

## 🔍 Exemples de données utilisées

Le TP utilise des exemples variés et concrets :
- Textes en français et en anglais
- Exemples de réseaux sociaux (émojis, URLs)
- Citations littéraires (Stephen King)
- Textes d'actualité (Apple, Steve Jobs)
- Phrases Star Wars (pour les n-grammes)

---

## 📊 Résultats attendus

Après avoir complété ce TP, vous serez capable de :

```python
# Exemple de pipeline complet
preprocesseur = PreprocesseurTexte(langue='french')

texte_brut = "Bonjour! 😀 Visitez https://example.com pour + d'infos!!!"
tokens_propres = preprocesseur.pretraiter(texte_brut)

print(tokens_propres)
# Output: ['bonjour', 'visiter', 'info']
```

---

## 🛠️ Dépannage

### Problème : Erreur lors du téléchargement des modèles spaCy
```bash
# Solution : Utiliser pip au lieu de python -m
pip install https://github.com/explosion/spacy-models/releases/download/fr_core_news_sm-3.7.0/fr_core_news_sm-3.7.0-py3-none-any.whl
```

### Problème : Module 'contractions' introuvable
```bash
pip install contractions
```

### Problème : Erreur avec TensorFlow
```bash
# Pour les systèmes plus anciens, utilisez une version antérieure
pip install tensorflow==2.13.0
```

### Problème : Jupyter ne trouve pas le kernel
```bash
python -m ipykernel install --user --name=venv
```

---

## 📚 Ressources complémentaires

### Documentation officielle
- [NLTK Documentation](https://www.nltk.org/)
- [spaCy Documentation](https://spacy.io/)
- [TensorFlow Text](https://www.tensorflow.org/text)
- [Scikit-learn Text Feature Extraction](https://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction)

### Tutoriels recommandés
- [NLTK Book](https://www.nltk.org/book/)
- [spaCy Course](https://course.spacy.io/)
- [Hugging Face NLP Course](https://huggingface.co/course/)

### Bibliothèques avancées (optionnelles)
- **nlpaug** : Augmentation de données avancée
- **textaugment** : Plus de techniques d'augmentation
- **transformers** : Pour aller vers BERT, GPT, etc.

---

## 🤝 Contribution

Si vous trouvez des erreurs ou souhaitez améliorer ce TP :
1. Créez une issue pour signaler le problème
2. Proposez une pull request avec vos améliorations
3. Partagez vos retours d'expérience

---

## 📝 Notes importantes

### ⚠️ Limitations du TP
- La **transformation numérique** (Partie 8) est volontairement succincte
- Les **word embeddings** (Word2Vec, GloVe, FastText) seront couverts dans un cours dédié
- Certaines bibliothèques d'augmentation avancée sont optionnelles

### 💾 Données et vie privée
- N'utilisez pas de données sensibles ou personnelles dans ce TP
- Les exemples fournis sont fictifs ou issus du domaine public

---

## 🎓 Auteur et Contexte

Ce TP accompagne un exposé sur le prétraitement de texte en NLP et est conçu pour des étudiants ayant :
- ✅ Des bases solides en analyse de données tabulaires
- ✅ Des notions de Data Science
- ✅ Une volonté d'apprendre le NLP progressivement

**Objectif pédagogique** : Montrer que le NLP n'est pas difficile quand on progresse étape par étape ! 🚀

---

## 📞 Support

Pour toute question ou problème :
1. Consultez la section **Dépannage** ci-dessus
2. Vérifiez que toutes les dépendances sont installées
3. Relisez les commentaires dans le notebook
4. Recherchez l'erreur dans la documentation officielle

---

## 📅 Temps estimé

- **Installation** : 15-30 minutes
- **Parties 1-3** : 1h30
- **Parties 4-6** : 2h00
- **Partie 7** (Deep Learning) : 1h30
- **Partie 8** (Aperçu) : 30 minutes

**Total** : ~5-6 heures pour une compréhension approfondie

---

## ✅ Checklist de progression

Cochez au fur et à mesure :

- [ ] Installation complète et fonctionnelle
- [ ] Partie 1 : Nettoyage de base maîtrisé
- [ ] Partie 2 : Normalisation comprise
- [ ] Partie 3 : Tokenisation et n-grammes OK
- [ ] Partie 4 : Stemming vs Lemmatisation clair
- [ ] Partie 5 : POS et NER expérimentés
- [ ] Partie 6 : Pipeline complet testé
- [ ] Partie 7 : Techniques Deep Learning pratiquées
- [ ] Partie 8 : Aperçu transformation numérique vu
- [ ] Exercice final réalisé
- [ ] Testé avec mes propres données

---

## 🎉 Félicitations !

Une fois ce TP terminé, vous aurez acquis des compétences solides en prétraitement de texte, une étape qui représente 60-80% du travail dans un projet NLP réel !

**Prochaine étape** : Approfondir la transformation numérique et les word embeddings dans le cours dédié.

---

*Bon apprentissage ! 📖✨*