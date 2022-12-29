# 상품 상세 옵션 수정

{% swagger method="patch" path="{상품번호}/options-details/{상세옵션번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="수정 시 변경할 항목만 전달하세요." %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>price</td><td></td><td>옵션 가격</td></tr><tr><td>stock</td><td></td><td>옵션 재고</td></tr><tr><td>stock_sku</td><td></td><td>재고관리 코드(SKU)</td></tr><tr><td>status</td><td></td><td><p>옵션 상태</p><ul><li>SALE: 판매중</li><li>SOLDOUT: 품절처리</li><li>HIDDEN: 숨김</li></ul></td></tr></tbody></table>

###
