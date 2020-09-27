# Création d'une base de données?????????????????????????????????????????????

On souhaite créer la base de données vue en cours: `vehicules_fonctions` avec les deux tables:

table `vehicules`:

| v_id | **marque** | Immat     | Annee | Entretien  |
| ---- | ---------- | --------- | ----- | ---------- |
| 1    | VW Caddy   | PO-654-KV | 2016  | 2018-12-18 |
| 2    | Opel Astra | MW-780-DF | 2010  | 2019-08-12 |
| 3    | BMW X6     | KH-778-CT | 2017  | 2020-07-15 |

table `employes`:

| nom            | num_secu        | **adresse**                        | v_id |
| -------------- | --------------- | ---------------------------------- | ---- |
| Dupond Jacques | 151205124775416 | 1, grand Boulevard 11111 LACITE    | 3    |
| Martin Jean    | 158213658974512 | 5,rue de la Gare 22222 LAVILLE     | 1    |
| Petit Hélène   | 265457893214562 | 3, place du Marché 33333 LEVILLAGE | 1    |
| Lefevre Lisa   | 272456987123652 | 4, rue de l’Eglise 44444 LAFORET   | 2    |



Pour rappel:  Dans la relation `vehicules`  v_id est la clé primaire. Dans la relation `employes`num_secu est la clé primaire et v_id est une clé étrangère en référence à la clé primaire v_id  de la relation `vehicules`.

1. Ouvrir DB browser et créer une base nommée `vehicules_fonctions`.
2. Pour créer une table, on utilise : 

```sql
CREATE TAB nom_table (attr1 dom1, attr2 dom2,....)
```

Pour chacun des attributs, on précise son type (domaine) et éventuellement les contraintes.

Pour créer  la table `vehicules` ,on saisit dans l'onglet réservé à SQL

``` SQL
CREATE TABLE "vehicules" (
	"v_id"	INTEGER NOT NULL,
	"marque"	VARCHAR(15),
	"Immat"	CHAR(9) NOT NULL,
	"Annee"	INTEGER NOT NULL,
	"Entretien"	DATE NOT NULL,
	PRIMARY KEY("v_id")
);
```

Pour créer  la table `vehicules` ,on saisit dans l'onglet réservé à SQL

```sql
CREATE TABLE "employes" (
	"nom"	VARCHAR(15) NOT NULL,
	"num_secu"	INTEGER NOT NULL,
	"adresse"	VARCHAR(50) NOT NULL,
	"v_id"	INTEGER,
	FOREIGN KEY("v_id") REFERENCES "vehicules"("v_id"),
	PRIMARY KEY("num_secu")
);
```

1. Déterminer le type(domaine) de chacun des attributs.

2. Déterminer les contraintes de chacun des attributs.
3. Remplir la base de données.

3. Exécuter différentes requêtes .

4. Exécuter une requête avec une jointure.

5. Insérer un nouvel employé: "Pochet Hugo",172456987123652,"17 rue de la marche 15489 CETISSY".

6. Insérer un nouveau véhicule: 4, "Renault Mégane", "GF-753-LK",2020,"2020-08-24"

7. Affecter ce véhicule à l'employé dont le numéro de sécurité sociale est 172456987123652

