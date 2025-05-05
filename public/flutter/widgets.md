# Flutter Widgets

Widgets are the basic building blocks of a Flutter application. Everything in Flutter is a widget, from structural elements like buttons and text to layout elements like rows and columns.

## Basic Widgets

### Text Widget

```dart
Text(
  'Hello, Flutter!',
  style: TextStyle(
    fontSize: 24,
    fontWeight: FontWeight.bold,
    color: Colors.blue,
  ),
)
```

### Container Widget

```dart
Container(
  width: 200,
  height: 200,
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(10),
    boxShadow: [
      BoxShadow(
        color: Colors.grey.withOpacity(0.5),
        spreadRadius: 2,
        blurRadius: 5,
      ),
    ],
  ),
  child: Center(
    child: Text('Container'),
  ),
)
```

### Button Widgets

```dart
// Elevated Button
ElevatedButton(
  onPressed: () {
    // Handle button press
  },
  child: Text('Elevated Button'),
)

// Text Button
TextButton(
  onPressed: () {
    // Handle button press
  },
  child: Text('Text Button'),
)

// Icon Button
IconButton(
  onPressed: () {
    // Handle button press
  },
  icon: Icon(Icons.favorite),
)
```

## Layout Widgets

### Row and Column

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Icon(Icons.star),
    Icon(Icons.star),
    Icon(Icons.star),
  ],
)

Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    Text('First'),
    Text('Second'),
    Text('Third'),
  ],
)
```

### Stack

```dart
Stack(
  children: [
    Container(
      width: 200,
      height: 200,
      color: Colors.blue,
    ),
    Positioned(
      top: 20,
      left: 20,
      child: Text('Stacked Text'),
    ),
  ],
)
```

### Expanded and Flexible

```dart
Row(
  children: [
    Expanded(
      flex: 2,
      child: Container(color: Colors.red),
    ),
    Flexible(
      flex: 1,
      child: Container(color: Colors.blue),
    ),
  ],
)
```

## Input Widgets

### TextField

```dart
TextField(
  decoration: InputDecoration(
    labelText: 'Username',
    hintText: 'Enter your username',
    border: OutlineInputBorder(),
  ),
  onChanged: (value) {
    // Handle text changes
  },
)
```

### Checkbox and Switch

```dart
Checkbox(
  value: isChecked,
  onChanged: (value) {
    setState(() {
      isChecked = value!;
    });
  },
)

Switch(
  value: isSwitched,
  onChanged: (value) {
    setState(() {
      isSwitched = value;
    });
  },
)
```

## List Widgets

### ListView

```dart
ListView.builder(
  itemCount: items.length,
  itemBuilder: (context, index) {
    return ListTile(
      title: Text(items[index]),
      onTap: () {
        // Handle item tap
      },
    );
  },
)
```

### GridView

```dart
GridView.builder(
  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 2,
    crossAxisSpacing: 10,
    mainAxisSpacing: 10,
  ),
  itemCount: items.length,
  itemBuilder: (context, index) {
    return Container(
      color: Colors.blue,
      child: Center(
        child: Text(items[index]),
      ),
    );
  },
)
```

## Custom Widgets

### Creating a Custom Widget

```dart
class CustomButton extends StatelessWidget {
  final String text;
  final VoidCallback onPressed;

  const CustomButton({
    required this.text,
    required this.onPressed,
  });

  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: onPressed,
      style: ElevatedButton.styleFrom(
        padding: EdgeInsets.symmetric(horizontal: 20, vertical: 10),
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
      ),
      child: Text(text),
    );
  }
}
```

## Widget Lifecycle

| Widget Type | Lifecycle Methods |
|------------|------------------|
| StatelessWidget | build() |
| StatefulWidget | createState(), initState(), build(), dispose() |

## Best Practices

1. **Widget Composition**: Break down complex UIs into smaller, reusable widgets
2. **const Constructors**: Use const constructors for widgets that don't change
3. **State Management**: Choose appropriate state management based on complexity
4. **Performance**: Use const widgets and avoid unnecessary rebuilds
5. **Accessibility**: Include semantic labels and proper contrast

## Resources

- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Flutter Widget of the Week](https://www.youtube.com/playlist?list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG)
- [Flutter Widget Index](https://docs.flutter.dev/development/ui/widgets) 