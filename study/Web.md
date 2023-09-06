[Back to main](/README.md)

# 웹
<details>
<summary> WAS와 WS의 차이 </summary>

- WS는 Web Server의 약어로 클라이언트가 브라우저 주소창에 어떤 url을 입력하여 페이지를 요청하면 http 요청을 받아 들여 정적인 콘텐츠를 사용자에게 전달해주는 것으로 비즈니스 로직을 넣을 수 없음
    - Nginx, Apache 등이 예시 

- WAS는 Web Application Server의 약어로 클라이언트가 브라우저 주소창에 어떤 url을 입력하여 페이지를 요청하면 http 요청을 받아들여 동작함. 웹 서버가 할 수 있는 대부분의 기능 외에도 비즈니스 로직을 처리할 수 있어 사용자에게 동적인 콘텐츠 전달 가능
    - Tomcat, PHP, ASP 등
  

### 사용 이점
- WAS와 WS를 동시에 사용하면 WAS의 부하를 줄일 수 있음

</details>

<details>
<summary> 웹 표준 웹 접근성 </summary>

- 웹 표준은 어떤 환경에서도 이용할 수 있는 웹 페이지를
- 웹 접근성은 어떤 사람이든 이용할 수 있는 웹 페이지를 만들 수 있는 방법

</details>

<details>
<summary> Spring Framework란? </summary>

### Framework란
- 특정 형태의 소프트웨어 문제를 해결하기 위해 상호 협력하는 클래스 프레임과 인터페이스 프레임의 집합
- 개발 시간을 줄일 수 있고 오류로부터 자유로울 수 있다는 장점
- 프레임워크는 개발자의 자유를 제한하기 위한 것으로 프레임워크에 의존하면 개발 능력이 떨어질 수 있음

### Spring Framework란?
- 스프링 프레임워크는 자바 개발을 편리하게 해주는 오픈소스 경량급 프레임워크

</details>

<details>
<summary> Spring의 특징</summary>

- 스프링은 경량 컨테이너로서 자바 객체의 생성, 소멸과 같은 라이프사이클을 관리하며 스프링으로부터 필요한 객체를 얻어올 수 있음
- 스프링의 특징으로는 IoC, DI, AOP가 있음
### IoC
IoC는 제어의 역전, 컨트롤의 제어권이 사용자가 아닌 프레임워크에 있어서 필요에 따라 스프링에서 사용자의 코드를 호출한다는 것, 예시로 @Controller나 @Service 어노테이션을 통해 생성한 bean 객체의 라이프사이클 관리를 개발자가 아닌 스프링 프레임워크가 관리하게끔 함

### DI
DI는 의존성 주입의 약자로 사용할 객체를 직접 생성하지 않고 외부로부터 주입받아 사용하는 것. 이를 통해 객체간의 결합도를 줄이고 코드 재사용성을 높일 수 있음
  - DI는 생성자 주입이 권장되는데 그 이유는?
    - 객체의 불변성을 확보할 수 있고, 순환 참조 에러를 애플리케이션 구동 시점에 파악하여 방지

### AOP
AOP는 관점지향프로그래밍의 약자로 핵심 비즈니스 로직에서 로깅과 같은 공통 관심사항을 분리하여 모듈화하는 것을 의미함, 중복 코드를 제거하고 재활용성을 극대화할 수 있음


</details>

<details>
<summary> Filter와 Interceptor, AOP </summary>
3가지 모두 공통된 로직을 사용하기 위한 것

### Filter
- 요청과 응답을 거른 뒤 정제하는 역할
- 웹 컨테이너에 의해 관리, 스프링 범위 밖에서 처리
- Dispatcher Servlet에 요청이 전달되기 전 / 후에 url 패턴에 맞는 모든 요청에 대해 부가 작업을 처리할 수 있는 기능
- 보안 및 인증/인가 관련 작업 시 사용

### Interceptor
- 요청에 대한 작업 전 / 후에 가로채 요청과 응답을 참조, 가공하는 역할
- 스프링 컨텍스트에서 동작
- Dispatcher Servlet이 Controller를 호출하기 전 / 후에 인터셉터가 요청과 응답을 참조하거나 가공
- API 호출에 대한 로깅, Controller로 넘겨주는 정보의 가공


### AOP
- AOP는 메소드 앞에 Proxy 패턴의 형태로 실행

</details> 

<details>
<summary> Filter, Interceptor, AOP 처리 흐름 </summary>

Filter와 Interceptor는 Servlet 단위에서 실행, AOP는 메소드 앞에 Proxy 패턴의 형태로 실행

- Filter는 스프링 밖에서 실행, Interceptor는 스프링 영역 내 DispatcherServlet 진입 후에, AOP는 메소드 앞에

</details>

<details>
<summary> Interceptor와 AOP의 차이 </summary>

- Interceptor는 Servlet 단위에서 실행
- AOP는 메소드 앞에 Proxy 패턴의 형태로 실행

</details>

<details>
<summary> DispatcherServlet </summary>
디스패처 서블릿이란 서블릿 컨테이너의 가장 앞단에서 HTTP 프로토콜로 들어오는 모든 요청을 먼저 받아 적합한 컨트롤러에 위임해주는 프론트 컨트롤러
</details>

<details>
<summary> Spring과 Spring Boot의 차이 </summary>

- Spring은 Java 기반 오픈 소스 프레임워크이며 대표적인 특징으로 DI, IoC, AOP가 있음
- Spring Boot는 Spring Framework를 사용하기 위한 설정의 많은 부분을 자동화한 프레임워크
  - SpringBootApplication이라는 어노테이션을 사용해 외부 라이브러리, 내장 톰캣 서버를 사용할 수 있는 것이 예시

</details>

<details>

<summary> Bean </summary>

- 스프링 컨테이너에 객체를 생성하면 객체끼리 의존성을 주입할 수 있는데, 이렇게 생성한 객체를 빈 이라고함
- @Component 어노테이션을 클래스 상단에 붙이면 해당 클래스들은 스프링 컨테이너에의해 자동으로 생성되어 스프링 빈으로 등록
- @Configuration 어노테이션을 클래스 선언부에 추가하여 설정 클래스를 만들고, 특정 탕비을 리턴하는 메소드를 만들어 @Bean을 붙이면 빈 객체가 생성됨
- 등록된 빈 객체들은 @Autowired나 @RequiredArgsConstructor를 통해 사용할 수 있음

</details>

<details>
<summary> Bean의 생명주기 </summary>

1. 스프링 IoC 컨테이너 생성
2. 스프링 빈 생성
3. 의존관계 주입
4. 초기화 콜백 메소드 호출
5. 소멸 전 콜백 메소드 호출
6. 스프링 종료

</details>

<details>
<summary> @RequestBody, @RequestParam, @ModelAttribute의 차이 </summary>

### @RequestParam
1개의 HTTP 요청 파라미터를 받기 위해 사용

### @RequestBody
클라이언트가 전송하는 JSON 형태의 HTTP Body 내용을 MessageConverter를 통해 Java 객체로 변환함

### @ModelAttribute
HTTP Body와 HTTP 파라미터의 값들을 생성자, Getter, Setter를 통해 주입하기 위해 사용

</details>

<details>
<summary> Spring MVC 에 대하여</summary>

### Spring MVC란?
- MVC는 Model, View, Controller의 약자로 각 계층별 기능을 구분하는데 중점을 둔 디자인 패턴
- Model은 데이터 관리 및 비즈니스 로직을 처리하는 부분 (DTO, Service)
- View는 비즈니스 로직의 처리 결과를 통해 UI가 표현되는 부분 (html, tymeleaf 등)
- Controller는 사용자의 요청을 처리하고 Model과 View를 중개하는 역할

### Spring MVC 동작 흐름
1. 클라이언트가 URL을 통해 요청을 전송
2. DispatcherServlet이 핸들러 매핑을 통해 해당 요청이 어느 컨트롤러에게 온 요청인지 찾음
3. DispatcherServlet이 핸들러 어뎁터에게 요청의 전달을 맡김
4. 핸들러 어뎁터가 해당 컨트롤러로 요청을 전달
5. 컨트롤러가 비즈니스 로직 처리 후 반환할 뷰의 이름을 반환
6. DispatcherServlet은 뷰 리졸버를 통해 반환할 뷰를 찾음
7. DispatcherServlet이 컨트롤러에서 뷰에 전달할 데이터를 추가
8. 데이터가 추가된 뷰를 반환

#### MVC model1과 model2의 차이
- model1은 JSP 안에 HTML과 Java 코드를 전부 넣어 View와 Controller를 모두 jsp에서 구현하는 구조
- model1로만 처리하기엔 사이트가 방대해져 model2가 나왔음
- model2는 요청 받았을 때와 응답 할 때 처리할 기능을 나누는 것으로 MVC라고 말하는 것은 model2를 의미함

</details>

<details>
<summary> Model 객체 </summary>

- view에 전달할 데이터를 key, Value 형식으로 전달하는 객체

</details>

<details>
<summary> HTTP와 HTTP Stauts </summary>

- HTTP는 서버와 클라이언트간 통신을 위한 통신 규약이다. 사용자가 웹 서버에 http 요청을 전송하고 서버는 사용자에게 http 응답을 응답함
- 응답 시 상태 코드를 통해 요청의 성공 여부를 확인할 수 있음
- 대표적으로 성공을 의미하는 200번대, 클라이언트 오류를 의미하는 400번대, 서버 오류를 의미하는 500번대가 있음

</details>

<details>

<summary> Controller와 RestController의 차이 </summary>

- Spring MVC의 컨트롤러는 @Controller 어노테이션을 적용시키고 RESTful 서비스를 개발 시 @Controller에 @ResponseBody를 합친 RestController를 사용함
- Controller는 View를 반환하기 위해 컨트롤러에서 뷰의 이름을 반환하고 dispatcher servlet이 뷰 리졸버를 통해 뷰를 반환함
- RestController는 컨트롤러에서 View의 이름을 반환하는 것이 아닌 ResponseEntity에 데이터를 담아 JSON 형체로 반환함 
  - Controller 사용 후 return 타입에 @ResponseBody를 붙여 ResponseEntity를 반환하는 것과 흐름이 동일함

</details>

<details>

<summary> REST </summary>

- REST란 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미
- 어떤 자원에 대해 CRUD 연산을 수행하기 위해 URI로 GET, POST 등의 HTTP 메소드를 통해 요청을 보내며, 요청을 위한 자원을 JSON과 같은 특정한 형태로 표현한 것

### 특징
1. Server-Client 구조
  - 자원이 있는 Server, 자원을 요청하는 Client로 나누어 Server가 API 제공, 비즈니스 로직 처리 및 저장을 책임지고 Client가 사용자 인증, 세션 등을 관리하는 것으로 서로의 역할을 구분시켜 의존성을 줄이는 것
2. Stateless (무상태성)
  - HTTP는 Stateless Protocol이기에 HTTP 프로토콜을 그대로 사용하는 REST 또한 무상태성을 가짐
  - 무상태하다는 것은 작업을 위한 상태 정보를 따로 저장하거나 관리하지 않는다는 것으로 클라이언트의 세션, 쿠키의 정보나 이전 api 요청에 대한 결과 등에 대한 영향 없이 api 요청을 처리하면 된다는 것
3. Cacheable (캐시 처리 기능)
  - 웹 표준 HTTP 프로토콜을 그대로 사용하므로 웹에서 사용하는 기존의 인프라를 그대로 활용할 수 있어 HTTP의 캐싱 기능을 적용할 수 있음
  - HTTP 프로토콜 표준에서 사용하는 Last-Modified Tag 또는 E-Tag를 이용해 캐싱을 구현할 수 있음
    - Last-Modified Tag : API 내용이 마지막으로 변경된 시간, 다음에 동일한 API를 요청할 경우 request header 에 if-modified-since 를 함께 보내 마지막 변경 시간을 체크하고 변경되지 않았을 경우 304 Status 코드를 주면서 활용 가능
    - E-Tag: Last-Modified와 방식은 거의 동일하나 시간 대신 Hash값을 사용함. 다음에 동일한 api를 요청할 경우 If-None-Match를 헤더에 추가하여 서버가 동일한 E-Tag를 가질 경우 304 return
    - 304 : Not-Modified
4. Layered System (계층 구조)
  - Client는 REST API 서버만 호출함
  - REST 서버는 다중 계층으로 구성될 수 있어 보안, 암호화 등의 계층을 추가하는 등 구조상 유연성을 가질 수 있고 PROXY 객체를 사용하는 등 중간매체를 사용해도 클라이언트가 알 수 없다는 것
5. Uniform Interface (인터페이스 일관성)
  - URI로 지정한 자원에 대한 요청을 통일되고, 한정적으로 수행하는 아키텍처 스타일
  - 아키텍처가 특정 언어나 기술에 종속되지 않도록 하는 것
6. Self-Descriptiveness (자체 표현)
  - 요청 메시지만 보고도 쉽게 이해할 수 있는 자체 구조로 표현되어 있음


</details>

<details>

<summary> REST API </summary>

- REST의 특징을 기반으로 API를 구현한 것을 REST API라고 함

- REST API 설계 시 가장 중요한 항목은 URI는 정보의 자원을 표현해야하며 자원에 대한 행위는 HTTP Method로 표현해야함. 단 URI에 Method는 포함해서는 안됨

### 설계 규칙
1. URI에 동사가 아닌 명사를 사용해야함
2. 슬래시(/)로 계층 관계를 표현
3. URI 마지막 문자로 슬래시를 포함하지 않음
4. 밑줄 대신 하이픈을 사용함
5. URI는 소문자로만 구성
6. 파일 확장자를 URI에 포함하지 않음
7. 응답 시 Http 응답 상태 코드를 활용하여 해당 요청에 대한 성공, 실패 여부를 알 수 있어야함

### RESTful API란?

- REST의 설계 규칙을 잘 지켜서 설계된 API를 Restful API라고 함
- API는 요청을 보내는 주소만으로 어떤 것을 요청하는지 파악이 가능해야함


</details>




<details>
<summary> Spring Container </summary>

- 스프링 프레임워크의 핵심 컴포넌트
- 스프링 내부에 존재하는 빈의 생명 주기를 관리하며, 생성된 빈에게 추가적인 기능을 제공하는 것


</details>

<details>
<summary> JPA </summary>
JPA는 Java Persistence API의 약어로 RDBMS와 객체의 패러다임 불일치 문제를 해결하기위해 만들어진 ORM 기술의 표준 API

### 이점
1. 생산성 증가 - 오직 객체지향적 접근만 고려하면 됨
2. 유지 보수 유리 - SQL과 JDBC를 모두 처리해야했던 과정을 JPA가 대신 하기에 수정 시 유지보수에 유리함
3. 성능 최적화 기회를 제공함

### 단점
1. 프로젝트의 규모가 크고 복잡하여 설계가 잘못된 경우, 속도 저하 및 일관성을 무너뜨릴 수 있음

### 꼬리질문1 - 패러다임 불일치 문제
OOP 객체에는 추상화, 상속, 다형성 같은 개념이 있지만 DB에는 없음. 서로가 지향하는 목적이 다르고 둘의 기능과 표현 방법 또한 다르기에 이것을 객체와 RDBMS의 패러다임 불일치 문제라고 함 

### 꼬리질문2 - ORM 기술이란?
Object Relational Mapping의 약어로 객체-관계 매핑 기술입니다. DB 데이터와 객체의 필드를 자동으로 매핑시킨다는 것으로, 객체를 통해 DB 데이터를 다룰 수 있음

### 꼬리질문3 - Spring Data JPA와 JPA의 차이
- Spring Data JPA는 JPA 기반 애플리케이션 개발을 보다 간편하게 만드는 라이브러리
- JPA는 EntityManager를 사용해야하지만 Spring Data JPA는 Repository 인터페이스를 통해 구현 가능

### 꼬리질문4 - JPA와 MyBatis 비교
- MyBatis는 Mapper를 작성해야했으나 JPA는 Mapper가 없었고, 대부분 메소드 이름으로 해결할 수 있어 SQL 문을 직접 작성하지 않아도 해결이 가능해 좋았음


</details>

<details>
<summary> 영속성 컨텍스트란 </summary>
영속성 컨텍스트란 엔티티를 영구 저장하는 환경을 의미

### 생명주기
- 영속
  - 영속성 컨텍스트에 저장된 상태
- 준영속
  - 영속성 컨텍스트에 저장되었다가 분리된 상태
- 비영속
  - 영속성 컨텍스트와 전혀 관계 없는 상태
- 삭제
  - 삭제된 상태

### 이점
- 1차 캐시
  - 조회가 가능하며 1차 캐시에 없으면 DB에서 조회하여 1차 캐시로 가져옴
- 동일성 보장
  - == 비교가 가능
- 쓰기 지연
  - 트랜잭션 커밋 전까지 SQL을 바로 보내지 않고 모아서 보낼 수 있음
- 변경 감지 (더티 체킹)
  - 1차 캐시에 들어온 데이터의 최초 상태를 스냅샷으로 저장하고 커밋 시점에 비교하여 updateSQL을 생성
- 지연 로딩
  - 엔티티 안에서 엔티티를 불러올 때 사용 시점에 쿼리를 날려 가져올 수 있음

</details>

<details>
<summary> N+1 문제 </summary>

1번의 쿼리를 날렸을 때 의도하지 않은 N번의 쿼리가 추가적으로 실행되는 것
- 1대다 또는 다대1의 관계를 가진 엔티티를 조회할 때 발생
- JPA Repository로 find 시 실행하는 첫 쿼리에서 하위 엔티티까지 한 번에 가져오지 않고, 하위 데이터를 사용할 때 추가로 조회하기 때문에 발생


### 문제 해결 방법
1. fetch join
   - 미리 두 테이블을 Join하여 한번에 모든 데이터를 가져오는 방법
   - JPQL을 사용하여 두 테이블을 JOIN하는 쿼리를 직접 작성하는 것
2. Entity Graph
   - @EntityGraph 어노테이션을 사용하여 attributePaths에 같이 조회할 연관 엔티티명을 적어서 해결

#### fetch join vs Entity Graph
Fetch join은 inner join, Entity Graph는 outer join을 기본으로 함
- 기본적으로 outer join보다 inner join이 성능 최적화에 유리하기 때문에 fetch join이 더 많이 사용됨


</details>

<details>
<summary> fetch join </summary>

- 미리 두 테이블을 Join하여 한번에 모든 데이터를 가져오는 방법
- JPQL을 사용하여 두 테이블을 JOIN하는 쿼리를 직접 작성하는 것
- Inner join을 기본으로 함

### 단점
- 쿼리 한번에 모든 데이터를 가져오기 때문에 JPA가 제공하는 Paging API 사용 불가능(Pageable 사용 불가)
  - JPQL 작성 시 CountQuery를 직접 명시하고 이후 OOM 방지를 위해 batchSize를 설정하여 사용할 수 있음
    - bathcSize: 설정한 사이즈만큼 데이터를 끌어와서, 컬랙션이나, 프록시 객체를 한꺼번에 IN쿼리를 이용해서 조회하는 것, 100 ~ 1000이 적당
    - 데이터 사이즈를 확실하게 알 수 없으면 안좋은 방법일 수 있음
- 1:N 관계가 두 개 이상인 경우 사용 불가
  - 대상 컬렉션 객체를 Set으로 설정하면 가능
- 패치 조인 대상에게 별칭 부여 불가능
- 쿼리문을 직접 작성해야함

- fetch join 시 카테시안 곱 문제의 방지를 위해 JPQL 작성 시 DISTINCT를 추가하여 중복을 제거하거나 OneToMany의 필드 타입을 Set으로 선언하여 중복을 제거하는 방법을 사용할 수 있음

</details>

<details>
<summary> Entity Graph </summary>

- @EntityGraph 어노테이션을 사용하는 방법
- 어노테이션 속성 중 attributePaths에 같이 조회할 연관 엔티티명을 적고 ,로 여러 개를 한번에 할 수도 있음
- Fetch join과 동일하게 JPQL을 사용해 Query문을 작성하고 필요한 연관관계를 EntityGraph에 설정
- outer join이 기본적임

</details>

<details>
<summary> Fetch Join과 EntityGraph 의 카테시안 곱 </summary>

카테시안 곱: 두 테이블 사이 유효 join 조건을 적지 않았을 때 해당 테이블에 대한 모든 데이터를 전부 결합하여 테이블에 존재하는 행 갯수를 곱한만큼의 결과 값이 반환되는 것
- 카테시안 곱은 JPA 기능의 문제가 아니라 쿼리의 표현에서 발생하는 문제
- Join 명령 시 명확한 Join 규칙이 주어지지 않았을 때 발생

### 해결방법
- JPQL에 DISTINCT를 추가하여 중복 제거
- OneToMany의 필드 타입을 Set으로 선언하여 중복 제거
  - 순서 보장이 필요한 경우 LinkedHashSet을 사용

</details>

<details>
<summary> @Transactional </summary>

### 동작원리
- Transactional을 메소드 또는 클래스에 명시하면, AOP를 통해 Target 객체를 상속한 Proxy 객체가 생성되며 Proxy 객체의 메소드를 호출하면 Target 메소드 전 후로 트랜잭션 처리를 수행

</details>

<details>
<summary> SSR과 CSR </summary>

### SSR
Server Side Rendering
- 서버쪽에서 렌더링 준비를 끝마친 상태로 클라이언트에 전달
- 서버에서 이미 렌더 가능한 상태로 클라이언트에 전달, JS가 다운로드 되는 동안 사용자가 무언가를 보고 있을 수 있음

### CSR
Client Side Rendering
- 렌더링이 클라이언트 쪽에서 일어남
- 서버는 요청을 받으면 클라이언트에 HTML과 JS를 보냄, 클라이언트는 그것을 받아 렌더링을 시작
- 서버에서 처리 없이 클라이언트로 보내기에 JS가 모두 다운로드되고 실행이 끝나기 전까지 사용자는 빈 화면을 보아야함

### 차이
- 첫페이지 로딩 시간
  - SSR이 더 빠름. CSR은 모두 다운로드 된 이후에 첫 페이지가 나오기 때문
- 나머지 로딩 시간
  - CSR이 더 빠름. SSR은 매번 새로 로딩, CSR은 이미 로딩이 완료된 상태에서 바꾸는 것

### 권장
- SSR
  - 네트워크가 느릴 때
  - 메인 스크립트가 크고 로딩이 매우 느릴 때
  - 최초 로딩이 빨라야하는 사이트
- CSR
  - 네트워크가 빠를 때
  - 사용자에게 보여줘야 하는 데이터의 양이 많을 때
  - 웹 어플리케이션에 사용자와 상호작용할 것들이 많을 때

</details> 

<details>
<summary> Spring Security란?  </summary>
Spring 기반의 애플리케이션의 보안을 담당하는 스프링 하위 프레임워크

- 인증과 인가에 대한 부분을 Filter 흐름에 따라 처리

### 꼬리질문1 - 인증과 인가란 무엇인가
- 인증: 해당 사용자가 본인이 맞는지 확인하는 것
- 인가: 인증된 사용자가 요청한 자원에 접근 가능한지를 결정하는것
- 인증 성공 후 인가가 이루어질 수 있음

</details>

<details>
<summary> annotation </summary>

- 사전적 의미로 주석이며, 코드 사이 사이에 작성해 특별한 의미, 기능을 수행하도록 하는 기술
- @ 기호와 함께 사용
- @Controller, @Service

</details> 

<details>
<summary> Spring Scope </summary>

빈이 존재할 수 있는 범위
- 싱글톤: 기본 스코프
  - 스프링 컨테이너의 시작부터 종료까지 유지되는 가장 넓은 범위의 스코프
- 프로토타입: 빈의 생성과 의존관계 주입까지만 관여하고 더는 관리하지않음
- 웹 스코프
  - request: 웹에 요청이 들어오고 나갈때까지 유지
  - session: 웹 세션이 종료될때까지 유지
  - application: 웹의 서블릿 컨텍스트와 같은 범위로 유지되는 스코프

</details> 

<details>
<summary> 롬복 라이브러리 </summary>

어노테이션을 통해 공통된 코드의 작성을 줄여주는 라이브러리

</details> 


<!-- 
<details>
<summary> </summary>


</details> 
-->