`/opt/sas/data/` Chemin du dossier SAS.

```LIBNAME nomBiblio "chemin";``` Créer une bibliothèque.

`OPTION
FMTSEARCH=(bibliotheque.format)` créer une bibliothèque format.

## DATA

```
DATA nomtable;
instruction ;
RUN ;
```

`LENGTH <$> taille;` taille des colonnes.
`FORMAT variable <$> taille.;` format des colonnes.
`WHERE condition;` sélectionner une partie du jeu de données.
`SET table;` utiliser une table.
`INFORMATION variable <type>;` format d'affichage de la table.
`KEEP variable;` colonne à garder (NB : voir arguments m chose).
`LABEL variable='libelle';` labelliser une colonne.
`RETAIN variable;` garder la valeur de la ligne au dessus.

## Les jointures

```
MERGE tab1 tab2
BY clé;
IF condition;
```

## Importer un jeu de données

```
INFILE fichier <option>;
```

Options :
`MISSOVER` lire des enregistrements avec des données manquantes en fin d'enregistrement.
`DSD` deux séparateurs successifs implique une donnée manquante.
`DELIMITER = delimiteur` séparateur de champs.

## Déclarer un jeu de données dans DATA

```
DATALINES;
données
;
```

## Condition

```
IF condition THEN DO;
	<instruction1>;
	<ELSE IF a THEN DO;>
	<instruction2>;
	<ELSE DO;>
	<instruction3>;
END;
```

### Comparateur

SAS définition
`val1 = val2` égalité
`var IN (val1, val2)` dans la liste
`val1 ¡¿ val2` différent
`val1 ¡= val2` ou `val1 ¿= val2` supérieur, inférieur ou égal
`IS NULL` valeur nulle pour les chaînes de caractères
`=.` valeur nulle pour les numériques

## Opérateur logique

SAS définition
`NOT condition` négation
`condition1 &/AND condition2` et
`condition1 —/OR condition2` ou

1.7 Fusion

```
SET table1 table2;
```

1.8 Fonctions
1.8.1 Fontions générale
`N` numéro de lignes.
`LAG(variable)` renvoyer la valeur de l'observation précédente.
`MISSING(variable)` renvoie vrai si la valeur est manquante.
`DELETE` supprimer l'observation lu.
`PUT( variable, format)` convertir le format d'une variable.
`SYMGET(macro-varibe)` utiliser une macro dans un data.
`INPUTN( date, format)` créer une variable date.
`SUBSTR( chaîne , début, fin)` extraire une chaine de caractère.
`chaine1 || chaîne2` concaténer des chaînes de caractères.
`CATX(chaîne1, chaîne2)` concaténer des chaînes des caractères.
`FLOOR(variable)` arrondir à l'entier inférieur.
`CALL SYMPUT('var','valeur')` attribuer une valeur a une macro variable dans une step DATA.
`COUNTW( phrase, "séparateur")` compter le nombre de separateur.
`RAND("UNIFORM")` générer un nombre aléatoire entre 0 et 1.

## Fonctions date

`DATEPART(dateheure)` extraire la date d'une datetime.
`YEAR(date)` récupérer l'année
`MONTH(date)` récupérer le mois.
`INTNX( 'type', datetime, nbre )` ajouter des jours, mois, à une date.
`'DAY'`
`'MONTH'`
`'YEAR'`
`MDY( mois, jour, année)` créer une date.
`HMS(heure, minute, seconde)` créer une heure.
`DHMS(date, heure)` créer une date heure.
`QTR(date)` donner le trimestre de la date.
`INTCK("YEAR", date1, date2, <"C">)` calculer la date l'âge.

## Paramètrer les sorties SAS 

`GOPTIONS `
Options : 
* `HTEXT=4pct` taille de la police.
* `FTEXT="police";` type de police.

## Les jockers

* `var1--var8` selection les variables 1 à 8.

## SQL

```
PROC SQL <option>;
requeteSQL
;QUIT;
```

Option :
* `OUTOBS=nbre` nombre d'observation en sortie.
* `FORMAT=format` formater une colonne.

## Trier

```
PROC SORT <option>;
BY (DESCENDING/ASCENDING) champ;
RUN;
```

Options :
* `NODUPKEY` supprime les doublons du BY.

## Décrire le contenu d'une table

```
PROC CONTENTS;
<option> ;
RUN ;
```

Option :
`BY variable;` appliquer la description pour chaque modalité d'une variable.

## Créer un nouveau format
```
PROC FORMAT <LIBRARY=> ;
VALUE/INVALUE <\$> nomFormat
modalite1 = libelle1
modalite2 = libelle2
<OTHER = "AUTRE"> ;
RUN;
```

`LIBRARY=bibliotheque` stoker le format dans une bibliothèque.

`$ variable` d'origine est en caractère.
`valeur1 - valeur2 = 'libelle'` construire des intervalles (`LOW` : mini `HIGH`: max ¡ pour exclure la valeur).
NB : utile pour les variables ordinales et les création d'intervalles.
`modalité1, modalité2` plusieurs éléments pour une modalité proc format.

## Transposer

```
PROC TRANSPOSE;
	VAR var1;
	BY var2;
	ID var3
RUN;
```

## Supprimer/renommer une table

```
PROC DATASETS <library=> ;
<action> table1 table2;
CHANGE ancien\_nom = nouveau\_nom;
RUN;
```

action :
* `DELETE` supprimer des tables (KILL supprime toutes les tables).
* `CHANGE` renommer des tables.

## Créer une variable rang

```
PROC RANK <OUT=data>;
VAR col;
RANK nvcolo;
<BY> col;
RUN;
```
