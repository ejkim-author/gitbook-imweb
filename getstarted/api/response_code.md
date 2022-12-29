# API 응답 코드

아임웹 API를 요청하면 아래와 같은 HTTP 상태 코드(HTTP status code) 형태의 응답 코드로 API 요청에 대한 처리 결과를 반환받습니다.&#x20;

API 응답 코드는 세 자리 코드로 API 요청 상태를 나타내며, HTTP 응답 본문(HTTP response body)으로 받습니다.&#x20;

* 정상 요청인 경우: 응답 코드는 '200'이며, 각 API별로 지정된 형식의 응답 데이터를반환받습니다.
* 비정상 요청인 경우: 응답 코드는 400번대와 500번대이며, 각 API 별로 지정된 오류 코드와 오류 메시지를 반환받습니다.

| 응답 코드 | 설명                |
| ----- | ----------------- |
| 200   | Success           |
| 400   | Bad Request       |
| 401   | Unauthorized      |
| 404   | Not Found         |
| 429   | Too many Requests |
| 500   | Code Error        |
| 501   | Not Implemented   |

