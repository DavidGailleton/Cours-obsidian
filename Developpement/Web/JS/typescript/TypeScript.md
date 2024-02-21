# TypeScript

La différence entre TS et [[JS]] est ue TS apporte une syntaxe qui permet d'ajouter des informations sur le type des variables

Voici le syntaxe de déclaration d'une variable en typescript :

```ts
let maVariable : type;
```

On peut créer ses propres type :
```ts
const monEtudiant: Etudiant = new Etudiant();
```

TypeScript supporte ce qu'on appelle la genericite :
```ts
const pleinDetudiants: Array<string> = [maChaine]; // ne prendra en parametre que les string
```

Il est possible de proposer plusieurs type :
```ts
let iCanChangeType : number | boolean = 0;
```

TypesScript propose le type enum :
```ts
enum StudentStatus {
    Asleep,
    Focused,
    Missing
}
```

Il est possile de créer des interfaces. Les interfaces sont comparables a des contrats, implementer une interface c'est s'engager a posseder toutes les propriétés prenstées dans l'interface. 
```ts
interface Student {
    firstname: string,
    lastname: string,
    age: number,
    status: StudentStatus,
    followInClass(cours: string): void
}

const Angelo: Student = {
    firstname: "Angelo",
    lastname: "MACAIRE",
    age: 22,
    status: StudentStatus.Focused,
    followInClass: function (cours: string) { console.log('je suis en' + cours)}
}
```

Les fonctions en TS :
```ts
function createStudent(firstname: string, lastname:string, age:number, status:StudentStatus): Student{
    const newstudent : Student = {
        age: age,
        firstname: firstname,
        lastname: lastname,
        status: status
    }
    return newstudent
}
```

## Les class

Les class permet de créer des objet :
```ts
class Personne {
    nom: string;
    age: number;
    sePresenter(): void {
        console.log("Je m'appelle " + this.nom + " et j'ai " + this.age + " ans");
    }
}
```

Il est possible d'implementer des interfaces ou des types au seins d'une class :
```ts
class Rectangle implements Forme { 
    constructor(public hauteur: number, public largeur: number) {
        this.largeur = hauteur;
        this.largeur = largeur;
    }
    calculerSurface(): number {
        const result = this.hauteur * this.largeur;
        return result;
    }
}
```
A la difference d'une interface, les paramètre d'une class ne doivent par forcement être utiliser.

## Promise
L'interface Promise représente un intermédiaire (proxy) vers une valeur qui n'est pas nécessairement connue au moment de la création de la promesse. Cela permet d'associer des gestionnaires au succès éventuel d'une action asynchrone et à la raison d'une erreur. Ainsi, les méthodes asynchrones peuvent renvoyer des valeurs de manière similaire aux méthodes synchrones, la seule différence est que la valeur retournée par la méthode asynchrone est une promesse (d'avoir une valeur plus tard).

Une Promise est dans un de ces états :

- pending (en attente) : état initial, la promesse n'est ni tenue, ni rompue ;
- fulfilled (tenue) : l'opération a réussi ;
- rejected (rompue) : l'opération a échoué.

```tsx
    
```