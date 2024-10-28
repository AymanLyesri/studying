

Pour ces exercices de recherche et de mise à jour de films, il est probable que vous travaillez avec une base de données, comme MongoDB, où les opérations de recherche et de mise à jour sont courantes. Voici comment réaliser ces tâches en utilisant des requêtes MongoDB :

### Exercice 7.1 : Recherche de films

1. **Rechercher tous les films dont le titre contient le mot "A"** :
   ```javascript
   db.films.find({ title: { $regex: /A/, $options: 'i' } });
   ```

   - `$regex` permet de rechercher un motif spécifique dans le champ `title`.
   - `$options: 'i'` rend la recherche insensible à la casse.

2. **Rechercher les films réalisés par "Christopher Nolan" sortis après 2010** :
   ```javascript
   db.films.find({ director: "Christopher Nolan", year: { $gt: 2010 } });
   ```

   - `director` correspond au nom du réalisateur.
   - `year: { $gt: 2010 }` sélectionne les films dont l'année de sortie est strictement supérieure à 2010.

3. **Rechercher tous les films dont le genre est "Science-fiction" ou "Thriller"** :
   ```javascript
   db.films.find({ genre: { $in: ["Science-fiction", "Thriller"] } });
   ```

   - `$in` permet de spécifier plusieurs valeurs possibles pour le champ `genre`.

### Exercice 7.2 : Mise à jour des documents

1. **Ajouter un champ "description" au film "Inception"** :
   ```javascript
   db.films.updateOne(
     { title: "Inception" },
     { $set: { description: "Un voleur professionnel spécialisé dans l'extraction d'informations rêve dans les rêves d'autrui." } }
   );
   ```

   - `$set` ajoute ou met à jour le champ `description` avec une brève description de l’intrigue.

2. **Modifier le nombre d’exemplaires disponibles pour le film "The Matrix" en le passant à 25** :
   ```javascript
   db.films.updateOne(
     { title: "The Matrix" },
     { $set: { available_copies: 25 } }
   );
   ```

   - `$set` modifie le champ `available_copies` pour indiquer le nombre d’exemplaires disponibles.

3. **Supprimer le champ "note" pour tous les films sortis avant 2000** :
   ```javascript
   db.films.updateMany(
     { year: { $lt: 2000 } },
     { $unset: { note: "" } }
   );
   ```

   - `$unset` supprime le champ `note` pour les documents correspondant au critère `year: { $lt: 2000 }`.

Ces commandes MongoDB permettent d'effectuer des opérations précises sur les documents dans votre collection de films.

Pour effectuer ces recherches avec des expressions régulières en MongoDB, voici comment procéder pour chaque critère :

### Exercice 7.3 : Utiliser des expressions régulières

1. **Rechercher tous les films dont le titre commence par une voyelle** :
   ```javascript
   db.films.find({ title: { $regex: /^[AEIOUaeiou]/ } });
   ```

   - L'expression `^[AEIOUaeiou]` spécifie que le titre doit commencer (`^`) par une voyelle, qu'elle soit en majuscule ou en minuscule.

2. **Trouver les films dont le titre contient au moins deux fois le mot "The"** :
   ```javascript
   db.films.find({ title: { $regex: /(The.*){2}/i } });
   ```

   - L'expression `(The.*){2}` recherche le mot "The" au moins deux fois dans le titre, peu importe ce qui se trouve entre les deux. 
   - Le modificateur `i` rend la recherche insensible à la casse.

3. **Rechercher les films dont le titre se termine par "e"** :
   ```javascript
   db.films.find({ title: { $regex: /e$/i } });
   ```

   - L'expression `e$` indique que le titre doit se terminer (`$`) par la lettre "e", et `i` permet de ne pas distinguer entre "e" et "E".

Ces requêtes MongoDB utilisant des expressions régulières permettent d’effectuer des recherches avancées sur les titres des films.