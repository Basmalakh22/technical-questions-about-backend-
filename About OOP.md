# About OOP

## what is OOP?

- Object-Oriented Programming (OOP) is a `programming paradigm` based on the concept of `objects` which can contain `data` and `code`. `Data` in the form of fields (`attributes` or `properties`), and `code` in the form of procedures (`methods`).

---

## what is the difference between objects and classes?

- Class: A prototype that defines the variables and methods common to all objects of a certain kind.
- Object: An instance of a class. It contains real values instead of variables.
- property: A variable defined within a class that represents the attributes or data of the object.
  - variable inside the class = property
  - variable outside the class = variable
- method: A function defined within a class that represents the behavior of the object. It performs actions or operations on properties or inputs.
  - function inside class = method
  - function outside class = function

```php
class Car {
    public $color; // Property
    public $speed; // Property

    public function drive() { // Method
        return "The car is driving at {$this->speed} km/h";
    }
}

// Creating an object
$car1 = new Car(); // Object
$car1->color = 'red'; // Property of $car1
$car1->speed = 100;   // Property of $car1

echo $car1->drive(); // The car is driving at 100 km/h (calling method)
```

---

## what is the difference between self and this?

- $this: Refers to the current instance of the class(Refers to object properties).
- self:: Refers to the class itself, not an instance. It is used to access static properties and methods.Access constant using self.not user $ because it is not represent variable but represent class construction.

```php
class Car {
    public $color; // Instance property
    public static $type = 'Vehicle'; // Static property

    public function setColor($color) {
        $this->color = $color; // Using $this to set instance property
    }

    public function getDetails() {
        return "This car is a {$this->color} " . self::$type; // Using both $this and self
    }

    public static function getType() {
        return self::$type; // Using self to access static property
    }
}

$car = new Car();
$car->setColor('red');
echo $car->getDetails(); // Outputs: This car is a red Vehicle
echo Car::getType();     // Outputs: Vehicle
```

---

## Difference Between Constants and Static Properties

- Constants: Used for values that never change.
- Static Properties: Used for values that may change but are shared across instances.

```php
class Car {
    public $color; // Instance property
    public static $type = 'Vehicle'; // Static property
    public const WHEELS = 4; // Class constant

    public function setColor($color) {
        $this->color = $color; // Using $this to set instance property
    }

    public function getDetails() {
        return "This car is a {$this->color} " . self::$type . " with " . self::WHEELS . " wheels."; 
        // Using both $this, self::$type, and self::WHEELS
    }

    public static function getType() {
        return self::$type; // Using self to access static property
    }

    public static function getWheels() {
        return self::WHEELS; // Using self to access constant
    }
}

// Usage
$car = new Car();
$car->setColor('red');
echo $car->getDetails(); // Outputs: This car is a red Vehicle with 4 wheels.
echo "\n";
echo Car::getType();     // Outputs: Vehicle
echo "\n";
echo Car::getWheels();   // Outputs: 4
```

---

## function with a parameter

- way to pass data into a function for it to process or act upon. Parameters act as placeholders for the values (called arguments) you supply when calling the function.

```php
function greet($name) {
    return "Hello, $name!";
}

echo greet("Basmala"); // Outputs: Hello, Basmala!
```

---

## Understanding the 4 Pillars of OOP in PHP

- Encapsulation is about bundling data and methods while restricting direct access. In PHP, we achieve this with access modifiers like private, protected, and public.
- Abstraction hides implementation details and exposes only the essentials.
- Inheritance allows us to reuse code by creating child classes from parent classes.
- Polymorphism lets methods perform differently based on the object calling them.

### Encapsulation

- Encapsulation = Private + (getter & setters)
- about bundling data and methods while restricting direct access. In PHP, we achieve this with access modifiers like private, protected, and public.

```php
class BankAccount {
    private $balance; // Private property

    // Constructor to initialize balance
    public function __construct($initialBalance) {
        if ($initialBalance < 0) {
            throw new Exception("Initial balance cannot be negative.");
        }
        $this->balance = $initialBalance;
    }

    // Getter for balance
    public function getBalance() {
        return $this->balance;
    }

    // Setter for balance
    public function deposit($amount) {
        if ($amount <= 0) {
            throw new Exception("Deposit amount must be positive.");
        }
        $this->balance += $amount;
    }

    // Method to withdraw money
    public function withdraw($amount) {
        if ($amount > $this->balance) {
            throw new Exception("Insufficient balance.");
        }
        $this->balance -= $amount;
    }
}

// Usage
$account = new BankAccount(100);
$account->deposit(50); // Adds $50
echo $account->getBalance(); // Outputs: 150
$account->withdraw(30); // Deducts $30
echo $account->getBalance(); // Outputs: 120
```

### Inheritance

- allows us to reuse code by creating child classes from parent classes.

```php
class Animal {
    protected $name;

    public function __construct($name) {
        $this->name = $name;
    }

    public function makeSound() {
        return "Some generic sound";
    }
}

class Dog extends Animal {
    public function makeSound() {
        return "Bark"; // Overriding the parent method
    }
}

class Cat extends Animal {
    public function makeSound() {
        return "Meow"; // Overriding the parent method
    }
}

// Usage
$dog = new Dog("Rex");
echo $dog->makeSound(); // Outputs: Bark

$cat = new Cat("Whiskers");
echo $cat->makeSound(); // Outputs: Meow

```

- note: Properties and constants cannot be declared final, only classes and methods may be declared as final.
- Final Classes: A class marked as final cannot be extended.
- Final Methods: A method marked as final cannot be overridden in a subclass.

```php
class ParentClass {
    final public function importantMethod() {
        return "This method cannot be overridden!";
    }
}

class ChildClass extends ParentClass {
    // This will throw an error
    public function importantMethod() {
        return "Trying to override.";
    }
}
```

### Abstraction

- can't be instantiated (can't create objects from)
- made for other classes to inherit properties and methods from
- abstract methods must be  declared
- focuses on hiding implementation details and exposing only the essential features of an object.

```php
abstract class Animal {
    protected $name;

    public function __construct($name) {
        $this->name = $name;
    }

    // Abstract method: must be implemented by subclasses
    abstract public function makeSound();

    // Concrete method: can be inherited or overridden
    public function eat() {
        return "{$this->name} is eating.";
    }
}

class Dog extends Animal {
    public function makeSound() {
        return "{$this->name} says: Bark!";
    }
}

class Cat extends Animal {
    public function makeSound() {
        return "{$this->name} says: Meow!";
    }
}

// Usage
$dog = new Dog("Rex");
echo $dog->makeSound(); // Outputs: Rex says: Bark!
echo $dog->eat();       // Outputs: Rex is eating.

$cat = new Cat("Whiskers");
echo $cat->makeSound(); // Outputs: Whiskers says: Meow!
```

## Polymorphism

- allows objects of different classes to be treated as objects of a common superclass. It enables a single interface to represent different underlying forms (data types). In simpler terms, polymorphism means "one interface, many implementations."

```php
interface Shape {
    public function calculateArea();
}

class Circle implements Shape {
    private $radius;

    public function __construct($radius) {
        $this->radius = $radius;
    }

    public function calculateArea() {
        return pi() * $this->radius * $this->radius;
    }
}

class Rectangle implements Shape {
    private $width;
    private $height;

    public function __construct($width, $height) {
        $this->width = $width;
        $this->height = $height;
    }

    public function calculateArea() {
        return $this->width * $this->height;
    }
}

function printArea(Shape $shape) {
    echo "The area is: " . $shape->calculateArea() . PHP_EOL;
}

// Usage
$circle = new Circle(5);
$rectangle = new Rectangle(4, 6);

printArea($circle);    // Outputs: The area is: 78.539816339744
printArea($rectangle); // Outputs: The area is: 24
```

---

## what is the acces modefiers?

- Access modifiers control the visibility of properties and methods in a class. They include:
  - public: Accessible from anywhere.
  - protected: Accessible within the class and its subclasses.
  - private: Accessible only within the class.

---

## what is the difference between abstract classes and interfaces and where have you used them?

- Interface: A contract that a class must follow, defining the methods a class must implement without providing the implementation itself.

```php
interface PaymentGateway {
    public function processPayment(float $amount): bool;
}

class StripeGateway implements PaymentGateway {
    public function processPayment(float $amount): bool {
        // Stripe-specific logic here
        return true;
    }
}
```

- Abstract class: A class that cannot be instantiated and may contain both abstract methods (without implementation) and concrete methods (with implementation).

```php
abstract class User {
    protected $name;

    public function __construct(string $name) {
        $this->name = $name;
    }

    abstract public function getRole(): string;

    public function getName(): string {
        return $this->name;
    }
}

class Admin extends User {
    public function getRole(): string {
        return 'Admin';
    }
}
```

---

## what is magic methods?

- Magic methods in PHP are special methods that start with double underscores (__). Examples include`__construct`, `__destruct`,`__get`,`__set`,`__call`, etc. They allow you to define behavior for when properties or methods are accessed or invoked in a way that is not directly defined.

---

## what is the difference between constructor and destructor?

- Constructor: A method called when an object is instantiated, used to initialize the object.
- Destructor: A method called when an object is destroyed, used to clean up resources.

```php
class FileHandler {
    private $file;

    public function __construct($filename) {
        $this->file = fopen($filename, 'w');
        echo "File opened: $filename" . PHP_EOL;
    }

    // Destructor to clean up
    public function __destruct() {
        fclose($this->file);
        echo "File closed." . PHP_EOL;
    }
}

// Creating an object
$fileHandler = new FileHandler("example.txt");
```

---

## what is the difference between trait and class?

- Class: A blueprint for creating objects with properties and methods.
- Trait: A mechanism for code reuse, allowing methods and properties to be shared across multiple classes.

```php
trait A {
    public function sayHello() {
        echo "Hello from Trait A!";
    }
}

trait B {
    public function sayHello() {
        echo "Hello from Trait B!";
    }
}

class Example {
    use A, B {
        A::sayHello insteadof B;
        B::sayHello as sayHelloFromB;
    }
}

$example = new Example();
$example->sayHello(); // Outputs: Hello from Trait A!
$example->sayHelloFromB(); // Outputs: Hello from Trait B!
```

---

## what is the difference between extend and implment?

- extend: Used to inherit from a class(inheritance).
- implement: Used to implement an interface (polymorphism).
- use extend when you want to inherit functionality, use implement when you want to define a contract for a class to follow.

---

## Namespace and Autoloading

- Namespace allows you to group related code under a specific name, improving code organization and reusability.
- Autoloading in PHP is a mechanism that automatically loads PHP classes when they are needed, without having to manually require or include them.The most common way to implement autoloading in PHP is by using Composer, the dependency manager. Composer generates an autoloader that follows the PSR-4 standard for autoloading classes.

---

## what is the difference between session and cookies?

- Sessions: Store data on the server side, more secure, used for storing sensitive information.
- Cookies: Store data on the client side (browser), less secure, used for storing less sensitive information like user preferences.

---

## What is a Callback Function?

- A Callback Function is a function that is passed as an argument to another function and is executed at a later time.

## What are Accessors and Mutators?

- Accessors: Methods used to format or transform attributes when they are accessed (e.g., `getNameAttribute`).
- Mutators: Methods used to format or modify data before saving it to the database (e.g., `setNameAttribute`).

## What is the difference between HTTP and HTTPS?

- HTTP is an unsecured protocol, while HTTPS is a secure version of HTTP that uses encryption (SSL/TLS) to protect data transmitted between the client and the server.

## What is Overloading & Overriding?

- Overloading: A feature where a method or function can have different signatures (e.g., a different number of parameters). PHP doesn't support method overloading directly but allows magic methods like `__call()`.
- Overriding: When a subclass provides a specific implementation of a method that is already defined in its parent class.
