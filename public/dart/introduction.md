# Introduction to Dart

Dart is a client-optimized programming language developed by Google. It is used for building mobile, desktop, server, and web applications. Dart is the primary language for Flutter development.

## Key Features

- **Strong Typing**: Static type system with type inference
- **Null Safety**: Built-in null safety to prevent null reference errors
- **Object-Oriented**: Everything is an object
- **Asynchronous Programming**: Built-in support for async/await
- **Garbage Collection**: Automatic memory management
- **JIT & AOT Compilation**: Just-in-time compilation for development, ahead-of-time for production

## Basic Syntax

```dart
// Variables
var name = 'Dart'; // Type inferred as String
String explicitName = 'Dart'; // Explicit type
final constantName = 'Dart'; // Cannot be reassigned
const compileTimeConstant = 'Dart'; // Compile-time constant

// Functions
String greet(String name) {
  return 'Hello, $name!';
}

// Arrow syntax for single-line functions
String greetShort(String name) => 'Hello, $name!';

// Null Safety
String? nullableName; // Can be null
String nonNullableName = 'Dart'; // Cannot be null

// Collections
List<String> names = ['Alice', 'Bob', 'Charlie'];
Map<String, int> ages = {'Alice': 25, 'Bob': 30};
Set<String> uniqueNames = {'Alice', 'Bob', 'Alice'}; // {'Alice', 'Bob'}

// Classes
class Person {
  String name;
  int age;
  
  Person(this.name, this.age);
  
  void sayHello() {
    print('Hello, I am $name');
  }
}

// Asynchronous Programming
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Data fetched!';
}
```

## Data Types

| Type | Description | Example |
|------|-------------|---------|
| `int` | Integer numbers | `42` |
| `double` | Floating-point numbers | `3.14` |
| `String` | Text | `'Hello'` |
| `bool` | Boolean values | `true` |
| `List` | Ordered collection | `[1, 2, 3]` |
| `Map` | Key-value pairs | `{'key': 'value'}` |
| `Set` | Unique collection | `{1, 2, 3}` |

## Control Flow

```dart
// If-else
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}

// For loops
for (var i = 0; i < 5; i++) {
  print(i);
}

// For-in loops
for (var name in names) {
  print(name);
}

// While loops
while (condition) {
  // code
}

// Switch statements
switch (value) {
  case 1:
    // code
    break;
  case 2:
    // code
    break;
  default:
    // code
}
```

## Null Safety

Dart's null safety helps prevent null reference errors:

```dart
// Non-nullable by default
String name = 'Dart'; // Cannot be null
name = null; // Compile error

// Nullable types
String? nullableName; // Can be null
nullableName = null; // OK

// Null-aware operators
String? name;
String greeting = name ?? 'Guest'; // Use 'Guest' if name is null
String length = name?.length.toString() ?? '0'; // Safe navigation
```

## Resources

- [Official Documentation](https://dart.dev/guides)
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [Dart API Reference](https://api.dart.dev/)
- [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style) 