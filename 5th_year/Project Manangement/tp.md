### **Planification et Gestion de Projet – PERT, Gantt et Lissage des Ressources**

---

### **Partie 1 : Analyse du Projet**

#### 1. **Liste des tâches et durées**

| Tâche | Description                    | Durée | Dépendances | Ressources nécessaires |
| ----- | ------------------------------ | ----- | ----------- | ---------------------- |
| A     | Réunion de lancement           | 2j    | Aucune      | GP                     |
| B     | Recherche de lieu              | 3j    | Aucune      | GP, AA                 |
| C     | Sélection des prestataires     | 4j    | B           | GP, AA                 |
| D     | Création des supports de comm. | 5j    | A           | GP, G                  |
| E     | Préparation logistique         | 6j    | C, D        | GP, L                  |
| F     | Test final de l’organisation   | 2j    | E           | GP, L                  |
| G     | Lancement de l’événement       | 1j    | F           | GP                     |

---

### **Partie 2 : Construction du Diagramme PERT**

#### 1. **Dépendances des tâches**

Les dépendances décrivent les relations d’antériorité :

- Tâche C dépend de B.
- Tâche D dépend de A.
- Tâche E dépend de C et D.
- Tâche F dépend de E.
- Tâche G dépend de F.

#### 2. **Chemin critique et justification**

Le chemin critique correspond au plus long chemin reliant le début à la fin du projet, déterminé en additionnant les durées des tâches critiques (sans marge).

- Chemin critique : A → D → E → F → G.
- Durée totale : 2j+5j+6j+2j+1j=16j2j + 5j + 6j + 2j + 1j = 16j.

#### 3. **Diagramme PERT**

Le diagramme PERT relie les tâches en suivant les dépendances. Il inclut les durées et met en évidence le chemin critique. Voici une représentation textuelle avant le schéma graphique :  
**A → D → E → F → G** (chemin critique)  
**B → C → E → F → G** (chemin secondaire)

---

### **Partie 3 : Construction du Diagramme Gantt**

#### 1. **Placement des tâches sur une ligne temporelle**

Un diagramme Gantt peut être représenté graphiquement en respectant les durées et dépendances. Voici un tableau avant la représentation graphique :

|Tâche|Jour de début|Jour de fin|Ressources nécessaires|
|---|---|---|---|
|A|J1|J2|GP|
|B|J1|J3|GP, AA|
|C|J4|J7|GP, AA|
|D|J3|J7|GP, G|
|E|J8|J13|GP, L|
|F|J14|J15|GP, L|
|G|J16|J16|GP|

---

### **Partie 4 : Lissage des Ressources Humaines**

#### 1. **Identification des conflits d’affectation**

Conflits possibles :

- J3 à J7 : Le gestionnaire de projet (GP) est assigné aux tâches D et C simultanément.

#### 2. **Plan de lissage des ressources**

Proposition d’ajustement :

- Décaler la tâche C pour qu’elle commence après la tâche D (J8 à J11).
- Les autres tâches restent inchangées.

Nouveau planning optimisé :

| Tâche | Jour de début | Jour de fin | Ressources nécessaires |
| ----- | ------------- | ----------- | ---------------------- |
| A     | J1            | J2          | GP                     |
| B     | J1            | J3          | GP, AA                 |
| D     | J3            | J7          | GP, G                  |
| C     | J7            | J10         | GP, AA                 |
| E     | J10           | J15         | GP, L                  |
| F     | J15           | J16         | GP, L                  |
| G     | J16           | J16         | GP                     |

---

### **Livrables**

#### 1. **Diagramme PERT**

![[Pasted image 20241203140949.png]]

#### 2. **Diagramme Gantt**

![[Pasted image 20241203140957.png]]

#### 3. **Rapport d’analyse :**

- **Chemin critique :**  
    Initialement : A → D → E → F → G.  
    Après lissage : A → B → C → E → F → G.
    
- **Évaluation des délais :**  
    Délais augmentés de 5 jours pour résoudre les conflits d’allocation, la durée totale est passée de 16 jours à 21 jours.
    
- **Plan optimisé :**  
    Décalage des tâches pour éliminer les conflits d’allocation tout en respectant l’ordre des dépendances.



---
