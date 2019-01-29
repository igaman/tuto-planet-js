#  Classes en javascript

Les classes JavaScript ont été introduites avec ECMAScript 2015. Elles sont un « sucre syntaxique » par rapport à l'héritage prototypal. En effet, cette syntaxe n'introduit pas un nouveau modèle d'héritage dans JavaScript ! Elle fournit uniquement une syntaxe plus simple pour créer des objets et manipuler l'héritage. Toutefois, l'objectif de cette évolution est de rendre le code plus lisible et plus facilement accessible.
```
class User {
  // méthode constructor
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }

  sayName() {
    return `${this.firstname} ${this.lastname}`;
  }
}

// instanciation
const user = new User("John", "Doe");

// appel de la méthode sayName()
console.log(user.sayName()); // John Doe

```
La méthode constructor est une méthode qui est utilisée pour créer et initialiser un objet lorsqu'on utilise le mot clé class.

#  L'héritage

Pour qu'une sous-classe hérite d'une autre classe on utilisera le mot clé extends.

```
class Contributor extends User {
  constructor(firstname, lastname, numberCommit) {
    // le mot clé super est utilisé comme super contructeur. Il permet d'appeler
    // et d'avoir accès aux méthodes du parent
    super(firstname, lastname);
    this.numberCommit = numberCommit;
  }

  sayNameWithCommit() {
    // on peut appeler une méthode de la classe parente avec `super.method`
    return super.sayName() + " " + this.sayNumberCommit();
  }

  sayNumberCommit() {
    return this.numberCommit;
  }
}

// instanciation
const contributor = new Contributor("Jane", "Smith", 10);

// appel de la méthode sayName()
console.log(contributor.sayName());
console.log(contributor.sayNumberCommit());

```

Le mot-clé super est utilisé afin d'appeler ou d'accéder à des fonctions définies sur l'objet parent.
