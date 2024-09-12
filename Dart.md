
## Language Dart
Dart est un langage de programmation développé par Google, principalement utilisé pour développer des applications mobiles avec **Flutter**, mais il est également adapté pour le développement web, serveur et de bureau. Il est conçu pour être simple à apprendre et à utiliser, tout en étant performant pour des applications modernes.

### 1. **Introduction à Dart**
   Dart est un langage **orienté objet**, **statiquement typé**, ce qui signifie que les types des variables sont connus à la compilation. Toutefois, il peut également être utilisé de manière dynamique, permettant d’omettre la spécification des types pour plus de flexibilité.

   Voici un exemple basique de code Dart :
   ```dart
   void main() {
     print('Hello, world!');
   }
   ```

### 2. **Caractéristiques de Dart**
   - **Statiquement typé** : Dart vérifie les types à la compilation, mais il supporte aussi la **typage dynamique** avec le mot-clé `var` ou `dynamic`.
   - **Orienté objet** : Tout dans Dart est un objet, même les types de base comme `int`, `double`, etc.
   - **Compatible avec le développement asynchrone** : Dart facilite le traitement asynchrone avec les `Future` et `Stream`.
   - **Cross-platform** : Avec Flutter, Dart permet de créer des applications pour Android, iOS, web, et desktop à partir d'une seule base de code.

### 3. **Syntaxe de Base**

#### a) **Variables et Types**
   En Dart, les variables peuvent être explicitement typées ou leur type peut être inféré automatiquement.
   - **Types de base** :
     - `int` : Nombres entiers.
     - `double` : Nombres à virgule flottante.
     - `bool` : Valeurs booléennes (`true` ou `false`).
     - `String` : Chaîne de caractères.
   
   Exemple de déclaration :
   ```dart
   int age = 25;
   double height = 1.75;
   bool isStudent = true;
   String name = "Alice";
   ```

   Avec inférence de type :
   ```dart
   var age = 25;
   var height = 1.75;
   ```

#### b) **Constantes**
   Dart utilise les mots-clés `const` et `final` pour définir des constantes. La différence est que `const` est une constante de compilation, tandis que `final` est une constante qui peut être initialisée à l’exécution, mais ne peut plus être modifiée par la suite.

   ```dart
   const pi = 3.14;
   final currentTime = DateTime.now();
   ```

### 4. **Contrôles de Flux**

#### a) **Conditions**
   Dart utilise les instructions classiques `if`, `else`, `switch` pour gérer les conditions.

   ```dart
   int score = 85;

   if (score >= 90) {
     print('Excellent');
   } else if (score >= 70) {
     print('Good');
   } else {
     print('Needs Improvement');
   }
   ```

#### b) **Boucles**
   Dart supporte les boucles `for`, `while`, et `do-while`.

   - Boucle `for` classique :
     ```dart
     for (int i = 0; i < 5; i++) {
       print(i);
     }
     ```

   - Boucle `for-in` :
     ```dart
     var numbers = [1, 2, 3, 4];
     for (var number in numbers) {
       print(number);
     }
     ```

   - Boucle `while` :
     ```dart
     int count = 0;
     while (count < 5) {
       print(count);
       count++;
     }
     ```

### 5. **Fonctions**
   Les fonctions en Dart sont des blocs de code qui peuvent être réutilisés. Elles peuvent renvoyer des valeurs ou non (dans ce cas, elles renvoient `void`).

   ```dart
   // Fonction avec retour
   int add(int a, int b) {
     return a + b;
   }

   // Fonction sans retour
   void greet(String name) {
     print('Hello, $name');
   }

   void main() {
     int sum = add(5, 3);
     print(sum);  // 8

     greet('Alice');
   }
   ```

   Dart supporte aussi les **fonctions anonymes** et les **fonctions fléchées** (lambda expressions) :
   ```dart
   var multiply = (int a, int b) => a * b;
   print(multiply(4, 5));  // 20
   ```

### 6. **Classes et Objets**
   Dart est orienté objet, donc les classes sont fondamentales. Une classe en Dart est une structure qui définit des attributs et des méthodes.

   - **Déclaration d'une classe** :
     ```dart
     class Person {
       String name;
       int age;

       // Constructeur
       Person(this.name, this.age);

       // Méthode
       void greet() {
         print('Hello, my name is $name and I am $age years old.');
       }
     }

     void main() {
       // Création d'une instance de Person
       Person person = Person('Alice', 25);
       person.greet();
     }
     ```

   - **Héritage** : Dart supporte l’héritage via la syntaxe `extends` et permet aussi la réutilisation du code via les **mixins**.
     ```dart
     class Student extends Person {
       String school;

       Student(String name, int age, this.school) : super(name, age);

       @override
       void greet() {
         super.greet();
         print('I study at $school.');
       }
     }
     ```

### 7. **Collections**
   Dart propose trois types de collections majeures :
   - **List** : Collection ordonnée d'éléments.
     ```dart
     List<String> fruits = ['Apple', 'Banana', 'Mango'];
     fruits.add('Orange');
     print(fruits[0]);  // Apple
     ```
   
   - **Set** : Collection non ordonnée d'éléments uniques.
     ```dart
     Set<int> numbers = {1, 2, 3, 4};
     numbers.add(5);
     ```
   
   - **Map** : Collection de paires clé-valeur.
     ```dart
     Map<String, String> capitals = {'France': 'Paris', 'Germany': 'Berlin'};
     print(capitals['France']);  // Paris
     ```

### 8. **Asynchrone avec Futures et Streams**
   Dart est conçu pour le traitement asynchrone avec des **Futures** et des **Streams**.
   
   - **Future** : Représente une opération asynchrone qui produira une valeur ou une erreur à un moment donné.
     ```dart
     Future<void> fetchData() async {
       await Future.delayed(Duration(seconds: 2));
       print('Data fetched');
     }
     ```

   - **Stream** : Représente une séquence d'événements asynchrones qui peuvent être manipulés avec des opérations comme `listen()`.
     ```dart
     Stream<int> numberStream = Stream.fromIterable([1, 2, 3, 4, 5]);
     numberStream.listen((number) {
       print(number);
     });
     ```

### 9. **Gestion des Exceptions**
   Dart utilise les blocs `try`, `catch`, `finally` pour gérer les erreurs.
   ```dart
   try {
     int result = 10 ~/ 0;  // Division par zéro
   } catch (e) {
     print('Error: $e');
   } finally {
     print('This block is always executed.');
   }
   ```

### 10. **Conclusion**
   Dart est un langage puissant et moderne, bien adapté au développement d'applications multiplateformes. Son intégration avec Flutter, sa syntaxe simple, et ses fonctionnalités avancées en font un excellent choix pour les développeurs qui cherchent à créer des applications performantes. Dart offre également des outils robustes pour la gestion des collections, l'asynchrone, et les classes, ce qui permet une grande flexibilité pour les développeurs.
