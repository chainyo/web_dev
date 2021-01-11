# <center>Javascript</center>

## Introduction 

JavaScript est un langage de script, multi-plateforme et orienté objet. C'est un langage léger qui doit faire partie d'un environnement hôte (un navigateur web par exemple) pour qu'il puisse être utilisé sur les objets de cet environnement.

JavaScript contient une bibliothèque standard d'objets tels que `Array`, `Date`, et `Math`, ainsi qu'un ensemble d'éléments de langage tels que les opérateurs, les structures de contrôles et les instructions. Ces fonctionnalités centrales et natives de JavaScript peuvent être étendues de plusieurs façons en fournissant d'autres objets, par exemple :

* *JavaScript côté client* étend ces éléments de base en fournissant des objets pour contrôler le navigateur et le *Document Object Model* (DOM). Par exemple, les extensions du langage côté client permettent de placer des éléments dans un formulaire HTML, de réagir aux événements déclenchés par l'utilisateur (les clics, la saisie d'un formulaire, les actions de navigation, etc.).
* *JavaScript côte serveur* étend ces éléments de base avec des objets utiles pour le fonctionnement sur un serveur tels que la possibilité de communiquer avec une base de données, manipuler des fichiers, passer d'une application à une autre, etc.

Le meilleur site avec toutes les meilleurs ressources pour du JS est celui de Mozilla, suivre [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript).   
L'avantage est que ce site est à la fois en Anglais et en Français.

Pour teste son code JS, une bonne pratique est d'utiliser la console développeur de Google Chrome qui est très performante pour voir l'application de son code JS et également ses pages HTML/CSS.

## Les bases de JS

Pour la déclaration des variables en JS, on utilise le `CamelCase` contrairement à Python qui préconise l'utilisation du `snale_case`.

Exemples de déclarations de variables en JS :  

```javascript
var MaVariableEstIncroyable = 0
var JeSuisUnSuperCodeur = 1 // mauvaise idée de faire des variables si peu descriptives.

// On favorise les variables aux noms courts et très explicites
var UserId = 'Jean'
var UserMail = 'lol@lol.com' 
```

Les différentes manières de déclarer une variable en JS :

```javascript
const // pour les constantes
var // pour définir uen variable globale
let // pour définir une variable dans le scope où la variable est déclarée
```

Comme pour `Python`, le langage `Javascript` est un langage orienté objet. Exemple de la création d'un objet :

```javascript
const myObject = {
  property: 'Value!',
  otherProperty: 77,
  "obnoxious property": function() {
    // do stuff!
 }
}
```

Il existe deux façons d'obtenir des informations avec ce langage :

```javascript
// dot notation
myObject.property // 'Value!'

// bracket notation
myObject["obnoxious property"] // [Function]
```

La notation en point est préférée habituellement par les développeurs web, mais l'utilisation d'une notation dépend du contexte.

Pour afficher des informations dans la console, on utilise le `console.log()` :

```javascript
function test() { 
    console.log("look ma’, no spaces"); 
}
```

La boucle `for`, fonctionne de la manière suivante :

```javascript
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement
```

```javascript
for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step');
}
```

Les autres structures de contrôle :

```javascript
do
  statement
while (condition);
```

```javascript
while (condition)
  statement
```

```javascript
for (variable in object) // parmis toutes les propriétés d'un objet
  statement
  
for (variable of object) // parmis toutes les propriétés d'un tableau
  statement
```

```javascript
continue [label];

break;
break [label];
```

```javascript
label :
   statement
   
markLoop:
    while (theMark === true) {
       doSomething();
}
```

Pour déclarer une classe :

```javascript
class Rectangle {
  constructor(hauteur, largeur) {
    this.hauteur = hauteur;
    this.largeur = largeur;
  }
}

const MonRectangle = new Rectangle();
```

Le mot-clef `self` en Python est remplacé par `this` en JS.  
On utilise le mot-clef `new` pour instancier un nouvel objet d'une classe en JS.  
Les instances des objets doivent être déclarées après la créationd de la classe, sinon on obtient une erreur (`ReferenceError`).

## Vérification des entrées d'un formulaire

Pour la vérification des mails :

```javascript
function ValidateEmail(mail) 
{
 if (/^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/.test(myForm.emailAddr.value))
  {
    return (true)
  }
    alert("You have entered an invalid email address!")
    return (false)
}
```

Pour récupérer en JS les entrées du formulaire et vérifier que les inputs sont complétées :

```javascript
function Verification() {
    // Récupérer lavaleur des champs nom et email
    var Nom = document.getElementById('idNom').value;
    var Email = document.getElementById('idEmail').value;
// Contrôle sur le nom
    if(Nom==''){
        alert('Vous devez compléter votre nom !');
        document.getElementById('idNom').style.backgroundColor="red";
        document.getElementById('idNom').style.color="#FFF";
        // Permet de bloquer l'envoi du formulaire
        return false;
    }
    else{
        document.getElementById('idNom').style.backgroundColor="#9C6";
    }
// Contrôle sur l'email
    if(Email=='') {MaVariableEstIncroyable = 0
        alert('Vous devez compléter votre adresse email');
        document.getElementById('idEmail').style.backgroundColor="red";
        document.getElementById('idEmail').style.color="#FFF";
        // Permet de bloquer l'envoi du formulaire
        return false;
    }
    else{
        document.getElementById('idEmail').style.backgroundColor="#9C6";
    }
}
```

Pour la vérification des inputs d'un formulaire (savoir si tout est complété) :

```javascript
$("input:checkbox").click(function() {
var bol = $("input:checkbox:checked").length >= 2;
$("input:checkbox").not(":checked").attr("disabled",bol);
});
```
