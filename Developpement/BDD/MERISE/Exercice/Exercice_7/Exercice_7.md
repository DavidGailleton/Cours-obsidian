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
id_e | id auto incrémenté de l'élève | int | 10 | eleves
nom_e | nom de l'eleve | string | 30 | eleves
prenom_e | prenom de l'eleve | string | 30 | eleves
date_naissance_e | date de naissance de l'eleve | date | 0 | eleves
id_eta | id auto incrémenté de l'etablissement | int | 10 | etablissement
nom_eta | nom de l'établissement | string | 50 | etablissement
id_exa | id auto incrementé de l'examen | int |