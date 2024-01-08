Identification des Utilisateurs : Chaque utilisateur (médecin) doit avoir un compte unique avec une authentification sécurisée pour accéder à l'application. 

Gestion des Profils des Patients : Les profils des patients doivent inclure des informations détaillées comme le nom, l'âge, le sexe, les antécédents médicaux, et les allergies connues. 

Création et Gestion des Ordonnances : Les médecins doivent pouvoir créer, modifier et annuler des ordonnances. Chaque ordonnance doit inclure le nom du médicament, la posologie, la durée du traitement, et les instructions spéciales si nécessaires Chaque ordonnace doit pouvoir être exportée au format .txt ou .pdf 

Base de Données des Médicaments : L'application doit avoir une base de données exhaustive des médicaments, y compris les informations sur les contre-indications et les interactions médicamenteuses. L'application doit avertir le médecin en cas de potentielles interactions dangereuses ou contre-indications basées sur le profil du patient.

## MCD
![[Pasted image 20240108114248.png]]
![[Pasted image 20231213121647.png]]
ou
![[Pasted image 20231213122002.png]]
## MLD
Medecin (**id_m**, nom_m, ... , password_m)
Patient (**ip_p**, nom_p, prenom_p, sexe_p)
Ordonnance (**id_p**, posologie, duree_traitement, instruction_specifique, `#id_m`, `#id_p`, `#id_med`)
Medicament (**id_med**, libelle_med, contre_indication)
Allergie (**id_al**, libelle_al)
Antecedent (**id_a**, libelle_a, `#id_p`)
etre (**#id_p**, **id_al**)
incompatible ( **#id_al**, **#id_med**, **#id_a**)