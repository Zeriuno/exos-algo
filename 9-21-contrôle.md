Exercice 1

Indiquez parmi les noms de variables proposés si la syntaxe est bonne. Justifiez si ce n'est pas le cas.

Prix@Total
_int
_Computer
1Variable
Numero-secu

Exercice 2

Algorithme qui, après lecture de 2 nombres entiers à stocker dans les variables vara et varb, interverti le contenu des variables.


Correction:

1.

* `Prix@Total` n'est pas autorisé à cause du caractère @.
* `_int` est autorisé, car ce n'est pas `int`, et que le tiret bas est autorisé.
* `_Computer` est valide, car le tiret bas est autorisé.
* `1Variable` n'est pas autorisé, car elle commence par un chiffre.
* `Numero-secu` n'est pas valide à cause du tiret, qui n'est pas autorisé (certains langages le lisent comme opérateur mathématique).

2

programme inversion_variables
déclarations
  vara varb varc en entiers
début
  écrire("Saisir un nombre entier : ")
  lire(vara)
  écrire("Saisir un deuxième nombre entier : ")
  lire(varb)
  écrire("Je vais maintenant intervertir les variables")
  varc ← vara
  vara ← varb
  varb ← varc
  écrire("La première variable vaut maintenant ", vara " et la deuxième ", varb)
fin
