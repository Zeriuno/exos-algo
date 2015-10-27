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


7.0
Un peu de cuisine

Choix: n_personnes, régime/sucrée

programme recette
déclarations
  variables décompte invités version farine mélange  rhum en entiers
début
  écrire("Saisir le nombre de personnes pour lesquelles réaliser la recette")
  lire(invités)
  écrire("Si vous voulez une recette sucrée, saisir 1, pour une recette régime, saisir 2")
  lire(version)
  selonque(version) alors
    cas 1: écrire("Vous avez choisi la recette sucrée") fincas
    cas 2: écrire("Vous avez choisi la recette régime") fincas
    par défaut: écrire("Le choix n'est pas valide, vous aurez une recette régime")
  finselonque
  pour invités variant de 1 à invités*2 par pas de 1 faire
    ajouter_un_oeuf()
    si (version = 1) alors
      pour décompte variant de 1 à 5 par pas de 1 faire
      ajouter_une_dose_de_sucre()
      finpour
      sinon
      pour décompte variant de 1 à 10 ar pas de 1 faire
      ajouter_une_dose_de_sucre()
      finpour
    finsi
    pour farine variant de 1 à 20 faire
      ajouter_une_dose_farine()
    finpour
    pour mélange variant de 1 à 15 par pas de 1 faire
      battre_le_mélange()
    finpour
  finpour
  pour invités variant de 1 à invités par pas de 1 faire
    pour rhum variant de 1 à 5 par pas de 1 faire
    ajouter_une_dose_rhum
    finpour
  mélanger()
  finpour
fin


Changement, pour ne pas parcourir la boucle à chaque fois qu'on ajoute du sucre

programme recette
déclarations
  variables décompte invités version farine mélange oeufs rhum en entiers
début
  écrire("Saisir le nombre de personnes pour lesquelles réaliser la recette")
  lire(invités)
  oeufs ← invités*2
  écrire("Si vous voulez une recette sucrée, saisir 1, pour une recette régime, saisir 2")
  lire(version)
  selonque(version) alors
    cas 1: écrire("Vous avez choisi la recette sucrée") fincas
    cas 2: écrire("Vous avez choisi la recette régime") fincas
    par défaut: écrire("Le choix n'est pas valide, vous aurez une recette régime")
  finselonque
  pour invités variant de 1 à rapport_oeuf par pas de 1 faire
    ajouter_un_oeuf()
    pour décompte variant de 1 à 5 par pas de 1 faire
    ajouter_une_dose_de_sucre()
    finpour
    si(version = 2)
      pour décompte variant de 1 à 5 par pas de 1 faire
      ajouter_une_dose_de_sucre()
    finsi
    sinon
    pour décompte variant de 1 à 10 ar pas de 1 faire
    ajouter_une_dose_de_sucre()
    finpour
    finsi
    pour farine variant de 1 à 20 faire
      ajouter_une_dose_farine()
    finpour
    pour mélange variant de 1 à 15 par pas de 1 faire
      battre_le_mélange()
    finpour
  finpour
  pour invités variant de 1 à invités par pas de 1 faire
    pour rhum variant de 1 à 5 par pas de 1 faire
    ajouter_une_dose_rhum
    finpour
  mélanger()
  finpour
fin

Améliorations possibles: sucrée / régime en booléen; sortir le redoublement du sucre = si régime, borne supérieure 5, sinon = 10;

Algorithme de fonctionnement d'une horloge

Algorithme pour reposer une question tant que la réponse n'est pas "oui" ou "non".

programme questionnement
déclarations
  variables réponse en chaîne de caractères
début
  réponse ← "bof"
  tantque((réponse != "oui") et (réponse != "non")) faire
  # → Lois de Morgan → tantque(!((réponse = "oui") ou (réponse = "non")))
    écrire("Répondez 'oui' ou 'non'!")
    lire(réponse)
  fintantque
  écrire("Enfin!")
fin

variante avec répéter jusqu'à

programme réponse_répéter
déclarations
  variables  réponse en chaîne de caractères
début
  répéter
    écrire("Répondre 'oui' ou 'non'")
    lire(réponse)
  jusqu'à((réponse = "oui") ou (réponse = "non"))
fin

Utiliser la boucle TantQue comme une boucle pour, afin d'écrire Bonjour 10 fois.

programme bonjour_tant_que
déclarations
 variable cpt en entiers
début
  cpt ← 1
  tantque(cpt <= 10) faire
    écrire("Bonjour")
    cpt ← cpt++
  fintantque
fin

2.1
Quelle est la valeur de A et B après l'exécution?

Variables A, B en entier
Début
A ← 1
B ← A + 3
A ← 3
Fin

A vaut 3
B vaut 4

2.7
Intervertir A (C), B (A) et C (B)

Début
A ← 5
B ← 2
C ← 7
D ← A
A ← C
C ← B
B ← D
Fin


2.8
Que produit cet algorithme?

Variables A, B, C en chaines
Début
A ← "423"
B ← "12"
C ← A + B
Fin

Une erreur, car on ne peut pas additionner des chaînes

2.9
Que produit cet algorithme?

Variables A, B, C en chaines
Début
A ← "423"
B ← "12"
C ← A & B
Fin

C est 42312, c'est-à-dire la concaténation de A et B

2.12

Écrivez l'algorithme pour la mensualité d'un crédit immobilier à taux fixe.
Capital emprunté
Nombre d'années
Taux annuel

M = C * T * ((1 + T)exp n)/(1+T)exp n -1


programme mensualité_crédit
déclarations
  variables  mensualité, capital, taux_annuel, taux_mensuel, années, moins en réels
début
  écrire("Saisir le montant du capital emprunté : ")
  lire(capital)
  écrire("Saisir le nombre d'années de durée de l'emprunt : ")
  lire(années)
  mois ← années* 12
  écrire("Saisir le taux annuel d'intérêt : ")
  lire(taux_annuel)
  taux_mensuel ← taux_annuel / 12
  mensualité = capital * taux_mensuel * ((1 + taux)**mois)/(1 + taux)**mois)-1)
fin

2.13
Un utilisateur rentre le rayon d'un cercle, calculer la circonference

programme circonférence
déclarations
  variables  rayon, circonference, en réels
  constante  pi ← 3.1415
début
  écrire("Saisir le rayon du cercle")
  lire(rayon)
  circonference = 2 * pi * rayon
  écrire("La circonférence d'un cercle avec un rayon de ", rayon " est ", circonference)
fin

2
Écrivez un programme qui donne le carré du nombre saisi par l'utilisateur.

programme carré_nombre
déclarations
  variables  nombre, carré en réels
début
  écrire("Saisir un nombre : ")
  lire(nombre)
  écrire("Je vais calculer son carré : ")
  carré ← nombre * nombre
  écrire("Le carré de ", nombre " est ", carré)
fin

##
Algorithme qui multiplie un premier nombre par un deuxième

programme multiplication_saisie
déclarations
  variables facteur_1, facteur_2, produit en réels
début
  écrire("Saisir le premier des deux facteurs de la multiplication : ")
  lire(facteur_1)
  écrire("Saisir le deuxième des deux facteurs de la multiplication : ")
  lire(facteur_2)
  écrire("Je multiplie ", facteur_1 " par ", facteur_2)
  produit ← facteur_1 * facteur_2
  écrire("Le résultat est ", produit)
fin


2015-10-26
Écrire un algo qui charge un fichier texte dont le nom est saisi par l'utilisateur.
Ce fichier contient un maximum de 50 notes. Si le fichier ne contient pas 50 notes, il est terminé par -1.
Les notes sont les unes à la suite des autres:

```
10
12
13
10,5
9
...
-1
```

Calculer la moyenne.

programme notes
déclarations
  variables nom en chaîne de caractères
  variables fic en fichier
  variables compteur en entiers
  variables note, total, moyenne en réels
début
  écriture("Saisir le nom du fichier à lire : ")
  lire(nom)
  fic ← ouvrir(nom, "lecture", "texte")
  compteur ← 0 /* initialisation de la variable */
  total ← 0 /* initialisation de la variable */
  tant que (!Findefichier(fic)) faire
    lire(fic, note)
    total ← total + note
    compteur ← compteur++
      si (note = -1) alors
        total ← total + 1
        compteur ← compteur - 1
      finsi
  fintantque
  fermer(fic)
  moyenne ← total / compteur
  écrire("La moyenne de ces ", compteur " notes est ", moyenne)
fin

programme notes
déclarations
  variables nom, ligne en chaîne de caractères
  variables fic en fichier
  variables compteur en entiers
  variables note, total, moyenne en réels
début
  écriture("Saisir le nom du fichier à lire : ")
  lire(nom)
  fic ← ouvrir(nom, "lecture", "texte")
  compteur ← 0 /* initialisation de la variable */
  total ← 0 /* initialisation de la variable */
  moyenne ← o /* initialisation non nécessaire de manière rigoureuse (moyenne est affecté), mais peut-être nécessaire pour le C */
  tant que (!Findefichier(fic)) faire /* ou bien ajouter "ou (note <> -1)" et ajouter la lecture avant la boucle, et initialiser le compteur à 1 */
    lire(fic, ligne)
    note ← numérique(ligne)
    total ← total + note
    compteur ← compteur++
      si (note = -1) alors
        total ← total + 1
        compteur ← compteur - 1
      finsi
  fintantque
  fermer(fic)
  moyenne ← total / compteur
  écrire("La moyenne de ces ", compteur " notes est ", moyenne)
fin


Autre possibilité

programme notes
déclarations
  variables nom, ligne en chaîne de caractères
  variables fic en fichier
  variables compteur en entiers
  variables note, total, moyenne en réels
début
  écriture("Saisir le nom du fichier à lire : ")
  lire(nom)
  fic ← ouvrir(nom, "lecture", "texte")
  compteur ← 0 /* initialisation de la variable */
  total ← 0 /* initialisation de la variable */
  moyenne ← o /* initialisation non nécessaire de manière rigoureuse (moyenne est affecté), mais peut-être nécessaire pour le C */
  tant que (!Findefichier(fic)) faire
    lire(fic, ligne)
    note ← numérique(ligne)
    total ← total + note
    compteur ← compteur++
  fintantque
  fermer(fic)
  si (note = -1) alors
    total ← total + 1
    compteur ← compteur - 1
  finsi
  moyenne ← total / compteur
  écrire("La moyenne de ces ", compteur " notes est ", moyenne)
fin
