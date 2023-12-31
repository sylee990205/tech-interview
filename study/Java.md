[Back to main](/README.md)

# Java
<details>
<summary> Java의 특징 </summary>
Java는 객체지향 프로그래밍 언어로 기본 자료형을 제외한 모든 요소들이 객체로 표현됩니다.

- 객체 지향 개념의 특징인 캡슐화, 상속, 다형성이 잘 적용된 언어
- 장점
  - 자바는 자바 프로그램이 실행되는 동안 운영체제를 대신하는 자바 가상 머신 JVM 위에서 동작하기에 운영체제에 독립적이다
  - GabageCollector를 통한 자동적인 메모리 관리 가능
- 단점
  - JVM 위에서 동작한다는 것은 큰 장점이지만 JVM 위에서 동작하기때문에 다른 언어에 비교하여 실행 속도가 느리다는 단점이 있다
  - 다중 상속이나 타입에 엄격하며 제약이 많음

### 꼬리질문
- 방금 말씀하신 객체 지향 개념의 특징을 설명해주세요
  - 캡슐화
    - 객체 내부의 속성이나 행위를 외부에서 직접 접근할 수 없게 하는 것
    - private 멤버변수, getter/setter

  - 상속
    - 자식 클래스에서 부모 클래스로부터 부모의 모든 자원을 물려 받는 것을 의미
    - 상속을 통해 비효율적인 코드 중복을 피할 수 있고, 부모 클래스의 수정을 통해 자식 클래스 전체가 수정되기때문에 유지보수가 편리함
      ### 꼬리질문2
        - 자바는 다중상속을 지원하지않는데 그 이유는? 그리고 인터페이스는 지원하는데 왜 가능?
          - 다중상속의 경우 하나의 클래스가 여러 상위 클래스를 상속받는 것을 말하는데 여러 상위 클래스에 동일한 이름의 메소드가 있을 때 하위 클래스에서 어떤 메소드를 사용해야하는지 알 수 없는 문제가 발생해 자바에서는 다중상속을 지원하지않는것입니다.
          - 인터페이스는 구현체가 없기때문에 가능합니다.
    - 예시: Spring Data JPA를 사용하면 Repository에서 JpaRepository를 상속하여 우리가 직접 기능을 정의하지않아도 CRUD, Paging 등의 기능을 사용할 수 있는 것
  - 추상화
    - 클래스들의 공통적인 요소를 뽑아서 상위 클래스를 만들어내는 것
    - 즉, 공통적인 속성과 기능을 정의함으로써 코드의 중복을 줄이는 것
    - 자바에서의 예시로는 추상클래스와 인터페이스가 있음
    - 단점: 자바는 다중상속을 지원하지 않기 때문에 추상화를 사용하면 상속에 제한이 생길 수 있음, 자식 클래스에서 부모의 모든 기능을 사용하지 않아도 가지고 있어야한다는 것
  - 다형성
    - 하나의 객체나 메소드가 여러가지 다른 형태를 가질 수 있는 것
    - 오버라이딩과 오버로딩이 그 예시
</details>

<details>
<summary> JVM의 역할 </summary>

- JVM은 스택 기반으로 동작

- Java Byte Code를 OS에 맞게 해석해주는 역할

- 가비지컬렉션을 통해 자동적인 메모리 관리
</details>

<details>
<summary> Java의 컴파일 과정 </summary>

- 개발자가 확장자명이 .java인 자바 파일을 생성하여 build
- java compiler에 의해 확장자명 .class인 자바 바이트코드를 생성
- Class Loader를 통해 JVM 메모리 내로 로드
- 실행엔진을 통해 컴퓨터가 읽을 수 있는 기계어로 해석

</details>

<details>
<summary> Java에서 제공하는 원시 타입, 각각 몇 바이트? </summary>

- 정수형 byte(1), short(2), int(4), Long(8)
- 실수형 float(4), double(8)
- 문자형 char(2)
- 논리형 boolean(1)
</details>

<details>
<summary> 오버라이딩과 오버로딩 </summary>

- 오버라이딩은 상위 클래스의 메소드를 하위 클래스의 메소드에서 재정의하는것
  - toString, 상속
- 오버로딩은 같은 이름의 메소드를 매개변수의 타입과 갯수를 다르게하여 여러개 정의하는것
  - 생성자 오버로딩(매개변수 없는 경우, 모든 매개변수가 있는 경우)
</details>

<details>
<summary> 객체지향 프로그래밍에 대해 설명 </summary>

- 객체지향 프로그래밍은 현실세계에 존재하는 모든 사물을 객체로 보고, 프로그래밍 구현 시 프로그램에 필요한 객체를 파악하고 그 상태와 행위를 가진 객체를 만들어 각각 객체들의 역할이 무엇인지 정의하여 객체들 간의 상호작용을 통해 프로그램을 만드는 것
- 기능이 아닌 객체가 중심으로 누가 무엇을 할것인가를 정의하는 것입니다.
- 특징으로는 캡슐화, 상속, 다형성, 추상화 등이 있고 모듈을 재사용할 수 있다는 장점이 있어 확장 및 유지보수가 용이합니다.
</details>


<details>
<summary> try-with-resources </summary>

- try-catch-finally의 문제점을 보완하기 위해 나온 개념
- try() 안에 자원 객체를 전달하면 try 블록이 끝나고 자동으로 자원을 해제해주는 기능입니다.
- 따로 finally 문을 작성하지 않아도 됩니다.

</details>

<details>
<summary> 불변 객체가 무엇인지 설명하고 대표적인 Java의 예시 </summary>

- 불변 객체란 객체가 생성된 이후 내부의 상태가 변하지 않는 객체
- Java에서는 원시 타입의 경우 final 키워드를 사용해 불변객체를 만들 수 있고 참조 타입일 경우엔 추가적인 작업이 필요함
- 참조타입일 경우 배열을 예시로 들면 배열을 받아 copy해서 저장하고, getter를 clone으로 반환하여 불변 객체를 만들 수 있습니다.
- 리스트도 마찬가지로 내부를 복사하여 전달하는데 이를 방어적 복사라고 합니다.
- 불변객체는 Thread-safe하여 병렬 프로그래밍에 유용하며, 동기화롤 고려하지 않아도 됩니다.
  - Thread-safe 하다는 것은?
    - Thread는 프로그램의 독립적인 실행 흐름, 여러 작업을 동시에 처리하기 위해 사용
    - Thread-safe는 멀티쓰레드 프로그래밍 환경에서 사용되는 용어로 어떤 자원에 여러 쓰레드가 동시에 접근해도 프로그램 실행에 문제가 없는 상태를 의미합니다.
- 메소드 호출 시 파라미터 값이 변하지 않는다는 것을 보장할 수 있습니다
- 가비지 컬렉터가 스캔하는 객체의 수가 줄기때문에 가비지 컬렉션 성능을 높일 수 있습니다. 
</details>

<details>
<summary> 동기화, 비동기화 </summary>

### 동기화
- 한 자원에 동시에 접근하는 것을 제한
- 동시 접근이 불가능하기때문에 순차적으로 접근
- 다음 실행 명령은 현재 실행 중인 명령이 종료될 때까지 대기

### 비동기화
- 현재 실행 중인 명령이 종료되지 않아도 다음 명령을 실행할 수 있는 것
- Ajax 등이 있음

</details> 

<details>
<summary> Synchronized </summary>
멀티 쓰레드 환경에서 사용되는 키워드로 동기화

- 하나의 쓰레드에서 자원을 사용하고 있다면 다른 쓰레드에서 접근하는 것을 막아 교착 상태를 방지하는 키워드
- 데이터의 Thread-safe를 위해 자바에서 제공하는 키워드
- 변수와 메소드에 사용할 수 있음
- 키워드를 너무 많이 사용하면 동기화 요청이 너무 많아져 성능 저하가 될 수 있어 적절히 사용해야함


</details>

<details>
<summary> 추상 클래스와 인터페이스는 각각 무엇이고 그 차이는 무엇인가? </summary>

- 추상 클래스는 클래스 내에 메소드에 선언부만 있고 구현부가 없는 추상메소드가 하나 이상 포함하는 클래스를 추상 클래스라고 합니다.
- 인터페이스는 모든 메소드가 추상 메소드로 이루어진것
### 공통점
- new 연산자로 인스턴스 생성 불가
- 사용을 위해 하위 클래스에서 확장 / 구현
### 차이점
- 추상 클래스는 클래스 내에 변수, 구현부가 있는 메소드가 존재할 수 있지만 인터페이스는 불가능
- 추상클래스는 다중상속이 불가능, 인터페이스는 가능
</details>

<details>
<summary> 싱글톤 패턴 </summary>

- 단 하나의 인스턴스를 생성해 사용하는 디자인 패턴
- 인스턴스가 1개만 존재해야 한다는 것을 보장하고 싶은 경우와 동일한 인스턴스를 자주 생성해야하는 경우 메모리 낭비 방지를 위해 주로 사용

</details>

<details>
<summary> 가비지 컬렉션 </summary>

- Java의 메모리 구조 중 Heap 메모리 영역에 동적 할당되었으나 더이상 참조되지 않는 대상을 탐지하여 메모리에서 해제하는 JVM의 기능
  - 왜 Heap 영역인가? -> 객체가 새로 생성되면 Heap 영역에 되기때문
  - 더이상 참조되지않는다는 것 객체가 null 이 되는 것
- 개발자가 코드로 호출할 필요 없이 JVM이 백그라운드에서 자동적으로 수행

### 장점
- 개발자가 동적으로 할당한 메모리 영역을 관리하지 않아도 되며 메모리 누수 등의 버그를 줄일 수 있음
  
### 단점
- 어떤 메모리를 해제할지 결정하는데 추가 비용 발생
- 메모리를 해제하는 시점이나 점유 시간을 예측할 수 없음
  - 프로그램이 예측 불가능하게 일시적으로 정지할 수 있다는 단점
</details>

<details>
<summary> 객체지향의 설계원칙 </summary>

객체 지향의 설계 원칙은 SOLID 라고 함
### S
SRP 단일 책임의 원칙
- 하나의 클래스는 하나의 책임을 가져야하며, 변경 또한 하나의 이유를 가져야함
### O
OCP 개방 폐쇄의 원칙
- 클래스는 확장에는 개방적이고 변경에는 폐쇄적이여야함
### L
LSP 리스코프 치환의 원칙
- 하위 타입의 객체는 상위 타입의 객체에서 가능한 행위를 수행할 수 있어야함
- 즉 하위 타입은 상위 타입으로 대체될 수 있어야함
### I
ISP 인터페이스 분리의 원칙
- 인터페이스는 최소한의 기능을 가져야 한다는 원칙
- SRP와 동일한 개념으로 SRP는 클래스 ISP는 인터페이스가 그 대상이 된다는 것
### D
DIP 의존관계 역전의 원칙
- 구현클래스에 의존하지말고 보다 추상적인 클래스 (인터페이스)에 의존해야한다는 것

</details>

<details>
<summary> 자바의 메모리 영역 </summary> 

- 자바의 메모리영역은 크게 모든 스레드가 공유해서 사용하는 메소드영역, 힙영역
- 스레드 별로 하나씩 생성되는 스택영역, PC 레지스터, 네이티브 메서드 스택으로 구분됨
  - 메소드 영역은 static 변수, final 클래스 등이 생성되는 영역,  JVM이 동작해서 클래스가 로딩될 때 생성
  - 힙 영역 new 키워드로 생성된 객체와 배열 등이 생성되는 영역, 런타임시 할당
    - GC가 사용하지않는 인스턴스를 감지해 메모리를 관리하는 영역
  - 스택영역은 지역 변수, 파라미터, 리턴 값 등이 생성되는 영역, 컴파일 타임 시 할당
  - PC 레지스터는 현재 스레드가 실행되는 부분의 주소와 명령을 저장하고 있는 영역
  - 네이티브 메서드 스택
    - 자바 이외의 언어로 작성된 네이티브 코드를 실행할 때 사용되는 메모리 영역

</details>

<details>
<summary> 람다식 </summary>
함수형 프로그래밍 기법, 메서드를 하나의 식으로 표현하는 방식

### 람다식의 장점
코드의 간결성과 가독성을 높일 수 있음

### 람다식 구현 방법
- 매개변수 -> 구현부로 이용하여 사용
- 구현부가 단일 실행문이면 {} 실행 가능
- 단일문이 return문만이면 괄호를 생략 가능

### 익명함수란
- 이름이 붙지 않고 프로그램에서 일시적으로 한번만 사용되고 버려지는 객체
- 재사용성이 없음
- 일시적으로 한번만 사용되어야 하는 객체의 경우 사용

</details>

<details>
<summary> 제네릭 </summary>
클래스나 메서드에서 사용될 데이터 타입을 미리 지정하지 않고 실행 시점에 결정할 수 있도록 하는 기술

- List가 그 예시, List에 담기는 객체를 그 때 그 때 지정해서 사용하는 것
- <> 괄호로 사용할 수 있음
- 제네릭은 괄호 내부에 식별자 기호를 지정해서 사용할 수 있는데 이 때 식별자를 타입 매개변수라고 하며 T로 사용함
### 타입 매개변수
- 제네릭을 이용한 클래스나 메소드 설계 시 사용
- jdk 1.7 버전 이후부터 new 생성자 부분의 제네릭 타입 생략 가능 -> 제네릭 나름 타입 추론을 하여 생략된 곳을 넣어주기 때문
- 타입 파라미터에 할당 가능한 타입은 Reference 타입 뿐
- Wrapper 클래스 (Integer, Double 등)이 이때 사용됨
- 제네릭 내부에 타입은 여러개 지정할 수 있음
### 제네릭 사용 이유와 이점
- 컴파일 시 타입 검사를 통해 예외 방지
- 불필요한 캐스팅을 없애 성능 향상

</details>

<details>
<summary> 예외처리 </summary>
  
  - 예외란 실행 도중 발생한 비정상적인 상황을 말하며 예외 처리를 통해 프로그램이 비 정상적으로 종료되지 않도록 처리 가능
  - try-catch-finally 구문을 사용하거나 throws 예외 타입을 메서드 선언부에 추가
  - ExceptionHandler를 통해 전역적으로 처리하는 방법 등이 있음

</details>

<details>
<summary> Error와 Exception의 차이 </summary>

- Error는 실행 중 일어날 수 있는 치명적인 오류로 컴파일 시점에서 체크할 수 없고, Error 발생 시 프로그램이 비정상 종료됨
- Exception은 Error보다는 비교적 경미한 오류이며, 예외처리를 통해 프로그램의 비정상 종료를 막을 수 있는 것


</details>

<details>
<summary> throw, throws 차이 </summary>

- throw: 개발자가 의도적으로 예외를 던지는것
- throws: 메소드 뒤에 붙여 예외 처리를 하는 것

</details>

<details>
<summary> CheckedException과 UnCheckedException의 차이</summary>

- CheckException은 실행 전 예측 가능한 예외를 말하며 반드시 예외 처리를 해야함. 대표적으로 IOException이 있음
- UnCheckException은 실행 중 발생할 수 있는 예외를 말하며, 반드시 예외 처리를 해야하는 것은 아님. 대표적으로 NullPointerException이 있음
- RuntimeException을 상속하여 CustomException을 구현한다면 UnCheckedException이 됨


</details>

<details> 
<summary> 클래스와 객체의 차이 </summary>

- 클래스는 객체를 만들어내기 위한 설계도로 객체를 생성하는데에 사용됨
- 객체는 클래스를 기반으로 생성된 것
- 객체에 메모리가 할당되어 실제로 활용되는 실체를 인스턴스 (소프트웨어 내로 들어오면 인스턴스)

</details>

<details>
<summary> Wrapper Class란 무엇이며, Boxing 과 UnBoxing은 무엇인가 </summary>

- 자바의 원시타입, 기본 자료형 int, long 등을 객체로 표현한 것을 Wrapper Class라고 함
- 기본 자료형을 Wrapper class로 변환하는 것을 Boxing 그 반대를 UnBoxing 이라고 함
### 꼬리질문
Wrapper Class를 왜 사용하는가?
- 자바의 원시타입은 null 값이 들어갈 수 없음, 또한 이들은 참조 객체가 아니기 때문에 제네릭 구문 내에 사용할 수 없음
  - 제네릭의 < > 안에는 참조 객체만 들어갈 수 있기때문
- 그래서 이를 위해 Wrapper Class를 사용

</details>

<details>
<summary> Stream </summary>

- 자바8에서 추가된 람다를 활용할 수 있는 기술 중 하나
- 자바 8 이전에는 배열이나 컬렉션 인스턴스를 다루기 위해 for문이나 foreach 문을 돌면서 요소를 하나하나 꺼내서 다루었어야함
- 이를 람다식을 활용하여 보다 간결하게 표현할 수 있게 하는 것
- forEach, filter, map 등이 있음

</details>
<details>
<summary> JRE와 JDK의 차이 </summary>

#### JRE
- java runtime environment 로 자바 프로그램을 실행시키는 환경
- read only

#### JDK
- java development kit 로 자바를 활용해서 개발하는데 사용, jdk는 jre를 포함하고 있다
- write, read only
</details>

<details>
<summary> Call by Value / Call by Reference </summary>

- 메소드의 매개변수 호출 방식
- Call by value는 값을 전달하는 것으로 a 메소드에서 보낸 값을 b에서 변경한다고 해도 a 메소드가 가지고 있던 본래의 값이 변화하지 않음
- Call by reference는 객체의 참조값, 주소를 전달하는 것으로 a 메소드에서 보낸 객체를 b 메소드에서 변경하면 a 메소드가 가지고 있던 본래의 값 또한 변경되는 것

</details>

<details>
<summary> static </summary>
고정된 이라는 의미를 가짐, 메모리에 한번 할당되어 프로그램이 종료될 때 해제되는 것

- static 키워드는 변수나 메소드에 사용할 수 있습니다
- 클래스가 메모리에 올라갈 때 자동으로 생성되며 클래스 로딩이 끝나면 바로 사용 가능합니다. 즉 인스턴스 생성 없이 사용 가능하다는 것
- 메소드 영역에 생성되기 때문에 GC의 관리를 받지 않고 프로그램이 종료될 때까지 메모리에 값이 유지된 채로 존재하게 됨

#### 사용하는 이유
- 자주 변하지 않는 값이나 공통으로 사용되는 값인 공용 자원에 접근 시 매번 메모리에 로딩하고 값을 읽어들이는 것보다 비용을 줄이고 효율을 높일 수 있음
- 인스턴스 생성 없이 바로 사용 가능하여 프로그램 내에서 공통으로 사용되는 데이터들을 관리할 때 이용
  #### 예시
  - Controller 반환 시 ResponseEntity 를 사용했는데 그 때 body에 보낼 내용을 CommonResponse에 담아서 보냈다. 그 때 CommonResponse 클래스 내 toResponse라는 static 메소드를 사용하여 CommonResponse 인스턴스를 생성하지않고 바로 body에 담아 보낼 수 있었음
</details>

<details>
<summary> collection </summary>

- 배열 사용 시 크기가 고정적이고 데이터 삭제 시 해당 인덱스의 데이터가 비면서 메모리가 낭비되는 등의 문제점이 있었음
- 이러한 문제없이 다수의 데이터를 효율적으로 관리하고자 만들어진 자료구조들이 있는 프레임워크
- collection framework에는 List, Set, Map 등이 있음

### List
- 순서가 있는 데이터의 집합, 데이터의 중복을 허용, 대표적인 구현체로 ArrayList, LinkedList, Vector
#### LinkedList?
- 각 노드가 데이터와 포인터를 가지고 한 줄로 연결되어 있는 방식의 자료구조
- 데이터의 추가 / 삭제가 많은 경우 사용
  - 데이터를 추가하거나 삭제할 때 인덱스가 변경되는 일이 없음
  - 검색 시 인덱스가 없어 탐색 속도가 떨어질 수 있음

#### Vector?
Vector는 동기화된 메소드로 구성되어있어, 멀티 스레드가 동시에 메소드를 실행할 수 없음
- 멀티스레드 환경에서 안전하게 객체를 추가, 삭제할 수 있음
- 스레드가 1개일때도 동기화를 하기 때문에 ArrayList보다 성능이 떨어짐


### Set
- 순서가 없는 데이터의 집합, 데이터의 중복 비허용, 대표적인 구현체로 HashSet, 순서를 보장하기 위해 LinkedHastSet을 사용할 수 있음

### Map
- 키와 값이 한 쌍으로 이루어져 있고, 순서가 없는 데이터,  키를 기준으로 중복을 허용하지 않음, 대표적인 구현체로 HastMap이 있고 순서를 보장하기 위해 LinkedHastMap을 사용할 수 있음
 

</details>

<details>
<summary> optional </summary> 
  
- 개발 시 가장 흔히 발생하는 예외 중 하나인 NullPointerException을 피하기 위해 null 검사를 해야하는데 그에 대한 처리를 모두 작성하면 코드가 복잡해질 수 있음
- Optional 클래스를 사용해 NPE를 방지할 수 있도록 함
- null이 올 수 있는 값을 감싸는 Wrapper 클래스

- Optional.empty, 등등이 있지만 가장 많이 사용한 것은 Optional.get.orElseThrow, 예외가 발생할 때의 처리를 해줄 수 있음

- Optional을 너무 많이 사용하면 시스템 성능이 저하되기 때문에 결과가 null이 될 수 있으며 그로 인해 오류가 발생할 가능성이 매우 높을 때만 잘 사용해야함

</details>

<details>
<summary> new String과 ""(리터럴 문자열)의 차이 </summary>

- new String()은 new 키워드로 새로운 객체를 생성하기때문에 메모리 Heap영역에 저장됨
- 리터럴 문자열은 Heap 안에 있는 String Pool 영역에 저장됨

</details>

<details>
<summary> String, StringBuffer, StringBuilder </summary>

셋 모두 문자열을 표현하는 객체 타입
- String은 불변 객체이고, StringBuffer와 StringBuilder는 가변의 속성을 가짐
- StringBuffer는 동기화를 지원하여 멀티 쓰레드 환경에서 주로 사용하며
- String Builder는 동기화를 지원하지 않아 싱글 쓰레드 환경에서 주로 사용

#### String은 왜 불변객체?
- String 객체들은 Heap의 String Pool 이라는 공간에 저장되는데 참조하려는 문자열이 String Pool에 존재하는 경우 새로 생성하지 않고 Pool 내의 객체를 사용함

</details>

<details>
<summary> 직렬화 </summary>

시스템 내부에서 사용되는 객체 또는 데이터를 외부의 시스템에서도 사용할 수 있도록 바이트 형태로 데이터를 변환하는 것

### 역직렬화
직렬화된 바이트 형태의 데이터를 다시 객체로 변환하는 과정

### 꼬리질문1 - 자주 변경되는 코드라면 직렬화를 하는 것이 좋은가?
- 아니다.
- 역직렬화의 경우 타입에 민감하기때문에 자주 변경되는 코드라면 직렬화를 안하는 것이 좋음

 </details>


<details>
<summary> 리플렉션 </summary>
구체적인 클래스 타입을 알지 못해도 그 클래스의 메소드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API

### 어떠한 경우에 사용되는가?
코드 작성 시점에는 어떤 타입의 클래스를 사용할지 모르지만, 런타임 시점에 지금 실행되고 있는 클래스를 가져와서 실행해야 하는 경우 사용
- ex) 스프링의 어노테이션, IDE의 자동완성기능

 </details>

<details>
<summary> 접근제어자 </summary>

- public
  - 전체
- protected
  - 같은 패키지와 자손 클래스
- default
  - 같은 패키지
- private
  - 같은 클래스


</details>

<details>
<summary> 쓰레드와 프로세스 </summary>

- 프로세스는 메모리 상에서 실행중인 프로그램
- 쓰레드는 이 프로세스 안에서 실행되는 흐름 단위

</details>

<details>
<summary> Java 8 </summary>

- 인터페이스 내에서 static과 defalut 메소드 사용 가능
- 람다식 추가
- stream 추가

</details>

<details>
<summary> Hash table과 Hash map </summary>

- Hash: 데이터를 다루는 기법 중 하나
- Hash 함수: 데이터를 효율적으로 관리하고자 임의의 길이의 데이터를 고정된 길이의 데이터로 매핑
- Key Value 값으로 매핑되는 과정을 해싱

### 해시 테이블과 해시 맵
- 해시 테이블과 해시 맵 모두 키, value 값을 사용하여 값을 저장, 조회하지만
- hash table은 null 값을 허용하지 않고
- hasp map은 null 값을 허용한다는 차이


</details> 


<details>
<summary> DAO, DTO, VO </summary>

- DAO : DB에 접근하기 위한 객체
- DTO : 계층간 데이터 교환을 위한 객체
- VO: 계층간 데이터 교환을 위해 사용되나 getter 기능만 존재

</details> 

<details>
<summary> inner class </summary>

클래스 내부에 또 하나의 클래스를 만든 것
- 외부 클래스에서는 내부 클래스를 객체화하여 객체로 클래스 내의 자원을 사용할 수 있음
- 내부 클래스에서는 외부 클래스의 자원을 직접 사용 가능

### 왜 사용하는가?

- 서로 관련 있는 클래스를 논리적으로 묶어서 표현함으로써 캡슐화를 증가시키고 코드 복잡성을 낮출 수 있음

</details> 

<details>
<summary> Servlet </summary>

클라이언트의 요청을 처리하고, 그 결과를 동적인 웹 페이지를 생성하며 반환하는 자바 웹 프로그래밍 기술
- Spring MVC에서 Controller로 이용되며, 사용자의 요청을 받아 처리한 후 결과를 반환

- 자바를 사용해 웹을 만들기 위해 필요한 기술
  
### 동작 방식
1. 사용자가 URL을 입력하면 HTTP Request가 Servlet Container로 전송
2. 요청 받은 컨테이너는 HttpServletRequest, HttpServletResponse 객체를 생성
3. web.xml을 기반으로 요청한 URL이 어느 서블릿에 대한 요청인지 찾음
4. 해당 서블릿에서 service 메소드 호출 후 GET, POST 여부에 따라 doGet, doPost를 호출
5. doGet, doPost 메소드는 동적 페이지를 생성한 후 HttpServletResponse 객체에 응답을 보냄
6. HttpServletRequest, HttpServletResponse 두 객체를 소멸

</details> 

<details>
<summary> SerialVersionUID </summary>

- 직렬화 시 Class의 버전 아이디를 설정하는 것
- 직접 설정하지 않을 시 컴파일러가 계산한 값을 부여함
- 컴파일러는 SerialVersionUID 설정 시 Serializable class 혹은 Outer Class를 참고하여 만들기 때문에 클래스 변경 시 UID가 변경될 수 있음
- 따라서 직렬화 시와 역직렬화 시 SerialVersionUID가 다름에서 오는 예외가 발생할 수 있기때문에 직접 지정해야함

</details> 

<details>
<summary> JSP란? </summary>

Java Server Page의 약어
- 하나의 파일 내 동적으로 처리하려는 부분을 JSP의 태그와 Java 코드를 삽입하여 웹 컨텐츠를 구현하는 HTML과 함께 구현하는 기술
- 실행 시 Java Servlet으로 변환된 후 실행


</details> 

<details>
<summary> MyBatis란? </summary>

- Object Mapping 기술로 자바에서 SQL Mapper를 지원해주는 프레임워크
- SQL을 직접 작성하여 객체와 매핑시키는 것으로 ORM과 다르다
  
### SQL Mapper
- SQL문을 사용하여 RDB에 접근하고, 데이터를 객체화함

### 장점
- SQL문을 잘알고 사용할 수 있다면 간단히 사용할 수 있다는 장점
- 동적 쿼리 구현이 가능함

### 단점
- DB 설정 변경 시 많은 부분을 직접 수정해야함
- Mapper 작성부터 인터페이스 설계까지 JPA보다 많은 설계와 파일, 로직이 필요

</details> 

<!-- 
<details>
<summary> </summary>

</details> 
-->