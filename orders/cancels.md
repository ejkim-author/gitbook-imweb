# 취소 처리

{% swagger method="patch" path="/orders/{주문번호}/cancel/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 처리가능 상태 설명

| 항목            | 설명                                                                                                                                                                                                                   |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| reject        | <p>취소 거절</p><p>취소 요청 건을 거절하고 발송 처리합니다.</p>                                                                                                                                                                           |
| accept        | <p>취소 승인</p><p>취소 요청 건에 대해 환불 처리를 진행합니다.</p><p><mark style="color:red;">주의: 자동 환불이 불가능한 주문건은 '자동환불불가' 오류가 발생합니다.</mark></p>                                                                                          |
| retry         | <p>자동 환불 재시도</p><p>자동 환불 가능(카드 결제 전체 취소) 취소 승인을 하였으나 PG사 장애 등의 이유로 취소 처리 중이 되었을 때 자동 환불을 다시 시도하는 기능입니다.</p>                                                                                                          |
| force\_cancel | <p>강제 취소(환불)완료 처리</p><p>강제 취소(환불)완료 처리 시 PG사를 거치지 않고 취소 완료 상태로 변경되므로 실질적으로 고객에게는 자동  환불되지 않습니다. <br>무통장 입금, 가상 계좌 등 자동 환불을 지원하지 않는 결제  수단에만 사용하시길 권장합니다.<br>카드 주문 등에 적용하는 경우, PG사 상점 관리자나 별도 환불 수단을 통해 환불 처리하세요.</p> |

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>개별/부분 처리 시 사용(선택)</td></tr><tr><td>etc</td><td></td><td><p>상태 별 필수 데이터</p><ul><li>reject: <a href="cancels.md#ordercancelreject-data">OrderCancelRejectData</a></li><li>accept:  <a href="cancels.md#ordercancelaccept-data">OrderCancelAcceptData</a></li></ul><p>처리 상태에 맞는 추가 데이터를 전달하세요.</p></td></tr></tbody></table>

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 주문서 목록</p><p><a href="cancels.md#orderactionfailedlist-data">OrderActionFailedList</a></p></td></tr></tbody></table>

### **OrderCancelReject Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">사용 가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장 번호</td></tr></tbody></table>

### **OrderCancelAccept Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>etc_price</td><td></td><td><p>기타 청구 비용 목록</p><p><mark style="color:red;">주의: 미입력 시 기타 비용은 처리되지 않습니다.</mark></p><p><a href="cancels.md#etcprice-data">EtcPriceData</a></p></td></tr><tr><td>refund_point</td><td></td><td><p>환불 적립금</p><p>전체 취소인 경우 사용한 적립금 전액이 자동 반영됩니다.</p><p>부분  취소는 환불하실 포인트를 직접 입력하실 수 있습니다.</p><p>예: 3000 포인트를 환불 받고 싶은 경우, 3000 입력(단, 해당 주문의 잔여 적립금보다 초과하여 입력 불가)</p><p><mark style="color:red;">주의: 미입력 시 적립금이 환불되지  않습니다.</mark></p><p><a href="cancels.md#refundpoint-data">RefundPointData</a></p></td></tr><tr><td>claim_memo</td><td></td><td>구매자에게 전하실 말씀</td></tr></tbody></table>

### **EtcPrice Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목 주문 번호</td></tr><tr><td>price</td><td></td><td>기타 청구 비용</td></tr></tbody></table>

### **RefundPoint Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목 주문 번호</td></tr><tr><td>price</td><td></td><td>환불 적립금</td></tr></tbody></table>

### **OrderActionFailedList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문 번호</td></tr><tr><td>prod_order_list</td><td></td><td><p>처리 실패한 품목 주문서 목록</p><p><a href="cancels.md#orderactionfailedlist-data-1">OrderActionFailedProdOrderList Data</a></p></td></tr></tbody></table>

### **OrderActionFailedProdOrderList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목 주문 번호</td></tr><tr><td>msg</td><td></td><td>실패 메시지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세 메시지</td></tr></tbody></table>

****
