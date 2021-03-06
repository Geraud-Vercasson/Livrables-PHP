﻿# Glossaire Programmation Orientée Objet

## Objet:
	
Variable (ou constante) collectant un ensemble d'informations / propriétés, ses attributs, et un ensemble de fonctions permettant d'agir sur cet objet, d'interagir avec, etc, ses méthodes 


## Classe :

Ensemble d'attributs et de méthodes permettant de définir la structure, le "plan de fabrication" d'un objet. Analogie du gâteau : un gâteau est un objet, sa classe est le moule qui définit la forme; la structure du gâteau. En PHP, une classe se déclare par le mot-clé `class`.

## Instance :

Une instance d'une classe est un objet créée à partir de la classe. Ce n'est pas une structure (classe seule), mais un objet défini selon les règles de construction et d'utilisation de cette classe. L'instanciation d'une classe est donc la création d'une instance de cette classe. En PHP, pour instancier une classe, on utilise le mot-clé `new` : `$monObjet = new MyClass()` => la variable $monObjet est une instance de la classe MyClass 

## opérateur `->` :

`->` est un opérateur utilisé pour atteindre une méthode ou un attribut d'un objet. Par exemple pour appeler la méthode bonjour() de l'objet $geraud, on écrit `$geraud->bonjour()`.

## Encapsulation :

Principe en informatique de créer des outils qui se comporteront en "boîte noire" : l'utilisateur n'aura ni à connaitre, ni à toucher au code à l'intérieur de cette "boîte" pour pouvoir utiliser cet outil (fonction, objet, classe, ou autre). 

Analogie de la voiture : pour démarrer une voiture, le conducteur a juste à tourner la clé (voire moins). Il n'a pas besoin de voir ou de comprendre le mécanisme qui, une fois la clé tournée, démarre la voiture : les concepts de bougie d'allumage, d'injection etc sont inutiles (et donc "cachés") à l'utilisateur.


## Visibilité :

La visibilité, d'un attribut ou d'une méthode, c'est la zone depuis laquelle on peut accéder à cet attribut, cette méthode. La visibilité  `public` permet d'appeler l'attribut ou la méthode depuis l'extérieur de l'objet / de la classe. à l'inverse la visibilité `private` rend inaccessible depuis l'extérieure de la classe / l'objet l'attribut ou la méthode concernée. Enfin, la visibilité `protected` permet d'appeler l'attribut ou la méthode concernée depuis la classe et toutes les classes héritées de celle-ci, tout en restant inaccessible depuis "l'extérieur". (voir Héritage)

Analogie : Prénom et Numéro de compte. En imaginant une personne comme étant un objet (ou une classe de manière générique), on pourrait définir son Prénom comme attribut public, car tout le monde à le droit de le connaître.

Son numéro de compte par contre, ne doit être connu que de lui, sans quoi il risque de se voir modifier cet attribut (en se faisant vider son compte par exemple).
Une méthode publique créditerCompte pourrait permettre de créditer automatiquement le compte de cette personne, en utilisant son numéro de compte.

le numéro n'est pas accessible depuis l'extérieur, mais des méthodes publiques de cette classe / cet objet peuvent y accéder (ce qui rejoint le concept d'encapsulation)

## Constructeur :

Le constructeur d'une classe est la méthode qui sera appellée automatiquement à l'instanciation de cette classe. Il peut prendre autant d'argument que l'on souhaite, et est (en PHP) toujours nommé __construct.

Cette méthode permet, par exemple, d'initialiser les variables de l'instance, d'informer l'utilisateur de la création d'objet, etc.

Exemple:

	//Définition de la class
	class Person {
	//Définition de ses attributs
	public $nom
	//Définition du constructeur
	public function __construct($nouveauNom){
		$this->nom = $nouveauNom;
		}
	}
	
	//Création de l'instance :
	$moi = new Person('Géraud');

A noter : lors de l'instanciation, nous n'avons pas fait appel directement au constructeur, mais `new NomDeLaClasse(argumentsDuConstructeur)`. PHP reconnait cette syntaxe et à ce moment appelle le constructeur avec les arguments ainsi passés

## Destructeur :

Le destructeur est la méthode de la classe qui sera appellée automatiquement à la destruction de l'instance. Cela se fait automatiquement dès qu'il n'y a plus de référence dans le code à l'instance concernée, lorsqu'on détruit explicitement l'instance.

Le destructeur en PHP est toujours nommé __destruct, et n'a jamais d'argument : en effet la façon de détruire une instance (contrairement au moment de le faire) ne dépend d'aucun paramètre.

Le destructeur peut servir, par exemple, à informer l'utilisateur de la destruction de l'instance, ou à sauvegarder les données de l'objet dans une base de données, ou tout autre action que l'on veut éxecuter avant la disparition de l'objet.

## Getter / Accesseur :

Lorsqu'un attribut n'est pas visible depuis l'extérieur et donc ne peut être ni lu ni modifié en dehors de la classe / l'objet, on peut quand-même avoir besoin de cet attribut. Pour cela, on peut implémenter dans notre classe / notre objet des méthodes publiques (donc accessible depuis l'extérieur) afin de retourner la valeur de cet attribut. on parle alors de "getter". Par convention, ces méthodes portent le même nom que l'attribut auxquelles elle renvoient.

## Setter / Mutateur :

De la même manière qu'un Getter permet de récupérer la valeur d'un attribut, un Setter est une méthode qui permet de modifier, depuis l'extérieur, la valeur de cet attribut.

## Héritage :

L'héritage est un concept de lien de parenté entre deux classes : une classe mère (parent) et une classe fille. Ce lien est défini lors de la déclaration de la classe fille, en PHP, via le mot-clé `extends`. Une classe fille "hérite" des attributs et des méthodes de sa classe mère : une méthode définie dans la classe mère est utilisable dans sa classe fille, et aura par défaut le même comportement.


## Override / Surcharge :

Une méthode héritée d'une classe mère peut être redéfinie pour avoir un comportement différent dans une classe fille. Ainsi, une méthode portant le même nom peut avoir un comportement différent en fonction de la classe (ou l'instance de la classe) depuis laquelle elle est apellée.

## mot-clé : `final`
	
Lorsque l'on veut empêcher l'override d'une méthode dans les classes héritées d'une classe mère, il faut utiliser le mot-clé `final` dans la déclaration de cette méthode, dans la classe mère. Ce mot clé permet de rendre"finale" la ou les méthodes concernées, et que par définition elle ne peut pas se comporter autrement dans les classes héritées.

`final` peut également être utilisé sur une classe, interdisant ainsi qu'on puisse l'étendre

## mot-clé : `static`

Par défaut, une méthode ou un attribut "seul" n'as pas forcément de sens : imaginons une class Person avec un attribut nom. La notion de nom pour une personne "générique" n'a pas de sens; ce n'est que lorsqu'on instancie (crée un objet) de la class Person (exemple moi) que l'on peut définir l'attribut nom (exemple Géraud).
Néanmoins, il est parfois utile de pouvoir appeler un attribut ou une méthode d'une classe sans pour autant l'instancier : par exemple une Person, sans qu'elle soit définie, peut quand même dire "bonjour". On appelle alors la méthode bonjour() de la classe Person avec l'opérateur `::`(apellé opérateur de résolution de portée) . Ceci n'est possible que si la méthode (ou l'attribut) concernée a été déclarée avec le mot-clé `static`

Dans notre exemple, l'appel de la méthode statique bonjour() se fera en écrivant `Person::bonjour()`.

De la même manière on peut définir un attribut statique, toujours avec le mot-clé `static`. Un attribut ainsi déclaré ne sera donc pas lié à une instance particulière, mais bien à la classe toute entière, indépendamment de ses instances.

## mot-clé `$this`

Pour accéder à l'attribut $nom de l'objet $geraud de la classe Person, on écrit `$geraud->nom`. Mais comment accéder à cet attribut depuis l'intérieur de l'objet?

Le mot-clé `$this` permet de faire référence à l'instance dans laquelle nous nous trouvons. Ainsi, depuis l'intérieur de l'objet $geraud, on peut accéder à l'attribut $nom par la ligne : `$this->nom`.

Ce mot-clé est très important dans les définitions de classe, car c'est avec `$this` que l'on fait référence à l'instance "que l'on manipule en ce moment". par exemple une méthode `direMonNom()` créée dans la classe Person, accèdera à l'attribut $nom par `$this->nom`.

**Attention !** L'attribut $nom, dans notre exemple, n'est pas un attribut statique : en effet, toutes les instances de la class Person n'auront pas (forcément) le même attribut $nom. Pour atteindre des propriétés statiques depuis l'intérieur de la classe, il faut utiliser :

## mot-clé `self`

Le mot-clé `self` permet de faire référence, depuis l'intérieur de la classe (ou d'une instance de cette classe) à une propriété statique inhérente à cette classe. `self` fait donc référence à la classe elle-même.

Exemple : en reprenant notre méthode statique bonjour() de la classe Person, nous pouvons l'appeler, depuis l'extérieur de la classe, par la ligne `Person::bonjour()`.

Pour l'appeler depuis l'intérieur de la classe, on écrit : `self::bonjour()`.

## mot-clé `parent`

Comme évoqué plus haut, l'opérateur `::`, appelé opérateur de résolution de portée, permet d'appeler une méthode ou un attribut directement depuis la classe concernée.

Outre les utilisations vues plus haut, comme l'appel à des propriétés statiques ou associé avec le mot-clé `self`, une idée importante concerne l'héritage et plus particulièrement la surchage (overriding) de méthode. En effet, si une méthode issue d'une classe mère et surchargée dans une classe fille, cette classe pourra quand-même faire référence à la méthode de la classe mère.

Ceci se fait par l'utilisation du mot-clé `parent`. Avec le mot-clé `parent`, nous pouvons appelé depuis une classe fille une méthode telle qu'elle est définie dans la classe mère, indépendamment de la surchage ou non dans la classe fille.

Exemple d'utilisation 'courante' : le constructeur d'une classe fille.

Lorsque l'on définit le constructeur d'une classe fille, on surcharge la méthode héritée de la classe mère. Hors, la construction d'un objet d'une classe fille commence (souvent) par refaire exactement les mêmes affectations, les mêmes opérations définies dans le constructeur de la classe mère. Dans ce cas, plutôt que de réécrire un morceau de code, il est plus judicieux d'appeler le constructeur de la classe mère dans la classe fille. Cela s'écrit :

	public function __construct([argumentsClasseFille]) {
		parent::__construct([argumentsClasseMère]);
	}
