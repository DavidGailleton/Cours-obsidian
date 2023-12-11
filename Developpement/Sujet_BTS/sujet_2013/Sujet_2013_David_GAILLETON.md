## Mission 1


## Mission 2

### 2.1
La création de courriels retourne une erreur car si l'un des clients n'est intéressé par aucune catégorie, alors la boucle `while` sera executer en boucle.

## 2.2
```c#
// GetClientsCateg
public static List<Client> GetClientsCateg(<CategVente> categorie) {
	List<Client> ret = new List<Client>;

	string req = "SELECT * FROM client WHERE CategVente = $categ"
	categ = categorie;
	SqlCommand cmd = new SqlCommand(req, Connect.Get());
	SqlDataReader a = cmd.ExecuteReader();
	if(a.Read()){
		ret[] = a[];
	}
	a.Close();
	return ret;
}

```

```c#
//EnvoiCourriel
static public void EnvoiCourriel(Vente uneVente){
	int idCateg = uneVente.GetLaCateg().GetId();
	List<Client> lesClients = ClientDAO.GetClientsCateg(idCateg);

	CreationCourriel(uneVente, lesClients);
}
```

## Mission 3

### 3.1 Modifier la structure de la base de données pour prendre en compte l’évolution demandée. 


### 3.2 Pour chaque couche de l’architecture présentée dans le dossier documentaire, indiquer si elle doit subir une évolution et présenter succinctement les modifications nécessaires (sans aller jusqu’à leur réalisation). 

Il faut ajouter une table `pieces jointe` : PiecesJointe(id, libelle) | clé primaire : id
et une association `Envoie d'un mail` : Envoie d'un mail(date) 
### 3.3 Adapter le diagramme des classes métier utilisées pour l’envoi des courriels pour prendre en compte cette demande d’évolution.
![[Pasted image 20231208123612.png]]


## Mission 4

### 4.1 Proposer les évolutions nécessaires de la structure de la base de données. 


## Mission 5

### 5.1
Présenter les avantages et les inconvénients de chacune des solutions en comparant : 
- la solution Android et la solution web d’une part, 
- le développement en interne et le recours à un prestataire externe d’autre part

Plateforme | Avantages | Inconveniants
:--: | :-- | :--
Android | - Plus de fonctionnalité diponible | - indisponible sur IOS  
Web | - Disponible sur toutes les plateformes | - Le client est obligé de chercher le site

Type de developpement | Avantages | Inconveniants
:--: | :-- | :--
Interne | - formation moins onéreuse que l'externalisation - Les compétence étant en interne le support et l'évolution de l'application est possible a long terme | Le developpeur formé n'aura pas d'expérience dans ce domaine
Externe | - le développeur aura de l'expérience - Garantie corrective de 6 mois | Le prix plus elevé
### 5.2
Je pense que la meilleur solution est un développement d'application Android en Externe.
Une application ayant plus de fonctionnalité qu'un site web, elle pourras attiré plus de client potentiel et les gardé sur le long terme. De plus, si l'application fonctionne bien, l'entreprise aura asses de fond pour développer une application pour IOS.

L'externalisation de l'application coutera plus cher mais garantie une application fonctionnel, fait par des personnes ayant déjà fait ceci plusieurs fois. Rien n'empêche a SoftSys de former son personnel interne pour la maintenance et l'évolution de l'application après la période de 6 mois de garantie.