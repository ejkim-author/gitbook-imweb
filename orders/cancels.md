# 취소 처리

{% swagger method="patch" path="/orders/{주문번호}/cancel/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 처리가능 상태 설명

| 항목            | 설명                                                                                                                                                                                                     |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| reject        | <p>취소거절</p><p>취소요청건을 거절하고 발송처리 합니다.</p>                                                                                                                                                                |
| accept        | <p>취소승인</p><p>취소요청건에 대해 환불처리를 진행합니다.</p><p><strong>주의: 자동환불이 불가능한 주문건은 '자동환불불가' 오류가 발생합니다.</strong></p>                                                                                                |
| retry         | <p>자동환불 재시도</p><p>자동환불 가능(카드결제 전체취소) 취소승인을 하였으나 PG사 장애 등의 이유로 취소처리중이 되었을 때 자동 환불을 다시 시도하는 기능입니다.</p>                                                                                                   |
| force\_cancel | <p>강제 취소(환불)완료 처리</p><p>강제 취소(환불)완료 처리시 PG사를 거치지 않고 취소완료 상태로 변경되므로 실제 고객에겐 자동으로 환불되지 않습니다. 무통장입금, 가상계좌 등 자동환불이 지원되지 않는 결제수단에만 사용을 권장하며, 신용카드 주문 등에 이 작업 수행시 PG사 상점관리자나 별도 환불수단으로 고객에게 환불해 주셔야 합니다.</p> |

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>개별/부분 처리 시 사용(선택)</td></tr><tr><td>etc</td><td></td><td><p>상태별 필수 데이터</p><ul><li>reject: <a href="cancels.md#ordercancelreject-data">OrderCancelRejectData</a></li><li>accept:  <a href="cancels.md#ordercancelaccept-data">OrderCancelAcceptData</a></li></ul><p>처리 상태에 맞는 추가 데이터를 전달해주세요.</p></td></tr></tbody></table>

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 주문서 목록</p><p><a href="cancels.md#orderactionfailedlist-data">OrderActionFailedList</a></p></td></tr></tbody></table>

### **OrderCancelReject Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">사용가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장번호</td></tr></tbody></table>

### **OrderCancelAccept Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>etc_price</td><td></td><td><p>기타 청구비용 목록</p><p>주의: 미입력 시 기타 비용 처리가 이루어지지 않습니다.</p><p><a href="cancels.md#etcprice-data">EtcPriceData</a></p></td></tr><tr><td>refund_point</td><td></td><td><p>환불 적립금</p><p>전체 취소인 경우 사용한 적립금 전액이 자동 반영됩니다.</p><p>부분취소는 환불하실 포인트를 직접 입력하실 수 있습니다.</p><p><strong>예: 3000 포인트를 환불하고 싶을 때 -></strong> 3000 입력 (단, 해당 주문의 잔여 적립금보다 초과하여 입력 불가)</p><p>주의: 미입력 시 적립금 환불 처리가 이루어지지 않습니다.</p><p><a href="cancels.md#refundpoint-data">RefundPointData</a></p></td></tr><tr><td>claim_memo</td><td></td><td>구매자에게 전하실 말씀</td></tr></tbody></table>

### **EtcPrice Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>price</td><td></td><td>기타 청구 비용</td></tr></tbody></table>

### **RefundPoint Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>price</td><td></td><td>환불 적립금</td></tr></tbody></table>

### **OrderActionFailedList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문번호</td></tr><tr><td>prod_order_list</td><td></td><td><p>처리 실패한 품목 주문서 목록</p><p><a href="cancels.md#orderactionfailedlist-data-1">OrderActionFailedProdOrderList Data</a></p></td></tr></tbody></table>

### **OrderActionFailedProdOrderList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>msg</td><td></td><td>실패 메세지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세메세지</td></tr></tbody></table>

****
