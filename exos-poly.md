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


Ajouter des notes dans un fichier déjà partiellement rempli:

12
15
17,5
-1

ouvrir en lecture, charger et stocker le contenu, modifier le contenu, écriture


Écrire un algo qui charge un fichier texte dont le nom est saisi par l'utilisateur.
Ce fichier contient un maximum de 50 notes.
Calculer la moyenne une fois le fichier chargé et fermé (afin de réduir le temps d'ouverture du fichier).

programme notes_via_tableau
déclarations
  variable notes en tableau [50] d'entiers
  variable liste_notes en fichiers
  variable tab, borne en entiers
  variable note en chaîne de caractères
  variables total, moyenne en réels
début
  pour tab variant de 1 à 50 par pas de 1 faire
    notes[tab] ← -1
  finpour
  tab ← 1 /*la variable était à 50, on va redémarrer, du coup on la remet à 1*/
  liste_notes ← ouvrir(liste_notes, "lecture", "texte")
  tantque(!Findefichier(liste_notes)) faire
    lire(liste_notes, note)
    notes[tab] ← numérique(note)
    tab ← tab++
  fintantque
  fermer(liste_notes)
  borne ← tab /* je garde trace de combien itérations on a fait afin de minimiser le travail de la boucle qui me permet de calculer la moyenne */
  somme ← 0 /* initialisation */
  pour tab variant de 1 à borne par pas de 1 faire
    somme ← somme + notes[tab]
  finpour
  moyenne ← somme / tab
fin

Correction de M. Jacquenod

programme notes_via_tableau
déclarations
  constante nb_max_notes ← 50
  variable notes en tableau [nb_max_notes] d'entiers
  variable liste_notes en fichiers
  variable tab, tab2borne en entiers
  variable note en chaîne de caractères
  variables total, moyenne en réels
début
  pour tab variant de 1 à nb_max_notes par pas de 1 faire
    notes[tab] ← -1
  finpour
  tab ← 0 /*la variable était à 50, on va redémarrer, du coup on la remet à 0, 0 afin que tab sorte de la boucle avec la valeur qui indique le nombre de notes lues*/
  liste_notes ← ouvrir("notes.txt", "lecture", "texte")
  tantque(!Findefichier(liste_notes)) faire
    tab ← tab++
    lire(liste_notes, note)
    notes[tab] ← numérique(note)
  fintantque
  fermer(liste_notes)
  borne ← tab /* je garde trace de combien itérations on a fait afin de minimiser le travail de la boucle qui me permet de calculer la moyenne */
  somme ← 0 /* initialisation */
  pour tab variant de 1 à borne par pas de 1 faire
    somme ← somme + notes[tab]
  finpour
  moyenne ← somme / tab
fin

Fichier notes (max 50). Y écrire, si il y a de la place, une nouvelle note au début.

programme insertion_note
déclarations
  constante NB_MAX_NOTES ← 50
  variable fic en fichiers
  variable tab_notes en tableau [NB_MAX_NOTES] de chaînes de caractères
  variable note, nom, ajout en chaîne de caractères
  variable cpt, cpt2 en entiers
début
  pour cpt variant de 1 à NB_MAX_NOTES par pas de 1 faire
    tableau[cpt] ← -1
  finpour
  écrire("Saisir le nom du fichier : ")
  lire(nom)
  liste_notes ← ouvrir(nom, "lecture", "texte")
  cpt ← 1 /* initialisation */
  tantque(!Findefichier(liste_notes)) faire
    lire(liste_notes, tab_notes[NB_MAX_NOTES])
  fintantque
  fermer(liste_notes)
  si(cpt > NB_MAX_NOTES-1) alors
    écrire("Le fichier est plein.")
  sinon
    écrire("Il reste de la place dans le fichier. Saisir la note à ajouter dans la première place : ")
    lire(ajout)
    liste_notes ← ouvrir(nom, "écriture", "texte")
    écrire(liste_notes, ajout)
    pour cpt2 variant de 1 à cpt par pas de 1 faire
      écrire(liste_notes, tab_notes[cpt2])
    finpour
    fermer(liste_notes)
    écrire("La note a bien été ajoutée.")
  finsi
fin


programme insertion_note /*variante avec tableau à NB_MAX_NOTES+1*/
déclarations
  constante NB_MAX_NOTES ← 50
  variable fic en fichiers
  variable tab_notes en tableau [NB_MAX_NOTES + 1] de chaînes de caractères
  variable note, nom, ajout en chaîne de caractères
  variable cpt, cpt2 en entiers
début
  pour cpt variant de 1 à NB_MAX_NOTES + 1 par pas de 1 faire
    tableau[cpt] ← -1
  finpour
  écrire("Saisir le nom du fichier : ")
  lire(nom)
  fic ← ouvrir(nom, "lecture", "texte")
  cpt ← 2 /* initialisation à deux afin de laisser la première case vide*/
  tantque(!Findefichier(fic)) faire
    lire(fic, tab_notes[NB_MAX_NOTES])
    cpt ← cpt++
  fintantque
  fermer(fic)
  si(cpt > NB_MAX_NOTES) alors
    écrire("Le fichier est plein.")
  sinon
    écrire("Il reste de la place dans le fichier. Saisir la note à ajouter dans la première place : ")
    lire(tab_notes[1])
    fic ← ouvrir(nom, "écriture", "texte")
    pour cpt2 variant de 1 à cpt par pas de 1 faire
      écrire(fic, tab_notes[cpt2])
    finpour
    fermer(fic)
    écrire("La note a bien été ajoutée.")
  finsi
fin

Faire une variante pour stocker la nouvelle note à n'importe quelle place.

programme insertion_note_place_choix
déclarations
  constante NB_MAX_NOTES ← 50
  variable fic en fichiers
  variable tab_notes en tableau [NB_MAX_NOTES] de chaînes de caractères
  variable cpt en entiers
début
  écrire("Saisir l'emplacement de la nouvelle note : ")
  lire(place)
  pour cpt variant de 1 à place -1 par pas de 1 faire
    écrire(Fic, tab_notes[cpt])
  finpour
  écrire(Fic, note_ajout)
  pour cpt variant de place + 1 à borne + 1 par pas de 1 faire
    écrire(Fic, tab_notes[cpt])
fin
