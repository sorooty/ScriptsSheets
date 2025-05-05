# Flutter State Management

State management is a crucial aspect of Flutter development. It determines how data flows through your application and how UI updates in response to data changes.

## Types of State

1. **Ephemeral State**: Local state that can be contained in a single widget
2. **App State**: State that needs to be shared across multiple widgets

## Built-in State Management

### setState

```dart
class CounterWidget extends StatefulWidget {
  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Counter: $_counter'),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

## Popular State Management Solutions

### Provider

```dart
// Define a model
class CounterModel extends ChangeNotifier {
  int _count = 0;
  int get count => _count;

  void increment() {
    _count++;
    notifyListeners();
  }
}

// Create a provider
void main() {
  runApp(
    ChangeNotifierProvider(
      create: (context) => CounterModel(),
      child: MyApp(),
    ),
  );
}

// Use the provider
class MyWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Consumer<CounterModel>(
      builder: (context, counter, child) {
        return Text('Count: ${counter.count}');
      },
    );
  }
}
```

### Bloc

```dart
// Events
abstract class CounterEvent {}
class IncrementEvent extends CounterEvent {}

// States
abstract class CounterState {}
class CounterInitial extends CounterState {
  final int count;
  CounterInitial(this.count);
}

// Bloc
class CounterBloc extends Bloc<CounterEvent, CounterState> {
  CounterBloc() : super(CounterInitial(0)) {
    on<IncrementEvent>((event, emit) {
      emit(CounterInitial(state.count + 1));
    });
  }
}

// Usage
BlocProvider(
  create: (context) => CounterBloc(),
  child: BlocBuilder<CounterBloc, CounterState>(
    builder: (context, state) {
      return Text('Count: ${state.count}');
    },
  ),
)
```

### Riverpod

```dart
// Create a provider
final counterProvider = StateProvider<int>((ref) => 0);

// Use the provider
class MyWidget extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final count = ref.watch(counterProvider);
    
    return Column(
      children: [
        Text('Count: $count'),
        ElevatedButton(
          onPressed: () => ref.read(counterProvider.notifier).state++,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

### GetX

```dart
// Controller
class CounterController extends GetxController {
  var count = 0.obs;

  void increment() => count++;
}

// Usage
class MyWidget extends StatelessWidget {
  final controller = Get.put(CounterController());

  @override
  Widget build(BuildContext context) {
    return Obx(() => Text('Count: ${controller.count}'));
  }
}
```

## State Management Comparison

| Solution | Learning Curve | Boilerplate | Performance | Scalability |
|----------|---------------|-------------|-------------|-------------|
| setState | Low | Low | Good | Poor |
| Provider | Medium | Medium | Good | Good |
| Bloc | High | High | Excellent | Excellent |
| Riverpod | Medium | Medium | Excellent | Excellent |
| GetX | Low | Low | Good | Good |

## Best Practices

1. **Choose the Right Solution**: Consider app complexity and team experience
2. **Keep State Minimal**: Only store what's necessary
3. **Immutable State**: Use immutable objects for state
4. **Separation of Concerns**: Keep business logic separate from UI
5. **Testing**: Write tests for state management logic

## Common Patterns

### Singleton Pattern

```dart
class AppState {
  static final AppState _instance = AppState._internal();
  factory AppState() => _instance;
  AppState._internal();

  // State properties
  int counter = 0;
}
```

### Repository Pattern

```dart
abstract class DataRepository {
  Future<List<Data>> fetchData();
}

class DataRepositoryImpl implements DataRepository {
  @override
  Future<List<Data>> fetchData() async {
    // Implementation
  }
}
```

## Resources

- [Flutter State Management](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Provider Package](https://pub.dev/packages/provider)
- [Bloc Package](https://pub.dev/packages/flutter_bloc)
- [Riverpod Package](https://pub.dev/packages/flutter_riverpod)
- [GetX Package](https://pub.dev/packages/get) 