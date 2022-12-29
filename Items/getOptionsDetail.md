# 상품 상세 옵션 조회

{% swagger method="get" path="{상품번호}/options-details" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="{상품번호}/options-details/{상세옵션번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 응답 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>no</td><td></td><td>옵션 번호</td></tr><tr><td>is_require</td><td></td><td>필수옵션 여부</td></tr><tr><td>option_code_list</td><td></td><td>옵션 코드 목록</td></tr><tr><td>value_code_list</td><td></td><td>옵션값 코드 목록</td></tr><tr><td>price</td><td></td><td>옵션 가격</td></tr><tr><td>stock</td><td></td><td>옵션 재고</td></tr><tr><td>stock_sku</td><td></td><td>재고 번호(SKU)</td></tr><tr><td>status</td><td></td><td><p>옵션 상태</p><ul><li>SALE: 판매 중</li><li>SOLDOUT: 품절 처리</li><li>HIDDEN: 숨김</li></ul></td></tr></tbody></table>
