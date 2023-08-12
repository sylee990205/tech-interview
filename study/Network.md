[Back to main](/README.md)

# 네트워크
<details>
<summary> HTTP </summary>

HTTP란 데이터를 주고 받기 위한 서버와 클라이언트 간의 통신 규약
- 상태 정보를 저장하지 않는 Stateless의 특징과 클라이언트의 요청에 맞는 응답을 보낸 후 연결을 끊는 Connectionless의 특징
- 장점
  - 통신간 연결 상태 처리나 상태 정보를 관리할 필요가 없음
  - 각각의 HTTP 요청에 독립적으로 응답하면 됨
- 단점
  - 이전의 통신 정보를 모르기에 매번 인증해야함
  - 이를 위해 쿠키나 세션을 사용

</details> 


<details>
<summary> HTTP와 HTTPS의 차이 </summary>

- HTTP는 평문 데이터를 전송하기에, 중요한 정보가 제 3자에 의해 조회될 수 있음
- HTTP에 암호화가 추가된 프로토콜이 HTTPS
- HTTPS는 인터넷을 통해 전달되는 정보를 보호하기 위해 개발한 통신 규약 SSL과 통신하고 SSL이 TCP와 통신
- 대칭키와 비대칭키 암호화를 둘 다 사용하여 HTTPS
- 비대칭키와 대칭키
  - 인증서 발급 시 비대칭키 사용 그 이후 통신에는 대칭키를 사용
- 암호화와 증명서, 안전성 보호를 이용할 수 있음


</details>

<details>
<summary> 쿠키와 세션 </summary>

### 사용 이유
- HTTP는 stateless 하여 사용자의 정보를 저장하지 않음. 따라서 사용자의 정보를 쿠키나 세션을 활용해 저장해야함


### 쿠키

- 사용자의 컴퓨터에 저장하는 작은 기록 정보 파일
- HTTP에서 클라이언트의 상태 정보를 PC에 저장했다가 필요시 정보를 참조하거나 재사용
- 쿠키 저장 시 만료 기간을 설정하고, 만료 기간이 지나면 삭제

### 세션

- 웹서버에 저장함
- 일정 시간동안 같은 사용자로부터 들어오는 일련의 요구를 하나의 상태로 보고, 그 상태를 유지

### 차이점
- 쿠키는 브라우저 종료와 상관 없이 쿠키 등록 시 설정한 만료기간이 지나면 삭제, 세션은 브라우저 종료시 삭제
- 쿠키가 더 빠른 속도
- 보안은 세션이 더 좋음 

</details> 

<details>
<summary> www.google.com 에 접속하면 생기는 일 </summary>

1. 사용자가 브라우저에 URL을 입력
   - www.google.com -> URL
   - www.google.com?name="구글" -> URI
   - URI는 자원에 대한 고유 식별자가 함께 있음
2. DNS 서버에 입력된 도메인 주소 기반의 IP 주소를 요청
3. DNS가 브라우저에게 찾는 사이트의 IP 주소를 응답
4. 브라우저가 서버에게 IP 주소를 이용하여 HTTP 요청 메시지를 전송
5. 웹 서버는 요청에 따른 로직 처리 후 응답 데이터를 담아 HTTP 응답 메시지를 전송
6. 도착한 HTTP 응답 메시지는 웹 페이지 데이터로 변환
7. 브라우저에 의해 출력

</details> 

<details>
<summary> URL과 URI </summary>

- URI: Uniform Resource Identifier, 자원 자체를 식별하는 방법
  - URI의 하위 개념으로 URL이 있음
- URL: Uniform Resource Locator, 자원이 어디 있는지 위치를 알려주는 것

### 예시
`http://www.google.com/index.html?page=5&id=10` 
- URL은 `http://www.google.com/index.html` 까지
- URI는 `?page=5&id=10`과 같이 자원의 식별자가 포함된 주소 전체
</details> 

<details>
<summary> 3 way-handshake, 4 way-handshake </summary>
TCP 네트워크에서 통신하는 장치를 다루는 방법

- 3 way-handshake
  - 통신하는 장치가 서로 연결이 잘 되었는지 확인하는 방법
- 4 way-handshake
  - 통신하는 장치의 연결을 해제하는 방법


</details> 

<details>
<summary> OSI 7 layer </summary>

- 7계층`응용` : 사용자에게 통신을 위한 서비스를 제공
- 6계층`표현` : 데이터의 형식을 정의하는 계층
- 5계층`세션` : 컴퓨터끼리 통신을 하기 위해 세션을 만드는 계층
- 4계층`전송` : 최종 수신 프로세스로 데이터의 전송을 담당하는 계층
  - 단위 Segment
  - TCP, UDP
- 3계층`네트워크` : 패킷을 목적지까지 가장 빠른길로 전송하기 위한 계층
  - 단위 Packet
  - Router
- 2계층`데이터링크` : 데이터의 물리적인 전송과 에러 검출, 흐름 제어를 담당하는 계층
  - 단위 frame
  - 이더넷
- 1계층`물리` : 데이터를 전기 신호로 바꾸어주는 계층
  - 단위 bit
  - 케이블, 리피터, 허브


</details> 

<details>
<summary> JWT 토큰 </summary>
Json Web Token으로 JSON 형식을 이용하여 인증에 필요한 정보들을 Token에 담아 암호화시키는 인터넷 표준 인증 방식

- 헤더, 내용을 담는 payload, 서명으로 구성되며 각 파트를 점으로 구분
- 각 부분은 BASE64로 인코딩 되어 표현
- 토큰 자체 정보를 사용하는 Self-Contained 방식
- 토큰 기반 인증 방식에 사용됨

### Header(헤더)
- 토큰의 타입과 해시 암호화 알고리즘으로 구성

### Payload(내용)
- 토큰에 사용자가 담고자 하는 정보를 담는 곳
- 정보의 한 조각을 claim이라고 부르며 JSON 형태 key value 쌍으로 구성

### Signature(서명)
- 토큰을 인코딩하거나 유효성 검증 시 사용하는 고유한 암호화 코드
- 헤더와 내용 값을 BASE64로 각각 인코딩하고, 인코딩한 값을 비밀키를 이용해 헤더에서 정의한 알고리즘으로 해싱하고, 이 값을 다시 BASE64로 인코딩하는 것

</details> 

<details>
<summary> OAuth </summary>
다양한 플랫폼 환경에서 권한 부여를 위한 산업 표준 프로토콜

- 인증과 권한을 다른 플랫폼으로부터 획득하는 것
- OAuth 1.0은 구현이 복잡하고 웹이 아닌 어플리케이션에서의 지원이 부족함
- OAuth 2.0이 많이 사용됨

### OAuth 2.0 흐름
1. 사용자가 클라이언트에게 사용 요청을 보냄
2. 클라이언트는 권한 서버에 권한 부여 승인 코드를 요청
3. 권한 서버는 클라이언트에게 로그인 페이지를 제공하고 클라이언트가 사용자에게 출력하면 사용자는 로그인함
4. 권한 서버가 권한 부여 승인 코드 요청 시 전달받은 redirect_url로 Authorization Code를 전달
5. Authorization Code는 권한 서버에서 제공하는 API를 통해 Access Token으로 교환

</details> 

<details>
<summary> access token, refresh token </summary>
토큰 기반 인증에 사용되는 것으로, access token만 사용되던 기존의 방식에서 보안을 강화한 것

- 토큰 기반 인증은 stateless하여 서버가 한번 발급한 토큰에 대한 제어권이 없음
- 이런 토큰이 탈취된다면 사용자가 계정의 제어권을 그대로 넘겨줄 수 밖에 없다는 보안 문제가 있음
- Refresh token: Access Token의 유효 기간을 짧고, 자주 재발급하도록 만들어 보안을 강화하면서 사용자에게 잦은 로그아웃 경험을 주지 않도록하는 것

### 흐름
1. 클라이언트가 로그인을 요청하고 성공하면, 서버는 access token과 refresh token을 함께 제공
2. 클라이언트는 인가가 필요한 요청에 access token을 header에 담아 함께 보냄
3. access token이 만료되었다면, 클라이언트는 refresh token을 서버로 전달
4. 서버는 access token이 조작되지 않았는지 확인한 후, refresh token을 처음에 발급한 refresh token과 비교하여 동일하고 refresh token의 유효기간이 만료되지 않았다면 새로운 access token을 발급
5. 새로운 access token을 헤더에 실어 다시 API 요청 응답을 진행
6. 로그아웃 시 두 토큰을 모두 만료시킴

</details> 

<details>
<summary> CORS </summary>
CORS : Cross-Origin Resource Sharing

- 서로 다른 2개의 사이트가 데이터를 주고 받을 때 발생하는 문제
- 서버에서 Access-Control-Allow-Origin 헤더를 세팅하여 해결할 수 있음
  - 전역적으로 CORS를 설정하거나
  - Controller 상단에 `@CrossOrigin` 을 붙여 해결 


</details> 



<!-- 
<details>
<summary> </summary>


</details> 
-->