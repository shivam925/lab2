# lab 2 Prepared by Surjoo Yogheshwar
## Task 1
# Figma to Flutter App Documentation

This documentation guides you through the process of transitioning from a Figma design to a Flutter app with a scenario of moving from Screen 1 to Screen 2 upon clicking a button.

## Step 1: Design in Figma

1. Open Figma and design your screens. Create two frames, one for Screen 1 and one for Screen 2.
2. Add components, buttons, and any other elements you want on each screen.
3. Ensure to name your layers and frames appropriately for easy reference.

## Step 2: Install Figma Flutter plugin

1. Open Figma and go to the "Community" tab.
2. Search for the "Flutter" plugin and install it.
3. Select the layers you want to export to Flutter and use the Flutter plugin to generate code snippets.

## Step 3: Set Up a Flutter Project

1. Open your terminal and navigate to the directory where you want to create your Flutter project.
2. Run the following commands to create a new Flutter project:

    ```bash
    flutter create your_project_name
    cd your_project_name
    ```

## Step 4: Add Dependencies

1. Open your `pubspec.yaml` file and add dependencies for any required packages, such as navigation:

    ```yaml
    dependencies:
      flutter:
        sdk: flutter
      cupertino_icons: ^0.1.3
      # Add any other dependencies you need
    ```

    Run `flutter packages get` to install the dependencies.

## Step 5: Implement Navigation

1. Open the `lib/main.dart` file and set up the initial structure:

    ```dart
    import 'package:flutter/material.dart';

    void main() {
      runApp(MyApp());
    }

    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Screen1(),
        );
      }
    }
    ```

2. Create two separate Dart files for Screen1 and Screen2:

    ```dart
    // screen1.dart
    import 'package:flutter/material.dart';
    import 'screen2.dart';

    class Screen1 extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text('Screen 1'),
          ),
          body: Center(
            child: ElevatedButton(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => Screen2()),
                );
              },
              child: Text('Go to Screen 2'),
            ),
          ),
        );
      }
    }
    ```

    ```dart
    // screen2.dart
    import 'package:flutter/material.dart';

    class Screen2 extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text('Screen 2'),
          ),
          body: Center(
            child: Text('Welcome to Screen 2!'),
          ),
        );
      }
    }
    ```

## Step 6: Run Your App

1. Save your changes and run your app using:

    ```bash
    flutter run
    ```

Your Flutter app should launch, and you can navigate from Screen 1 to Screen 2 by clicking the button.


