# 기본지식

### AOP란

### 함수형 프로그래밍이란

### Stream이란 무엇인가

### Domain모델의 정의
- 도메인의 정의
	* A domain is a field of study that defines a set of common requirements, terminology, and functionality for any software program constructed to solve a problem in the area of computer programming, known as domain engineering.
	* 도메인이란 요구사항, 용어, 기능등을 컴퓨터프로그래밍을 통해 문제를 해결하기 위해 정의된 학문적인 용어로써 현실세계의 요구사항,용어,기능등을 통틀어서 얘기함을 의미한다.
- 도메인모델의 정의
	* A domain model in problem solving and software engineering is a conceptual model of all the topics related to a specific problem. It describes the various entities, their attributes, roles, and relationships, plus the constraints that govern the problem domain. It does not describe solutions to the problem.
	* 

출처: http://javacan.tistory.com/entry/what-is-a-domain-model [자바캔(Java Can Do IT)]

### 디자인 패턴의 종류

- 스트래티지 패턴 (strategy pattern)
	* 교환 가능한 행동을 캡슐화하고 위임을 통해서 어떤 행동을 사용할지 결정한다. [http://hyeonstorage.tistory.com/146](http://hyeonstorage.tistory.com/146)
	
- 옵저버 패턴 (observer pattern)
	* 상태가 변경되면 다른 객체들한테 연락을 돌릴 수 있게 한다.

- 데코레이터 패턴 (decorator pattern)
	* 객체를 감싸서 새로운 행동을 제공한다.

- 팩토리 패턴 (factory pattern)
	* 생성할 구상 클래스를 서브클래스에서 결정한다.

- 추상 팩토리 패턴 (AbstractFactory pattern)
	* 클라이언트에서 구상 클래스를 지정하지 않으면서도 일군의 객체를 생성할 수 있도록 한다.

- 싱글턴 패턴 (singleton pattern)
	* 딱 한 객체만 생성되도록 한다.

- 커맨드 패턴 (command pattern)
	* 요청을 객체로 감싼다.

- 어댑터 패턴 (adaptor pattern)
	* 객체를 감싸서 다른 인터페이스를 제공한다.

- 퍼사드 패턴 (facade pattern)
	* 일련의 클래스에 대해서 간단한 인터페이스를 제공한다.

- 템플릿 메소드 패턴 (template method pattern)
	* 알고리즘의 개별 단계를 구현하는 방법을 서브클래스에서 결정한다.

- 이터레이터 패턴 (iterator pattern)
	* 컬렉션이어떤 식으로 구현되었는지 드러내진 않으면서도 컬렉션 내에 있는 모든 객체에 대해 반복 작업을 처리할 수 있게 한다.

- 컴포지트 패턴 (composite pattern)
	* 클라이언트에서 객체 컬렉션과 개발 객체를 똑같이 다룰 수 있도록 한다.

- 스테이트 패턴 (state pattern)
	* 알고리즘의 개별 단계를 구현하는 방법을 서브클래스에서 결정한다.

- 프록시 패턴 (proxy pattern)
	* 객체를 감싸서 그 객체에 대한 접근을 제어한다.

- 컴파운드 패턴 (compound pattern)
	* 반복적으로 생길 수 있는 일반적인 문제를 해결하기 위한 용도로 두 개 이상의 패턴을 결합해서 사용한는 것

- 브리지 패턴 (bridge pattern)
	* 구현 뿐만 아니라 추상화된 부분까지 변경시켜야 하는 경우

- 빌더 패턴 (builder pattern)
	* 제품을 여러 단계로 나눠서 만들 수 있도록 제품 생산 단계들을 캡슐화할 때

- 역할 사슬 패턴 (chain of responsibility pattern)
	* 한 요청을 두 개 이상의 객체에서 처리하고 싶을 때

- 플라이웨이트 패턴 (flyweight pattern)
	* 어떤 클래스의 인스턴스 한 개만가지고 여러 개의 "가상 인스턴스"를 제공하고 싶을 때

- 인터프리터 패턴 (Interpreter pattern)
	* 어떤 언어에 대한 인터프리터를 만들 때

- 미디에이터 패턴 (mediator pattern)
	* 서로 관련된 객체 사이의 복잡한 통신과 제어를 한 곳으로 집중시키고자 할 때

- 메멘토 패턴 (memento pattern) 
	* 객체를 이전의 상태로 복구시켜야 하는 경우

- 프로토타입 패턴 (prototype pattern)
	* 어떤 클래스의 인스턴스를 만드는 것이 자원/시간을 많이 잡아먹거나 복잡한 경우

- 비지터 패턴 (visitor pattern)
	* 다양한 객체에 새로운 기능을 추가해야 하는데 캡슐화가 별로 중요하지 않은 경우


### 디자인패턴의 분류
* 클래스 패턴
	- 템플릿 메소드
	- 팩토리 메소드
	- 어댑터
	- 인터프리터
* 객체 패턴
	- 스트레티지
	- 옵저버
	- 데코레이터
	- 프록시
	- 컴포지트
	- 이터레이터
	- 스테이트
	- 추상 팩토리
	- 싱글턴
	- 비지터
	- 메멘토
	- 역할 사슬
	- 브리지
	- 미디에이터
	- 플라이웨이트
	- 프로토타입
	- 빌더


### 상속, 캡슐화, 추상화, 다형성 개념

### 포인터변수란? 그리고 쓰이는 이유

### 글로벌변수와 정적변수의 개념

### 데이터베이스를 쓰는이유?(파일에 쓰는것과 비교해서)

### 데이터베이스에서 인덱스란? 그리고 인덱스의 종류

### 네트워크 라우트,스위치

### TCP vs UDP

### POST, GET 방식 설명

### POST 방식에서 보안성을 높이는 방법

### 암호화 알고리즘 종류(RSA 등등)

### 코틀린에 대해서 어떻게 생각하는지

### 코틀린의 장점

### Rx를 사용하는 이유

### Rx에서 subject란?

### Rx에서 Subject와 Observable 차이

### Rx에서 2개에서 emit될때 먼저도착하고나서 수행하고 싶을때

### Rx Maybe

### Rx CompositeDisposable

### Rx subscribeOn, observeOn

### Rxjava Scheduler 종류와 차이
