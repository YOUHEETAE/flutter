# TIL: Set과 Map 활용(Dart)
## 배울 내용
Dart에서 Set과 Map을 사용하는 방법을 학습합니다.

중복을 허용하지 않는 Set과 키-값 형태로 데이터를 관리하는 Map의 특징을 이해합니다.

forEach 문법을 통해 콜백 함수를 간단히 사용하는 법을 익힙니다.
## 코드
```dart
void main () {
  var lottoNums = {5, 6, 11, 13, 17, 21};
 // lottoNums.forEach((num){
 //   print(num);
 // });
 // lottoNums.forEach((num) => print(num));
 // lottoNums.forEach(print);
 
  /*lottoNums.remove(6);
  lottoNums.add(9);
  lottoNums.add(9);
 
  print(lottoNums);
 
  print(lottoNums[0]);
  lottoNums[0] = 1;
  print(lottoNums);
  */
  var map = {'한국': '서울', '일본': '도쿄'};
  print(map['한국']);
  map['중국'] = '북경';
  print(map);
 
}
```
## 코드 설명
### 1. Set 사용 예제:

- var lottoNums = {5, 6, 11, 13, 17, 21};

중복 없이 값들을 저장할 수 있는 Set 자료구조를 사용하여 로또 번호를 관리합니다.

- 주석 처리된 forEach 구문들을 통해 각 요소를 출력할 수 있습니다.

- 중복 허용 X, 인덱스로 접근 불가

- remove()와 add()를 사용하여 값을 제거하거나 추가할 수 있습니다.

### 2. Map 사용 예제:

- var map = {'한국': '서울', '일본': '도쿄'};

Map 자료구조를 사용하여 키-값 쌍으로 데이터를 관리합니다.

- map['중국'] = '북경';

새로운 키와 값을 추가할 수 있습니다.

- print(map['한국']);

키를 사용하여 값을 출력합니다.
## 실행 결과
![](https://github.com/YOUHEETAE/mygit/blob/main/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202025-03-31%20230415.jpg)
