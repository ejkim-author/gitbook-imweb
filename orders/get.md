# 주문 조회

{% swagger method="get" path="/orders" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="/orders/{주문번호}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **목록 요청 데이터**

{% hint style="info" %}
주문서 목록 조회 시 검색 조건을 전달할 수 있습니다.&#x20;

주문서 상태에 관련된 필터는 1개만 사용 가능합니다. (status, claim\_type, claim\_status)
{% endhint %}

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>주문 매체</p><ul><li>normal: 아임웹 주문</li><li>npay: 네이버 주문</li><li>talkpay: 카카오톡 주문</li></ul></td></tr><tr><td>order_date_from</td><td></td><td><p>주문일(시작일)</p><p>Timestamp</p></td></tr><tr><td>order_date_to</td><td></td><td><p>주문일(종료일)</p><p>Timestamp</p></td></tr><tr><td>status</td><td></td><td><p>주문서 상태</p><ul><li>PAY_WAIT: 입금대기</li><li>PAY_COMPLETE: 결제완료</li><li>STANDBY: 배송준비중</li><li>DELIVERING: 배송중</li><li>COMPLETE: 배송완료</li><li>CANCEL: 취소완료</li><li>RETURN: 반품완료</li><li>EXCHANGE: 교환완료</li></ul></td></tr><tr><td>claim_type</td><td></td><td><p>주문서 클레임 타입</p><ul><li>CANCEL: 취소</li><li>RETURN: 반품</li><li>EXCHANGE: 교환</li></ul></td></tr><tr><td>claim_status</td><td></td><td><p>주문서 클레임 상태</p><ul><li>CANCEL_REQUEST: 취소요청</li><li>CANCELING: 취소요청중</li><li>CANCEL_FAILED: 취소 실패</li><li>RETURN_REQUEST: 반품요청</li><li>RETURN_COLLECTING: 반품수거중</li><li>RETURN_COLLECT_DONE: 반품수거완료</li><li>RETURN_REFUNDING: 반품환불진행중</li><li>RETURN_REFUND_FAILED: 반품환불실패</li><li>EXCHANGE_REQUEST: 교환요청</li><li>EXCHANGE_COLLECTIN: G교환수거중</li><li>EXCHANGE_COLLECT_DONE: 교환수거완료</li><li>REDELIVERING: 교환재배송중</li></ul></td></tr><tr><td>member</td><td></td><td>회원코드</td></tr></tbody></table>

## **응답 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문번호</td></tr><tr><td>device</td><td></td><td><p>주문기기 정보</p><p><a href="get.md#orderdevice-data">OrderDeviceData</a></p></td></tr><tr><td>order_time</td><td></td><td><p>주문 시각</p><p>Timestamp</p></td></tr><tr><td>complete_time</td><td></td><td><p>전체 상품 배송완료 시각</p><p>Timestamp</p></td></tr><tr><td>orderer</td><td></td><td><p>주문자 정보</p><p><a href="get.md#orderdevice-data-1">OrderOrdererData</a></p></td></tr><tr><td>delivery</td><td></td><td><p>배송지 정보</p><p><a href="get.md#orderdelivery-data">OrderDeliveryData</a></p></td></tr><tr><td>payment</td><td></td><td><p>결제 정보</p><p><a href="get.md#orderpayment-data">OrderPaymentData</a></p></td></tr><tr><td>cash_receipt</td><td></td><td><p>현금영수증 정보</p><p><a href="get.md#orderreceipt-data">OrderReceiptData</a></p></td></tr><tr><td>form</td><td></td><td><p>결제입력폼 정보</p><p><a href="get.md#orderform-data">OrderFormData</a></p></td></tr></tbody></table>

### OrderDevice Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>주문 기기 타입</p><ul><li>pc: PC</li><li>mobile: Mobile</li></ul></td></tr><tr><td>app</td><td></td><td><p>앱 정보</p><ul><li>android: 안드로이드</li><li>ios: 아이폰</li></ul></td></tr><tr><td>device_code</td><td></td><td>디바이스 코드</td></tr></tbody></table>

### OrderOrderer Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>member_code</td><td></td><td>회원 코드</td></tr><tr><td>name</td><td></td><td>주문자명</td></tr><tr><td>email</td><td></td><td>주문자 메일주소</td></tr><tr><td>call</td><td></td><td>주문자 연락처1</td></tr><tr><td>call2</td><td></td><td>주문자 연락처2</td></tr></tbody></table>

### OrderDelivery Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>country</td><td></td><td>배송국가</td></tr><tr><td>country_text</td><td></td><td>배송국가 한글명</td></tr><tr><td>address</td><td></td><td><p>배송지 정보</p><p><a href="get.md#orderdelivery-data-1">OrderAddressData</a></p></td></tr><tr><td>memo</td><td></td><td>배송 메모</td></tr><tr><td>unipass_number</td><td></td><td>개인통관고유부호</td></tr></tbody></table>

### OrderAddress Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>name</td><td></td><td>수령인명</td></tr><tr><td>phone</td><td></td><td>수령인 연락처1</td></tr><tr><td>phone2</td><td></td><td>수령인 연락처2</td></tr><tr><td>postcode</td><td></td><td>우편번호</td></tr><tr><td>address</td><td></td><td>주소</td></tr><tr><td>address_detail</td><td></td><td>상세주소</td></tr><tr><td>address_street</td><td></td><td>영문주소 - 거리주소</td></tr><tr><td>address_building</td><td></td><td>영문주소 - 건물명</td></tr><tr><td>address_city</td><td></td><td>영문주소 - 도시명</td></tr><tr><td>address_state</td><td></td><td>영문주소 - 도시군</td></tr></tbody></table>

### OrderPayment Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>pay_type</td><td></td><td><p>결제 수단</p><ul><li>free: 무료결제</li><li>card: 신용카드</li><li>iche: 실시간 계좌이체</li><li>virtual: 가상계좌</li><li>cash: 무통장입금</li><li>phone: 핸드폰 결제</li><li>payco: 페이코</li><li>kakaopay: 카카오페이</li><li>paypal: 페이팔</li><li>manual: 수기결제</li><li>eximbay: 엑심베이</li><li>eb_atrpay: 알리페이</li><li>eb_molpay: 몰페이</li><li>eb_wechatpay: 위쳇페이</li><li>eb_econtext: 편의점결제</li><li>npay_point: 네이버페이 포인트 결제</li><li>easy_payment_card: 신용카드 간편결제 </li><li>easy_payment_virtual: 계좌 간편결제</li><li>easy_payment_phone: 휴대폰 간편결제</li></ul></td></tr><tr><td>pg_type</td><td></td><td><p>PG 타입</p><ul><li>kcp: NHN KCP</li><li>inicis: KG 이니시스</li><li>nicepay: 나이스페이</li><li>paynuri: 페이누리</li><li>paypal: 페이팔</li><li>eximbay: 엑심베이</li><li>allatpay: 올앳페이</li><li>ags: 올더게이트</li><li>uplus: LG유플러스</li><li>ksnet: KSNet</li></ul></td></tr><tr><td>deliv_type</td><td></td><td><p>배송방법</p><ul><li>parcel: 택배</li><li>direct: 직접배송</li><li>quick: 퀵배송</li><li>visit: 방문수령</li><li>no_deliv: 배송없음</li><li>download: 디지털 컨텐츠</li><li>subscribe: 회원그룹 이용권</li></ul></td></tr><tr><td>deliv_pay_type</td><td></td><td><p>배송비 결제방식</p><ul><li>price: 선결제</li><li>deliv_price_after: 착불</li></ul></td></tr><tr><td>price_currency</td><td></td><td>통화</td></tr><tr><td>total_price</td><td></td><td>총 결제금액</td></tr><tr><td>price_tax_free</td><td></td><td>면세 금액</td></tr><tr><td>price_sale</td><td></td><td>상품 자체 할인 금액</td></tr><tr><td>deliv_price</td><td></td><td>배송비</td></tr><tr><td>point</td><td></td><td>사용 적립금</td></tr><tr><td>coupon</td><td></td><td>쿠폰 할인액</td></tr><tr><td>membership_discount</td><td></td><td>회원 그룹 할인액</td></tr><tr><td>period_discount</td><td></td><td>즉시/기간 할인액</td></tr></tbody></table>

### OrderReceipt Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>request</td><td></td><td><p>현금영수증 신청 여부</p><ul><li>AUTO: 자동 발행</li><li>Y: 신청</li><li>N: 미신청</li></ul></td></tr><tr><td>type</td><td></td><td><p>현금영수증 종류</p><ul><li>deducation: 소득공제용</li><li>proof: 지출증빙용</li></ul></td></tr><tr><td>value</td><td></td><td>현금영수증 신청 정보</td></tr><tr><td>status</td><td></td><td><p>현금영수증 처리 상태</p><ul><li>WAIT: 처리 대기</li><li>COMPLETE: 처리 완료</li></ul></td></tr><tr><td>complete_date</td><td></td><td><p>현금영수증 발행일</p><p>Timestamp</p></td></tr></tbody></table>

### **OrderForm Data**

<table><thead><tr><th>항목</th><th data-type="select" data-multiple>타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>입력폼 타입</p><ul><li>text: 한 줄 텍스트</li><li>textarea: 여러 줄 텍스트</li><li>radio: 단일선택</li><li>select: 목록선택</li><li>checkbox: 복수선택</li><li>date: 날짜형식</li><li>time: 시간형식</li><li>file: 파일 업로드</li></ul></td></tr><tr><td>title</td><td></td><td>입력폼 항목 제목</td></tr><tr><td>desc</td><td></td><td>입력폼 항목 설명</td></tr><tr><td>value</td><td></td><td><p>입력폼 항목 사용자 입력값</p><p><a href="get.md#undefined-2">입력폼 항목 사용자 입력값 예시</a> 참고</p></td></tr></tbody></table>

### 입력폼 항목 사용자 입력값 예시

**text, textarea, radio, select, date, time** (string)

```
[value] => 홍길동
```

**checkboxarray** (string)

```
[value] => Array
(
	[0] => 농구
	[1] => 배구
)
```

file (array)

{% hint style="danger" %}
file 타입에서 URL은 주문서 조회 API를 호출한 IP에서만 접근 가능합니다.
{% endhint %}

```
[value] => Array
(
	[name] => 파일명
	[url] => /shop_form_file_download.cm?secret={secret}
	[size] => 파일용량
)
```
