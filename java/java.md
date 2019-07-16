# Java

### Process와 Thread 설명
*Process* : 운영체제로 부터 자원을 할당받은 작업의 단위로 프로세서를 할당받아 주소공간, 파일, 메모리등 자원을 할당 받아 작업이 실행됨. 각 프로세스는 자신만의 고유 공간과 자원을 할당받기 때문에 프로세스간 자원 공유등의 통신을 위해서는 IPC(Inter-Process Communication)를 통해 진행하여야 함.

*Thread* : 프로세스가 할당받은 자원을 이용하는 실행의 단위로 한 프로세스 내에서 동작되는 여러 실행의 흐름을 얘기하며 프로세스 내의 주소 공간이나 자원등을 쓰레드끼리 공유하며 실행이 가능함.

[http://ralf79.tistory.com/34](http://ralf79.tistory.com/34)

[https://brunch.co.kr/@kd4/3](https://brunch.co.kr/@kd4/3)

### Process와 Thread의 퍼포먼스 비교
스레드는 프로세스 내에서 각각의 스택 공간을 제외한 나머지 공간과 시스템 자원을 공유한다.그러므로 프로세스를 이용하여 동시에 처리하던 일을 스레드로 구현할 경우 메모리 공간은 물론 시스템 자원 소모도 현격히 줄어든다.. 이와 같이 프로세스를 생성하는 것보다 스레드를 생성하는 것이 효율적이다. 특히 멀티 프로세서 환경에서는 더욱 효과가 탁월하다. 스레드 간의 통신이 필요한 경우 별도의 자원을 이용하는 것이 아니라 전역 변수의 공간을 이용하여 데이터를 주고받을 수 있다.

##### Thread 장점

* 시스템의 처리량이 향상
* 시스템의 자원소모가 줄어듬
* 프로그램간 응답 시간 단축
* 프로세스간 통신 방법 보다 스레드간 통신방법이 간단

##### Thread 단점

* 멀티쓰레드 프로그래밍시 주의 깊게 설계가 필요 - 미묘한 시간, 잘못된 변수 공유로 오류 발생 확률 증가
* 공유되는 전역 변수에 대한 충돌로 인한 동기화 문제 해결 필요
* 프로그램 디버깅이 어려움 
* 단일 프로세서 시스템에서의 효과 미비

### Recursive Programming의 경험

### 병렬처리 중 Deadlock현상을 막기 위해 사용하는 기법
다중 프로그래밍 시스템에서 하나 또는 그 이상의 프로세스가 수행할 수 없는 어떤 특정 이벤트를 기다리는 상태(교착상태)

* 한정된 자원을 사용하려고 서로 경쟁하는 상황
* 프로세스가 자원을 요청시 그 시각에 해당 자원을 누군가가 사용하거나 점유하여 사용할 수 없는 상태가 발생하여 대기 상태가 발생하는 상황
* 대기상태가 다시 실행 상태로 변경되지 않을 경우

##### 교착상태의 특징

* 상호배제(Mutual exclusion) : 한번에 오직 한 프로세스만 자원을 사용
* 점유대기(Hold and wait) : 프로세스가 적어도 하나의 자원을 점유하면서 다른 프로세스가 점유하고 있는 자원을 추가로 얻기위해 대기
* 비선점(No preemption) : 점유된 자원은 강제로 해제될 수 없고, 점유하고 있는 프로세스가 작업을 마치고 자원을 자발적으로 해제
* 순환대기(Circular wait) : 대기하고 있는 프로세스 집합에서 P0 ~ Pn에서 꼬리를 물면서 점유한 자원을 계속 대기하고 있는 상태

##### 처리 방법

* 교착상태 예방 및 회피 : 교착상태가 되지 않도록 보장하기 위해 교착상태를 예방하거나 회피하는 프로토콜을 이용하는 방법
* 교착상태 탐지 및 회복 : 교착상태가 되도록 허용하고 다음에 회복시키는 방법
* 교착 상태 무시 : 대부분의 시스템이 교착상태가 잘 발생하지 않으므로, 교착상태 예방, 회피 ,탐지, 복구방법을 무시

### Java8에 추가된 것

### Comparable 사용 경험

### Annotatiaon
소스코드에 메타데이터를 삽입하는 것으로 구독성 및 체계적인 소스코드를 작성하는데 용이한 기법(주석)이다.

소스코드상에서 비지니스 로직에 영향을 주지 않지만, 해당 타겟의 연결 방법 및 소스코드의 구조를 변경 가능하다.

어노테이션은 컴파일 시기에 처리도 가능할 수 있으며, 자바의 리플렉션을 거쳐서 런타임에서 처리가 가능할 수 있습니다.

### Singleton 패턴에 대해 설명하고 구현하기

### Builder 패턴에 대해 설명하라

### Abstract를 활용한 패턴에 대해 설명

### JVM(JAVA) Stack, Heap 메모리구조
*Stack*
변수값, 기본타입(Primitive Type)인 정수형 변수, 실수형 변수, 논리형 변수를 실제값으로 저장한다.
크기가 정해져 있는 타입으로 메모리 할당시 컴파일될때 이미 계산이 이루어짐.
메소드 호출시에 처리되는 value(Heap메모리상의 Objects 참조 값 -refer objects, 메소드 내에서 생성 되고 사라지는 변수들 - short-lived values)가 저장되며, 항상 LIFO(Last-In-First-Out)형태로 실행된다.
메소드가 실행되면 새로운 블록의 Stack메모리 공간이 잡히며 local primitie values와 메소드 내의 refer Objects가 Stack 메모리 공간에 할당된다. 메소드가 끝날시 메모리 공간은 반환되어 비워진다.

*Heap*
객체(Objects, JRE classes)와 배열이 생성되는 공간이며 GC(Garbage Collection)는 Heap 메모리 공간 내에 Objects 중 참조(Reference) 값이 없는 Objects에 대해서 실행하여 Objects가 할당된 메모리 공간을 반환해주어 Heap 메모리 영역을 청소/관리 해준다.
Heap메모리영역의 모든 Objects은 프로세스(어플리케이션) 내에서 전역적으로 액세스가 가능하며 참조(Reference)가 가능하다.


###### Example
```java
package com.journaldev.test;

public class Memory {

	public static void main(String[] args) { // Line 1
		int i=1; // Line 2
		Object obj = new Object(); // Line 3
		Memory mem = new Memory(); // Line 4
		mem.foo(obj); // Line 5
	} // Line 9

	private void foo(Object param) { // Line 6
		String str = param.toString(); //// Line 7
		System.out.println(str);
	} // Line 8

}
```
![https://github.com/csi111/Interview/blob/master/java/Java-Heap-Stack-Memory.png](https://github.com/csi111/Interview/blob/master/java/Java-Heap-Stack-Memory.png)


[http://www.journaldev.com/4098/java-heap-space-vs-stack-memory] (http://www.journaldev.com/4098/java-heap-space-vs-stack-memory)

### JAVA GC 구동 원리
Java는 프로그램 코드 내에서 명시적으로 메모리 해제를 선언하지 않으며, GC(Garbage Collector)가 참조가 없어진 객체(필요없어진 객체)를 Heap메모리 영역에서 찾아서 메모리를 반환(지우는) 작업을 한다.

JVM에서 GC가 수행될때는 프로그램의 수행을 모두 멈추고 GC를 수행하게 되어 프로그램 성능에 영향을 끼치는 단점이 존재

[http://d2.naver.com/helloworld/1329] (http://d2.naver.com/helloworld/1329)

### GC대상 판별법

### Mobile에서 GC의 단점
GC가 수행될때 단말의 성능이 좋지 않은 경우 한번에 많은 Objects의 메모리가 반환되는 처리가 될때 앱이 버벅이는 경우가 발생

안드로이드의 경우 3.0 이상 부터 concurrent 및 partial collection방식을 통해 가비지컬렉션의 반응성이 높아졌으며 동작 시간이 5ms 이하로 단축되어 GC가 적시에 동작되도록 개선됨.

[https://source.android.com/devices/tech/dalvik/gc-debug.html] (https://source.android.com/devices/tech/dalvik/gc-debug.html)

[https://rejrecords.wordpress.com/2016/11/26/android-gc-vs-ios-ref-counting/amp/] (https://rejrecords.wordpress.com/2016/11/26/android-gc-
vs-ios-ref-counting/amp/)

### JAVA finalize란?
- 자바의 메모리 해제는 Garbage Collector(이하 GC)에 의해 수행됩니다. finalize()는 GC에 의해 호출됩니다. 
- finalize()는 실행된다는 보장이 없습니다. 실행이 될 수도 안 될 수도 있고 머 그렇습니다. 그래서 필수적인 로직을 포함시켜서는 안 됩니다. 
-  finalize()는 모하는데 쓰느냐? 혹시나 하는 로직을 넣으면 됩니다. 디비를 열고 사용자가 혹시 안 닫았으면 닫는 로직

Reference [http://iilii.egloos.com/4091133](http://iilii.egloos.com/4091133)

### HashMap, HashTable을 구현시 사용할 자료구조 및 설명

### Hashcode의 return 값
int형 반환(-2147483648 ~ 2147483647)

Java의 정수/실수형의 값 범위

* **boolean** 1bit
* **int** 32bits
* **long** 64bits
* **float** 32bits
* **double** 64bits
* **short** 16bits
* **char** 16bits
* **byte** 8bits

### Hash의 정의

### OOP 5대 원칙

#### SRP (단일책임의 원칙: Single Responsibility Principle)

- 작성된 클래스는 하나의 기능만 가지며 클래스가 제공하는 모든 서비스는 그 하나의 책임(변화의 축: axis of change)을 수행하는 데 집중되어 있어야 한다는 원칙
- 어떤 변화에 의해 클래스를 변경해야 하는 이유는 오직 하나뿐이어야 함을 의미
- 책임을 적절히 분배함으로써 코드의 가독성 향상, 유지보수 용이라는 이점까지 누릴 수 있으며 객체지향 원리의 대전제 격인 OCP원리뿐 아니라 다른 원리들을 적용하는 기초

#### OCP (개방폐쇄의 원칙: Open Close Principle)

- 소프트웨어의 구성요소(컴포넌트, 클래스, 모듈, 함수)는 확장에는 열려있고, 변경에는 닫혀있어야 한다는 원리
- 요구사항의 변경이나 추가사항이 발생하더라도, 기존 구성요소는 수정이 일어나지 말아야 하며, 기존 구성요소를 쉽게 확장해서 재사용할 수 있어야 한다는 뜻
- OCP를 가능케 하는 중요 메커니즘은 추상화와 다형성이라고 설명

#### LSP (리스코브 치환의 원칙: The Liskov Substitution Principle)

- LSP를 한마디로 한다면, “서브 타입은 언제나 기반 타입으로 교체할 수 있어야 한다.”라고 할 수 있습니다. 즉, 서브 타입은 언제나 기반 타입과 호환될 수 있어야 합니다. 달리 말하면 서브 타입은 기반 타입이 약속한 규약(public 인터페이스, 물론 메소드가 던지는 예외까지 포함됩니다.)을 지켜야 합니다. 상속은 구현상속(extends 관계)이든 인터페이스 상속(implements 관계)이든 궁극적으로는 다형성을 통한 확장성 획득을 목표로 합니다. LSP원리도 역시 서브 클래스가 확장에 대한 인터페이스를 준수해야 함을 의미합니다
- 다형성과 확장성을 극대화 하려면 하위 클래스를 사용하는 것보다는 상위의 클래스(인터페이스)를 사용하는 것이 더 좋습니다. 일반적으로 선언은 기반 클래스로 생성은 구체 클래스로 대입하는 방법을 사용
- 생성 시점에서 구체 클래스를 노출시키기 꺼려질 경우 생성 부분을 Abstract Factory 등의 패턴을 사용하여 유연성을 높임
- 상속을 통한 재사용은 기반 클래스와 서브 클래스 사이에 IS-A관계가 있을 경우로만 제한 되어야 합니다. 그 외의 경우에는 합성(composition)을 이용한 재사용을 해야 합니다. 상속은 다형성과 따로 생각할 수 없습니다. 그리고 다형성으로 인한 확장 효과를 얻기 위해서는 서브 클래스가 기반 클래스와 클라이언트 간의 규약(인터페이스)를 어겨서는 안 됩니다. 결국 이 구조는 다형성을 통한 확장의 원리인 OCP를 제공

#### ISP (인터페이스 분리의 원칙: Interface Segregation Principle)

- ISP원리는 한 클래스는 자신이 사용하지 않는 인터페이스는 구현하지 말아야 한다는 원리
- 어떤 클래스가 다른 클래스에 종속될 때에는 가능한 최소한의 인터페이스만을 사용

#### DIP (의존성역전의 원칙: Dependency Inversion Principle)

- 의존 관계의 역전 Dependency Inversion 이란 구조적 디자인에서 발생하던 하위 레벨 모듈의 변경이 상위 레벨 모듈의 변경을 요구하는 위계관계를 끊는 의미의역전
- 실제 사용 관계는 바뀌지 않으며, 추상을 매개로 메시지를 주고 받음으로써 관계를 최대한 느슨하게 만드는 원칙

Reference [http://www.nextree.co.kr/p6960/](http://www.nextree.co.kr/p6960/)

### Java equals
- equals(Object obj) 는 객체의 레퍼런스가 아닌 객체의 내용이 같은 지를 판단하는 메쏘드
- equals는 어떤 오브젝트가 인자로 받은 다른 오브젝트와 그 내용이 일치하는 지를 판단합니다. == 부호로 판단하는 것은 레퍼런스, 즉 메모리 상에 같은 객체인지를 판단하는 반면, equals는 그 내용을 판단합니다.
- 추이성: 어떤 x,y,z에 대해서도 x.equals(y)와 y.equals(z)가 true면 x.equals(z)도 true를 리턴해야 합니다.
- 일관성: x,y의 멤버 변수가 변하지 않는 이상 x.equals(y)는 항상 같은 값을 리턴해야 한다.
- 대칭성. 어떠한 x,y에 대해서도 x.equals(y) 와 y.equals(x)는 같은 값을 가져야 합니다.
- 어떤 객체 x에 대해서도 x.equals(x)는 반드시 true를 리턴해야 합니다.

Reference [http://egloos.zum.com/iilii/v/3999066](http://egloos.zum.com/iilii/v/3999066)

### Java hashcode
- hashCode는 hash 값을 리턴
- 같은 자바 어플리케이션에서 실행된다면, equals에서 비교하는 멤버변수가 변경되지 않는다면, 같은 int 값을 리턴해야 합니다.
equals에서 쓰는 멤버 변수를 hashCode를 구현하는데도 똑같이 쓰면 됩니다. 결국 equals의 구현과 hashCode의 구현은 동떨어질 수 없습니다.
-  a.equals(b)가 true일 경우 a의 hashCode와 b의 hashCode는 같은 값을 리턴해야 합니다.
-  a.equals(b)가 false일 경우 a의 hashCode와 b의 hashCode가 반드시 다른 값을 리턴할 필요는 없지만, 가능하면 다른 값을 리턴하는 게 좋습니다.

### Java equals를 상속받을시, 같이 상속받아 사용해야 하는 Method는?
hashcode
같은 자바 어플리케이션에서 실행된다면, equals에서 비교하는 멤버변수가 변경되지 않는다면, 같은 int 값을 리턴해야 합니다.
equals에서 쓰는 멤버 변수를 hashCode를 구현하는데도 똑같이 쓰면 됩니다.


```java
public class Person {
    private String name;
    public Person(String name) {
        super();
        this.name = name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public int hashCode() {
        final int PRIME = 31;
        int result = 1;
        result = PRIME * result + ((name == null) ? 0 : name.hashCode());
        return result;
    }
    @Override
    public boolean equals(Object obj) {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        final Person other = (Person) obj;
        if (name == null) {
            if (other.name != null)
                return false;
        } else if (!name.equals(other.name))
            return false;
        return true;
    }
```

Reference [http://iilii.egloos.com/4000476](http://iilii.egloos.com/4000476)

### String의 이해
리터럴과 new String선언의 차이

Reference [https://medium.com/@joongwon/string-%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EC%B0%B0-57af94cbb6bc](https://medium.com/@joongwon/string-%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EC%B0%B0-57af94cbb6bc)


### ENUM에 대해 설명
관련이 있는 상수들의 집합입니다. 자바에서는 final로 String과 같은 문자열이나 숫자들을 나타내는 기본 자료형의 값을 고정할 수 있습니다. 이렇게 고정된 값을 상수라고 합니다. 영어로는 constant입니다. 어떤 클래스가 상수만으로 작성되어 있으면 반드시 class로 선언할 필요는 없습니다. 이럴 때 class로 선언된 부분에 enum이라고 선언하면 이 객체는 상수의 집합이다. 라는 것을 명시적으로 나타냅니다. enum은 enumeration이라는 셈, 계산, 열거, 목록이라는 영어단어의 앞부분만 따서 만든 예약어입니다.

Java에서 enum 타입은 열거형을 의미하는 특별한 형태의 클래스입니다. 그렇기 때문에 일반 클래스와 같이 생성자(Constructor)가 있어야 합니다. 물론 생성자를 만들어주지 않아도 Java가 default생성자를 만들어주긴 하지만, enum의 경우에는 다른 클래스들과 달리 일반적으로 생성자의 접근 제어자를 private로 지정 해야합니다.. enum 타입의 생성자를 일반적인 클래스의 생성자와 같이 public으로 설정하거나 protected로 하게 되면 다음과 같은 에러가 발생합니다.

enum타입은 고정된 상수들의 집합으로써, 런타임(run-time)이 아닌 컴파일타임(compile-time)에 모든 값을 알고 있어야 합니다. 즉 다른 패키지나 클래스에서 enum 타입에 접근해서 동적으로 어떤 값을 정해줄 수 없습니다. 따라서 컴파일 시에 타입안정성이 보장됩니다(해당 enum클래스 내에서 까지도 new키워드로 인스턴스 생성이 불가능하며 newInstance(), clone()등의 메소드도 사용 불가). 이 때문에 생성자의 접근제어자를 private으로 설정해야 합니다. 이렇게 되면 외부에서 접근 가능한 생성자가 없으므로 enum타입은 실제적으로 final과 다름이 없습니다. 클라이언트에서 enum의 인스턴스를 생성할 수 없고 상속을 받을 수도 없으므로, 클라이언트의 관점에서 보면 인스턴스는 없지만 선언된 enum 상수는 존재하는 셈입니다. 결국 enum타입은 인스턴스 생성을 제어하며, 싱글톤(singleton) 을 일반화합니다. 이러한 특성 때문에, enum타입은 싱글톤을 구현하는 하나의 방법으로 사용되기도 합니다.

Reference [http://www.nextree.co.kr/p11686/](http://www.nextree.co.kr/p11686/)

### ENUM과 static 상수를 선언하여 사용하는 것의 차이

코드가 단순해지며 가독성이 좋습니다.
인스턴스 생성과 상속을 방지합니다.
키워드 enum을 사용하기 때문에 구현의 의도가 열거임을 분명하게 나타낼 수 있습니다.

### 상속이란 
상속(Inheritance)이란 물려준다는 의미다. 어떤 객체가 있을 때 그 객체의 필드(변수)와 메소드를 다른 객체가 물려 받을 수 있는 기능을 상속이라고 한다.

### Object의 기본 메소드

* hashcode()
* equals(Object obj)
* clone()
* toString()
* finalize()


### Generic이란  
제네릭(Generic)은 클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법을 의미한다.
쉽게말해서 ArrayList(컬렉션 클래스에서 사용가능하지만 쉬운 설명을 위해 대표적인 컬렉션 클래스인 ArrayList를 가지고 설명 하겠습니다.) 가 다룰 객체를 미리 명시해줌으로써 형변환을 하지 않고 사용하는 것입니다. 즉 ArrlayList가 사용할 객체의 타입이란 이야기 입니다


- 컴파일 단계에서 오류가 검출된다
- 중복의 제거와 타입 안전성을 동시에 추구할 수 있다
- 제네릭으로 올 수 있는 데이터 타입을 특정 클래스의 자식으로 제한할 수 있다

Reference 

[http://lng1982.tistory.com/240] (http://lng1982.tistory.com/240)
[https://opentutorials.org/module/516/6237] (https://opentutorials.org/module/516/6237)

### Java Collection 중 비동기 처리에 적합한 Class에 대해 설명

### List, Set, Map의 차이


##### List
*List*의 특징

* 순서가 있는 Collection
* Data를 중복해서 포함할 수 있음

*Stack*

* Data의 삽입/추출이 가능한 자료구조로 LIFO(Last In First Out 후입 선출) 구조로 되어 있음
* push() : data 삽입에 사용
* pop() : data 추출에 사용
* peek() : data 추출시 삭제를 하지 않고 data만 가져오도록 사용
* search() : data를 검색할때 사용

*Vector*

* 자동으로 동기화 보장
* ArrayList에 동기화가 보장되도록 최적화된 클래스
* Java 5.0 이후 AutoBoxing/AutoUnBoxing지원
	- AutoBoxing이란 primitive타입을 Wrapper클래스형의 객체로 자동으로 변환해주는 기능

*ArrayList*

* 동기화를 보장해주지 않는다
* 배열에 동적 메모리 증가 기능을 구현한 클래스

##### Set
*Set*의 특징

* 집합적인 개념의 Collection
* 순서의 의미가 없음
* Data를 중복해서 포함할 수 없음

##### Map
*Map*의 특징

* List와 Set이 순서나 집합의 개념이라면 Map은 검색의 개념이 추가된 인터페이스
* 데이터 삽입시 Key,Value 형태로 삽입되며 Key를 이용하여 Value를 찾을 수 있음

*HashMap과 HashTable*

##### 공통점

* 내부적으로 모두 Hash기법을 사용
* Java Collection Package의 Map인터페이스를 구현
* Key,Value방식을 이용하여 Data 관리

##### 차이점

* Hashtable은 동기화가 보장된다.
* HashMap은 동기화가 보장되지 않는다.
* HashMap은 저장요소의 순회를 위해 Fail-Fast Iterator를 반환하며 HasTable은 Enumeration을 반환한다. 

****

### Singleton에서 메모리누수 발생상황

### Singleton을 깨는 방법은?

### 쓰레드에서 공유하는 리소스는?

### 쓰레드는 왜 각자 스택영역을 갖는가

### 익명클래스에서 static접근 가능여부

### static변수 메모리 저장영역

### ArrayList와 LinkedList차이

### ArrayList가 한번에 찾을 수 있는 이유는?

### TreeSet과 HashSet의 차이

### Hashmap을 사용하는 이유

### Hashmap에서 정렬된상태로 유지하고싶은 경우

### Primitive타입에서 read write는 atomic할까

### Tree에 대해서 설명

### Tree에서 balance상태를 유지하기위해서 수행하는 작업이 시간복잡도에 영향을 미치는가

### Volatile 키워드에 대해 설명

### JIT 컴파일러