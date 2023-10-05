Voici la syntaxe de création de [[Methodes (Programmation orienté objet)|Methodes]] en JAVA

``` java
[modificateurs] typeRetour nomMethode ([listeParametres])
									[throws listeExeception]
{

}
```

Les modificateurs de visibilité sont les mêmes que pour les champs :
- private
- protected
- public

Des modificateurs supplémentaires existent :

- static : la methode est une methode de classe, elle peut etre appelée sans instancier la classe
- abstract : la methode ne possede pas de code, elle doit etre redéfinie avec les classes filles
- final : la methode ne peut pas etre redéfinie dans les classes filles

```java
    public class Person{
        private String name;    
        private String firstName;
        private int age;
        private static int nbPerson = 0;
        private final String pays = "France";
        private LocalDate dateNaissance;

        public Person(String name, String firstName, int age){
            this.name = name;
            this.firstName = firstName;
            this.age = age;
            nbPerson++;
        }

        public String getName(){
            return this.name;
        }

        public String getFirstName(){
            return this.firstName;
        }

        public int getAge(){
            return this.age;
        }

        public static int getNbPerson(){
            return nbPerson;
        }

        public final String getPays(){
            return this.pays;
        }

        public int calculAge(){
            if (dateNaissance != null){
                return dateNaissance.until(LocalDate.now()).getYears(); 
            } else {
                return 0;
            }   
        }
    }
```
