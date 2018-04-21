## Graphiques classiques
PROC GCHART DATA=table;
type variable </ option>;
RUN;

### Graphiques univariée

Type :
* VBAR : diagramme en barres verticales
* HBAR : diagramme en barres horizontales.
* PIE : secteur circulaire.
* STAR

Argument (ajouter / avant):

DISCRETE : évite les regroupement des modalités.
LEVELS= n : nombre de classes.
MISSING : les valeurs manquantes constitue une modalité.
SUBGROUPS = variable : ajouter une variable.
EXPLODE = modalité : séparer une modalité d’un diagramme circulaire.

## Boxplot

``` 
PROC BOXPLOT DATA=nomTable;
PLOT variableQuantitative\*variableQualitative;
<paramétres>;
RUN;
``` 

### Paramétres

* `INSERT MEAN/MIN/MAX/NMIN/NMAX/NOBS/STDDEV;` encadrer avec les stat générales.
* `INSETGROUP (voir au dessus);` encadré avec les stat par groupes.

## Analyse bivariée
```
PROC GPLOT <UNIFORM>;
<TITLE "titre";>
<type> variable1\*variable2 </ option> ;
RUN;
```

Option 
* `UNIFORM` garder les même échelles d’axe.

### Type :
* PLOT ???.
10
* VBOX

Option

* `HREF/VREF=valeur` tracer une barre horizontale/verticale.
* `OVERLAY` superposer plusieurs graphiques.
* `GROUP=var` par groupe de variables.

## Résumer statistique pour un jeu de données

``` 
PROC UNIVARIATE DATA=table <NORMAL>;
VAR var;
HISTOGRAM vari </ option>;
RUN;
``` 

### Option

`NORMAL` qqplot.

## Dendrogramme

```
	\begin{verbatim}
PROC TREE <option>;
	ID libelle;
	HEIGHT taille_branches;
RUN;
```

### Option
* `HAXIS` et `VAXIS` paramétrer les axes avec la AXIS1.
* `HORIZONTAL` afficher horizontal.

## Présentation du graphique

### Les axes

```
AXISnom <option>;
```

Option : 
* `LABEL=('')` ajouter le titre des ordonnés.
* `ORDER=(val to val by pas)` définir les dimensions d'un axe.