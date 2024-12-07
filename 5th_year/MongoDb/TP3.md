Voici les requêtes MongoDB nécessaires pour répondre aux questions mentionnées. Ces requêtes utilisent l’agrégation pour exploiter les relations entre les collections.

### 1. Affichez la liste des livraisons avec les noms des clients et des chauffeurs associés.

```javascript
db.livraisons.aggregate([
  {
    $lookup: {
      from: "clients",
      localField: "client_id",
      foreignField: "_id",
      as: "client_info"
    }
  },
  {
    $lookup: {
      from: "chauffeurs",
      localField: "chauffeur_id",
      foreignField: "_id",
      as: "chauffeur_info"
    }
  },
  {
    $project: {
      date_livraison: 1,
      poids_colis: 1,
      "client_info.nom": 1,
      "chauffeur_info.nom": 1
    }
  }
]);
```

---

### 2. Identifiez les chauffeurs ayant transporté plus de 500 kg au total.

```javascript
db.livraisons.aggregate([
  {
    $group: {
      _id: "$chauffeur_id",
      total_poids: { $sum: "$poids_colis" }
    }
  },
  {
    $match: {
      total_poids: { $gt: 500 }
    }
  },
  {
    $lookup: {
      from: "chauffeurs",
      localField: "_id",
      foreignField: "_id",
      as: "chauffeur_info"
    }
  },
  {
    $project: {
      _id: 0,
      "chauffeur_info.nom": 1,
      total_poids: 1
    }
  }
]);
```

---

### 3. Trouvez les véhicules ayant été utilisés pour le plus grand nombre de livraisons.

```javascript
db.livraisons.aggregate([
  {
    $group: {
      _id: "$véhicule_id",
      total_livraisons: { $count: {} }
    }
  },
  {
    $sort: { total_livraisons: -1 }
  },
  {
    $limit: 1
  },
  {
    $lookup: {
      from: "véhicules",
      localField: "_id",
      foreignField: "_id",
      as: "vehicule_info"
    }
  },
  {
    $project: {
      _id: 0,
      "vehicule_info.marque": 1,
      total_livraisons: 1
    }
  }
]);
```

---

### 4. Calculez la moyenne des poids des colis livrés par chaque chauffeur.

```javascript
db.livraisons.aggregate([
  {
    $group: {
      _id: "$chauffeur_id",
      moyenne_poids: { $avg: "$poids_colis" }
    }
  },
  {
    $lookup: {
      from: "chauffeurs",
      localField: "_id",
      foreignField: "_id",
      as: "chauffeur_info"
    }
  },
  {
    $project: {
      _id: 0,
      "chauffeur_info.nom": 1,
      moyenne_poids: 1
    }
  }
]);
2```

---

### 5. Affichez les villes ayant reçu le plus de livraisons, triées par ordre décroissant.

```javascript
db.livraisons.aggregate([
  {
    $lookup: {
      from: "clients",
      localField: "client_id",
      foreignField: "_id",
      as: "client_info"
    }
  },
  {
    $unwind: "$client_info"
  },
  {
    $group: {
      _id: "$client_info.ville",
      total_livraisons: { $count: {} }
    }
  },
  {
    $sort: { total_livraisons: -1 }
  }
]);
```

---

Ces requêtes couvrent les relations entre les collections pour répondre aux questions tout en optimisant l’utilisation des **pipelines d’agrégation**.