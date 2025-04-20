# Flutter TIL: 위젯의 생명주기와 Stack 구조 동작 흐름
## 1. Flutter 위젯의 기본 구조
```dart
class MyWidget extends StatefulWidget {
  @override
  _MyWidgetState createState() => _MyWidgetState();
}

class _MyWidgetState extends State<MyWidget> {
  @override
  void initState() {
    super.initState();
     print('🟢 initState');
  }

  @override
  Widget build(BuildContext context) {
    print('🟡 build');
    return Scaffold(
      appBar: AppBar(title: Text("My Widget")),
      body: Center(child: Text("Hello")),
    );
  }

  @override
  void dispose() {
    print('🔴 dispose');
    super.dispose();
  }
}
```
## 2. 라이프사이클 메서드 설명
                                                             
### initState()	 

- 위젯이 최초로 생성될 때 1회 호출	

- 초기화 작업(애니메이션, 컨트롤러 생성 등)에 사용

### build()	                     

- 위젯이 그려질 때마다 호출됨	      

- UI를 그릴 때마다 호출됨 (setState() 호출 시 포함)

### dispose()	                       

- 위젯이 사라질 때 호출됨	                

- 자원 해제, 리스너 제거 등에 사용
## 3. Navigator Stack에서 push/pop 시 메서드 호출 흐름
### ▶ 첫 화면 (Page1)
```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => Page2()),
);
```
🟢 Page2가 생성되면서:

- Page2: initState() → build() 호출됨

- Page1: 그대로 있음 (위에 덮인 상태)
### ◀ 뒤로가기 (pop)
```dart
Navigator.pop(context);
```
🔴 Page2가 종료되면서:

- Page2: dispose() 호출됨

- Page1: 다시 보이지만, 이미 살아있던 상태 → initState() 안 불림, build()는 다시 호출될 수 있음 (상황에 따라)
## 4. 출력 흐름
### 첫 진입 시 (Page1 → Page2)

Page1: 🟢 initState

Page1: 🟡 build

Page2: 🟢 initState

Page2: 🟡 build

### pop() 시 (Page2 → Page1)

Page2: 🔴 dispose

Page1: 🟡 build (다시 그려지는 경우)
