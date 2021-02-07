# zenity
HowTo Zenity and Samples

Ici seront listées des patrons opérationnel pour réaliser un but donné.

Basés sur : https://wiki.visionduweb.fr/index.php/Programmation_GNU_Linux_Zenity

# Liste pour exécuter une commande cachée
```sh
#!/bin/bash
commande=$( zenity \
--width=600 --height=600 --list --text= --title="Action à exécuter" \
--column="Action" --column="commande" --hide-column=2 --print-column=2 \
\
"Titre_1" \
"commande_1" \
\
"Titre_2 \
qui peut être réparti sur plusieurs lignes" \
"commande_2 \
qui peut être répartie en plusieurs lignes \
\
)
# Nota : pour éviter des lignes à rallonge on peut les scinder avec un
# \ final (même dans les chaines "..." elles-mêmes)

eval "$commande"
```
Ainsi quand on double clique l'intitulé Titre_1 on exécutera commande_1
