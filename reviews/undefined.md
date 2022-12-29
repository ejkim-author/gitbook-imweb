# 상품 구매평 수정

{% swagger method="patch" path="/reviews/{구매평번호}" baseUrl="https://api.imweb.me/v2/shop" summary="수정 시 변경할 항목만 전달하세요." %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>nick</td><td></td><td>작성자명</td></tr><tr><td>body</td><td></td><td>구매평 내용</td></tr><tr><td>rating</td><td></td><td>구매평 점수</td></tr></tbody></table>
