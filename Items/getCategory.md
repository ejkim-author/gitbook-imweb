# 상품 카테고리 조회

{% swagger method="get" path="/categories" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="/categories/{카테고리 코드}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 응답 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>code</td><td></td><td>카테고리 코드</td></tr><tr><td>name</td><td></td><td>카테고리명</td></tr><tr><td>list</td><td></td><td>하위 카테고리 목록</td></tr></tbody></table>
