# Hello World - Flutter 프로젝트

이 프로젝트는 Flutter를 사용하여 만든 간단한 "Hello World" 애플리케이션입니다.

## 📌 프로젝트 구조

hello_world/ 

│── android/ 

│── ios/

│── lib/

│ &nbsp; &nbsp; &nbsp; &nbsp;├── main.dart 

│── test/ 

│── pubspec.yaml 

│── README.md 

## 📝 main.dart 코드

```JAVA
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

        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: 'Flutter Demo'),
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

        backgroundColor: Theme.of(context).colorScheme.inversePrimary,

        title: Text(widget.title),
      ),
      body: Center(

        child: Column(

          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text('Hello World'),
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
## 🎯 주요기능

- Hello World 텍스트 표시: 앱 실행 시 화면 중앙에 "Hello World" 텍스트가 표시됩니다.

- 카운터 증가 기능: Floating Action Button을 누르면 숫자가 증가합니다.

## 📜 실행결과

![](https://github.com/YOUHEETAE/mygit/blob/main/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202025-03-16%20201715.jpg)
