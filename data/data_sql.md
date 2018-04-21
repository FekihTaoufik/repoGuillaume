## Selectionner

```
SELECT * FROM tab
```

## Filtrer

```
SELECT * FROM tab
WHERE condition
```

## Limiter le nombre de lignes à récupérer

```
SELECT * FROM tab
LIMIT n1 <OFFSET n2>
```

Options :
* `OFFSET` saisir le numéro du 0 pour le LIMIT.

## Filter avec une fonction d'agrégation
```
SELECT * FROM tab
HAVING fct(col1)
```

## Agréger les données

```
SELECT col1, col2, <fct\_agr> FROM table
GROUP BY col1, col2
```

NB : il est possible d’utiliser le numéro de la colonne à la place de son nom.
## Tirer 

```
SELECT * FROM tab
ORDER BY col1 <ASC/DESC>, col2 <ASC/DESC> ;
```

Paramétre (par défaut ASC) :

* `ASC` trier par ordre croissant (par défaut).
* `DESC` trier par ordre décroissant.

## Renommer les libellés

`col AS nv_nom` renommer une colonne.
`table AS nv_nom` renommer une table.

## Les comparateurs

## Les fonctions

### Les fonctions d’agregation
autres
Les fonctions date

## Les jointures

```
SELECT * FROM table1 
jointure table2 
ON table1.a=table2.b
```

## Gestion des tables

### Créer une table et sa structure

```
CREATE TABLE table 
( 	col1 type <option1>,
	col2 type <option2>, 
	... 
)
```

### Créer une table à partir d’une table

```
CREATE TABLE tab AS
[SELECT * FROM tab1]
```

Option :
* `NOT NULL` empecher la variable d’être nulle.
* `DEFAULT` attribuer une valeur par défaut.
* `PRIMARY KEY` clé primaire.

### Modifier une table

```
ALTER TABLE table
```

### Supprimer une table

```
DROP TABLE table
```

### Modifier des lignes

```
UPDATE table
SET colonne = ’nouvelle valeur’
WHERE condition
```

## Les formats
