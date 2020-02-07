# typescript_study
Create Blockchain with Typescript

Typescript란 Javascript의 superset이다

Typescript는 모두 자바스크립트로 컴파일 과정이 필요하다.

Javascript는 엄격한 규칙이 없어 사용하기 쉽다.

그러나 큰프로젝트를 하거나 팀으로 일하거나 버그를 최소화 하고 싶을때 위의 장점은 단점이 된다.

Typescript를 사용하면 언어가 예측 가능하고 읽기 쉬워 진다.

tsconfig.json -> ts가 어떻게 js로 변환할지 옵션설정

tsc 명령어 -> ts파일에 있는 코드를 컴파일해서 index.js, index,js.map 파일을 생성

node.js는 ts를 이해하지 못하기 때문에 JS로 컴파일 해주어야 한다.

Typescript는 Typed 언어 어떤 종류의 변수와 데이터인지 설정을 할 수 있다.

그래서 코드를 읽을 때 어떤동작이 일어날지 예상이 가능하다.
```javascript
const sayHi = (name, age, gender) => {
  console.log(`Hello ${name}, you are ${age}, you are a ${gender}`);
};

sayHi("s", 10);
매개변수가 3개가 아닌 2개가 들어와서 에러

const sayHi = (name: string, age: number, gender: string): string => {
  return `Hello ${name}, you are ${age}, you are a ${gender}!`;
};

어떠 타입의 인수를 넣을지 지정
name: string, age: number, gender: string
return 의 타입은 string

```

tsc-watch -> 파일수정시마다 작업실행

객체 전달하기

interface 명령어로 새로운 타입을 만들어 사용
```javascript
interface Human {
  name: string;
  age: number;
  gender: string;
}

const person = {
  name: "nicolas",
  age: 22,
  gender: "male"
};

const sayHi = (person: Human): string => {
  return `Hello ${person.name}, you are ${person.age}, you are a ${
    person.gender
  }!`;
};

Typescript에서의 Class
class Human {
  public name: string;
  private age: number;
  public gender: string;
  constructor(name: string, age: number, gender: string) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
}

const john = new Human("john", 20, "male");

const sayHi = (person: Human): string => {
  return `Hello ${person.name}, you are ${person.age}, you are a ${
    person.gender
  }!`;
};

private 속성인 person.age에 접근하기 때문에 컴파일 되지 않는다.
```

