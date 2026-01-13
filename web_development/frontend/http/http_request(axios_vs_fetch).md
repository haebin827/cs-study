# HTTP Request (Axios vs. Fetch)

## 참고
- https://www.bezkoder.com/react-axios-example/

## fetch vs axios 차이점 총정리
- fetch와 axios 모두 HTTP 요청을 보낼 때 사용되지만, 실무에는 axios가 주로 쓰임.
![img.png](img%2Fimg.png)

## Fetch vs. Axios
- Fetch
  - 브라우저 내장 API로 가볍지만, 일부 기능을 직접 구현해야 함
- Axios
  - 추가 설치가 필요하지만, 에러 처리, JSON 자동 변환, 인터셉터 등 편리한 기능이 많음

## Axios 요청에 대한 응답에는 다음이 포함됨
- data
  - 서버에서 제공한 구문 분석된 응답 본문
- status
  - HTTP 상태 코드
- statusText
  - HTTP 상태 메시지
- headers
  - HTTP 헤더(소문자)
- config
  - 제공된 요청 구성axios
- request
  - 이 응답을 생성한 마지막 클라이언트 요청 인스턴스

## fetch vs axios CRUD 비교 (실제 프로덕트 수준)

### fetch 특징
- catch()에서 Network error만 잡고, HTTP 오류(4xx, 5xx)를 잡지 X
- 4xx, 5xx를 위해 무조건 if(!response.ok)로 임의 검사해야 함
- response.json()을 호출해야 data를 JSON 데이터를 가져올 수 있음

### 무조건 지켜야 하는 axios 사용법
- HTTP 오류(4xx, 5xx)를 자동으로 catch()에서 감
- data를 바로 사용할 수 있음 (res.data)
- 별도의 .json() 호출 필요 X

## READ
- fetch
  - (특별한 거 없음)
![img_1.png](img%2Fimg_1.png)
- axios
  - 아니시발 fetch처럼 Http error를 잡을 필요도 없고, json도 자동변환됨ㅎㅎ 너무조아
![img_2.png](img%2Fimg_2.png)

## CREATE
- fetch
  - HTTP POST 요청 시, headers 명시 필수
  - 반드시 body를 JSON.stringify로 변환
![img_3.png](img%2Fimg_3.png)
- axios
  - Header 명시 필요 X (자동처리)
  - body를 JSON 변환 필요 X (자동처리)
![img_4.png](img%2Fimg_4.png)

## UPDATE
- fetch
  - (CREATE와 동일)
![img_5.png](img%2Fimg_5.png)
- axios
  - 마찬가지로 body를 JSON.stringify() 할 필요 없음
![img_6.png](img%2Fimg_6.png)

## DELETE
- fetch
  - delete는 보통 body가 필요없지만, 특정 경우에 요구될 수도 있음
![img_7.png](img%2Fimg_7.png)
- axios
  - 여전히 body 없어도 됨
![img_8.png](img%2Fimg_8.png)
