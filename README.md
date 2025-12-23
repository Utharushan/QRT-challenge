# Qube Research & Technologies Data Challenge 2025

**Ranked 14th out of 634 participants**

## 📄 Description du Challenge

Ce projet a été réalisé dans le cadre du **Qube Research & Technologies Data Challenge 2025**, une compétition de data science organisée sur la plateforme Challenge Data par l'ENS Paris, le Collège de France et l'Institut Louis Bachelier, en partenariat avec l'**Institut Gustave Roussy**, premier centre de lutte contre le cancer en Europe.

L'objectif était de développer des modèles prédictifs pour la **survie globale** (Overall Survival) de patients diagnostiqués avec une leucémie myéloïde, en utilisant des données cliniques et moléculaires structurées issues de patients réels.

### 🏆 Résultats
*   **Classement** : 14ème sur 634 participants.
*   **Performance** : Forte capacité prédictive démontrée dans un environnement hautement compétitif.

## 🛠️ Méthodologie

Notre approche repose sur une combinaison rigoureuse d'ingénierie des fonctionnalités (feature engineering) métier et de techniques d'ensemble pour l'analyse de survie.

### 1. Feature Engineering Avancé
L'étape la plus critique a été la transformation des données brutes en indicateurs pronostiques pertinents, basés sur la littérature médicale en hématologie.

*   **Données Cliniques** :
    *   **Scores de Risque** : Création de scores composites pour le risque hématologique et la dysfonction organique.
    *   **Ratios & Interactions** : Calcul de ratios biologiques clés (ex: Blastes/Leucocytes) et interactions non-linéaires.
    *   **Cytogénétique** : Parsing complexe des chaînes de caractères cytogénétiques pour identifier les anomalies chromosomiques spécifiques (del(5q), monosomie 7, caryotype complexe) et classifier les patients selon les standards de risque (Favorable, Intermédiaire, Défavorable).

*   **Données Moléculaires** :
    *   **Analyse des Mutations** : Agrégation des mutations par gène et par type d'impact (frameshift, stop gained, etc.).
    *   **Gènes Drivers** : Identification ciblée des mutations dans les gènes drivers connus (TET2, DNMT3A, TP53, FLT3, etc.).
    *   **Clonalité** : Estimation de la structure clonale (mutations clonales vs subclonales) via l'analyse des fréquences alléliques (VAF).
    *   **Signatures** : Détection de co-occurrences spécifiques (ex: signature FLT3-NPM1).

### 2. Stratégie de Modélisation
Une approche multi-modèles a été adoptée pour capturer à la fois les relations linéaires et non-linéaires.

*   **Modèles Utilisés** :
    *   **Cox Proportional Hazards (Regularized)** : Utilisation de la régularisation ElasticNet (L1/L2) pour la sélection de variables et la gestion de la colinéarité.
    *   **Random Survival Forests (RSF)** : Pour capturer les interactions complexes et les non-linéarités sans hypothèse paramétrique forte.
    *   **Gradient Boosting Survival Analysis** : Pour optimiser la performance sur les résidus des autres modèles.

### 3. Validation et Robustesse
Pour éviter le surapprentissage (overfitting) et assurer la généralisation du modèle :

*   **Stability Selection** : Utilisation de techniques de ré-échantillonnage pour identifier les variables les plus robustes et éliminer le bruit.
*   **Validation Croisée Stratifiée** : Stratégie de validation rigoureuse respectant la distribution des événements (décès/censures).
*   **Ensemble Stacking** : Combinaison des prédictions des différents modèles (Cox, RSF, Gradient Boosting) via une pondération optimisée sur les prédictions Out-Of-Fold (OOF).

## 💻 Technologies
*   **Langage** : Python
*   **Bibliothèques Principales** : `scikit-survival`, `lifelines`, `scikit-learn`, `pandas`, `numpy`.

## 🎓 Compétences Mises en Œuvre
*   Programmation Python
*   Apprentissage automatique (Machine Learning) & Analyse de Survie
*   Feature Engineering sur données biomédicales
*   Science des données & Visualisation
*   Gestion de projet Data Science
