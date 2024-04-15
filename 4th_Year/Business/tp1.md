Une entreprise de vente de produits alimentaires souhaite mettre en place un système d’information décisionnel par le biais d’un datamart (un mini entrepôt de données), pour observer son activité de ventes, au niveau des différents magasins de distributions de ses articles, et cela dans plusieurs villes. Ces magasins de distributions sont renseignés par leur enseigne, leur surface, leur ville et leur région. Les ventes sont renseignées selon une période
qui se décline en mois, en trimestre et année. Les ventes sont observées par le nombre d’articles selon le type et le chiffre d’affaires.

1. Identifier les mesures et les axes d’analyses (dimensions).
2. Etablir le modèle en étoile de ce datamart.
3. Décomposer les dimensions du modèle en étoile en sous hiérarchies.
Dimension Hiérarchie
Niveau 1 Niveau 2 Niveau 3
4. Etablir le modèle en flocon.


1. les chiffre d affaire / nbre article - 
DIMENSION : magasin / type darticle / periode



2.                       [region]----[ville]
                             |
                             |
                             |
             [enseign]---[magasin]----[surface]        [nbr article]
                             |                             |
                             |                             |
                             |                             |
                             |                             |
                             |                             |
   [periode]-------------[vente]---------------------------+---------[type]
	       |                                                   |
	       |                                                   |
	       |                                                   |
	       |                                                   |
	       |                                                   |
    [annee]---[mois]---[trimestre]                     [chfr affaire]


3. plus detaile

---

Une entreprise de restauration rapide souhaite analyser ses ventes en mettant en place un système décisionnel. Le principe est de mesurer les ventes grâce aux quantités vendues et aux bénéfices, en fonction des ventes réalisées par jour, dans un restaurant donné, pour un aliment donné. L’objectif est de pouvoir analyser les ventes par jour, par semaine, par mois et par année.
Un restaurant est caractérisé par son enseigne. Les restaurants peuvent être regroupés en fonction de leur ville et de leur pays.
1. Identifier les mesures et les axes d’analyses (dimensions).
2. Concevoir un modèle en étoile.
3. Modifier ce modèle en un modèle en flocon de neige pour modéliser explicitement les
hiérarchies des dimensions représentant le temps et la localisation géographique des
restaurants.
4. On souhaite à présent mesurer le nombre de commandes qui est donné par jour et par
restaurant. Etendre le modèle précédent afin de prendre en compte cet aspect.


1. quantite vendues / benefices.
2. 

[restaurant]
    |
    |
[ventes]---[periode]
    |
    |
[alimen]


3. 
                 [ville]
                    |
                    |
                  [pays]
                    |
                    |
                [restaurant]------[enseign]
                    |
                    |
                    |                            [annee]
                    |                               |
                    |                               |
                    |                               |
                    |                               |
                [ventes]------------------------[periode]---[mois]--[semaine]
                    |                               |
                    |                               |
                    |                               |
                    |                               |
                    |                            [jour]
                    |
                    |
                [aliment]


4. 
                              [ville]
                                 |
                                 |
                               [pays]
                                 |
                                 |
		    [commande]-------[restaurant]------[enseign]
                                 |
                                 |
                                 |                            [annee]
                                 |                               |
                                 |                               |
                                 |                               |
                                 |                               |
                    ----------[ventes]------------------------[periode]---[mois]--[semaine]
                                 |                               |
                                 |                               |
                                 |                               |
                                 |                               |
                                 |                            [jour]
                                 |
                                 |
                             [aliment]


---

Exercice 3 :

Une agence de voyage aimerait pouvoir analyser ses données afin de planifier des
campagnes de promotion auprès du nombre et du montant des ventes en fonction :
- De l’hôtel de destination : type (nombre d’étoile : de 1 à 5), ville, région, pays, continent.
- De la date d'achat : jour, mois, année.
- De la date de départ : jour, mois, année.
- Du client : CIN, nom, prénom, âge, sexe, adresse, ville.
Proposer un schéma en flocon pour modéliser l’entrepôt de données.

le fait: les donnes AKA ventes
les metrics : nbr et montant des ventes


1. Schema en flocon AKA plus detaille de celui en etoile
				[Destination: type, ville, region, pays, continent]
					|
					|
					|
					|
					|
				[Ventes]--------------------[Client: nom, prenom, age, sexe, address, ville]
					|
					|
					|
					|
					|
				[Date]---------------[Achat: Jour, mois, annee]----------------------   [Jour]
					|                                                                                                             [Mois]
					|                                                                                                             [Annee]
					|                                                                                                          
				[Depart: Jour, mois, annee]------------------------------------------



![[tp1.canvas]]