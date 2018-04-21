PROC LOGISTIC <option>;
CLASS var_qualitative <option CLASS>;
MODEL var_explique <(EVENT=’modalite’ )> = var_quantitative / <option MODELE>;
<paramètre>;
RUN;

## Option
* OUTEST=data : jeu de test.
* PLOTS = ALL :  afficher les graphiques (nécessite ODS GRAPHICS).
* OUTMODEL=data :  exporter le modèle.
* INMODEL=data : charger un modèle existant (créer à partir de OUTMODEL).

## Paramètre

* BY variable : séparer les analyses en fonction d’une variable.

## Option CLASS

* MISSING : les valeurs manquantes sont traitées comme une modalité.

## Option MODELE

* LINK=fonction : fonction de liaison (logit).
* SELECTION=backward/stepwise/forward : algorithme de selection des variables explciatives.
* CORRB : afficher la matrice des corrélations.
* CTABLE PPROB=proba : afficher la matrice de confusion en fonction du seuil.