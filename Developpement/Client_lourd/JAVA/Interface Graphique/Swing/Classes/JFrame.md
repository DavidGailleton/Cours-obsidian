Voici la hierarchie de classe de la classe JFrame :
![[Pasted image 20231003120958.png]]

Maintenant que nous sommes capables d’afficher une fenêtre, le plus gros de notre travail va consister à ajouter un contenu à la fenêtre. Avant de pouvoir ajouter quelque chose sur une fenêtre, il faut bien comprendre sa structure qui est relativement complexe. Un objet JFrame est composé de plusieurs éléments superposés jouant chacun un rôle bien spécifique dans la gestion de la fenêtre.
![[Pasted image 20231003121022.png]]

L’élément RootPane correspond au conteneur des trois autres éléments. L’élément LayeredPane est lui responsable de la gestion de la position des éléments aussi bien sur les axes X et Y que sur l’axe Z ce qui permet la superposition de différents éléments. L’élément ContentPane est le conteneur de base de tous les éléments ajoutés sur la fenêtre. C’est bien sûr à lui que nous allons confier les différents composants de l’interface de l’application. Par-dessus le ContentPane, se superpose le GlassPane comme on le fait avec une vitre placée sur une photo. Il présente d’ailleurs beaucoup de similitudes avec la vitre.

Il est transparent par défaut.

Ce qui est dessiné sur le GlassPane masque les autres éléments.

Il est capable d’intercepter les événements liés à la souris avant que ceux-ci n’atteignent les autres composants.

De tous ces éléments, c’est incontestablement le ContentPane que nous allons le plus utiliser. Celui-ci est accessible par la méthode getContentPane de la classe JFrame. Il est techniquement possible de placer des composants directement sur l’objet ContentPane mais c’est une pratique déconseillée par Oracle. Il est préférable d’intercaler un conteneur intermédiaire qui lui va contenir les composants et de placer ce conteneur sur le ContentPane. Le composant JPanel est le plus couramment utilisé dans ce rôle.

Le scénario classique de conception d’une interface graphique consiste donc à créer les différents composants puis à les placer sur un conteneur et enfin à placer ce conteneur sur le ContentPane de la fenêtre. L’exemple suivant met cela en application en créant une interface utilisateur composée de trois boutons.

```java
import javax.swing.*;

public class Main {
    public static void main(String[] args)
    {
        JFrame fenetre = new JFrame("Ma première fenêtre Java");

         fenetre.setBounds(0,0,300,100);
          fenetre.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
          // création des trois boutons
          JButton b1,b2,b3;
          b1=new JButton("Rouge");
          b2=new JButton("Vert");
          b3=new JButton("Bleu");
          // création du conteneur intermédiaire
          JPanel pano;
          pano=new JPanel();
          // ajout des boutons sur le conteneur intermédiaire
          pano.add(b1);
          pano.add(b2);
          pano.add(b3);
          // ajout du conteneur intermédiaire sur le ContentPane
          fenetre.getContentPane().add(pano);
          // affichage de la fenêtre
          fenetre.setVisible(true);
    }
}
```
