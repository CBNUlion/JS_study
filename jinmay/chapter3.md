# Chapter3 리터럴과 변수, 상수, 데이터 타입

> 변수, 상수, 리터럴에 대하 알아보자

## 3.1 변수와 상수

**변수**는 변할 수 있는 값이며, **상수**는 변할 수 없는 값이다. ES5 까지는 var를 사용해서 변수 또는 상수를 선언했지만 ES6에 let과 const가 등장했으며 각각 변수와 상수를 선언할때 사용한다. **그리고 변수는 한 번만 선언 할 수 있다.**

```javascript
let currentTempC = 22;
const AGE = 19;
```

반드시 초기값을 지정할 필요는 없다. **변수 선언시 초기값이 없다면 undefined가 할당된다.**

## 3.2 변수와 상수 중 어떤 것을 사용할까?

**가능한 상수를 사용하자.**

먼저 상수를 사용해보고 값이 바뀌는 게 자연스럽다면 그 때 변수로 바꾸어 사용하는 편이 낫다.

## 3.3 식별자 이름

- 글자, 달러(\$), 밑줄(\_\)로 시작해야 한다
- 글자, 숫자, 달러 기호, 밑줄만 쓸 수 있다
- 유니코드 문자 사용 가능
- 예약어 불가

## 3.4 리터럴

**리터럴은 값을 프로그램 안에서 직접 지정하는 걸 의미한다.** 리터럴은 값을 만드는 방법 중 하나이다.

리터럴과 식별자의 차이를 이해해야한다.

```javascript
let room1 = "conference_room";
```

위의 코드에서 room1는 변수를 가리키는 식별자이다. 그리고 'conference_room'은 문자열 리터럴인 동시에 room1의 값 이다. 자바스크립트는 따옴표를 통해 식별자와 리터럴을 구분한다!!

## 3.5 원시 타입과 객체

자바스크립트의 값은 원시 값(primitive)또는 객체(object)이다. 원시 타입은 불변(immutable)한 특성을 가지고 있다.

```javascript
let str = "javascript";
str = "python";
```

**하지만 불변성이라는 말이 변수의 값이 바뀔 수 없다는 건 아니다.**

원시 타입과 객체 타입에 해당하는 데이터 타입을 아래와 같다.

#### 원시 타입

- 숫자
- 문자열
- 불리언
- null
- undefined
- 심볼(symbol)

#### 객체 타입

- Array
- Date
- RegExp
- Map과 WeakMap
- Set과 WeakSet

## 3.6 숫자

자바스크립트는 실제 숫자의 근사치를 저장할 때 IEEE-764 배정도 부동소수점 숫자 형식을 사용한다. 더블(double)이라고 부른다. **숫자형 데이터 타입은 더블 하나이다.**

## 3.7 문자열

**자바스크립트의 문자열은 유니코드 텍스트이다.** 문자열 리터럴에는 작은따옴표, 큰따옴표, 백틱을 사용하며, 백틱은 ES6에서 도입한 문법으로 템플릿 문자열에서 사용된다.

## 3.8.1 템플릿 문자열

ES6 이전의 자바스크립트에서는 문자열 안에서 값을 사용하는 방법이 꽤 까다로웠다.

```javascript
let age = 14;
console.log("my age is " + age);
```

위와 같이 문자열 병합을 통해서 사용했다. ES6에서는 문자열 템플릿 기능을 도입해 아래와 같이 사용할 수 있다.

```javascript
let age = 15;
console.log(`Hello, I am ${age} years old`);
```

### 3.8.2 여려 줄 문자열

소스 코드에서 문자열을 여러 행에 나눠 써야 할 때 문자열 병합을 사용하는 것이 더 좋을 것 같다. 문자열 보간을 이용하거나 템플릿 문자열 기능을 사용하자.

### 3.8.3 숫자와 문자열

숫자를 따옴표 안에 넣으면 **문자열**이 된다.

```javascript
const result1 = 3 + "30"; // 330
const result2 = 3 * "30"; // 90
```

데이터 타입에 조심하자.

## 3.9 불리언

true와 false가 있다.

## 3.10 심볼

ES6에서 유일한 토큰을 나타내기 위해 도입한 새로운 데이터 타입이다. 심볼은 항상 유일하다. 객체는 모두 유일한데 항상 유일하다는 점을 제외하면 심볼은 원시 값의 특징을 모두 가지고 있어서 확장성 있는 코드를 만들 수 있다.

```javascript
const RED = Symbol("The color of a sunset!");
const ORANGE = Symbol("The color of a sunset!");
RED === ORANGE;
```

## null과 undefined

**변수를 상자라고 가정한다면, 상자에 뭘 넣을지 안 정했으면 undefined. 상자에 아무것도 담지 않기로 했다면 null. 상자에 숫자만 담기로 했는데 숫자가 아니라면 NaN이라고 생각하자.**

## 3.12 객체

원시 타입은 단 하나의 값만 나타낼 수 있고 불변이지만, 객체는 여러 개의 값을 담을 수도 있고 변할 수도 있다. 객체의 본질은 값을 담는 컨테이너이다. **객체는 primitive 타입이 아닌 점에 주의하자.**

```javascript
const obj = {};
```

객체의 내용물을 프로퍼티(property) 또는 멤버(member)라고 부른다. 객체의 프로퍼티는 키와 값으로 구성된다(key: value) key는 반드시 문자열 또는 심볼이어야 하며, 값은 상관없다.

```javascript
obj.color = "red";
```

멤버 접근 연산자를 통해서 새로운 프로퍼티를 추가했다. 객체의 프로퍼티에 접근할 때 멤버 접근 연산자(.)와 계산된 멤버 접근 연산자([])를 사용할 수 있는데 중요한 차이점이 있다.

프로퍼티 이름에 유효한 식별자를 써야지 멤버 접근 연산자(.)를 사용할 수 있으며, 프로퍼티 이름에 유요한 식별자가 아닌 경우 계산된 멤버 접근 연산자([])를 써야만한다.

```javascript
obj["not an id"] = 3;
obj; // Object { color: "red", "not an id": 3 }
```

color 프로퍼티의 값을 변경해보자.

```javascript
obj.color = "pink";
obj; // Object { color: "pink", "not an id": 3 }
```

멤버 접근 연산자를 통해서 color 프로퍼티의 값을 변경했다. 헷갈리지 말아야 할 것이 있다면, obj의 color 프로퍼티를 변경했지만 같은 객체를 가리키고 있다는 것이다. **다시 말해 obj는 같은 객체를 가리리고 있고, 바뀐 것은 객체의 프로퍼티인 것이다.**

또한 객체에는 함수도 담을 수 있다

```javascript
obj.speak = function() {
  return "hello";
};
obj; // Object { color: "pink", "not an id": 3, speak: speak() }
```

객체의 함수 호출은 아래와 같이 한다

```javascript
obj.speak(); // 'hello'
```

## 3.13 Number, String, Boolean 객체

Number, String, Boolean 객체에는 두 가지 목적이 있다

1. Number.INFINITY와 같은 특별한 값을 사용하기 위해
2. 함수의 형태로 기능을 제공하기 위해

아래의 예제를 살펴보자

```javascript
const s = "hello";
s.toUpperCase(); // 'HELLO'
```

s는 마치 함수 프로퍼티를 가진 객체처럼 보인다. 하지만 'hello'라는 문자열을 할당한 것에서 알 수 있듯이 s는 원시 문자열 타입이다. 이와 같이 작동한 이유는 자바스크립트가 일시적으로 String 객체를 만들었기 때문이다. 이 임시 객체에 toUpperCase() 함수가 있는 것이고 함수를 호출 한 뒤에 바로 임시 객체를 파괴한다.

s가 객체가 아닌 것을 보기 위해 아래의 코드를 살펴보자

```javascript
s.rating = 3;
s.rating; // undefined
```

조금 전에 생성한 문자열 s에 rating 프로퍼티를 할당한 것처럼 보인다. 하지만 사실은 임시적인 String 객체에 rating 프로퍼티를 할당한 것이며 임시 객체는 즉시 파괴되므로 s.rating의 값이 undefined가 되는 것이다.

## 3.14 배열

자바스크립트의 배열은 특수한 객체이다. 아래와 같은 특징이 있다.

- 배열 크기는 고정되지 않는다. 언제든 요소 추가와 삭제가 가능하다
- 요소의 데이터 타입을 가리지 않는다. 여러 타입이 하나의 배열에 있을 수 있다.
- 배열 요소는 0부터 시작한다.

## 3.20 요약

- 자바스크립트에는 문자열, 숫자, 불리언, null, undefined, 심볼의 여섯 가지 원시 타입과 객체 타입이 있다
- 자바스크립트의 모든 숫자는 배정도 부동소수점 숫자(더블)이다
- 배열은 특수한 객체이며, 객체와 마찬가지로 매우 강력하고 유연한 데이터 타입이다