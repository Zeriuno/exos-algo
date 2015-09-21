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

2.2

Quelles seront les valeurs des variables A, B et C après l'exécution des instructions suivantes?

Variables A, B, C en Entier
Début
A ← 5
B ← 3
C ← A + B
A ← 2
C ← B - A
Fin
--
A vaut 2
B vaut 3
C vaut 1
--

2.3
Quelles seront les valeurs des variables A et B après l'exécution des instructions suivantes?

Variables A, B en Entier
Début
A ← 5
B ← A + 4
A ← A + 1
B ← A - 4
Fin
--
A vaut 6
B vaut 2
--

2.4
Quelles seront les valeurs des variables A, B et C après l'exécution des instructions suivantes?

Variables A, B, C en Entier
Début
A ← 3
B ← 10
C ← A + B
B ← A + B
A ← C
Fin
--
A vaut 13
B vaut 13
C vaut 13
--

2.5
Quelles seront les valeurs des variables A et B après l'exécution des instructions suivantes?

Variables A, B en Entier
Début
A ← 5
B ← 2
A ← B
B ← A
Fin
--
A vaut 2
B vaut 2
--
2.6
Échanger la valeur de deux variables, A et B.

Variables A, B, C #(ajouté après)
en Entier
Début
A ← 5
B ← 2
#D'après le corrigé de Christophe Darmangeat, on est obligé de passer par une variable temporaire (C dans ce cas)
C ← B
B ← A
A ← C
Fin

--
2.7
Écrire un algorithme transférant la valeur de A à C, B à A et C à A.
Début
A ← 5
B ← 2
C ← 7
--
D ← B
B ← A
A ← C
C ← D
Fin

Comme le signale Christophe Darmangeat, une seule variable temporaire suffit, indépendamment du nombre de variables à échanger.

--
2.8
Que produit l'algorithme suivant?

Variables A, B, C en chaînes
Début
A ← "423"
B ← "12"
C ← A + B
Fin

Une erreur, forcément, car il est impossible d'additionner des chaînes.

--
2.9
Que produit l'algorithme suivant?

Variables A, B, C en chaînes
Début
A ← "423"
B ← "12"
C ← A & B
Fin

C est égal à la chaîne 42312

--
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
