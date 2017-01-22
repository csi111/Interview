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
