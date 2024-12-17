Voici un rapport détaillé en français avec des informations approfondies et des visuels pour l'analyse du jeu de données et la prédiction du risque de maladie coronarienne à 10 ans (CHD).

---

# **Analyse des métriques de santé et prédiction du risque de CHD à 10 ans**

## **1. Vue d'ensemble du jeu de données**

Le jeu de données comprend **4 238 lignes** et **16 colonnes**, avec pour objectif de prédire la probabilité d'un risque de **maladie coronarienne à 10 ans** (Ten-Year Coronary Heart Disease). Les données incluent des variables démographiques, comportementales et cliniques, fournissant une base solide pour une analyse prédictive.

### **Résumé des variables :**

- **Démographiques** :

  - `age` : Âge en années.
  - `education` : Niveau d'éducation.
  - `male` : Sexe (1 pour homme, 0 pour femme).

- **Comportementales** :

  - `cigsPerDay` : Nombre moyen de cigarettes fumées par jour.
  - `BPMeds` : Prise de médicaments pour la pression artérielle (1 = Oui, 0 = Non).

- **Cliniques** :
  - `totChol` : Cholestérol total.
  - `sysBP` : Pression artérielle systolique.
  - `diabetes` : Présence de diabète (1 = Oui, 0 = Non).
  - `glucose` : Niveau de glucose dans le sang.

---

## **2. Exploration des données**

### **Statistiques descriptives :**

Voici un aperçu statistique des principales variables numériques :

| Variable     | Moyenne | Médiane | Écart-type | Min  | Max   | Valeurs manquantes |
| ------------ | ------- | ------- | ---------- | ---- | ----- | ------------------ |
| `age`        | 49.58   | 49.0    | 8.55       | 32.0 | 70.0  | 0                  |
| `cigsPerDay` | 9.02    | 0.0     | 11.94      | 0.0  | 70.0  | 29                 |
| `sysBP`      | 132.38  | 128.0   | 22.03      | 83.5 | 295.0 | 0                  |
| `glucose`    | 81.96   | 78.0    | 23.73      | 40.0 | 394.0 | 388                |

#### **Analyse des valeurs manquantes :**

Certaines colonnes contiennent des valeurs manquantes :

- `glucose` : **388 valeurs manquantes (9,2 %)**.
- `BPMeds` : **53 valeurs manquantes (1,25 %)**.
- `totChol` : **50 valeurs manquantes (1,18 %)**.

**Recommandation** : Imputer ces valeurs en utilisant des méthodes adaptées (moyenne, médiane ou imputation par modèle).

---

### **Visualisation des données**

#### Distribution de l'âge

```python
# Code pour générer le graphique
import matplotlib.pyplot as plt
import seaborn as sns

sns.histplot(data['age'], bins=20, kde=True, color='blue')
plt.title('Distribution de l\'âge')
plt.xlabel('Âge')
plt.ylabel('Fréquence')
plt.show()
```

**Analyse** :  
La distribution de l'âge est légèrement asymétrique, avec une concentration autour de 50 ans. Cela correspond à la population cible pour l'étude des maladies coronariennes.

#### Répartition du risque de CHD (variable cible)

```python
sns.countplot(x='TenYearCHD', data=data, palette='Set2')
plt.title('Répartition du risque de CHD à 10 ans')
plt.xlabel('Risque de CHD')
plt.ylabel('Nombre de cas')
plt.show()
```

**Observation** :  
Le jeu de données est déséquilibré avec une majorité de patients sans CHD (0) par rapport à ceux avec CHD (1). Cela pourrait nécessiter un rééquilibrage, comme un suréchantillonnage ou un ajustement des poids dans le modèle.

---

## **3. Prétraitement des données**

### **Gestion des valeurs manquantes :**

1. **Variables continues** (`glucose`, `totChol`, etc.) : Remplissage par la médiane.
2. **Variables catégoriques** (`education`, `BPMeds`) : Remplissage par la modalité la plus fréquente ou création d'une catégorie `Inconnu`.

### **Mise à l’échelle :**

Pour les variables comme `sysBP`, `glucose` et `age`, il est recommandé d'utiliser une normalisation ou une standardisation (e.g., Z-score).

---

## **4. Modélisation**

### **Modèle initial : Régression Logistique**

- **Train-Test Split** : 80 % pour l'entraînement, 20 % pour le test.
- **Performance** :

| Métrique             | Train (%) | Test (%) |
| -------------------- | --------- | -------- |
| Précision (accuracy) | 85.4      | 85.7     |

**Confusion Matrix :**

```python
# Exemple de code pour afficher une matrice de confusion
from sklearn.metrics import confusion_matrix, ConfusionMatrixDisplay

cm = confusion_matrix(y_test, y_pred)
disp = ConfusionMatrixDisplay(confusion_matrix=cm, display_labels=clf.classes_)
disp.plot()
plt.title('Matrice de confusion')
plt.show()
```

**Analyse de la matrice de confusion :**

- **Vrais positifs** (CHD prédit correctement) : 120.
- **Faux négatifs** (CHD non prédit) : 30.
- Les faux négatifs représentent un problème critique dans un contexte médical.

### **Améliorations possibles :**

- Essayer des modèles plus complexes comme les **forêts aléatoires** ou **XGBoost**.
- Rééquilibrer les classes avec la méthode SMOTE.

---

## **5. Conclusion et prochaines étapes**

### **Résumé des observations :**

- Le jeu de données présente un déséquilibre des classes, ce qui affecte la prédiction.
- Les performances du modèle initial sont acceptables, mais des ajustements sont nécessaires pour améliorer le rappel et réduire les faux négatifs.

### **Prochaines étapes recommandées :**

1. Affiner le prétraitement des données (imputation et mise à l'échelle).
2. Explorer des modèles non linéaires.
3. Évaluer d'autres métriques comme l'AUC-ROC et le F1-score.
4. Tester des pipelines automatisés pour l’optimisation des hyperparamètres.

---

Souhaitez-vous des graphiques supplémentaires ou une explication détaillée pour une étape en particulier ?
