# 품목 주문 처리

{% swagger method="patch" path="/prod-orders/{품목주문번호}/{상태}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
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

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>success</td><td></td><td>처리 성공한 품목 주문서 번호</td></tr><tr><td>failed</td><td></td><td><p>처리 실패한 품목 주문서 목록</p><p><a href="patchProdOrder.md#undefined-2">ProdOrderActionFailedList Data</a></p></td></tr></tbody></table>

### ProdOrderActionFailedList Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_order_no</td><td></td><td>품목주문번호</td></tr><tr><td>msg</td><td></td><td>실패 메세지</td></tr><tr><td>detail_msg</td><td></td><td>실패 상세메세지</td></tr></tbody></table>
