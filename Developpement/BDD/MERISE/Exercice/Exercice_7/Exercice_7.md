Les examens nationaux sont gérés par l'inspection Académique et concernent les élèves de cette académie. Les élèves doivent obligatoirement remplir un dossier d'inscription numéroté avant le 31 décembre de l'année scolaire en cours.

Ce dossier comprend le nom, la date de naissance, l'établissement de l'élève et le nom de l'examen. Un établissement est défini par son code, son nom son adresse et la ville.

Chaque examen comprend un serie d'épreuve qui lui est propre, chacune dotée d'un coefficient.
Chaque épreuve d'examen se déroule donc à la meme date dans toute l'académie.

La gestion de ces examens comprend aussi la convocation d'une dizaine d'enseignants de l'académie à la commission de rédaction du sujet de chaque épreuve. Cette commission se réunit à l'inspection académique au plus tard 2 mois avant la date de l'epreuve.

Les corrections ont lieu le lendemain de l'épreuve. Une enseignant est connu par son matricule, son nom, son téléphone, adresse, ville et son établissement.

La centralisation des notes de l'élève est faite sur un bordereau transmis au jury chargé d'examiner l'admission définitive du candidat.

## Dictionnaire de donnée

Code mnémonique | Désignation | Type | Taille | table
--- | --- | --- | --- | ---
id_ele | identifiant de l'élève | N | 10 | eleves
nom_ele | nom de l'eleve | A | 50 | eleves
prenom_ele | prenom de l'eleve | A | 50 | eleves
date_naissance_ele | date de naissance de l'eleve | DATE | 0 | eleves
id_eta | identifiant de l'etablissement | N | 10 | etablissement
nom_eta | nom de l'établissement | A | 100 | etablissements
no_rue_eta | numéro de rue de l'etablissements | N | 10 | etablissements
nom_rue_eta | nom de la rue de l'etablissements | A | 30 | etablissements
ville_eta | nom de la ville de l'etablissements | A | 30 | etablissements
cp_eta | code postale de l'etablissements | N | 6 | etablissements
id_exa | identifiant de l'examen | N | 10 | examens
nom_exa | libellé de l'examen | A | 50 | examens
id_epr | identifiant de l'epreuve | N | 10 | epreuves
nom_epr | libellé de l'epreuve | A | 50 | epreuves
coeff_epr | coefficient de l'epreuve | N | 3 | epreuves
date_epr | date de l'epreuve | DATE | 0 | epreuves
matricule_ens | matricule de l'enseignant | int | 10 | enseignants
nom_ens | nom de l'enseignant | string | 50 | enseignants
prenom_ens | prenom de l'enseignant | string | 50 | enseignants
telephone_ens | numéro de telephone de l'enseignant | int | 10 | enseignants
no_rue_ens | numéro de rue de l'enseignant | int | 10 | enseignants
nom_rue_ens | nom de la rue de l'enseignant | string | 30 | enseignants
ville_ens | nom de la ville de l'enseignant | string | 30 | enseignants
cp_ens | code postale de l'enseignant | int | 6 | enseignants
id_ins | identifiant du dossier d'inscription | int | 10 | dossier_inscription
id_jur | identifiant du jury | int | 10 | Jury
id_res | identifiant des resultat | int | 10 | Resultat
note_res | note des resultat défini par les enseignant | int | 10 | Resultat
confirmation_jury | confirmation du passage de l'eleve défini par le jury | boolean | 1 | Resultat

 
## MCD
![[Pasted image 20231205154949.png]]
## MLD  
Eleves (**id_ele**, nom_ele, prenom_ele, date_naissance_ele, `#id_eta`)   
Etablissements (**id_eta**, nom_eta, no_rue_eta, nom_rue_eta, ville_eta, cp_eta)   
Enseignants (**matricule_ens**, nom_ens, prenom_ens, telephone_ens, no_rue_ens, nom_rue_ens, ville_ens, cp_ens)   
Epreuves (**id_epr**, nom_epr, coeff_epr, date_epr)   
Examens (**id_exa**, nom_exa)   
Dossier_inscription (**id_ins**, `#id_ele_Eleves`)   
Sujets (**id_suj**, nom_suj, description_suj, `#id_epr_Epreuves`)   
Resultat (**id_res**, note_res, confirmation_jury, `#matricule_ens_Enseignants`, `#id_jur_Jury`)   
Jury (id_jur)   
contiens... (**id_exa**, **id_epr_Epreuves**)   
est_rédigé_par... (**matricule_ens**, **id_suj**)   
passe_l'examen (**id_ele**, **id_exa**, **id_res**, reponse_eleve)