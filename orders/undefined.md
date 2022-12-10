# 운송장 입력

{% swagger method="get" path="/orders/{주문번호}/invoice" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>parcel_code</td><td></td><td><p>택배사 코드</p><p><a href="../appendix/undefined.md">지원 택배사 목록</a></p></td></tr><tr><td>invoice_no</td><td></td><td>운송장번호</td></tr><tr><td>prod_order_no</td><td></td><td><p>변경할 품목주문번호(선택)</p><p>개별/부분 발송 시 사용</p></td></tr></tbody></table>
