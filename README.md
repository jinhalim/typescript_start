# typescript_start
생활코딩(예습)

typescript란?
 - javascript + 타입 체크  = typescript
 - javascript실행환경 -> typescript 동작 X
 - typescript실행환경 -> javascript 동작 O

 javascript vs typescript
 - javascript : 변수의 데이터 타입을 명확하게 알기 어려음(데이터 안정성 낮음)
 - typescript : 변수의 데이터 타입을 지정하여 수시로 확인 가능(데이터 안정성 높음)

 typescript 사용하는 이유?
 - javascript의 타입 체크 기능을 추가 가능
 - github에서 4번째로 인기있는 언어(트렌드에 맞추어 가는중)

typescript 사용환경!
- 웹 브라우저
https://www.typescriptlang.org/play

- vscode에서 사용하기
  1. node js 설치
  2. `npm install typescript --save-dev`
  3. 프로젝트 초기화 `npx tsc --init`
  ![img](/image/1.png)
  4. 파일 컴파일 `npx tsc` -> 실시간 컴파일 `npx tsc --watch`

typescript 타입 종류!
 - number: 숫자 타입으로, 정수와 실수를 포함합니다.
 - string: 문자열 타입입니다.
 - boolean: 참(true)과 거짓(false)을 나타내는 불리언 타입입니다.
 - null: 값이 없음을 나타내는 타입입니다.
 - undefined: 값이 할당되지 않은 변수의 기본값인 타입입니다.
 
 - object: 객체를 나타내는 타입입니다.
 - array: 동일한 타입의 요소를 가진 배열을 나타내는 타입입니다.
 - tuple: 각 요소가 다른 타입을 가질 수 있는 배열을 나타내는 타입입니다. (TS 전용)
 
 - any: 어떠한 타입이든 할당될 수 있는 타입입니다. (TS 전용)
 - unknown: 타입을 미리 알 수 없는 경우에 사용되는 타입입니다. 이 타입은 안전한 타입 검사를 위해 사용됩니다. (TS 전용)
 - never: 절대 발생하지 않는 값의 타입을 나타냅니다. 예를 들어, 함수가 항상 예외를 발생시키거나 무한 루프를 실행할 때 이 타입을 사용할 수 있습니다. (TS 전용)

 타입 선언 방법
 -  let [변수명]: 타입 
 -  const [상수명]: 타입

Array 타입 선언
 - `let arr1: number[] = [1, 2 , 3];` -> 타입 + []
 - `let arr2: Array = [1, 2 , 3];` -> Array타입

 Tuple 타입 선언
 -  `let tuple: [string, number, boolean] = ['Hello', 42, true];`
 - 각 요소의 타입과 순서가 지정되어 있다.
 - typescript에서만 제공하는 기능

Array vs Tuple
 - Array : 길이 가변적 , 동일한 타입이 요소로 구성
 - Tuple : 길이 고정적 , 각 요소의 타입이 지정되어 있음.(TS에서만 존재) 

객체 타입 선언 방법
 ~~~ts 
 const user: {name: string, age: number} = {
    name: "Ha",
    age : 25
  };
~~~

함수 타입 선언 방법
~~~ts
function add(a: number, b: number): number {
  return a + b;
}
~~~
 -  반환되는 타입은 ()밖에 표시
~~~ts
function greet(name: string, greeting?: string): string {
  if(greeting){
    return `${greeting}, ${name}!`;
  }else {
    return `Hello, ${name}!`;
  }
}
~~~
- greeting? 와 같이 매개변수 뒤에 `?`를 사용하는 경우 선택적으로 import를 결정할 수 있습니다.

Type Aliases란?
 - typescript에서 기존 타입에서 사용자 정의 이름을 부여할수 있는 방법
 - 코드의 가독성 상승 및 복잡한 타입구조 단순화 가능
 - 원시 데이터 타입, Array, Tuple, 객체, 함수등 타입에 적용 가능
~~~ts
type Age = number;
const myAge: Age = 30;
~~~
~~~ts
type UserID = string;
type UserName = string;
type Age = number;

type User = {
  id: UserID;
  name: UserName;
  age: Age;
};

const user: User = {
  id: '1',
  name: 'Ha Lim',
  age: 28
};
~~~