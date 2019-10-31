# First Flutter App

## Installing Flutter

Setup instructions for:

- [macOS](https://flutter.dev/docs/get-started/install/macos)
- [Windows](https://flutter.dev/docs/get-started/install/windows)
- https://www.youtube.com/watch?v=1ukSR1GRtMU - Youtube video for Windows
- https://www.youtube.com/watch?v=dOBc8nIIXJg - Youtube video for Mac
- I sincerely recommend you follow a Youtube video, because they will go over it in far more detail. If the videos linked aren't sufficient, try searching how to install flutter on windows/mac
- also if you're using linux, you're probably smart enough to google how to do this.

### IDE

Recommended that you either use Android Studio or Visual Studio Code

https://developer.android.com/studio

https://code.visualstudio.com/

For these coding environments, you will need to download and install the plugin for Flutter (Dart too, but that is optional for now)

#### Android Studio

- Preferences > Plugins (macOS) or File > Settings > Plugins 

- search for the Flutter plugin within the repository list and hit install.

https://plugins.jetbrains.com/plugin/9212-flutter

#### Visual Studio Code

Here is the plugin: https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter

or you can download from the plugin store on vs code

## Creating a new Flutter project

Assuming that you’ve installed Flutter and Android Studio/XCode installed, we can go ahead and create a new Flutter project.

We can do this via the Terminal:

```shell
$ flutter create hello_flutter
$ cd hello_flutter
$ code .
```

## Launching the project

https://www.youtube.com/results?search_query=open+flutter+project - once again, I **strongly** recommend you just follow a youtube video from the link above. The setup for Flutter is confusing, and if you can't get it, then we can go over it at our next meeting.

#### VS Code

Hit the “Debug” section of the editor and click “Play” to add a new configuration.

Select “Dart & Flutter” from the dropdown and then choose the editor you’d like to use. We should then see our demo application:

![Hello, Flutter](https://d33wubrfki0l68.cloudfront.net/bb292421e6186b8024767ab442474246907756bf/3c7cb/images/flutter/your-first-flutter-app/flutter-demo.png)

##### 

## Material

Hopefully you have an app's code open. There is sample code pasted in, but it has more moving psrts than we want to worry about right now. Go to lib/main.dart to find the sample code / the main code that we run. Paste in the code below and read the comments, as they explain the purpose of each line.

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        // This is the theme of your application.
        //
        // Try running your application with "flutter run". You'll see the
        // application has a blue toolbar. Then, without quitting the app, try
        // changing the primarySwatch below to Colors.green and then invoke
        // "hot reload" (press "r" in the console where you ran "flutter run",
        // or simply save your changes to "hot reload" in a Flutter IDE).
        // Notice that the counter didn't reset back to zero; the application
        // is not restarted.
        primarySwatch: Colors.blue,
      )
      home: MyHomePage(title: 'Power of'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key key, this.title}) : super(key: key);

  // This widget is the home page of your application. It is stateful, meaning
  // that it has a State object (defined below) that contains fields that affect
  // how it looks.

  // This class is the configuration for the state. It holds the values (in this
  // case the title) provided by the parent (in this case the App widget) and
  // used by the build method of the State. Fields in a Widget subclass are
  // always marked "final".

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      // This call to setState tells the Flutter framework that something has
      // changed in this State, which causes it to rerun the build method below
      // so that the display can reflect the updated values. If we changed
      // _counter without calling setState(), then the build method would not be
      // called again, and so nothing would appear to happen.
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // This method is rerun every time setState is called, for instance as done
    // by the _incrementCounter method above.
    //
    // The Flutter framework has been optimized to make rerunning build methods
    // fast, so that you can just rebuild anything that needs updating rather
    // than having to individually change instances of widgets.
    return Scaffold(
      appBar: AppBar(
        // Here we take the value from the MyHomePage object that was created by
        // the App.build method, and use it to set our appbar title.
        title: Text("HACK"),
      ),
      body: Center(
        // Center is a layout widget. It takes a single child and positions it
        // in the middle of the parent.
        child: Column(
          // Column is also layout widget. It takes a list of children and
          // arranges them vertically. By default, it sizes itself to fit its
          // children horizontally, and tries to be as tall as its parent.
          //
          // Invoke "debug painting" (press "p" in the console, choose the
          // "Toggle Debug Paint" action from the Flutter Inspector in Android
          // Studio, or the "Toggle Debug Paint" command in Visual Studio Code)
          // to see the wireframe for each widget.
          //
          // Column has various properties to control how it sizes itself and
          // how it positions its children. Here we use mainAxisAlignment to
          // center the children vertically; the main axis here is the vertical
          // axis because Columns are vertical (the cross axis would be
          // horizontal).
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'Congrats on your first app!',
            ),
          ],
        ),
      ),
   // This trailing comma makes auto-formatting nicer for build methods.
    );
  }
}

```

------

Additional things to note:

- you can easily change the base design of the app by using CupertinoApp instead of MaterialApp
- look up the role of widgets in flutter apps as it will help you understand the concepts we talk about
- Look up the difference between stateless and stateful widgets and watch a video because it is really confusing