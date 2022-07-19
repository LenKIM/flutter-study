dynamic name = '기정규';



```dart
String name = '김정규';
print(name);
// name 은 Null 이 될 수 없다.

String? name2 = '김정규2';
print(name2);
// name 은 Null 이 될 수 있다.
print(name2!); // Null이 절대 아니다 라고 단언한다.

```



## final, const

```dart
void main() {
  final String name = '김정규';
  print(name);
  // final 을 사용할 경우 변경할 수 없다
  
  const String name2 = '김정규2';
  
  print(name2);
  
  // const도 바꿀 수 없다.
  
  // 차이점은 var 키워드를 생략할 수 있다.
  
  final name3 = '김정규';
  print(name3);
  
  const name4 = '김정규2';
  print(name4);
}

```



## dateTime

```dart
void main() {
  final DateTime now = DateTime.now();
  
  print(now);
  
  const DateTime now2 = DateTime.now();
	//안된다. 빌드 시점에 타입을 알아야 한다.  
  print(now2);
}

```



## math

```dart
void main() {
  int number = 2;
  
  print(number);
  print(number + 2);
  print(number - 2);
  print(number * 2);
  print(number / 2);
  
  print('----------------------');
  print(number % 2);
  print(number % 3);
  
  print(number);
  
  print('----------------------');
  
  number++;
  
  print(number);
  
  number--;
  
  print(number);
  
  
  double number2 = 4.0;
  
  print(number2);
  
  number2 += 1;
  
  print(number2);
  
  number2 *= 2;
  
  print(number2);
  
  number2 /= 2;
  
  print(number2);
}

```

```dart
void main() {
  double? number = 4.0;
  
  print(number);
  
  number = 2.0;
  
  print(number);
  
  number = null;
  
  print(number);
  
  number ??=3.0; // 만약에 오른쪽 값이 null 이면 왼쪽 값으로 바꿔라.
  print(number);
}
```



```dart
void main() {
  int number1 = 1;
  int number2 = 2;

  print(number1 is int);
  print(number1 is String);
  
  print(number2 is! int);
  print(number2 is! String);
  
}
```



```dart
void main() {
  bool result = 12 > 10 && 1 > 0;
  print(result); 
}
```



```dart
void main() {
  //List
  // 리스트

  List<String> people = ['김씨', '박씨'];
  List<int> people2 = [1, 2, 3, 4];

  print(people);
  print(people2);
  
  //index의 순서는 0부터 시작한다
  print(people[0]);
  print(people[1]);
  
  print(people[100]);
}

```



```dart
void main() {
  // Map
  // Key / Value

  Map<String, String> dictionary = {'Harry Potter': '해리포터', 'Ron': '론'};

  print(dictionary);

  Map<String, bool> isHarryPorter = {'Harry Potter': true, 'Ron': true};

  print(isHarryPorter);

  isHarryPorter.addAll({'Spiderman': false});

  print(isHarryPorter['Spiderman']);

  isHarryPorter['Hulk'] = false;
  print(isHarryPorter);
}
```



```dart
void main() {
  // for loop
  int total = 0;
  
  List<int> numbers = [1,2,3,4,5,6];
  
  for(int i = 0; i < numbers.length; i++ ){
    total += numbers[i];
  }
  
  print(total);
  
  total = 0;
  for(int number in numbers){
    print(number);
  }
}
```

```dart
enum Status {
  
  approval,
  pending,
  rejected
}
void main() {
  Status status = Status.approval;
  
  if(status == Status.approval) {
    print('승인');
  } else if(status == Status.pending) {
    print('대기');
  } else {
    print('거절');
  };
}

```

## 함수 작성

```dart
void main() {
  addNumbers();
}

// 세개의 숫자(x,y,z)를 더하고 짝수인지 홀수인지 알려주는 함수
addNumbers() {
  int x = 10;
  int y = 20;
  int z = 30;

  int sum = x + y + z;
  print('x + $x');
  print('y + $y');
  print('z + $z');
  
  if(sum % 2 == 0){
    print("짝수");
  } else {
    print("홀수");
  }
}
```



```dart
void main() {
  addNumbers(10, 20, 30);
  addNumbers2(10);
  
  addNumbers3(x:11, y:12);
  addNumbers4(10, y:22, z:33);
  
}

// 세개의 숫자(x,y,z)를 더하고 짝수인지 홀수인지 알려주는 함수
addNumbers(int x, int y, int z) {
  int sum = x + y + z;
  print('x + $x');
  print('y + $y');
  print('z + $z');
  
  if(sum % 2 == 0){
    print("짝수");
  } else {
    print("홀수");
  }
}

// positional parameter - 있어도 되고 없어도 되는 파라미터
// optional paramet - 있어도 되고 없어도 되는 파라미터
addNumbers2(int x, [int y = 20, int z= 30]) {
  int sum = x + y + z;
  print('x + $x');
  print('y + $y');
  print('z + $z');
  
  if(sum % 2 == 0){
    print("짝수");
  } else {
    print("홀수");
  }
}

// positional parameter - 있어도 되고 없어도 되는 파라미터
// optional paramet - 있어도 되고 없어도 되는 파라미터
// named parameter
addNumbers3({
  required int x,
  required int y,
  int z = 30,
}) {
  int sum = x + y + z;
  print('x + $x');
  print('y + $y');
  print('z + $z');
  
  if(sum % 2 == 0){
    print("짝수");
  } else {
    print("홀수");
  }
}

addNumbers4(int x, {
  required int y,
  int z = 30,
}) {
  int sum = x + y + z;
  print('x + $x');
  print('y + $y');
  print('z + $z');
  
  if(sum % 2 == 0){
    print("짝수");
  } else {
    print("홀수");
  }
}


void main() {
  print(addNumbers(10, 20, 30));
}
// 세개의 숫자(x,y,z)를 더하고 짝수인지 홀수인지 알려주는 함수
int addNumbers(int x, int y, int z) => x + y + z;

```



```dart
void main() {
  Operation operation = add;
  
  int result = operation(10,20,30);
  
  print(result);
  
  operation = subtract;
  
  int result2 = operation(10,20,30);
  
  print(result2);
  
  int result3 = calculate(30,40,50, add);
  print(result3);
  
  int result4 = calculate(30,40,50, subtract);
  print(result4);
}


typedef Operation = int Function(int x, int y, int z);

// 더하기
int add(int x, int y, int z) => x + y + z;

// 빼기
int subtract(int x, int y, int z) => x - y - z;


int calculate(int x, int y, int z, Operation operation) {
  return operation(x,y,z);
}
```

