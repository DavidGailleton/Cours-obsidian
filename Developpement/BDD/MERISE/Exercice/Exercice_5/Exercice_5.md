	On reprend le problème de la CDthèque, en s'attelant cette fois pour de bon à la question des artistes ayant signé les disques:
- Un disque peut avoir été signé par un group, par un individu, ou par plusieurs.
- Les groupes sont naturellement formés d'individus, dont on note de surcroit quels instruments ils jouent.
- Et en plus, sur un CD, il peut avoir des guest-stars, qui sont venus jouer sans pour autant être signataire du disque.
- Pour ajouter à la difficulté, un même individu peut à la même époque avoir participé à un (ou plusieurs) groupe, et avoir collaboré à un (ou plusieur) disques en tant qu'invité.
- Bref il faut prévoir toutes les situation possibles et pouvoir restituer toures les informations, qu'elles soient relatives aux disques, aux groupes, à leurs membres à l'historique de chaque instrumentiste, etc...

## MCD
![[Pasted image 20231205161633.png]]
## MLD
Label (**id_label**, nom_label)   
Artistes (**id_artiste**, nom_artiste)   
Instruments (**id_instrument**, nom_instrument)   
Groupes (**id_groupe**, nom_groupe)   
Disque (**id_disque**, titre, annee, `#id_label`)   
enregistre (**id_disque**, **id_instrument**, id_artiste, sous_son_nom)   
signe (**id_disque**, id_group)