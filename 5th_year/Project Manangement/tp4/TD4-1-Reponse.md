![[Pasted image 20241105125833.png]]


# Part 1

Pour planifier ce projet de développement d’une application mobile en utilisant une analyse PERT et gérer efficacement les ressources humaines, voici les étapes et calculs nécessaires :

### Étape 1 : Construction du diagramme PERT

1. **Identification des tâches et dépendances** : Voici les tâches avec leurs durées, ressources et dépendances :

   | Tâche | Durée (jours) | Ressources requises | Prédécesseur(s) |
   |-------|---------------|---------------------|------------------|
   | A     | 5             | 2 développeurs      | -               |
   | B     | 4             | 1 designer          | A               |
   | C     | 6             | 2 développeurs      | A               |
   | D     | 7             | 2 développeurs      | B, C            |
   | E     | 3             | 1 testeur           | C               |
   | F     | 5             | 2 développeurs      | D, E            |

2. **Calcul des dates au plus tôt et au plus tard pour chaque tâche** :
   - Le calcul des dates au plus tôt et au plus tard permet d’identifier le chemin critique.
   - Les dates au plus tôt (ou earliest start time, **EST**) et les dates au plus tard (ou latest start time, **LST**) sont calculées pour chaque tâche.

#### Calcul des dates au plus tôt :

- Tâche **A** : **EST = 0**, Durée = 5 jours → **EFT (Earliest Finish Time) = 5**
- Tâche **B** : **EST = 5** (fin de A), Durée = 4 jours → **EFT = 9**
- Tâche **C** : **EST = 5** (fin de A), Durée = 6 jours → **EFT = 11**
- Tâche **D** : **EST = 11** (fin de B et C), Durée = 7 jours → **EFT = 18**
- Tâche **E** : **EST = 11** (fin de C), Durée = 3 jours → **EFT = 14**
- Tâche **F** : **EST = 18** (fin de D et E), Durée = 5 jours → **EFT = 23**

#### Calcul des dates au plus tard :

On part de la fin du projet, soit **F** qui termine à jour 23 :

- Tâche **F** : **LFT = 23**, Durée = 5 jours → **LST = 18**
- Tâche **D** : **LFT = 18** (car D est un prédécesseur de F), Durée = 7 jours → **LST = 11**
- Tâche **E** : **LFT = 18** (car E est un prédécesseur de F), Durée = 3 jours → **LST = 15**
- Tâche **B** : **LFT = 11** (car B est un prédécesseur de D), Durée = 4 jours → **LST = 7**
- Tâche **C** : **LFT = 11** (car C est un prédécesseur de D), Durée = 6 jours → **LST = 5**
- Tâche **A** : **LFT = 5** (car A est un prédécesseur de B et C), Durée = 5 jours → **LST = 0**

### Chemin critique
Les tâches avec une marge nulle sont sur le chemin critique, car elles ne peuvent pas être retardées sans affecter la durée totale du projet :

- **Chemin critique** : A → C → D → F
- **Durée totale du projet** : 23 jours

![[Pasted image 20241105125209.png]]

### Étape 2 : Nivellement et lissage des ressources

Le projet dispose d'une équipe de :
- **3 développeurs**
- **1 designer**
- **1 testeur**

#### Analyse des ressources nécessaires par tâche

| Tâche | Ressources requises | Période d'exécution | Contrainte de ressource? |
| ----- | ------------------- | ------------------- | ------------------------ |
| A     | 2 développeurs      | Jours 1-5           | Non                      |
| B     | 1 designer          | Jours 6-9           | Non                      |
| C     | 2 développeurs      | Jours 6-11          | Non                      |
| D     | 2 développeurs      | Jours 12-18         | Non                      |
| E     | 1 testeur           | Jours 12-14         | Non                      |
| F     | 2 développeurs      | Jours 19-23         | Non                      |

#### Lissage des ressources

- **Développeurs** : Les développeurs sont répartis sur les tâches sans conflit, car on utilise un maximum de 2 développeurs à la fois, et l’équipe dispose de 3 développeurs.
- **Designer et Testeur** : Il n’y a pas de conflit non plus, car chaque tâche requérant un designer ou un testeur est assignée sans chevauchement.

### Récapitulatif du planning optimisé avec lissage des ressources :

| Tâche | Durée (jours) | Ressources | Prédécesseurs | Dates au plus tôt | Dates au plus tard | Marge |
|-------|---------------|------------|---------------|--------------------|--------------------|-------|
| A     | 5             | 2 dév.     | -             | 0                 | 0                 | 0     |
| B     | 4             | 1 designer | A             | 5                 | 7                 | 2     |
| C     | 6             | 2 dév.     | A             | 5                 | 5                 | 0     |
| D     | 7             | 2 dév.     | B, C          | 11                | 11                | 0     |
| E     | 3             | 1 testeur  | C             | 11                | 15                | 4     |
| F     | 5             | 2 dév.     | D, E          | 18                | 18                | 0     |

### Conclusion

Grâce à l’analyse PERT et au lissage des ressources, le planning est optimisé pour une durée totale de **23 jours** sans dépassement des capacités de l’équipe.





---
# Part 2

Pour élaborer un échéancier pour un projet de développement d’un progiciel informatique, voici les étapes clés à suivre, incluant les rôles des différents départements de ProDev Maroc et les phases de réalisation. En tant que chef de projet junior, votre rôle consistera à coordonner ces étapes, gérer les délais et garantir que chaque département est aligné sur les objectifs.

### 1. Analyse et planification initiale
   - **Définir les objectifs et les besoins** : Recueillir les besoins du client (département Commercial) et clarifier les spécifications techniques (département Technique).
   - **Études de faisabilité** : Valider avec le département Juridique pour assurer la conformité légale du projet.
   - **Ressources et compétences nécessaires** : Travailler avec le département RH pour identifier les ressources humaines nécessaires.
   - **Planification préliminaire** : Élaborer un plan initial avec des phases et des jalons. 
   - **Estimation des coûts** : Évaluation budgétaire avec le département Administratif.

   **Durée estimée** : 2 à 4 semaines

### 2. Conception
   - **Conception fonctionnelle** : Avec le département Technique, concevoir une maquette fonctionnelle du progiciel en fonction des spécifications.
   - **Conception technique** : Détailler l’architecture technique avec l'équipe SI pour définir l’infrastructure et les technologies nécessaires.
   - **Validation de la conception** : Obtenir l’approbation du client sur la conception proposée.

   **Durée estimée** : 3 à 5 semaines

### 3. Développement
   - **Développement en phases** : Organiser les tâches en sprints pour une approche Agile (ou autre méthodologie de gestion choisie), en collaboration avec les développeurs du département Technique.
   - **Intégration des fonctionnalités** : Chaque sprint se termine par la livraison d’une version partielle.
   - **Suivi des performances et des ajustements** : Évaluation continue avec les tests unitaires pour identifier les améliorations nécessaires.

   **Durée estimée** : 8 à 12 semaines

### 4. Test et validation
   - **Tests fonctionnels et techniques** : Effectuer des tests approfondis avec le département Technique et les utilisateurs clés pour valider le bon fonctionnement du progiciel.
   - **Correction des bogues** : Recueillir les retours, corriger les problèmes et re-tester.
   - **Tests de sécurité et conformité** : Collaborer avec les départements SI et Juridique pour s’assurer de la conformité aux normes de sécurité.

   **Durée estimée** : 3 à 4 semaines

### 5. Formation et documentation
   - **Création de la documentation** : Rédiger des guides d’utilisation, des manuels de l’utilisateur et de l’administrateur.
   - **Formation des utilisateurs** : Organiser des sessions de formation avec le département RH pour assurer une adoption rapide du progiciel.
   
   **Durée estimée** : 2 à 3 semaines

### 6. Déploiement
   - **Mise en production** : Le département Technique procède au déploiement du progiciel dans l’environnement de production.
   - **Suivi post-déploiement** : Suivi pendant la période initiale pour corriger les éventuels problèmes.

   **Durée estimée** : 1 à 2 semaines

### 7. Maintenance
   - **Support et maintenance corrective** : Le département Technique est responsable de la résolution des problèmes éventuels.
   - **Mises à jour et améliorations** : Planifier les évolutions futures du progiciel.

   **Durée estimée** : En continu

### Tableau récapitulatif de l’échéancier

| Étape                      | Département principal                    | Durée estimée | Precedent |
| -------------------------- | ---------------------------------------- | ------------- | --------- |
| Analyse et planification   | Commercial, RH, Administratif, Juridique | 2-4 semaines  |           |
| Conception                 | Technique, SI                            | 3-5 semaines  |           |
| Développement              | Technique                                | 8-12 semaines |           |
| Test et validation         | Technique, Juridique, SI                 | 3-4 semaines  |           |
| Formation et documentation | Technique, RH                            | 2-3 semaines  |           |
| Déploiement                | Technique                                | 1-2 semaines  |           |
| Maintenance                | Technique                                | Continu       |           |

Cet échéancier est une proposition de base et peut être ajusté selon les besoins spécifiques du projet et les imprévus.