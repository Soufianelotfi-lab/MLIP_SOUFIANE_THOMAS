# Classification des Planètes et Lunes

Ce projet explore et compare différentes approches de Machine Learning (ML) et de Deep Learning (DL) pour la classification d'images de planètes et de lunes. Nous avons mis en œuvre plusieurs modèles allant des méthodes classiques (SVM, Forêts Aléatoires) aux réseaux de neurones convolutifs (CNN) pour identifier automatiquement les Planète.

## 👥 Auteurs
Projet réalisé par **Soufiane** et **Thomas**.

## 📂 Jeu de Données
Le jeu de données utilisé est **"Planets and Moons Dataset - AI in Space"**, provenant de Kaggle.

- **Source :** [Kaggle - Planets and Moons Dataset](https://www.kaggle.com/datasets/emirhanai/planets-and-moons-dataset-ai-in-space)
- **Classes sélectionnées :** Nous avons restreint notre étude aux 6 classes suivantes :
  - 🌍 Earth (Terre)
  - 🌕 Jupiter
  - 🔴 Mars
  - 🔵 Neptune
  - ⚪ Pluto (Pluton)
  - 🌟 Venus (Vénus)
- **Volume :** Environ 150 images par classe.
- **Répartition des données :**
  - Entraînement (Train)(ML et DL) : 80%
  - Test (ML) : 20%
  - Validation (Val) (DL) : 10%
  - Test (DL): 10%
    
## 🛠️ Installation et Prérequis
Les notebooks sont conçus pour fonctionner sur Google Colab ou un environnement local avec support GPU recommandé pour le CNN.

**Dépendances principales :**
```bash
pip install torch torchvision numpy pandas scikit-learn scikit-image opencv-python mahotas matplotlib seaborn kagglehub tqdm
```

## 🚀 Méthodologie et Modèles

- ### 1. Deep Learning : CNN (**Classification_CNN.ipynb**)
  Nous avons implémenté un Réseau de Neurones Convolutif (CNN) utilisant la librairie PyTorch.

    - Fonctionnalités :
  
      - Téléchargement et structuration automatique du dataset.
      
      - Prétraitement : Redimensionnement (224x224), normalisation, data augmentation.
      
      - Architecture CNN personnalisée (couches de convolution, pooling, dropout).
      
      - Entraînement sur GPU avec suivi de la perte (loss) et de la précision (accuracy).
      
      - Génération de la matrice de confusion et du rapport de classification.
      
    - Remarques :
      
      - Ouvrir dans Google Colab.
      
      - Activer le GPU (Exécution > Modifier le type d'exécution > T4 GPU).
      
      - Exécuter toutes les cellules. Le modèle s'entraînera sur 30 époques par défaut.
    
- ### 2.Machine Learning : SVM (**Classification_planet_(SVM).ipynb**)
    Utilisation d'un Support Vector Machine (SVM) avec une étape d'extraction de caractéristiques manuelles.
  
    - Fonctionnalités :
  
      - Extraction d'un vecteur de caractéristiques combinant :
      
      - Couleur : Histogrammes HSV.
      
      - Texture : Local Binary Patterns (LBP) via la librairie mahotas.
      
      - Forme : Histogram of Oriented Gradients (HOG).
      
      - Entraînement d'un Support Vector Machine (SVM).
      
      - Visualisation des performances (Accuracy, Matrice de confusion).
       
    - Remarques :
      
      - Ouvrir dans Google Colab.
      
      - Exécuter toutes les cellules.
      
- ### 3.Machine Learning : Arbres & Forêts (**Classification_Planet_DT_RF.ipynb**)
    Comparaison des performances entre un Arbre de Décision (Decision Tree) et une Forêt Aléatoire (Random Forest) avec une étape d'extraction de caractéristiques manuelles.
  
    - Fonctionnalités :
  
      - Utilise la même pipeline d'extraction de features (Couleur + LBP + HOG).
      
      - Comparatif : Entraîne plusieurs modèles en faisant varier la profondeur maximale (max_depth) et le nombre d'arbres.
      
      - Affiche des graphiques comparant le temps d'entraînement et la précision (Accuracy).
      
    - Remarques :
      
      - Ouvrir dans Google Colab.
      
      - Exécuter toutes les cellules.
    

