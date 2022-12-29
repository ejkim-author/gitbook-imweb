# 여러 품목 주문 목록 조회

{% swagger method="get" path="/prod-orders" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **요청 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td><p>주문서 번호 목록</p><p>주문서 번호는 최대 25개까지 입력할 수  있습니다.</p></td></tr></tbody></table>

## **응답 데이**터

[품목 주문서 조회](prodOrders.md)와 동일하나, 아래와 같은 구조로 응답합니다.

```
Array
(
    [msg] => SUCCESS
    [code] => 200
    [request_count] => 4
    [version] => 2.0
    [data] => Array
        (
            [주문서번호] => Array
                (
                    [품목주문서번호] => Array
                        (
                            [code] => 품목주문서코드
                            [order_no] => 품목주문서번호
                            ...
```
