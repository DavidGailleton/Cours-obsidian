Le php doit être entouré de balise :
```php
<?php     

?>
```

Pour ecrire une ligne on utilise la fonction echo :
```php
<?php  
echo "Hello World !"  
?>
```

![[Pasted image 20240212094852.png]]

Il est possible d'ecrire du [[HTML]] dans un fichier PHP :
```php
<?php  
echo "Hello World !"  
?>  
  
<!DOCTYPE html>  
<html>  
<head>  
  
</head>  
<body>  
	<h1>Introduction php</h1>  
</body>  
</html>
```

![[Pasted image 20240212095217.png]]

## Variable
Pour créer une variable on utilise le signe `$`
```php
<?php  
$texte = "hello world !";  
echo $texte;  
?>
```

## Condition
Les condition en php se font de cette manière :
```php
$nombre = 42;  
if ($nombre > 30){  
    echo "Nombre supérieur à 30";  
} elseif ($nombre == 30)  {  
    echo "Nombre  égal à 30";  
} else {  
    echo "Nombre inférieur à 30";  
}
```

> A noter qu'il est obligatoire d'avoir un `else` en php

## Boucle
### For
```php
for ($i = 0; $i < $nombre; $i++){  
    # code...  
}
```

## Fonction
La fonction se créer avec le mot clé `function` :
```php
function addition($a, $b){  
    return $a + $b;  
}  
  
echo addition(4, 7);
```

> En PHP, les variable déclarer en dehors d'une fonction ne sont pas a l'intérieur de cette même fonction. 

> La portée d'une fonction se limite a son fichier


## Include
Il y a 2 moyens d'inclure des fichiers en PHP :
- `include` : si le fichier n'est pas trouvé on obtient un warning
- `require` : si le fichier n'est pas trouvé on obtient une erreur fatal et l'arrêt du script

```php
include 'inc.php';
require 'inc.php';
```

## Portée d'un variable


