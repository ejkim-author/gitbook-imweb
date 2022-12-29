# 상품 구매평 조회

{% swagger method="get" path="/reviews" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="/reviews/{구매평번호}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_no</td><td></td><td><p>상품 번호</p><p>특정 상품의 구매평만 조회하는 경우 입력하세요.</p></td></tr><tr><td>type</td><td></td><td><p>구매평 타입</p><p>특정 타입의 구매평만 조회하는 경우 입력하세요.</p><ul><li>imweb: 아임웹 구매평</li><li>npay: 네이버페이 구매평</li></ul></td></tr><tr><td>rating</td><td></td><td><p>구매평 점수</p><p>특정 점수의 구매평만 조회하는 경우 입력하세요.</p></td></tr><tr><td>is_photo</td><td></td><td>포토 구매평만 조회하는경우 true값을 전달하세요.</td></tr></tbody></table>

## **응답 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>idx</td><td></td><td>구매평 번호</td></tr><tr><td>np_review_id</td><td></td><td>네이버페이 구매평 번호</td></tr><tr><td>type</td><td></td><td><p>구매평 타입</p><ul><li>imweb: 아임웹 구매평</li><li>npay: 네이버페이 구매평</li></ul></td></tr><tr><td>prod_no</td><td></td><td>상품 번호</td></tr><tr><td>prod_option</td><td></td><td>상품 옵션 이름</td></tr><tr><td>nick</td><td></td><td>작성자</td></tr><tr><td>body</td><td></td><td>구매평 내용</td></tr><tr><td>rating</td><td></td><td>구매평 점수</td></tr><tr><td>is_secret</td><td></td><td>비밀글 여부</td></tr><tr><td>is_hide</td><td></td><td>숨김 여부</td></tr><tr><td>is_photo</td><td></td><td>포토  구매평 여부</td></tr><tr><td>read_cnt</td><td></td><td>조회수</td></tr><tr><td>wtime</td><td></td><td><p>작성 시간</p><p>Timestamp</p></td></tr></tbody></table>

