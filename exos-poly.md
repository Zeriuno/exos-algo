Exercices du polycopié de cours

2.1

programme exécution
declarations
  variables a, b en entiers
début
 a ← 1
 b ← a + 3
 a ← 3
fin

Quelles seront les valeurs de a et de b après l'exécution?

a vaudra 3 (affectation dans la dernière ligne), b vaudra 4 (affectation quand a valait 1).

2.14

1€ = 6.56F

---

programme conversion_euro_franc_1chiffre
declarations
  variables francs, euros en réels
  constante franc_vers_euro_fois_dix ← 65,5957
début
  écrire("Saisissez le montant en francs à convertir en euros : ")
  lire(francs)
  euros ← partie_ent(francs / franc_vers_euro_fois_dix)/10
  écrire("Le montant en euros qui correspond au montant de ", francs "francs est de ", euros)
fin

---

programme conversion_euro_franc_1chiffre-arrondi
declarations
  variables francs, euros en réels
  constante franc_vers_euro_fois_dix ← 65,5957
début
  écrire("Saisissez le montant en francs à convertir en euros : ")
  lire(francs)
  euros ← partie_ent(francs / franc_vers_euro_fois_dix + 0,5)/10
  écrire("Le montant en euros qui correspond au montant de ", francs "francs est de ", euros)
fin

---
#Version sans optimisation de code, algorithme de M. Jacquenod

#en dehors du cadre de l'exercice, il est nécessaire de déclarer la fonction avant le programme lui-même.

fonction partie_entiere() en entier
declaration
  variable ...
début
  ...
fin


programme convertisseur
declarations
  constante taux ← 6,55
  variables euros, pdeci, franc, resultat en reels
  variable pentierie en entier
début
  écrire("Donnez la valeur en Francs")
  lire("franc")
  pentiere ← partie_entiere((franc/taux)*10)
  pdeci ← (franc/taux)*10 - pentiere
  si(pdeci >= 0,5) alors
    euros ← (pentiere + 1)/10
  sinon
    euros ← pentire / 10
  finsi
  écrire("La valeur en euros de ", franc " francs est ", euros)
fin
