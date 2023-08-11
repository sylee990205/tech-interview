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
<summary> 3 way-handshake, 4 way-handshake </summary>



</details> 

<details>
<summary> OSI 7 layer </summary>


</details> 

<!-- 
<details>
<summary> </summary>


</details> 
-->