# TIL - Flutter Stack으로 도형 겹치기 UI 만들기
## 배운 내용
Flutter의 Stack과 Positioned 위젯을 활용해서 도형이 겹치는 레이아웃을 구현하는 방법을 배웠다.

기본적으로 Container, Row, Column, 그리고 Stack의 조합으로 UI를 정교하게 구성할 수 있다.
## 코드
```dart
import 'package:flutter/material.dart';

void main() => runApp(const ColorBlockApp());

class ColorBlockApp extends StatelessWidget {
  const ColorBlockApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          child: Stack(
            alignment: Alignment.bottomCenter,
            children: [
              Container(
                width: 200,
                height: 200,
                color: Colors.yellow,
              ),
              Positioned(
                bottom: 100,
                child: Row(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Container(
                      width: 120,
                      height: 100,
                      color: Colors.red,
                    ),
                    Column(
                      children: [
                        Container(
                          width: 80,
                          height: 50,
                          color: Colors.blue,
                        ),
                        Row(
                          children: [
                            Container(
                              width: 40,
                              height: 50,
                              color: Colors.black,
                            ),
                            Container(
                              width: 40,
                              height: 50,
                              color: Colors.orange,
                            ),
                          ],
                        ),
                      ],
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```
## 코드 설명
- Stack: 겹치는 도형 배치를 위해 사용

- Positioned: 상단 도형 그룹을 노란 사각형 위에 정확히 배치

- Row, Column: 파란색 + 검정/주황 도형을 정렬하기 위한 구조
## 실행 결과
![](https://github.com/YOUHEETAE/mygit/blob/main/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202025-04-13%20224420.jpg)
