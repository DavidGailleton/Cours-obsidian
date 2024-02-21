On souhaite établir des statistique sur les soldats en guerre.
Pour chaque soldat, outre l'etat-civil, il souhaite avoir la trace :
- de la date de son décès si celui-ci est survenu suite aux combat
- des blessures reçues (type et date de la blessure, en plus de la bataille où elle a été infligée. Les batailles seront référencées dans une liste comportant le lieu, les dates de début et de fin)
- des grades obtenue (avec les dates)
- de l'unité de rattachement (avec les dates)

## MCD
![[Pasted image 20231205101512.png]]
## MLD
Soldats (**code_soldat**, ....., d_deces)

Grades (**code_grade**, intitule_grade)

Unites (**code_unite**, nom_unite)

Bataille (**code_bataille**, ... , date_fin)

Blessures (**code_blessure**, type_blessure)

affecté (**#code_unite**, **#code_soldat**, date_affectation)

promu (**#code_soldat**, **#code_grade**, date_promotion)

blessé (**#code_soldat**, **#code_bataille**, **#code_blessure**, date_blessure)
