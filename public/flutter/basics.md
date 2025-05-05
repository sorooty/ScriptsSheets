# Introduction to Flutter

Flutter is an open-source UI software development kit created by Google. It is used to develop cross-platform applications for Android, iOS, Linux, macOS, Windows, Google Fuchsia, and the web from a single codebase.

## Key Features

- **Cross-platform Development**: Write once, run anywhere
- **Hot Reload**: See changes instantly without rebuilding
- **Rich Widget Library**: Extensive collection of pre-built widgets
- **Dart Programming Language**: Modern, object-oriented language
- **Customizable UI**: Complete control over every pixel
- **High Performance**: Native compilation and optimized rendering

## Basic Flutter App Structure

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

## Widget Tree

Flutter apps are built using a widget tree structure:

```
MaterialApp
└── Scaffold
    ├── AppBar
    ├── Center
    │   └── Column
    │       ├── Text
    │       └── Text
    └── FloatingActionButton
```

## Common Widgets

| Widget | Description |
|--------|-------------|
| `Container` | A box that can be decorated with a background, border, and shadow |
| `Row` | A horizontal array of children |
| `Column` | A vertical array of children |
| `Text` | A run of text with a single style |
| `Image` | A widget that displays an image |
| `Icon` | A graphical icon widget |
| `Button` | A clickable button widget |

## State Management

Flutter provides several ways to manage state:

1. **setState()**: For simple state management
2. **Provider**: For dependency injection and state management
3. **Bloc**: For complex state management
4. **Riverpod**: For flexible state management
5. **GetX**: For reactive state management

## Resources

- [Official Documentation](https://flutter.dev/docs)
- [Flutter Gallery](https://gallery.flutter.dev/)
- [Flutter Samples](https://flutter.github.io/samples/)
- [Flutter Cookbook](https://flutter.dev/docs/cookbook) 