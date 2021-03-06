# Development common sense

한재엽님의 깃허브를 참고했습니다.

https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Development_common_sense

## **좋은 코드란?**

좋은 코드란 대체 뭘까? 대부분의 사람들은 읽기 쉬운 코드, 중복이 없는 코드, 테스트가 용이한 코드 등을 말할 것이다. 하지만 이것들은 상황에 따라 좋고 나쁨이 언제든지 바뀔 수 있다. 중복을 줄이는 것 보다 직관성을 위해 내버려 두는 것이 나을 수도 있고 읽기 쉬운 코드지만 효율적인 측면에서 좋지 못할 수 도 있다. 확실히 좋은 것은 뭘까? 그것은 아마 확실히 나쁜것을 줄여나가는 것이 아닐까. 이 글에서는 좋지 않은 코드들을 줄이기 위해 다음과 같은 것들을 추천한다.

- 코드 간의 의존성을 고민하자. 분리가 가능하다면 분리하자 ex)abstract
- 합의된 규칙으로 일관성 있게 작성하자.ex) Naming, Directory
- 적절하게 확장 가능하도록 설계하자.
- 어쩔 수 없는 코드는 주석과 함께 격리하자.ex) 삭제하기 쉬운, 어려운 등등

## **객체 지향 프로그래밍 OOP**

절차 지향 프로그래밍 => 객체 지향 프로그래밍 => 함수형 프로그래밍

컴퓨터 중심 => 인간 중심 => ?

객체의 핵심 -> 기능을 제공하는 것

객체가 제공하는 기능 -> operation

인터페이스 -> 객체가 제공하는 모든 operation 집합

메시지 -> operation의 실행을 요청하는 것을 메시지를 보낸다라고 표현

캡슐화 => 내부적으로 기능 구현 방법을 감추는 것, 내부 구현 변경의 유연함을 주는 기법

### **OOP의 장점**

- 코드의 재사용성이 높다. => 이미 검증된 코드를 재사용 => 신뢰성 확보
- 생산성이 높다. => 내부적 동작을 모르더라도 라이브러리의 기능 사용 가능
- 디버깅이 쉽고 유지 보수에 용이하다. => 객체 단위로 코드가 나눠져 작성되기 때문
- 요구사항을 보다 명확하게 프로그래밍 가능하다. => 데이터 모델링 시 객체와 매핑하는 것이 수월하기 때문

### **OOP의 단점**

- 객체간의 정보 교환이 모두 메시지 교환을 통해 일어남 => 시스템에 많은 overhead but 하드웨어 발전 덕분에 대부분 보완
- 객체가 상태를 가진다. => 변수가 존재하고 이 변수를 통해 객체가 예측할 수 없는 상태를 갖게 되어 어플리케이션 내부에서 버그를 발생시킴

### **객체 지향적 설계 원칙**(SOLID)

1. SRP(Single Responsibility Principle) : 단일 책임 원칙 클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.

   (객체는 기능이 적을수록 좋다.)

2. OCP(Open-Closed Principle) : 개방-폐쇄 원칙 확장에는 열려 있어야 하고 변경에는 닫혀 있어야 한다.

3. LSP(Liskov Substitution Principle) : 리스코프 치환 원칙 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.

4. ISP(Interface Segregation Principle) : 인터페이스 분리 원칙 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.

5. DIP(Dependency Inversion Principle) : 의존 역전 원칙 

   - 첫째, 상위 모듈은 하위 모듈에 의존해서는 안된다. 상위 모듈과 하위 모듈 모두 추상화에 의존해야 한다.
   
   - 둘째, 추상화는 세부 사항에 의존해서는 안된다. 세부사항이 추상화에 의존해야 한다.
   
   이 원칙은 '상위와 하위 객체 모두가 동일한 추상화에 의존해야 한다'는 객체 지향적 설계의 대원칙을 제공한다
   
   이처럼 **자신보다 변하기 쉬운 것에 의존하던 것을 추상화된 인터페이스나 상위 클래스를 두어** **변하기 쉬운 것의 변화에 영향받지 않게 하는 것**이 **의존 역전 원칙**이다.
   
   참고 자료 - https://server-engineer.tistory.com/228
   
   (너무 의존적인 코드는 좋지 않다.)

## **RESTful API**

REST 는 `Resource Oriented Architecture` 이다. API 설계의 중심에 자원(Resource)이 있고 HTTP Method 를 통해 자원을 처리하도록 설계하는 것이다.

### REST이란?

- Representational State Transfer의 약자로 로이필딩에 의해 만들어졌습니다.
- 웹 서버에서에서 사용하는 것으로 애플리케이션 사이의 결합도를 낮춰 설계하는 아키텍쳐 스타일입니다.
- 즉, 결합도를 낮춰 서버 / 클라이언트가 별도로 구축되고 결합할 수 있게 하는 것이다.
- 이러한 결합도를 낮추기 위해 6가지의 제약 조건을 가지고 있으며 제약 조건을 잘 지켜야 RESTful하다고 할 수 있습니다.

### RESTful API 6가지 제약조건

#### Client-Server

- 이 조건의 기본 원칙은 관심사의 명확한 분리입니다.
- 사용자들에게 제공하는 Interface인 User Interface와 데이터 스토리지(ex. DB), 알고리즘 등 서버 내부의 작업을 분리함으로써 User Interface는 여러 플랫폼에서의 이식성을 향상 시킬 수 있으며 서버는 그 구성요소를 단순화하여 확장성을 단순화 할 수 있습니다.
- 이 조건을 따르게 되면 클라이언트와 서버는 서로 의존하지 않고 서로 진화 할 수 있는데, 클라이언트는 서버의 URI만 알고 있으면 되기 때문입니다.

#### Stateless

- 무상태성
- 서버에서 클라이언트의 상태 정보를 저장하지 않고 들어오는 요청에 대해서만 처리하여 구현을 단순화 하는 것이다.
- 이러다 보니 클라이언트의 모든 요청은 서버가 요청을 알아듣는데 필요한 모든 정보를 담고 있어여 합니다.
- 세션 상태도 클라이언트 쪽에 보관되어 클라이언트 요청 시 세션을 같이 보내 서버와 같이 데이터베이스와 같은 서비스로 전송되어 일정 기간동안 지속 상태를 유지하여 인증하는데 사용하게 된다.

#### Cacheable

- 캐시 가능
- 즉 요청에 대한 응답 내의 데이터에 해당 요청은 캐시가 가능한지 불가능 한지 명세를 해줘야 합니다.
- 캐시 사용이 가능하면 클라이언트는 응답 데이터를 재사용 할 수 있어야 합니다.
- `cache-control` 헤더를 통해 캐시 여부를 명시해줘야 합니다.
- Last-Modified, E-Tag를 이용하여 캐시 구현이 가능합니다.

#### Uniform Interface

- URI로 지정된 리소스에 균일하고 통일된 인터페이스를 제공해야 한다.

- 아키텍처를 단순하게 분리하여 독립적으로 만들 수 있다는 장점이 있다.

- Resource Identification in Reqeust

  - 요청의 자원식별이라는 의미로 요청 부분에서 개별 자원에 대한 식별을 할 수 있어야 하며 예를 들면 URI가 있다.
  - http://localhost:8080/resource/1
  - 서버는 데이터베이스의 내부 자료를 직접 전송하는 대신, DB의 레코드를 HTML, XML, JSON 등 형태로 전송한다.

- Manipulation of Resources Through Representations

  - 메시지를 통한 자원을 조작한다는 의미로 클라이언트의 요청에 어떤 자원에 대한 적절한 표현과 작업을 수행하기 위한 메타데이터를 충분히 갖추고 있다면 이 것은 서버 상에서 해당 자원을 변경, 삭제할 수 있는 충분한 정보를 가지고 있다는 의미이다.
  - 예를들면 Content-Type: Application/JSON 같은 경우가 된다.

- Self-Descriptive Message

  - 자기 서술적 메시지라는 의미로 각 메시지는 자신을 어떻게 처리해야 하는지 충분한 정보를 포햄해야 한다는 의미입니다.

  - 예를 들어 `GET / HTTP/1.1` 이러한 요청을 보낸다고 했을 때 목적지가 빠져 있기 때문에 이 조건을 충족시키지 못했다.

  - 아래와 같이 나오는 것이 조건을 충족시킨 것이다.

    ```
    GET / HTTP1.1
    Host: localhost:8080
    ```

  - 응답도 똑같다. 아래와 같이 JSON으로 반환했다고 보자.

    ```
    HTTP/1.1 200 OK
    { name: rutgo }
    ```

  - 어떤 데이터 형식인지 알수가 없다. 따라서 아래와 같이 응답을 해줘야 한다.

    ```
    HTTP/1.1 200 OK
    Conent-Type: application/json
    
    { name: rutgo }
    ```

- Hypermedia As The Engine Of Application State(HATEOAS)

  - 애플리케이션 상태에 대한 엔진으로서의 하이퍼미디어
  - 즉, 단순히 결과 데이터만이 아닌 결과 리소스 정보를 포함해야 한다는 의미 입니다.

#### Layered System

- 서버는 중개 서버(게이트웨이, 프록시)나 로드 밸런싱, 공유 캐시 등의 기능을 사용하여 확장성 있는 시스템을 구성할 수 있다.

#### Code-On-Demand(Optional)

- 클라이언트는 서버에서 자바 애플릿, 자바스크립트 실행 코드를 전송받아 기능을 일시적으로 확장할 수 있다.
- 이 제약 조건은 선택 가능합니다.

### 참고자료

[[REST API\] REST API에 관하여_6가지 제약조건](https://sabarada.tistory.com/26)

[REST 제대로 알고 프로젝트에 적용하기](https://daimhada.tistory.com/141)

[REST(REpresentational State Transfer)](https://velog.io/@codemcd/RESTREpresentational-State-Transfer-hgk2muj4l2)



### **RESTful 하게 API 를 디자인 한다는 것은 무엇을 의미하는가.(요약)**

### **리소스 와 행위 를 명시적이고 직관적으로 분리한다.**

- **리소스(정보의 자원)는 `URI`로 표현되는데 리소스가 가리키는 것은 `명사`로 표현되어야 한다.**
- **행위는 `HTTP Method`로 표현하고, `GET(조회)`, `POST(생성)`, `PUT(기존 entity 전체 수정)`, `PATCH(기존 entity 일부 수정)`, `DELETE(삭제)`을 분명한 목적으로 사용한다.**

1. Message 는 Header 와 Body 를 명확하게 분리해서 사용한다.

- Entity 에 대한 내용은 body 에 담는다.
- 애플리케이션 서버가 행동할 판단의 근거가 되는 컨트롤 정보인 API 버전 정보, 응답받고자 하는 MIME 타입 등은 header 에 담는다.
- header 와 body 는 http header 와 http body 로 나눌 수도 있고, http body 에 들어가는 json 구조로 분리할 수도 있다.

1. API 버전을 관리한다.

- 환경은 항상 변하기 때문에 API 의 signature 가 변경될 수도 있음에 유의하자.
- 특정 API 를 변경할 때는 반드시 하위호환성을 보장해야 한다.

1. 서버와 클라이언트가 같은 방식을 사용해서 요청하도록 한다.

- 브라우저는 form-data 형식의 submit 으로 보내고 서버에서는 json 형태로 보내는 식의 분리보다는 json 으로 보내든, 둘 다 form-data 형식으로 보내든 하나로 통일한다.
- 다른 말로 표현하자면 URI 가 플랫폼 중립적이어야 한다.

### **어떠한 장점이 존재하는가?**

1. Open API 를 제공하기 쉽다
2. 멀티플랫폼 지원 및 연동이 용이하다.
3. 원하는 타입으로 데이터를 주고 받을 수 있다.
4. 기존 웹 인프라(HTTP)를 그대로 사용할 수 있다.

### **단점은 뭐가 있을까?**

1. 사용할 수 있는 메소드가 4 가지 밖에 없다.(한정적)
2. 분산환경에는 부적합하다.
3. HTTP 통신 모델에 대해서만 지원한다.





> 여기서 부터는 그대로 옮겼습니다.

[JaeYeopHan/Interview_Question_for_Beginner](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Development_common_sense)

## **TDD**

Test-Driven Development(TDD)는 매우 짧은 개발 사이클의 반복에 의존하는 소프트웨어 개발 프로세스이다. 우선 개발자는 요구되는 새로운 기능에 대한 자동화된 테스트케이스를 작성하고 해당 테스트를 통과하는 가장 간단한 코드를 작성한다. 일단 테스트 통과하는 코드를 작성하고 상황에 맞게 리팩토링하는 과정을 거치는 것이다. 말 그대로 테스트가 코드 작성을 주도하는 개발방식인 것이다.

### **Add a test**

테스트 주도형 개발에선, 새로운 기능을 추가하기 전 테스트를 먼저 작성한다. 테스트를 작성하기 위해서, 개발자는 해당 기능의 요구사항과 명세를 분명히 이해하고 있어야 한다. 이는 사용자 케이스와 사용자 스토리 등으로 이해할 수 있으며, 이는 개발자가 코드를 작성하기 전에 보다 요구사항에 집중할 수 있도록 도와준다. 이는 정말 중요한 부분이자 테스트 주도 개발이 주는 이점이라고 볼 수 있다.

### **Run all tests and see if new one fails**

어떤 새로운 기능을 추가하면 잘 작동하던 기능이 제대로 작동하지 않는 경우가 발생할 수 있다. 더 위험한 경우는 개발자가 이를 미처 인지하지 못하는 경우이다. 이러한 경우를 방지하기 위해 테스트 코드를 작성하는 것이다. 새로운 기능을 추가할 때 테스트 코드를 작성함으로써, 새로운 기능이 제대로 작동함과 동시에 기존의 기능들이 잘 작동하는지 테스트를 통해 확인할 수 있는 것이다.

### **Refactor code**

'좋은 코드'를 작성하기란 정말 쉽지가 않다. 코드를 작성할 때 고려해야 할 요소가 한 두 가지가 아니기 때문이다. 가독성이 좋게 coding convention 을 맞춰야 하며, 네이밍 규칙을 적용하여 메소드명, 변수명, 클래스명에 일관성을 줘야하며, 앞으로의 확장성 또한 고려해야 한다. 이와 동시에 비즈니스 로직에 대한 고려도 반드시 필요하며, 예외처리 부분 역시 빠뜨릴 수 없다. 물론 코드량이 적을 때는 이런 저런 것들을 모두 신경쓰면서 코드를 작성할 수 있지만 끊임없이 발견되는 버그들을 디버깅하는 과정에서 코드가 더럽혀지기 마련이다.

이러한 이유로 코드량이 방대해지면서 리팩토링을 하게 된다. 이 때 테스트 주도 개발을 통해 개발을 해왔다면, 테스트 코드가 그 중심을 잡아줄 수 있다. 뚱뚱해진 함수를 여러 함수로 나누는 과정에서 해당 기능이 오작동을 일으킬 수 있지만 간단히 테스트를 돌려봄으로써 이에 대한 안심을 하고 계속해서 리팩토링을 진행할 수 있다. 결과적으로 리팩토링 속도도 빨라지고 코드의 퀄리티도 그만큼 향상하게 되는 것이다. 코드 퀄리티 부분을 조금 상세히 들어가보면, 보다 객체지향적이고 확장 가능이 용이한 코드, 재설계의 시간을 단축시킬 수 있는 코드, 디버깅 시간이 단축되는 코드가 TDD 와 함께 탄생하는 것이다.

어차피 코드를 작성하고나서 제대로 작동하는지 판단해야하는 시점이 온다. 물론 중간 중간 수동으로 확인도 할 것이다. 또 테스트에 대한 부분에 대한 문서도 만들어야 한다. 그 부분을 자동으로 해주면서, 코드 작성에 도움을 주는 것이 TDD 인 것이다. 끊임없이 TDD 찬양에 대한 말만 했다. TDD 를 처음 들어보는 사람은 이 좋은 것을 왜 안하는가에 대한 의문이 들 수도 있다.

### **의문점들**

### **Q. 코드 생산성에 문제가 있지는 않나?**

두 배는 아니더라도 분명 코드량이 늘어난다. 비즈니스 로직, 각종 코드 디자인에도 시간이 많이 소요되는데, 거기에다가 테스트 코드까지 작성하기란 여간 벅찬 일이 아닐 것이다. 코드 퀄리티보다는 빠른 생산성이 요구되는 시점에서 TDD 는 큰 걸림돌이 될 수 있다.

### **Q. 테스트 코드를 작성하기가 쉬운가?**

이 또한 TDD 라는 개발 방식을 적용하기에 큰 걸림돌이 된다. 진입 장벽이 존재한다는 것이다. 어떠한 부분을 테스트해야할 지, 어떻게 테스트해야할 지, 여러 테스트 프레임워크 중 어떤 것이 우리의 서비스와 맞는지 둥 여러 부분들에 대한 학습이 필요하고 익숙해지는데에도 시간이 걸린다. 팀에서 한 명만 익숙해진다고 해결될 일이 아니다. 개발은 팀 단위로 수행되기 때문에 팀원 전체의 동의가 필요하고 팀원 전체가 익숙해져야 비로소 테스트 코드가 빛을 발하게 되는 것이다.

### **Q. 모든 상황에 대해서 테스트 코드를 작성할 수 있는가? 작성해야 하는가?**

세상에는 다양한 사용자가 존재하며, 생각지도 못한 예외 케이스가 존재할 수 있다. 만약 테스트를 반드시 해봐야 하는 부분에 있어서 테스트 코드를 작성하는데 어려움이 발생한다면? 이러한 상황에서 주객이 전도하는 상황이 발생할 수 있다. 분명 실제 코드가 더 중심이 되어야 하는데 테스트를 위해서 코드의 구조를 바꿔야 하나하는 고민이 생긴다. 또한 발생할 수 있는 상황에 대한 테스트 코드를 작성하기 위해 배보다 배꼽이 더 커지는 경우가 허다하다. 실제 구현 코드보다 방대해진 코드를 관리하는 것도 쉽지만은 않은 일이 된 것이다.

모든 코드에 대해서 테스트 코드를 작성할 수 없으며 작성할 필요도 없다. 또한 테스트 코드를 작성한다고 해서 버그가 발생하지 않는 것도 아니다. 애초에 TDD 는 100% coverage 와 100% 무결성을 주장하지 않았다.

## **MVC 패턴이란 무엇인가?**

[설명 링크](http://asfirstalways.tistory.com/180)를 참고하자! 우리가 기존에 알고 있던 MTV 패턴과 거의 유사하다!

## **Git 과 GitHub 에 대해서**

Git 이란 VCS(Version Control System)에 대해서 기본적인 이해를 요구하고 있다.

- [Git 을 조금 더 알아보자 slide share](https://www.slideshare.net/ky200223/git-89251791)

Git 을 사용하기 위한 각종 전략(strategy)들이 존재한다. 해당 전략들에 대한 이해를 기반으로 Git 을 사용해야 하기 때문에 면접에서 자주 물어본다. 주로 사용되는 strategy 중심으로 질문이 들어오며 유명한 세 가지를 비교한 글을 첨부한다.

- [Gitflow vs GitHub flow vs GitLab flow](https://ujuc.github.io/2015/12/16/git-flow-github-flow-gitlab-flow/)

많은 회사들이 GitHub 을 기반으로 협업을 하게 되는데, (BitBucket 이라는 훌륭한 도구도 존재합니다.) GitHub 에서 어떤 일을 할 수 있는지, 어떻게 GitHub Repository 에 기여를 하는지 정리한 글을 첨부한다.

- [오픈소스 프로젝트에 컨트리뷰트 하기](http://guruble.com/오픈소스-프로젝트의-컨트리뷰터는-어떻게-되는-것/)
- [GitHub Cheetsheet](https://github.com/tiimgreen/github-cheat-sheet)