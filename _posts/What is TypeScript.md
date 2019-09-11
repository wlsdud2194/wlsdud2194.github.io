---
bg: 'typescript.png'
layout: post
title: "How to use TypeScript"
crawlertitle: "How to use TypeScript"
summary: "How to use TypeScript"
date: 2019-09-05
categories: posts
tags : ['Node.js']
author: "Young"
---

 `Typescript`를 배우면서 중요한 내용을 정리한 글입니다 😃

 이전부터 타입스크립트의 장점과 필요성을 알고는 있었지만 Typescript를 쓰지 않고도 개발을 잘 해왔기 때문에 사용을 꺼려왔다. 그리고 평소처럼 React로 javascript만을 이용하여 웹 어플리케이션 개발을 하던 도중 서버에서 받아온 데이터를 하위 컴포넌트로 주는 과정이 있었는데, 실수로 하위 컴포넌트에 잘못된 값을 넘겨주었고 당연히 boolean 타입이여야 했던 것이 integer(정수) 타입으로 받게 되면서 자잘한 버그가 발생하였다. props-type을 정의 하지 않는 이유도 있지만 개발하면서 일일히 props-type을 정의 하는 것은 꽤나 번거러운 일이 발생하였고 이번 기회에  Typescript를 사용해보자고 마음먹게 되었다.

※ 틀린게 있을 수도 있으니 있다면 이슈를 남겨주세요 ;)

<br/>

<img src="https://user-images.githubusercontent.com/38432821/64664349-e0490280-d489-11e9-935b-78078e70541f.png" />

### 왜 타입스크립트 인가?

 타입스크립트는 타입이 있는 자바스크립트란 단어는 보다 정확히는 **정적 타입 시스템(static type system)을 도입한 자바스크립트**라는 뜻이다. 또한 JS는 인터프린터 이지만 TS는 컴파일을 통해 타입을 체크하여 오류검출등을 한다. 이를 통해 정적 타입을 이용하여 코딩을 할 수 있도록 도와준다.

> 와 타입스크립트를 쓰니까 너무 좋아! awesome Typescript !!

왜 이런 말이 나오는 지 알아보자

<br/>

## Typescript의 기본 타입

 기본적으로 c, c++, java와 같은 언어 처럼 숫자, 문자열, 불리언(참, 거짓) 등의 타입들을 지원한다.

```typescript
// number
const integer: number = 1;

// string
const myName: string = 'Lee Young';

// boolean
const isTypeScriptAwesome: boolean = true;
```

 또한 javascript에서 발생할 수 있는 특별한 타입들이 있다.

```typescript
// null
const nullValue: null = null;

// undefined
const undefinedValue: undefined = undefined;

// any
let allValue: any = 1;
allValue = 'hello world';
allValue = {};
allValue = true;

// void - null과 undefined만 가질 수 있음, 보통 아무런 값을 반환하지 않는 함수에서 사용함
function voidFunc(): void {}

// never - 그 어떤 값도 가질 수 없다. 보통 아래와 같은 경우에 사용하기도 함
function alwaysThrow(): never {
    throw new Error('This is Exception Error');
}
```

 배열, 튜플 이나 객체에 대해 타입을 정의 할 때는 아래처럼 한다.

```typescript
// array
const myArray: Array<number> = [1, 2 ,3, 4, 5, 6];
const myArray2: number[] = [1, 2, 3, 4, 5, 6];

// 튜플 - 튜플 타입 변수는 정확히 명시된 개수 만큼의 원소만을 가질 수 있다.
const myArray3: [string, number] = ['홍길동', 145];
```

<br/>

## 사용자 정의 타입 (타입 별칭)

 사용자가 원하는 구조를 타입으로 정의 하여 사용할 수 있다.  ~~c언어의 구조체 같은 느낌~~

```typescript
type UUID = string;
type Human = {
    name: string;
    age: number;
    address?: string; // ?는 해당 속성이 존재하지 않을 수도 있다는 것을 명시
};

function getHuman(uuid: UUID): Human {
    /* 함수 본문 */
}
```

<br/>

## 인터페이스

`interface` 키워드를 사용해 값이 특정한 형태(shape)를 갖도록 제약할 수 있다.

```typescript
interface Life {
  name: string;
  readonly sex: string; // 읽기 전용 속성
  weight?: number; // 선택 속성 
}

const cat: Life = { name: '길냥이', sex: 'male' }; // ok

// error TS2540: Cannot assign to 'sex' because it is a constant or a read-only property.
cat.sex = 'female';

interface GetLife {
    (uuid: UUID): Life;
}

const getLife: GetLife = function (u) {
    const dog: Life = { name: '홍길동', sex: 'female', weight: 30 };
    return dog;
}
```

 위 예제에서 생물이라는 인터페이스를 정의 하고 cat과 dog라는 변수에 객체를 정의 하였지만 `extends`으로 상속을 활용한다면 더욱 명확하게 작성 할 수 있다.

```typescript
// 다중 상속도 가능 
// interface Animal extends Life, Cute {...}
interface Animal extends Life {
    height: number;
    animalSpecies: string;
}

// ok
const myCat: Animal = {
    name: '냥냥이',
    sex: 'male',
    height: 25,
    animalSpecies: 'russian blue'
};
```

 위 처럼 `extends`를 사용하면 부모 인터페이스가 가지고 있던 특정을 가지면서 자식에서 추가적인 타입을 정의 할 수 있다.

#### 🤔 인터페이스와 타입 별칭의 차이

 사용자 정의 타입 이라는 측면에서만 보았을 때는 차이가 없는 것 같지만 다음과 같은 차이를 가진다.

1. 인터페이스는 `extends` 키워드를 이용하여 확장 할 수 있지만 타입별칭은 불가

2. 타입 별칭은 기본타입, 튜플, 배열과 유니온 타입에 새로운 이름을 줄 수 있음

3. 타입 별칭은 실제로는 새 타입을 생성하지 않기 때문에 `type UUID = string`으로 정의 하여 타입 에러가 발생하였을 때 `UUID` 대신 `string`을 보여준다. 하지만 인터페이스로 새 타입을 정의하면 (위에 GetHuman을 예시로) 정의한 인터페이스에 관한 에러가 발생하였을 때, `GetHuman`를 에러메세지로 보여준다.

<br/>

## 클래스

 이전에 자바스크립트에서 상속이라는 기능을 사용할 때는 `prototype`이라는 기능을 사용해야 했지만 es6에 들어서 `class` 라는 개념이 추가되면서 java에서 클래스를 사용하듯히 사용할 수 있다. 타입스크립트에서의 `class` 는 기존의 es6 class 보다 상위 집합으로 es6의 클래스를 포함하면서 여러가지 기능을 제공한다.

```typescript
class Base {
    static num: number = 0; // 스태틱 변수
    
    // 스태틱 메소드
    static incrementNum() {
        Base.num += 1;
    }

    baseProps: number; // 클래스 변수
    
    // 생성자
    constructor() {
        this.baseProps = 123;
    }
}

class MyCustom extends Base {
    private extendsProps: number = 0;
    constructor() {
        super();
        this.extendsProps = 456;
    }
}

const myCustom: MyCustom = new MyCustom();
console.log(Base.num); // 0

console.log(myCustom.baseProps); // 123
console.log(myCustom.extendsProps) // 456
```

##### 접근 제한자 (타입 스크립트에서만 가능)

- public (어디서든 접근 가능)
- private (외부 접근 불가)
- protected (내부접근 가능, 서브클래스 접근 또한 가능)



<br/>

이 밖에도  **색인타입**을 이용해 불분명한 객체 속성에 대해 타입을 정의 할 수 있고,  위 예제에는 없지만 클래스가 인터페이스를 상속받아서 사용할 수 도 있다. 또한 **추상 클래스**를 정의 하여 상속받아 사용할 수 도 있다.

### 🤞 마치며

 타입스크립트를 사용해 보면서 가장 편리했던 것은 함수나 객체를 선언할 때, 타입을 같이 정의 하면서 어떤 타입을 인자로 혹은 속성으로 써줘야 할지 재확인할 필요가 없어졌다는 것이다. 또한 추상적이 였던  타입이 명시적으로 나타나면서 좀 더 정확하고 명확한 코드를 작성할 수 있었다.

 대규모의 프로잭트에서 타입스크립트를 활용한다면 인터페이스나 클래스를 활용하여 체계적인 프로젝트 개발을 할 수 있을 것 같다.

 하지만 항상 타입스크립트가 좋다고 말하지 않는 개발자 분들도 계신다. 여러가지 이유로 타입스크립트를 쓰지 않는 것이 생산성이나 안정성과 같은 여러 측면에서 더욱 효율적이다라는 이야기가 있다. 안쓰는 이유를 들어 보면 충분히 일리 있는 이유지만 내가 내린 결론은 사용하는 것이 더욱 좋다는 것이다. 프로젝트의 규모가 커지고 버그 수정, 유지보수 측면에서 정적 타입 존재한다면 더욱 빠른 해결이 가능할 것이고 타입스크립트의 장점은 더욱 부각될 것이다. 타입스크립트의 생태계가 계속해서 커지고 있는 만큼 한번쯤 사용해 보는 것도 좋다고 생각한다.

##### 추가적으로 읽어보면 좋은 문서

- <a href="[https://ahnheejong.gitbook.io/ts-for-jsdev/](https://ahnheejong.gitbook.io/ts-for-jsdev/)">자바스크립트 개발자를 위한 타입스크립트</a>

- <a href="[https://typescript-kr.github.io/](https://typescript-kr.github.io/)">타입스크립트 공식 문서</a>
