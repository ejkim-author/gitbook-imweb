# 품목 주문 목록 조회

{% swagger method="get" path="/orders/{주문번호}/prod-orders" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="get" path="/orders/{주문번호}/prod-orders/{품목주문번호}" baseUrl="https://api.imweb.me/v2/shop" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **응답 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>order_no</td><td></td><td>품목 주문 번호</td></tr><tr><td>status</td><td></td><td>품목 주문서 상태</td></tr><tr><td>claim_status</td><td></td><td>품목 주문서 클레임 상태</td></tr><tr><td>claim_type</td><td></td><td>품목 주문서 클레임 타입</td></tr><tr><td>pay_time</td><td></td><td><p>결제 시간</p><p>Timestamp</p></td></tr><tr><td>delivery_time</td><td></td><td><p>배송 시작 시간</p><p>Timestamp</p></td></tr><tr><td>complete_time</td><td></td><td><p>배송 완료 시간</p><p>Timestamp</p></td></tr><tr><td>parcel_code</td><td></td><td>택배사 코드</td></tr><tr><td>invoice_no</td><td></td><td>운송장 번호</td></tr><tr><td>items</td><td></td><td>주문 아이템 정보</td></tr></tbody></table>

### **ProdOrderItem Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>no</td><td></td><td>번호</td></tr><tr><td>prod_no</td><td></td><td>상품 번호</td></tr><tr><td>prod_name</td><td></td><td>상품명</td></tr><tr><td>prod_custom_code</td><td></td><td>상품 자체 코드</td></tr><tr><td>prod_sku_no</td><td></td><td>상품 SKU</td></tr><tr><td>payment</td><td></td><td><p>결제 정보</p><p><a href="prodOrders.md#prodorderitempayment-data">ProdOrderItemPaymentData</a></p></td></tr><tr><td>delivery</td><td></td><td><p>배송 정보</p><p><a href="prodOrders.md#prodorderitemdelivery-data">ProdOrderItemDeliveryData</a></p></td></tr><tr><td>options</td><td></td><td><p>옵션 정보</p><p><a href="prodOrders.md#prodorderitemoption-data">ProdOrderItemOptionData</a></p></td></tr></tbody></table>

### **ProdOrderItemPayment Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>count</td><td></td><td>상품 갯수</td></tr><tr><td>price</td><td></td><td>상품 금액</td></tr><tr><td>price_tax_free</td><td></td><td>상품 면세 금액</td></tr><tr><td>deliv_price_tax_free</td><td></td><td>비과세 상품 배송비</td></tr><tr><td>deliv_price</td><td></td><td>기본 배송비</td></tr><tr><td>island_price</td><td></td><td>도서산간 배송비</td></tr><tr><td>price_sale</td><td></td><td>상품 할인 금액</td></tr><tr><td>point</td><td></td><td>사용 적립금</td></tr><tr><td>coupon</td><td></td><td>쿠폰 할인 금액</td></tr><tr><td>membership_discount</td><td></td><td>회원 등급 할인 금액</td></tr><tr><td>period_discount</td><td></td><td>즉시/기간 할인 금액</td></tr></tbody></table>

### **ProdOrderItemDelivery Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>deliv_code</td><td></td><td>배송 코드</td></tr><tr><td>deliv_price_mix</td><td></td><td>묶음 배송 여부</td></tr><tr><td>deliv_group_code</td><td></td><td>묶음 배송 그룹 코드</td></tr><tr><td>deliv_type</td><td></td><td><p>배송 방법</p><ul><li>parcel: 택배</li><li>direct: 직접 배송</li><li>quick: 퀵배송</li><li>visit: 방문 수령</li><li>no_deliv: 배송 없음</li><li>download: 디지털 콘텐츠</li><li>subscribe: 회원그룹 이용권 </li></ul></td></tr><tr><td>deliv_pay_type</td><td></td><td><p>배송비 결제 방식</p><ul><li>price: 선결제</li><li>deliv_price_after: 착불</li></ul></td></tr><tr><td>deliv_price_type</td><td></td><td><p>배송비 부과 방식</p><ul><li>fix: 고정 배송비</li><li>free: 무료 배송비</li><li>flexable: 조건부 무료</li><li>weight: 무게 별 배송비</li><li>quantity: 수량 별 배송비</li><li>amount: 구매 금액 별 배송비</li></ul></td></tr></tbody></table>

### **ProdOrderItemOption Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>no</td><td></td><td>번호</td></tr><tr><td>type</td><td></td><td><p>옵션 타입</p><ul><li>require: 필수 옵션</li><li>optional: 선택 옵션</li></ul></td></tr><tr><td>stock_sku_no</td><td></td><td>옵션 SKU</td></tr><tr><td>option_code_list</td><td></td><td>옵션 코드 목록</td></tr><tr><td>option_name_list</td><td></td><td>옵션명 목록</td></tr><tr><td>value_code_list</td><td></td><td>옵션값 코드 목록</td></tr><tr><td>value_name_list</td><td></td><td>옵션값 이름 목록</td></tr><tr><td>option_data</td><td></td><td>옵션 데이터</td></tr><tr><td>payment</td><td></td><td><p>결제 정보</p><p><a href="prodOrders.md#prodorderitemoption-data-1">ProdOrderItemOptionPayment Data</a></p></td></tr></tbody></table>

### **ProdOrderItemOptionPayment Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>price</td><td></td><td>옵션 가격</td></tr><tr><td>count</td><td></td><td>옵션 갯수</td></tr><tr><td>deliv_price</td><td></td><td>옵션 기본 배송비</td></tr><tr><td>island_price</td><td></td><td>옵션 도서산간 배송비</td></tr></tbody></table>

### ****
