# 상품 옵션 조회

{% swagger method="get" path="{상품번호}/options" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="{상품번호}/options/{옵션번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="{상품번호}/options/{옵션코드}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 응답 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>no</td><td></td><td>옵션 번호</td></tr><tr><td>type</td><td></td><td><p>옵션 타입</p><ul><li>default: 기본</li><li>input: 입력형</li><li>color: 색상</li></ul></td></tr><tr><td>code</td><td></td><td>옵션 코드</td></tr><tr><td>name</td><td></td><td>옵션명</td></tr><tr><td>value_list</td><td></td><td><p>옵션값 목록 <a href="getOptions.md#rod_type_data-digital-data">ProdOptionValueData</a></p><p>입력형 옵션은 해당되지 않습니다.</p></td></tr><tr><td>is_require</td><td></td><td>필수옵션 여부</td></tr></tbody></table>

### ProdOptionValueData

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>code</td><td></td><td>옵션값 코드</td></tr><tr><td>name</td><td></td><td>옵션값 명</td></tr></tbody></table>
