# Flutter Installation & Setup

This guide will help you set up Flutter on your development machine and create your first Flutter application.

## System Requirements

- **Operating System**: Windows 10 or later (64-bit), macOS, or Linux
- **Disk Space**: 2.8 GB (does not include disk space for IDE/tools)
- **Tools**: Git for Windows, PowerShell 5.0 or newer

## Installation Steps

### 1. Download Flutter SDK

1. Visit the [Flutter SDK download page](https://docs.flutter.dev/get-started/install)
2. Download the latest stable version for your operating system
3. Extract the downloaded zip file to a desired location (e.g., `C:\src\flutter`)

### 2. Update Your Path

Add Flutter to your PATH environment variable:

```powershell
# For Windows
$env:Path += ";C:\src\flutter\bin"

# For Linux/macOS
export PATH="$PATH:`pwd`/flutter/bin"
```

### 3. Run Flutter Doctor

Run the following command to check for any missing dependencies:

```bash
flutter doctor
```

This will check your environment and display a report of the status of your Flutter installation.

### 4. Install Android Studio

1. Download and install [Android Studio](https://developer.android.com/studio)
2. During installation, make sure to include:
   - Android SDK
   - Android SDK Command-line Tools
   - Android SDK Build-Tools
   - Android Emulator

### 5. Configure Android Studio

1. Open Android Studio
2. Install the Flutter and Dart plugins:
   - Go to File > Settings > Plugins
   - Search for "Flutter"
   - Click "Install"
   - Restart Android Studio

### 6. Create a New Flutter Project

```bash
flutter create my_first_app
cd my_first_app
flutter run
```

## IDE Setup

### Visual Studio Code

1. Install [VS Code](https://code.visualstudio.com/)
2. Install the Flutter extension:
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Search for "Flutter"
   - Click "Install"

### Android Studio/IntelliJ

1. Install the Flutter plugin:
   - Go to File > Settings > Plugins
   - Search for "Flutter"
   - Click "Install"
   - Restart the IDE

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| Flutter command not found | Add Flutter to your PATH |
| Android SDK not found | Install Android Studio and SDK |
| No connected devices | Start an emulator or connect a physical device |
| Gradle build failed | Update Gradle version in `android/build.gradle` |

## Verifying Installation

Run the following commands to verify your installation:

```bash
flutter --version
flutter doctor
flutter devices
```

## Next Steps

1. [Create your first Flutter app](https://flutter.dev/docs/get-started/codelab)
2. [Learn Flutter basics](https://flutter.dev/docs/get-started/learn-more)
3. [Explore Flutter samples](https://flutter.github.io/samples/)

## Resources

- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Flutter Documentation](https://flutter.dev/docs)
- [Flutter GitHub Repository](https://github.com/flutter/flutter)
- [Flutter Community](https://flutter.dev/community) 