# 주문 처리

{% swagger method="patch" path="/orders/{주문번호}/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 처리가능 상태 설명

| 항목       | 설명         |
| -------- | ---------- |
| deposit  | 입금확인 처리    |
| place    | 배송준비 처리    |
| send     | 발송처리       |
| complete | 강제 배송완료 처리 |
| cancel   | 판매취소       |
| return   | 반품처리       |
| exchange | 교환처리       |

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>개별/부분 처리 시 사용(선택)</td></tr><tr><td>etc</td><td></td><td><p>상태별 필수 데이터</p><p>처리 상태에 맞는 추가 데이터를 전달해주세요.</p><ul><li>send: <a href="patchOrders.md#ordersend-data">OrderSendData</a></li><li>cancel:  <a href="patchOrders.md#ordercancelrequest-data">OrderCancelRequestData</a></li><li>return <a href="patchOrders.md#orderreturnrequest-data">OrderReturnRequestData</a></li><li>exchange <a href="patchOrders.md#orderexchangerequest-data">OrderExchangeRequestData</a></li></ul></td></tr></tbody></table>

### 요청 예제

```
$data = [
    'etc' => [
    	'reason_code' => 'INTENT_CHANGED'
    ]
];
```

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 주문서 목록</p><p><a href="patchOrders.md#orderactionfailedlist-data">OrderActionFailedList</a></p></td></tr></tbody></table>

### **OrderSend Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">사용가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장번호</td></tr></tbody></table>

### **OrderCancelRequest Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>reason_code</td><td></td><td><p>판매취소 사유</p><ul><li>INTENT_CHANGED: 구매 의사 취소</li><li>COLOR_AND_SIZE: 색상 및 사이즈 변경</li><li>WRONG_ORDER: 다른 상품 잘못 주문</li><li>PRODUCT_UNSATISFIED: 서비스 및 상품 불만족</li><li>DELAYED_DELIVERY: 배송 지연</li><li>DROPPED_DELIVERY: 배송 누락</li><li>SOLD_OUT: 상품 품절</li><li>BROKEN: 상품 파손</li><li>INCORRECT_INFO: 상품 정보 상이</li><li>WRONG_DELIVERY: 오배송</li><li>WRONG_OPTION: 색상 등이 다른 상품을 잘못 배송</li></ul></td></tr></tbody></table>

### **OrderReturnRequest Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>reason_code</td><td></td><td><p>반품사유</p><ul><li>INTENT_CHANGED: 구매 의사 취소반품비용 발생시 구매자 부담</li><li>COLOR_AND_SIZE: 색상 및 사이즈 변경반품비용 발생시 구매자 부담</li><li>WRONG_ORDER: 다른 상품 잘못 주문반품비용 발생시 구매자 부담</li><li>PRODUCT_UNSATISFIED: 서비스 및 상품 불만족반품비용 발생시 판매자 부담</li><li>DELAYED_DELIVERY: 배송 지연반품비용 발생시 판매자 부담</li><li>DROPPED_DELIVERY: 배송 누락반품비용 발생시 판매자 부담</li><li>SOLD_OUT: 상품 품절반품비용 발생시 판매자 부담</li><li>BROKEN: 상품 파손반품비용 발생시 판매자 부담</li><li>INCORRECT_INFO: 상품 정보 상이반품비용 발생시 판매자 부담</li><li>WRONG_DELIVERY: 오배송반품비용 발생시 판매자 부담</li><li>WRONG_OPTION: 색상 등이 다른 상품을 잘못 배송반품비용 발생시 판매자 부담</li></ul></td></tr><tr><td>deliv_fee_method</td><td></td><td><p>반품비용 처리방법</p><p>구매자 귀책 사유일 때만 입력해주세요.</p><ul><li>REFUND: 환불금에서 차감</li><li>CASH: 판매자에게 송금</li><li>BOX: 수거시 박스에 동봉</li></ul></td></tr><tr><td>collect_type</td><td></td><td>직접 수거 여부</td></tr><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p>직접 수거를 사용하지 않는 경우 필수로 입력해주세요.</p><p><a href="../appendix/undefined.md">사용가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td><p>운송장번호</p><p>직접 수거를 사용하지 않는 경우 필수로 입력해주세요.</p></td></tr></tbody></table>

### **OrderExchangeRequest Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>reason_code</td><td></td><td><p>교환사유</p><ul><li>INTENT_CHANGED: 구매 의사 취소교환비용 발생시 구매자 부담</li><li>COLOR_AND_SIZE: 색상 및 사이즈 변경교환비용 발생시 구매자 부담</li><li>WRONG_ORDER: 다른 상품 잘못 주문교환비용 발생시 구매자 부담</li><li>PRODUCT_UNSATISFIED: 서비스 및 상품 불만족교환비용 발생시 판매자 부담</li><li>DELAYED_DELIVERY: 배송 지연교환비용 발생시 판매자 부담</li><li>DROPPED_DELIVERY: 배송 누락교환비용 발생시 판매자 부담</li><li>SOLD_OUT: 상품 품절교환비용 발생시 판매자 부담</li><li>BROKEN: 상품 파손교환비용 발생시 판매자 부담</li><li>INCORRECT_INFO: 상품 정보 상이교환비용 발생시 판매자 부담</li><li>WRONG_DELIVERY: 오배송교환비용 발생시 판매자 부담</li><li>WRONG_OPTION: 색상 등이 다른 상품을 잘못 배송교환비용 발생시 판매자 부담</li></ul></td></tr><tr><td>collect_type</td><td></td><td>직접 수거 여부</td></tr><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p>직접 수거를 사용하지 않는 경우 필수로 입력해주세요.</p><p><a href="../appendix/undefined.md">사용가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td><p>운송장번호</p><p>직접 수거를 사용하지 않는 경우 필수로 입력해주세요.</p></td></tr></tbody></table>

### **OrderActionFailedList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문번호</td></tr><tr><td>prod_order_list</td><td></td><td>처리 실패한 품목 주문 목록<a href="patchOrders.md#orderactionfailedprodorderlist-data">OrderActionFailedProdOrderListData</a></td></tr></tbody></table>

### **OrderActionFailedProdOrderList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>msg</td><td></td><td>실패 메세지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세메세지</td></tr></tbody></table>

