# 상품 문의 조회

{% swagger method="get" path="/inquirys" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="/inquirys/{문의번호}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>status</td><td></td><td><p>답변 상태</p><p>특정 상태의 문의만 조회하고 싶은 경우 입력하세요.</p><ul><li>WAIT: 답변 대기</li><li>COMPLETE: 답변 완료</li></ul></td></tr></tbody></table>

## **응답 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>idx</td><td></td><td>문의 번호</td></tr><tr><td>np_review_id</td><td></td><td>네이버페이 문의 번호</td></tr><tr><td>type</td><td></td><td><p>문의 타입</p><ul><li>imweb: 아임웹 문의</li><li>npay: 네이버페이 문의</li></ul></td></tr><tr><td>prod_no</td><td></td><td>상품 번호</td></tr><tr><td>nick</td><td></td><td>작성자</td></tr><tr><td>subject</td><td></td><td>문의 제목</td></tr><tr><td>body</td><td></td><td>문의 내용</td></tr><tr><td>images</td><td></td><td>첨부 이미지 목록</td></tr><tr><td>is_secret</td><td></td><td>비밀글 여부</td></tr><tr><td>is_hide</td><td></td><td>숨김 여부</td></tr><tr><td>read_cnt</td><td></td><td>조회수</td></tr><tr><td>status</td><td></td><td><p>답변 상태</p><ul><li>WAIT: 답변 대기</li><li>COMPLETE: 답변 완료</li></ul></td></tr><tr><td>writer_ip</td><td></td><td>작성자 IP</td></tr><tr><td>wtime</td><td></td><td><p>작성 시간</p><p>Timestamp</p></td></tr></tbody></table>
