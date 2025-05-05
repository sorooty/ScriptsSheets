# Object-Oriented Programming in Dart

Dart is a fully object-oriented language where everything is an object. This guide covers the core OOP concepts in Dart.

## 🏗️ Basic Class Structure

```dart
// Basic class definition
class Person {
  // Instance variables
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.anonymous() : name = 'Anonymous', age = 0;
  
  // Method
  void sayHello() => print('Hello, I am $name');
  
  // Getter
  String get greeting => 'Hello, I am $name';
  
  // Setter
  set newAge(int value) => age = value;
}
```

## 🧬 Inheritance

```dart
// Base class
class Animal {
  String name;
  Animal(this.name);
  
  void makeSound() => print('Some sound');
}

// Derived class
class Dog extends Animal {
  String breed;
  
  // Super constructor call
  Dog(String name, this.breed) : super(name);
  
  // Method override
  @override
  void makeSound() => print('Woof!');
  
  // Additional method
  void fetch() => print('Fetching...');
}
```

## 📝 Interfaces

```dart
// Interface (abstract class with no implementation)
abstract class Shape {
  double get area;
  double get perimeter;
}

// Implementing class
class Circle implements Shape {
  double radius;
  
  Circle(this.radius);
  
  @override
  double get area => 3.14 * radius * radius;
  
  @override
  double get perimeter => 2 * 3.14 * radius;
}
```

## 🔍 Abstract Classes

```dart
// Abstract class with some implementation
abstract class Vehicle {
  String name;
  
  Vehicle(this.name);
  
  // Abstract method
  void move();
  
  // Concrete method
  void honk() => print('Beep beep!');
}

// Concrete class
class Car extends Vehicle {
  Car(String name) : super(name);
  
  @override
  void move() => print('$name is moving on wheels');
}
```

## 🧩 Mixins

```dart
// Mixin definition
mixin Flyable {
  void fly() => print('Flying...');
}

mixin Swimmable {
  void swim() => print('Swimming...');
}

// Using mixins
class Duck with Flyable, Swimmable {
  void quack() => print('Quack!');
}
```

## 🔧 Extensions

```dart
// Extension on String
extension StringExtension on String {
  String get capitalize => 
      '${this[0].toUpperCase()}${substring(1)}';
  
  bool get isPalindrome => 
      toLowerCase() == toLowerCase().split('').reversed.join('');
}

// Using extension
void main() {
  print('hello'.capitalize); // 'Hello'
  print('racecar'.isPalindrome); // true
}
```

## 📦 Generics

```dart
// Generic class
class Box<T> {
  T value;
  
  Box(this.value);
  
  T getValue() => value;
}

// Generic method
T first<T>(List<T> items) => items.first;

// Using generics
void main() {
  var box = Box<int>(42);
  print(box.getValue()); // 42
  
  var names = ['Alice', 'Bob'];
  print(first(names)); // 'Alice'
}
```

## 🔄 Method Overriding

```dart
class Animal {
  void makeSound() => print('Some sound');
}

class Cat extends Animal {
  @override
  void makeSound() => print('Meow!');
  
  // Using super
  void makeSoundTwice() {
    super.makeSound();
    makeSound();
  }
}
```

## 🔒 Encapsulation

```dart
class BankAccount {
  // Private field (underscore prefix)
  double _balance = 0;
  
  // Public getter
  double get balance => _balance;
  
  // Public methods
  void deposit(double amount) {
    if (amount > 0) {
      _balance += amount;
    }
  }
  
  void withdraw(double amount) {
    if (amount <= _balance) {
      _balance -= amount;
    }
  }
}
```

## 📚 Resources

- [Dart Language Tour - Classes](https://dart.dev/guides/language/language-tour#classes)
- [Dart Language Tour - Inheritance](https://dart.dev/guides/language/language-tour#extending-a-class)
- [Dart Language Tour - Mixins](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Dart Language Tour - Generics](https://dart.dev/guides/language/language-tour#generics) 