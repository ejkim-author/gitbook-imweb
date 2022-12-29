# 품목 주문 운송장 조회

{% swagger method="get" path="/prod-orders/{품목주문번호}/invoice" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">사용 가능한 택배사 목록 보기</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장 번호</td></tr><tr><td>status</td><td></td><td>배송 상태</td></tr></tbody></table>
