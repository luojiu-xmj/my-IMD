 ![Tux, the Linux mascot](https://flutter.dev/assets/flutter-lockup-1caf6476beed76adec3c477586da54de6b552b2f42108ec5bc68dc63bae2df75.png)
 # Flutter —— Beautiful native apps in record time
>Flutter is Google’s UI toolkit for building beautiful, natively compiled applications for [mobile](https://flutter.dev/docs), [web](https://flutter.dev/web), and [desktop](https://flutter.dev/desktop) from a single codebase.

- Design beautiful apps
- Create faster apps
- Target mobile, web, & desktop apps
- Productively build apps

***Fast Development***
>Paint your app to life in milliseconds with Stateful Hot Reload. Use a rich set of fully-customizable widgets to build native interfaces in minutes.
>Flutter's *hot reload* helps you quickly and easily experiment, build UIs, add features, and fix bugs faster. Experience sub-second reload times without losing state on emulators, simulators, and hardware.
>[learn more](https://flutter.dev/docs/development/tools/hot-reload)

***Expressive and Flexible UI***
>Quickly ship features with a focus on native end-user experiences. Layered architecture allows for full customization, which results in incredibly fast rendering and expressive and flexible designs.
>Delight your users with Flutter's built-in beautiful Material Design and Cupertino (iOS-flavor) widgets, rich motion APIs, smooth natural scrolling, and platform awareness.
>[Browse the widget catalog](https://flutter.dev/docs/development/ui/widgets/catalog)

***Native Performance***
>Flutter’s widgets incorporate all critical platform differences such as scrolling, navigation, icons and fonts, and your Flutter code is compiled to native ARM machine code using [Dart's native compilers](https://dart.dev/platforms).
Flutter’s widgets incorporate all critical platform differences such as scrolling, navigation, icons and fonts to provide full native performance on both iOS and Android.
[Examples of apps built with Flutter](https://flutter.dev/showcase)
Demo design inspired by Aurélien [Salomon](https://dribbble.com/aureliensalomon)'s [Google Newsstand Navigation Pattern](https://dribbble.com/shots/2940231-Google-Newsstand-Navigation-Pattern)

***Learn from developers***
>Watch these videos to learn from Google and developers as you build with Flutter.
[Visit our YouTube playlist](https://www.youtube.com/flutterdev)

***Try Flutter in your browser***
```sh
import 'package:flutter/material.dart';

void main() async {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        body: MyApp(),
      ),
    ),
  );
}

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp>
    with SingleTickerProviderStateMixin {
  AnimationController controller;
  Animation<double> animation;

  @override
  void initState() {
    super.initState();

    controller = AnimationController(
      duration: Duration(seconds: 1),
      vsync: this,
    );

    animation = CurvedAnimation(
      parent: controller,
      curve: Curves.easeInOutCubic,
    ).drive(Tween(begin: 0, end: 2));
  }

  @override
  void dispose() {
    controller.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () {
        controller
          ..reset()
          ..forward();
      },
      child: RotationTransition(
        turns: animation,
        child: Stack(
          children: [
            Positioned.fill(
              child: FlutterLogo(),
            ),
            Center(
              child: Text(
                'Click me!',
                style: TextStyle(
                  fontSize: 60.0,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```
Want more practice? [Try a codelab](https://flutter.dev/codelabs).


  
