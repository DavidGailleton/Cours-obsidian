Une interface est une classe abstraite dont toutes les méthodes sont abstraites. Elle ne peut donc pas être instanciée. Elle sert uniquement à définir un contrat entre une classe et ses utilisateurs. Ce contrat définit les méthodes que la classe doit obligatoirement implémenter. Une classe peut implémenter plusieurs interfaces. Dans ce cas, elle doit obligatoirement implémenter toutes les méthodes de toutes les interfaces qu’elle implémente. Une interface peut hériter d’une autre interface. Dans ce cas, la classe implémentant l’interface fille doit obligatoirement implémenter toutes les méthodes de l’interface mère et de l’interface fille.

```java
public interface Interface1 {
    public void methode1();
    public void methode2();
    public void methode3();
    public void methode4();
}

public interface Interface2 {
    public void methode5();
}

public class Classe1 implements Interface1 {
    public void methode1() {
        // code de la méthode 1
    }
    public void methode2() {
        // code de la méthode 2
    }
}
```
