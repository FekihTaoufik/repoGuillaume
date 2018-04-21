```
res.afc = CA(pop.2, graph = F)

fviz_eig(res.afc) # histogramme des valeurs propres

res.afc\$row
res.afc\$col

# + foncton résumé

fviz_ca(res.afc, repel = T) # graphique 
```