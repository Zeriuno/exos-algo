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

programme conversion-euro-franc-1chiffre.pscd
declarations
  variables francs, euros
  constante franc-vers-euro-fois-dix ← 65,5957
début
  écrire("Saisissez le montant en francs à convertir en euros : ")
  lire(francs)
  euros ← partie_ent((francs / franc-vers-euro-fois-dix) + 5)/10
fin

---
