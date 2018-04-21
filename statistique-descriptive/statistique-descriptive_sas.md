## Tableau statistique élémentaire

```
PROC TABULATE <option> <MISSING>;
CLASS variablesDescriptif ;
VAR variableAnalyse ;
TABLE ligne,colonnes*calculs ;
<FORMAT variable format>
RUN;
```

Option :
* `MISSING` Créer une modalité valeur manquante.
* `var='libellé'` changer le libellé dans le tableau.
* `FORMAT variable format.` formater une variable.

Principale statistiques disponibles dans la PROC TABULATE.

Formule définition
`N` effectif
`<zone>PCTN` fréquence d'obsevation total par ligne (ROW), par colonne(COL)
`NMISS` nombre de valeurs manquantes
`<zone>PCTSUM`
`MEAN` moyenne
`SUM` somme
`MIN/MAX` minimun et maximum
`MEADIAN` médiane
`Qa` quartiles a.
`Px` centile à x% (ex : P15 -¿ 15%)
`VAR` variance
`STD` ecart type
`LCLM/UCLM` intervalle de confiance (borne inf et sup)

## Tableau indicateurs (moyenne, médiane, max, min
variance)

```
PROC MEANS <options>;
VAR variable;
CLASS modalite;
RUN;
```

Options :
`MAXDEC=n` nombre de décimale

## Tableau fréquences

```
PROC FREQ <option>;
TABLE col / <option> ;
RUN;
```

Options:
* `NOCUM` supprimer les fréquences cumulatives.
* `MISSING` afficher le nbre de valeurs manquantes.
* `CHISQ` test du khi 2.

## Corrélation

```
PROC CORR <PEARSON/SPEARMAN>;
VAR var1 var2 var;
RUN;
```

2.4 Afficher
PROC PRINT <option>;
RUN;
Option :
NOOBS LABEL afficher le label des individus `a la place du num´ero d observation
(NOOBS).
OUTOBS= n nombre d’individus en sortie.