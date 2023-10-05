Lorsqu’une application Java sans interface graphique est exécutée, au moins deux threads sont exécutés :

Le thread principal (le thread main) dont le rôle est d’exécuter la méthode main du programme. C’est le point d’entrée obligatoire pour l’exécution d’une application Java SE standard. Le thread du ramasse-miettes (garbage collector) pour nettoyer la mémoire lorsque celle-ci est occupée au-delà d’un certain seuil. Un thread est tout simplement une unité d’exécution d’un programme. Un programme peut être composé d’un ou plusieurs threads. L’avantage d’avoir plusieurs threads est de permettre l’exécution de plusieurs tâches en parallèle. Prenons l’exemple d’un navigateur : il est très fréquent d’effectuer une requête vers un site et, en attendant son téléchargement et son affichage, de consulter une autre page, de visionner une vidéo… Tout cela est possible grâce à l’utilisation de différents threads.

Sur une machine multiprocesseur, les différents threads peuvent effectivement s’exécuter en parallèle en exploitant les différents processeurs. Sur une machine monoprocesseur, c’est la fréquence de transition entre les différents threads qui permet à l’utilisateur de penser que les tâches s’exécutent en parallèle. En effet, le processeur partage son temps entre les différents threads. Il n’exécute qu’un seul thread à la fois, mettant en pause les autres threads pendant ce temps. Ainsi, pour exécuter la totalité d’un thread, le processeur peut s’y prendre à plusieurs fois en mettant le thread en pause à plusieurs reprises pour exécuter les autres threads.

Pour exécuter une application Java avec une interface graphique, un troisième thread entre en jeu : c’est le thread EDT (Event Dispatching Thread). Ce thread est responsable de la gestion de l’interface graphique et de la gestion des événements (comme un clic sur un bouton).

Dans l’exemple précédent, l’interface graphique a été créée dans la méthode main et donc par le thread main. C’est donc le thread main qui est « propriétaire » des boutons présents sur l’interface graphique. Si l’utilisateur clique dessus, le thread EDT est sollicité pour réagir à cette action. Pour cela, le thread EDT a souvent besoin d’accéder aux éléments graphiques. Une opération inter-thread est donc nécessaire dans ce cas de figure. Et c’est là que les problèmes peuvent survenir. En effet, les composants graphiques ne sont pas thread safe. Cela signifie qu’un accès à partir d’un autre thread peut éventuellement causer un problème.

Pour éviter ce genre de situation, il est donc nécessaire de faire en sorte que seul le thread EDT manipule l’interface graphique, que ce soit pour la création de l’interface ou pour la gestion des événements. Il faut donc être capable, depuis le thread main qui exécute la méthode main, de demander au thread EDT de construire l’interface graphique de l’application. Ceci est possible par l’utilisation de la méthode invokeLater de la classe SwingUtilities. Cette méthode attend en paramètre un objet de type Runnable qui est une interface fonctionnelle contenant une seule méthode abstraite dont la signature est la suivante : void run(). Cet objet (ou cette expression lambda) définit simplement ce qui doit être exécuté par le thread EDT. Le code suivant apporte donc une modification essentielle à l’exemple précédent pour s’assurer du bon fonctionnement de l’application dans toutes les situations :

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.SwingUtilities;

public class Principale {
     private JFrame fenetre;
     //Constructeur appelé par le thread EDT
     Principale(String[] args) {
         // Construction de l'IHM
         // création de la fenêtre
         this.fenetre=new JFrame();
         this.fenetre.setTitle("première fenêtre en JAVA");
         this.fenetre.setBounds(0,0,300,100);
         this.fenetre.setDefaultCloseOperation (JFrame.EXIT_ON_CLOSE);
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
         this.fenetre.getContentPane().add(pano);
   }

     //Méthode appelée par le thread EDT
   public void show() {
         // Affichage de l'IHM
       this.fenetre.setVisible(true);
   }

   //Point d'entrée exécuté par le thread main
   public static void main(final String[] args) {
         // Programme une tâche pour le thread EDT:
         // Création et affichage de l'interface graphique
         /*SwingUtilities.invokeLater(new Runnable() {
             public void run() {
                 new Principale(args).afficher();
             }
         });*/
         SwingUtilities.invokeLater(()->
                                 new Principale(args).afficher());
   }
}
```