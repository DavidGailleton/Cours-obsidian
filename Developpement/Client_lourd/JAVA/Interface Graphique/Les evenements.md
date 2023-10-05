Il existe des types de classe ou interface qui permettent de gerer la detection des evenements, elles se terminent toutes par 'listener'

```java
    public interface MouseMotionListener extends EventListener
    {
        void mouseDragged(MouseEvent e);
        void mouseMoved(MouseEvent e);
    }
```

Nous avons donc besoin de créer des classes implémentant ces interfaces. De ce point de vue, nous avons une multitude de possibilités :

- Créer une classe "normale" implémentant l’interface.
    
- Implémenter l’interface dans une classe déjà existante.
    
- Créer une classe interne implémentant l’interface.
    
- Créer une classe interne anonyme implémentant l’interface.
    
- Créer éventuellement une expression lambda si l’interface est une interface fonctionnelle.