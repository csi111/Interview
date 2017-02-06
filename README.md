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

### Annotatiaon
소스코드에 메타데이터를 삽입하는 것으로 구독성 및 체계적인 소스코드를 작성하는데 용이한 기법(주석)이다.

소스코드상에서 비지니스 로직에 영향을 주지 않지만, 해당 타겟의 연결 방법 및 소스코드의 구조를 변경 가능하다.

어노테이션은 컴파일 시기에 처리도 가능할 수 있으며, 자바의 리플렉션을 거쳐서 런타임에서 처리가 가능할 수 있습니다.

### Generics란?
제네릭스란 쉽게말해서 ArrayList(컬렉션 클래스에서 사용가능하지만 쉬운 설명을 위해 대표적인 컬렉션 클래스인 ArrayList를 가지고 설명 하겠습니다.) 가 다룰 객체를 미리 명시해줌으로써 형변환을 하지 않고 사용하는 것입니다. 즉 ArrlayList가 사용할 객체의 타입이란 이야기 입니다

## JVM(JAVA) 메모리구조
Stack
Heap

## JAVA finalize란?

## OOP 5대 원칙

######SRP (단일책임의 원칙: Single Responsibility Principle)
- 작성된 클래스는 하나의 기능만 가지며 클래스가 제공하는 모든 서비스는 그 하나의 책임(변화의 축: axis of change)을 수행하는 데 집중되어 있어야 한다는 원칙
- 어떤 변화에 의해 클래스를 변경해야 하는 이유는 오직 하나뿐이어야 함을 의미
- 책임을 적절히 분배함으로써 코드의 가독성 향상, 유지보수 용이라는 이점까지 누릴 수 있으며 객체지향 원리의 대전제 격인 OCP원리뿐 아니라 다른 원리들을 적용하는 기초

######OCP (개방폐쇄의 원칙: Open Close Principle)

- 소프트웨어의 구성요소(컴포넌트, 클래스, 모듈, 함수)는 확장에는 열려있고, 변경에는 닫혀있어야 한다는 원리
- 요구사항의 변경이나 추가사항이 발생하더라도, 기존 구성요소는 수정이 일어나지 말아야 하며, 기존 구성요소를 쉽게 확장해서 재사용할 수 있어야 한다는 뜻
- OCP를 가능케 하는 중요 메커니즘은 추상화와 다형성이라고 설명


######LSP (리스코브 치환의 원칙: The Liskov Substitution Principle)
- LSP를 한마디로 한다면, “서브 타입은 언제나 기반 타입으로 교체할 수 있어야 한다.”라고 할 수 있습니다. 즉, 서브 타입은 언제나 기반 타입과 호환될 수 있어야 합니다. 달리 말하면 서브 타입은 기반 타입이 약속한 규약(public 인터페이스, 물론 메소드가 던지는 예외까지 포함됩니다.)을 지켜야 합니다. 상속은 구현상속(extends 관계)이든 인터페이스 상속(implements 관계)이든 궁극적으로는 다형성을 통한 확장성 획득을 목표로 합니다. LSP원리도 역시 서브 클래스가 확장에 대한 인터페이스를 준수해야 함을 의미합니다
- 다형성과 확장성을 극대화 하려면 하위 클래스를 사용하는 것보다는 상위의 클래스(인터페이스)를 사용하는 것이 더 좋습니다. 일반적으로 선언은 기반 클래스로 생성은 구체 클래스로 대입하는 방법을 사용
- 생성 시점에서 구체 클래스를 노출시키기 꺼려질 경우 생성 부분을 Abstract Factory 등의 패턴을 사용하여 유연성을 높임
- 상속을 통한 재사용은 기반 클래스와 서브 클래스 사이에 IS-A관계가 있을 경우로만 제한 되어야 합니다. 그 외의 경우에는 합성(composition)을 이용한 재사용을 해야 합니다. 상속은 다형성과 따로 생각할 수 없습니다. 그리고 다형성으로 인한 확장 효과를 얻기 위해서는 서브 클래스가 기반 클래스와 클라이언트 간의 규약(인터페이스)를 어겨서는 안 됩니다. 결국 이 구조는 다형성을 통한 확장의 원리인 OCP를 제공

######ISP (인터페이스 분리의 원칙: Interface Segregation Principle)
- ISP원리는 한 클래스는 자신이 사용하지 않는 인터페이스는 구현하지 말아야 한다는 원리
- 어떤 클래스가 다른 클래스에 종속될 때에는 가능한 최소한의 인터페이스만을 사용

######DIP (의존성역전의 원칙: Dependency Inversion Principle)
- 의존 관계의 역전 Dependency Inversion 이란 구조적 디자인에서 발생하던 하위 레벨 모듈의 변경이 상위 레벨 모듈의 변경을 요구하는 위계관계를 끊는 의미의역전
- 실제 사용 관계는 바뀌지 않으며, 추상을 매개로 메시지를 주고 받음으로써 관계를 최대한 느슨하게 만드는 원칙

Reference [http://www.nextree.co.kr/p6960/](http://www.nextree.co.kr/p6960/)

## Java equals
- equals(Object obj) 는 객체의 레퍼런스가 아닌 객체의 내용이 같은 지를 판단하는 메쏘드
- equals는 어떤 오브젝트가 인자로 받은 다른 오브젝트와 그 내용이 일치하는 지를 판단합니다. == 부호로 판단하는 것은 레퍼런스, 즉 메모리 상에 같은 객체인지를 판단하는 반면, equals는 그 내용을 판단합니다.
- 추이성: 어떤 x,y,z에 대해서도 x.equals(y)와 y.equals(z)가 true면 x.equals(z)도 true를 리턴해야 합니다.
- 일관성: x,y의 멤버 변수가 변하지 않는 이상 x.equals(y)는 항상 같은 값을 리턴해야 한다.
- 대칭성. 어떠한 x,y에 대해서도 x.equals(y) 와 y.equals(x)는 같은 값을 가져야 합니다.
- 어떤 객체 x에 대해서도 x.equals(x)는 반드시 true를 리턴해야 합니다.

Reference [http://egloos.zum.com/iilii/v/3999066](http://egloos.zum.com/iilii/v/3999066)

## Java hashcode
- hashCode는 hash 값을 리턴
- 같은 자바 어플리케이션에서 실행된다면, equals에서 비교하는 멤버변수가 변경되지 않는다면, 같은 int 값을 리턴해야 합니다.
equals에서 쓰는 멤버 변수를 hashCode를 구현하는데도 똑같이 쓰면 됩니다. 결국 equals의 구현과 hashCode의 구현은 동떨어질 수 없습니다.
-  a.equals(b)가 true일 경우 a의 hashCode와 b의 hashCode는 같은 값을 리턴해야 합니다.
-  a.equals(b)가 false일 경우 a의 hashCode와 b의 hashCode가 반드시 다른 값을 리턴할 필요는 없지만, 가능하면 다른 값을 리턴하는 게 좋습니다.

## Java equals를 상속받을시, 같이 상속받아 사용해야 하는 Method는?
hashcode
같은 자바 어플리케이션에서 실행된다면, equals에서 비교하는 멤버변수가 변경되지 않는다면, 같은 int 값을 리턴해야 합니다.
equals에서 쓰는 멤버 변수를 hashCode를 구현하는데도 똑같이 쓰면 됩니다.

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

Reference [http://iilii.egloos.com/4000476](http://iilii.egloos.com/4000476)


## ENUM에 대해 설명
관련이 있는 상수들의 집합입니다. 자바에서는 final로 String과 같은 문자열이나 숫자들을 나타내는 기본 자료형의 값을 고정할 수 있습니다. 이렇게 고정된 값을 상수라고 합니다. 영어로는 constant입니다. 어떤 클래스가 상수만으로 작성되어 있으면 반드시 class로 선언할 필요는 없습니다. 이럴 때 class로 선언된 부분에 enum이라고 선언하면 이 객체는 상수의 집합이다. 라는 것을 명시적으로 나타냅니다. enum은 enumeration이라는 셈, 계산, 열거, 목록이라는 영어단어의 앞부분만 따서 만든 예약어입니다.

Java에서 enum 타입은 열거형을 의미하는 특별한 형태의 클래스입니다. 그렇기 때문에 일반 클래스와 같이 생성자(Constructor)가 있어야 합니다. 물론 생성자를 만들어주지 않아도 Java가 defaul t생성자를 만들어주긴 하지만, enum의 경우에는 다른 클래스들과 달리 일반적으로 생성자의 접근 제어자를 private로 지정 해야합니다.. enum 타입의 생성자를 일반적인 클래스의 생성자와 같이 public으로 설정하거나 protected로 하게 되면 다음과 같은 에러가 발생합니다.

enum타입은 고정된 상수들의 집합으로써, 런타임(run-time)이 아닌 컴파일타임(compile-time)에 모든 값을 알고 있어야 합니다. 즉 다른 패키지나 클래스에서 enum 타입에 접근해서 동적으로 어떤 값을 정해줄 수 없습니다. 따라서 컴파일 시에 타입안정성이 보장됩니다(해당 enum클래스 내에서 까지도 new키워드로 인스턴스 생성이 불가능하며 newInstance(), clone()등의 메소드도 사용 불가). 이 때문에 생성자의 접근제어자를 private으로 설정해야 합니다. 이렇게 되면 외부에서 접근 가능한 생성자가 없으므로 enum타입은 실제적으로 final과 다름이 없습니다. 클라이언트에서 enum의 인스턴스를 생성할 수 없고 상속을 받을 수도 없으므로, 클라이언트의 관점에서 보면 인스턴스는 없지만 선언된 enum 상수는 존재하는 셈입니다. 결국 enum타입은 인스턴스 생성을 제어하며, 싱글톤(singleton) 을 일반화합니다. 이러한 특성 때문에, enum타입은 싱글톤을 구현하는 하나의 방법으로 사용되기도 합니다.

Reference [http://www.nextree.co.kr/p11686/](http://www.nextree.co.kr/p11686/)

## ENUM과 static 상수를 선언하여 사용하는 것의 차이

코드가 단순해지며 가독성이 좋습니다.
인스턴스 생성과 상속을 방지합니다.
키워드 enum을 사용하기 때문에 구현의 의도가 열거임을 분명하게 나타낼 수 있습니다.

## 상속이란 
상속(Inheritance)이란 물려준다는 의미다. 어떤 객체가 있을 때 그 객체의 필드(변수)와 메소드를 다른 객체가 물려 받을 수 있는 기능을 상속이라고 한다.
 
## Generic이란  
제네릭(Generic)은 클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법을 의미한다.

- 컴파일 단계에서 오류가 검출된다
- 중복의 제거와 타입 안전성을 동시에 추구할 수 있다
- 제네릭으로 올 수 있는 데이터 타입을 특정 클래스의 자식으로 제한할 수 있다

Reference 

[http://lng1982.tistory.com/240] (http://lng1982.tistory.com/240)
[https://opentutorials.org/module/516/6237] (https://opentutorials.org/module/516/6237)

## String Reverse 방법 

	 public class ReverseInPlace {

	  static char[]  str=null;

	    public static void main(String s[]) {
	      if(s.length==0)
		System.exit(-1);

	       str=s[0].toCharArray();

	       int begin=0;
	       int end=str.length-1;

	       System.out.print("Original string=");
	       for(int i=0; i<str.length; i++){
		 System.out.print(str[i]);
	       }

	       while(begin<end){
		  str[begin]= (char) (str[begin]^str[end]);
		  str[end]= (char)   (str[begin]^str[end]);
		  str[begin]= (char) (str[end]^str[begin]);

		  begin++;
		  end--;       
	       }

	       System.out.print("\n" + "Reversed string=");
	       for(int i=0; i<str.length; i++){
		 System.out.print(str[i]);
	       }

	    }
	}
 
