# 반품 처리

{% swagger method="patch" path="/orders/{주문번호}/return/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 처리가능 상태 설명

| 항목                  | 설명                                                                                                                      |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| reject              | <p>반품 거부</p><p>반품요청 주문에 대해 반품 거부하거나 교환으로 변경합니다.</p>                                                                     |
| accept              | <p>수거지시</p><p>운송업체에게 반품상품 수거를 지시(요청)한 경우 처리해주세요.</p>                                                                    |
| collect\_done       | <p>반품수거 완료</p><p>수거중인 상품을 수거완료 처리합니다.</p>                                                                               |
| withhold            | <p>반품보류</p><p>구매자에게 반품 배송비 또는 기타 반품 추가 비용을 청구해야 하거나 반품이 불가할 때 사용합니다.(네이버페이 용)</p>                                       |
| releasehold         | <p>반품 보류 해제</p><p>반품 보류 사유가 해결되어 반품 진행이 계속 가능할 때 사용합니다.(네이버페이 용)</p>                                                    |
| return\_done        | <p>반품완료 처리</p><p>수거가 확인된 반품 상품의 환불 처리를 진행하며 구매자에게 추가 비용 청구를 할 수 있습니다.</p><p>주의: 자동환불이 불가능한 주문건은 '자동환불불가' 오류가 발생합니다.</p> |
| return\_force\_done | <p>강제 반품완료 처리</p><p>환불처리실패 또는 환불진행중인 주문을 반품완료 처리합니다. 강제 반품 완료 처리는 자동환불이 지원되지 않으므로 구매자와 협의된 방법으로 환불을 별도 진행해 주셔야 합니다.</p> |

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>개별/부분 처리 시 사용(선택)</td></tr><tr><td>etc</td><td></td><td><p>상태별 필수 데이터</p><ul><li>reject: <a href="returns.md#orderreturnreject-data">OrderReturnRejectData</a></li><li>return_done:  <a href="returns.md#orderreturnreturndone-data">OrderReturnReturnDoneData</a></li></ul><p>처리 상태에 맞는 추가 데이터를 전달해주세요.</p></td></tr></tbody></table>

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 주문서 목록</p><p><a href="returns.md#orderactionfailedlist-data">OrderActionFailedList</a></p></td></tr></tbody></table>

### **OrderReturnReject Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>reason</td><td></td><td>거부사유</td></tr></tbody></table>

### **OrderReturnReturnDone Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>etc_price</td><td></td><td><p>기타 청구비용 목록</p><p>주의: 미입력 시 기타 비용 처리가 이루어지지 않습니다.</p><p><a href="returns.md#etcprice-data">EtcPriceData</a></p></td></tr><tr><td>refund_point</td><td></td><td><p>환불 적립금</p><p>전체 반품인 경우 사용한 적립금 전액이 자동 반영됩니다.</p><p>부분반품은 환불하실 적립금을 직접 입력하실 수 있습니다.</p><p><strong>예: 3000 포인트를 환불하고 싶을 때-></strong> 3000 입력 (단, 해당 주문의 잔여 적립금보다 초과하여 입력 불가)</p><p>주의: 미입력 시 적립금 환불 처리가 이루어지지 않습니다.</p><p><a href="returns.md#refundpoint-data">RefundPointData</a></p></td></tr><tr><td>claim_memo</td><td></td><td>구매자에게 전하실 말씀</td></tr></tbody></table>

### **EtcPrice Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>price</td><td></td><td>기타 청구 비용</td></tr></tbody></table>

### **RefundPoint Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>point</td><td></td><td>환불 적립금</td></tr></tbody></table>

### **OrderActionFailedList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>주문번호</td></tr><tr><td>prod_order_list</td><td></td><td>처리 실패한 품목 주문서 목록<a href="returns.md#orderactionfailedprodorderlist-data">OrderActionFailedProdOrderListData</a></td></tr></tbody></table>

### **OrderActionFailedProdOrderList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>msg</td><td></td><td>실패 메세지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세메세지</td></tr></tbody></table>
