# 교환 처리

{% swagger method="patch" path="/orders/{주문번호}/exchange/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 처리가능 상태 설명

| 항목             | 설명       |
| -------------- | -------- |
| reject         | 교환 거부    |
| accept         | 수거 지시    |
| collect\_done  | 교환 수거 완료 |
| withhold       | 교환 보류    |
| releasehold    | 교환 보류 해제 |
| resend         | 교환 재발송   |
| exchange\_done | 교환 완료 처리 |

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>개별/부분 처리 시 사용(선택)</td></tr><tr><td>etc</td><td></td><td><p>상태 별 필수 데이터</p><ul><li>reject:  <a href="exchanges.md#orderexchangereject-data">OrderExchangeRejectData</a></li><li>accept:  <a href="exchanges.md#orderexchangeaccept-data">OrderExchangeAcceptData</a></li><li>withhold:  <a href="exchanges.md#orderexchangewithhold-data">OrderExchangeWithHoldData</a></li><li>resend:  <a href="exchanges.md#orderexchangeresend-data">OrderExchangeReSendData</a></li></ul><p>처리 상태에 맞는 추가 데이터를 전달해주세요.</p></td></tr></tbody></table>

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 주문서 목록</p><p><a href="exchanges.md#orderactionfailedlist-data">OrderActionFailedList</a></p></td></tr></tbody></table>

### **OrderExchangeReject Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">사용 가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장 번호</td></tr></tbody></table>

### **OrderExchangeAccept Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>etc_price</td><td></td><td>기타 청구 비용</td></tr></tbody></table>

### **OrderExchangeWithHold Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>reason_code</td><td></td><td><p>보류 사유 코드</p><ul><li>EXCHANGE_DELIVERYFEE: 교환 배송비 청구</li><li>EXCHANGE_EXTRAFEE: 기타 교환 비용 청구</li><li>EXCHANGE_PRODUCT_READY: 교환 상품 준비 중</li><li>EXCHANGE_PRODUCT_NOT_DELIVERED: 교환 상품 미입고</li><li>EXCHANGE_HOLDBACK: 교환 구매 확정 보류</li><li>ETC: 기타 사유</li></ul></td></tr><tr><td>reason_detail</td><td></td><td>보류 상세 사유</td></tr><tr><td>etc_price</td><td></td><td><p>기타 비용</p><p>보류 사유가 EXCHANGE_EXTRAFEE인 경우에만 입력하세요.</p></td></tr></tbody></table>

#### etc\_price 입력 예시

```
$etc = [
	'etc_price' => [
		'품목주문서번호' => 1000
	]
];
```

### **OrderActionFailedList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문번호</td></tr><tr><td>prod_order_list</td><td></td><td>처리 실패한 품목 주문서 목록 <a href="exchanges.md#orderactionfailedprodorderlist-data">OrderActionFailedProdOrderListData</a></td></tr></tbody></table>

### **OrderActionFailedProdOrderList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목 주문 번호</td></tr><tr><td>msg</td><td></td><td>실패 메시지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세 메시지</td></tr></tbody></table>

### **OrderExchangeReSend Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>method</td><td></td><td><p>재배송 방법</p><ul><li>DELIVERY: 택배, 등기, 소포</li><li>VISIT_RECEIPT: 방문 수령</li><li>DIRECT_DELIVERY: 직접 전달</li><li>QUICK_SVC: 퀵서비스</li><li>NOTHING: 배송 없음</li></ul></td></tr><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p>재배송 방법이 택배, 등기, 소포인 경우에만 입력하세요.</p><p><a href="../appendix/undefined.md">사용  가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td><p>운송장 번호</p><p>재배송 방법이 택배, 등기, 소포인 경우에만 입력하세요.</p></td></tr></tbody></table>
