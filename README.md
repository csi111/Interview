# Interview
Interview Q&amp;A


# Android

Android Process와 Thread

###Process 와 Thread

###Android Service vs Intent Service

* IntentService는 Service를 상속받은 클래스로 작업을 수행하는 스레드(Thread)를 별도로 생성하는 서비스
* 여러번 실행될 경우 별도의 Queue를 통해 처리됨.

####IntentService의 장점

* 서비스의 콜백메소드들에 대해서 디폴트 구현을 제공하기 때문에 별도로 콜백 메소드를 구현할 필요가 없음. 
* onHandleIntent() 메소드만 구현하면 되고 이 메소드 안에서 클라이언트에 의해 제공되는 작업.
* 작업이 완료되면 자동적으로 서비스를 중단하기 때문에 stopSelf() 또는 stopService()를 호출할 필요가 없음.

참고 <http://android-kr.tistory.com/9#Lifecycle> 

### Width와 MeasureWidth의 차이
Layout의 드로잉 과정 
* Animate 과정(animate)
* Measure 과정(requestLayout)
* Layout 과정(requestLayout)
* Draw 과정(Invalidate)

뷰의 기하는 사각형이다.
[(left, top), (right, bottom)] or [(left, top), (width, height)] 로 사각형을 정의한다.

Measured Width, Measured Height 는 뷰가 부모뷰 크기의 범위 내에서 가지고 싶어하는 너비와 높이이다.
Drawing Width, Drawing Height 는 뷰의 실제 너비와 높이로 뷰를 그리기 위해서 사용한다.
안드로이드에서는 이 Drawing Width와 Drawing Height를 width와 height로 표기한다.
따라서 Measured Width, Measured Height 는 Drawing Width, Drawing Height 와 다를 수 있다.
왜냐하면 뷰의 패딩, 마진 등을 고려하면 원하는 크기에서 패딩 및 마진 값을 빼야 하기 때문이다.

뷰의 정확한 위치와 크기는 언제 알 수 있는가?
안드로이드에서 뷰의 위치와 크기는 Layout 과정이 끝나야 정확히 계산된다.
이 Layout 과정은 여러번 호출 될 수 있다.
그렇기 때문에 Draw 과정이 시작되기 직전에 View의 정확한 위치와 크기를 알 수 있다.
위치 얻기 : getLeft(), getTop()
크기 얻기 : getWidth(), getHeight()
그렇다면 View의 Draw 과정이 시작되기 직전을 어떻게 알 수 있을까?
ViewTreeObserver 사용
뷰의 크기를 알고자 하는 뷰에서 getViewTreeObserver() 를 통해서 ViewTreeObserver를 가져온다
OnPreDrawListener 를 등록해서 드로잉 직전에 리스너가 호출 되도록 한다.
픽셀 단위의 뷰의 크기를 알 수 있다.


# Java

### Annotatiaon
소스코드에 메타데이터를 삽입하는 것으로 구독성 및 체계적인 소스코드를 작성하는데 용이한 기법(주석)이다.

소스코드상에서 비지니스 로직에 영향을 주지 않지만, 해당 타겟의 연결 방법 및 소스코드의 구조를 변경 가능하다.

어노테이션은 컴파일 시기에 처리도 가능할 수 있으며, 자바의 리플렉션을 거쳐서 런타임에서 처리가 가능할 수 있습니다.

### Generics란?
제네릭스란 쉽게말해서 ArrayList(컬렉션 클래스에서 사용가능하지만 쉬운 설명을 위해 대표적인 컬렉션 클래스인 ArrayList를 가지고 설명 하겠습니다.) 가 다룰 객체를 미리 명시해줌으로써 형변환을 하지 않고 사용하는 것입니다. 즉 ArrlayList가 사용할 객체의 타입이란 이야기 입니다

### JVM(JAVA) 메모리구조
Stack
Heap

### JAVA finalize란?

### OOP 5대 원칙

### Java equals를 상속받을시, 같이 상속받아 사용해야 하는 Method는?

### ENUM에 대해 설명

### ENUM과 static 상수를 선언하여 사용하는 것의 차이

 
