# Quest 22. TypeScript

## Introduction

- javascript의 슈퍼셋이다. 슈퍼셋이란?
  기본적으로 하위 호환성을 지원한다고 표현할 수 있다. Typescript는 javascript의 모든 기능을 기본적으로 제공하면서 추가적인 기능을 제공하기 때문에 슈퍼셋이라고 칭함.
  javascript가 제공하지 못하는 것 : 명시적인 유형 설명 - 데이터에 대한 유형 설명이라는 측면에서 javascript는 지원할 수 없는 기능
  을 Typescript가 제공한다.

## Topics

- Typescript는 왜 필요할까?

데이터를 설명할 수 있는 것과 없는 것의 차이, 그리고 어떻게 데이터에 설명을 붙이는가?

### Type 정의, 데이터를 설명하는 것은 왜 중요한가?

프론트엔드 코드의 구성요소를 살펴보면 실제 데이터가 차지하는 비중이 높다. 보통 데이터 혹은 데이터 상태라고도 하는데 이 데이터가 복잡하고, 많고 , 큼
프론엔드 앱의 규모가 커지면 커질수록 다루는 데이터는 훨씬 많아진다. 그리고 그 데이터는 상황에 따라서 어떤 이유로든 변한다.데이터가 변경되면 코드도 변경되어야 한다. 하지만 프로그램의 규모가 크면 클수록 많은 개발자들이 있을 것이고, 그 서비스가 종료되기 전까지 계속해서 유지보수되어야한다는 특성이 존재.
지금 보고 있는 코드가 내가 작성하지 않은 코드일 수 있고, 내가 작성하지 않은 코드를 수정해야할 경우도 비일비재하기 때문에 이런 상황에서 데이터 유형의 설명이 명확하지 않다면 데이터를 수정하기 위해 수많은 문서와 추가적인 정보를 찾아다니는 등의 시간을 허비하게 될 것.
그래서 코드 자체가 데이터의 유형을 잘 설명할 수 있다고 하는 것이 베스트

자바스크립트는 컨셉상 구조적으로 데이터의 유형을 설명하기 어려운 언어이므로 트랜스 파일링이라는 자연스러운 과정 속에서 데이터 유형을 설명할 수 있는 타입스크립트라는 언어가 탄생.

### Typescript의 가장 핵심적인 기능. 즉, 타입을 제공한다는 것은 어떤 것을 의미하는가? 왜? 그리고 무엇이 좋아지는가?

```
let age = 10;
let x = 10;

// javascript는 변수에 이름을 어떻게 정해주느냐에 따라 데이터를 설명할 수 있게 한다. 하지만 이것은 실제로 데이터에 있는 값이 어떠한 유형인지 알 수 없고, 단지 변수명을 통해 해당 데이터에 대한 의미만을 전달한다. Typescript는 이러한 부분을 문법적으로 보완하여 데이터의 유형 설명 기능을 제공한다.

type Centimeter = number;
type RainbowColor = 'red' | 'orange' | 'yellow' | 'green' | 'blue' | 'indigo' | 'violet'

let weight:number = 80;
let height:number = 176;
// height라는 변수가 숫자인 것을 명시적으로 표현할 수 있으나 176이 의미하는 것이 cm인지 혹은 inchi인지 그 유형을 확인할 수 없는데
Typescript는 이것을 유형으로 만들어 낼 수 있다.

let height: Centimeter = 176;

let color = 'orange';
let color: RainbowColor = 'orange';

// 타입을 제공해준다는 것은 코드가 자신을 표현하는 데에 명확하고 풍성한 내용을 담을 수 있게 된다.
```

javascript 코드가 주는 정보보다 더 많고 깊은 양의 정보를 코드를 통해 전달할 수 있게 되고, 코드를 봤을 때 해당 코드가 어떤 일을 하는지를 더욱 손쉽게 알 수 있게 되어 버그를 줄일 수 있고 유지보수, 가독성측면에서도 매우 용이하다.
타입을 정의하는 것 뿐만아니라 실제 오류 가능성을 낮출 수 있음

### Typescript가 이런 기능을 어떻게 제공할 수 있을까?

- typescript는 트랜스 파일러이기 때문에 가능한 것.
  트랜스파일러라는 작업이 뭔가 부가적인 작업(기존에 수행하던 작업과 이질감이 있었다면)이었다고 한다면 타입스크립트를 받아 들이지 못했을 것.
  하지만 기존에도 이미 바벨이라는 트랜스파일러를 이용해서 상위버전의 자바스크립트 언어를 하위버전으로 변환하는 역할을 하고 있었다.

상위버전의 자바스크립트를 그대로 지원하면서 더해서 타입 유형이라는 것을 제공하고 더 표현력 높은 기능들을 제공하므로서 개발자들이 타입스크립트를 사용하기 시작한 것.
