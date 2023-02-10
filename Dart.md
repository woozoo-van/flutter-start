# Dart Start

## Variables

### 기본 변수
- 기본 ```var```사용
- 타입을 명시적으로 선언하는 방법
```dart
String name = 'Bob';
```
- 변수가 단일 유형으로 제한되니 않는 경우 ```Object```, ```dynamic``` 필요
```dart
Object name = 'Bob';
dynamic wow = 2;
```
### 기본 값
Dart는 모든 것이 객체, 초기는 null
```dart
int? lineCount;
assert(lineCount == null);
```

### Late 변수
- 선언 후 초기화되는 null 허용X 변수
- 변수를 나중에 초기화
뱐수를 사용하기 전에 선언하고 활용할때, 오류가 발생할 수 있다. ```late``` 키워드를 사용해 수정할 수 있다. 
```late``` 변수는 변수가 처음 사용될 때 초기화가 진행된다. 이는 장점이 있다.
- 변수가 필요하지 않을 수 있으며, 초기화하는 데 비용이 많이 든다.
- 인스턴스 변수를 초기화하고 있으면 이 인스턴스에대한 접근 권한이 필요하다. 

Example
```dart
late String temperature = readThermometer(); // Lazily initialized.
```

### Final, const
변수를 변경하지 않으려면 ```final``` 추가하여 사용. 
```dart
final name = 'Bob';
final String nickname = 'Bobby';
```

컴파일 타임 상수를 ```const```를 사용한다. 
```const```변수가 class 레벨에 있다면, ```static const```로 표현된다. 
문자열 리터럴, 상수, 산술 연산 결과와 같은 컴파일 타임 상수로 설정한다. 

```const```는 상수를 정의하기 위한 키워드가 아니다. 다른 변수값 또는 생성자 선언에서도 사용할 수 있다.
```dart
var foo = const [];
final bar = const [];
const baz = []; // == const []
```
const를 중복해서 사용하지 말자..

const는 컴파일 타임 상수이기 때문에, 당연히 값을 변경할 수 있다.
```dart
foo = [1, 2, 3]; // Was const []
```

함정은 컴파일 변수에는 값을 바꿀 수 없다.
```dart
baz = [42]; // Error: Constant variables can't be assigned a value.
```

상수 선언시, 타입 체크와 캐스트, 컬렉션 if 그리고 spread operator를 사용할 수 있다. 

```dart
const Object i = 3; // Where i is a const Object with an int value...
const list = [i as int]; // Use a typecast.
const map = {if (i is int) i: 'int'}; // Use is and collection if.
const set = {if (list is List<int>) ...list}; // ...and a spread.
```

### 내장 타입
- Numbers (int, double)
- Strings (String) - UTF-16 
- Booleans (bool)
- Lists (List, also known as arrays)
- Sets (Set)
- Maps (Map)
- Runes (Runes; often replaced by the characters API)
- Symbols (Symbol)
- The value null (Null)



## Data type 

---

## 참고 자료
- [공홈](https://dart.dev/guides/language/language-tour#variables)