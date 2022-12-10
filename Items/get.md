# 상품 조회

{% swagger method="get" path="{상품번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="상품번호를 입력하지 않으면 전체 상품 목록을 조회합니다." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="category" type="String" %}
상품 카테고리 코드
{% endswagger-parameter %}

{% swagger-parameter in="path" name="prod_status" type="String" %}
상품 상태
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## **상품 목록 요청 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>prod_status</td><td></td><td><p>특정 상태의 상품을 조회할 때 입력합니다.</p><p><br>상품 상태 종류</p><ul><li><strong>sale</strong>: 판매중</li><li><strong>soldout</strong>: 품절</li><li>nosale: 숨김</li></ul></td></tr><tr><td>category</td><td></td><td>상품 카테고리 코드<br><a href="getCategory.md">상품 카테고리 조회</a></td></tr></tbody></table>

## **응답 데이터**

### **기본 응답 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>no</td><td></td><td>상품번호</td></tr><tr><td>prod_status</td><td></td><td><p>상품 상태</p><ul><li>sale: 판매중</li><li>soldout: 품절</li><li>nosale: 숨김</li></ul></td></tr><tr><td>categories</td><td></td><td>카테고리 코드 목록</td></tr><tr><td>custom_prod_code</td><td></td><td>자체 상품코드</td></tr><tr><td>name</td><td></td><td>상품명</td></tr><tr><td>images</td><td></td><td>이미지 파일 코드</td></tr><tr><td>image_url</td><td></td><td>이미지 파일 URL</td></tr><tr><td>content</td><td></td><td>상세설명</td></tr><tr><td>simple_content</td><td></td><td>요약 설명</td></tr><tr><td>use_mobile_prod_content</td><td></td><td>모바일 상세설명 사용 유무</td></tr><tr><td>mobile_content</td><td></td><td>모바일 상세 설명</td></tr><tr><td>prod_type</td><td></td><td><p>판매 방식 설정</p><ul><li>normal: 일반 상품</li><li>digital: 디지털 상품세부 정보는 prod_type_data 참고</li><li>subscribe: 회원그룹 이용권세부 정보는 prod_type_data 참고</li></ul></td></tr><tr><td>prod_type_data</td><td></td><td><p>판매 방식 데이터</p><p>prod_type 형식에 맞는 데이터를 전달해주세요.</p><ul><li>디지털 상품(<a href="get.md#prod_type_data-digital-data">Dgital Data</a>)</li><li>회원그룹 이용권 상품(<a href="get.md#prod_type_data-subscribe-data">Subscribe Data</a>)</li></ul></td></tr><tr><td>use_pre_sale</td><td></td><td>판매기간 설정 여부</td></tr><tr><td>pre_sale_start_date</td><td></td><td>판매기간 시작일(Timestamp)</td></tr><tr><td>pre_sale_end_date</td><td></td><td>판매기간 종료일(Timestamp)</td></tr><tr><td>price</td><td></td><td>상품가격</td></tr><tr><td>price_org</td><td></td><td>할인 이전 가격</td></tr><tr><td>price_tax</td><td></td><td>세금 포함 여부</td></tr><tr><td>price_none</td><td></td><td>가격 없음 여부</td></tr><tr><td>point</td><td></td><td>적립금 설정 (<a href="get.md#point-config-data">PointConfigData</a>)</td></tr><tr><td>product_discount_options</td><td></td><td><p>할인 사용 설정</p><ul><li>coupon: 쿠폰</li><li>point: 적립금</li><li>shopping_group_dc: 쇼핑등급 할인</li></ul></td></tr><tr><td>weight</td><td></td><td>상품 무게</td></tr><tr><td>stock</td><td></td><td><p>상품 재고 정보</p><p>옵션 재고 정보는 옵션 정보를 참고해주세요. (<a href="get.md#prodstockconfig-data">ProdStockConfigData</a>)</p></td></tr><tr><td>origin</td><td></td><td>원산지</td></tr><tr><td>maker</td><td></td><td>제조사</td></tr><tr><td>brand</td><td></td><td>브랜드</td></tr><tr><td>badge</td><td></td><td>뱃지 정보 (<a href="get.md#prodbadge-data">ProdBadgeData</a>)</td></tr><tr><td>seo</td><td></td><td>SEO 관련 정보 (<a href="get.md#prodseodata-data">ProdSeoData</a>)</td></tr><tr><td>sync</td><td></td><td>외부 연동용 정보(<a href="get.md#prodsyncdata-data">ProdSyncData</a>)</td></tr><tr><td>etc</td><td></td><td>기타설정 (<a href="get.md#prodetcdata-data">ProdEtcData</a>)</td></tr><tr><td>prodinfo</td><td></td><td>상품정보제공고시</td></tr><tr><td>is_exist_options</td><td></td><td><p>상품의 옵션 유무</p><ul><li>Y: 옵션이 존재</li><li>N: 단일 상품</li></ul></td></tr><tr><td>is_mix</td><td></td><td><p>상품의 조합형 옵션 여부</p><ul><li>Y: 조합형 옵션</li><li>N: 단일 옵션</li></ul></td></tr><tr><td>add_time</td><td></td><td>상품 추가시간 Timestamp</td></tr><tr><td>edit_time</td><td></td><td>상품 최근 수정시간 Timestamp</td></tr></tbody></table>

### **prod\_type\_data - Digital Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>use_limit</td><td></td><td>다운로드 한도 설정</td></tr><tr><td>period</td><td></td><td>기간 제한</td></tr><tr><td>maximum</td><td></td><td>횟수 제한</td></tr></tbody></table>

### **prod\_type\_data - Subscribe Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>group_code</td><td></td><td>대상 그룹 코드</td></tr><tr><td>period</td><td></td><td>그룹 유지 기간(일)</td></tr></tbody></table>

### **Point Config Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>적립금 설정 타입</p><ul><li>common: 기본 설정을 따름</li><li>individual: 개별 적립금 설정</li></ul></td></tr><tr><td>value_type</td><td></td><td><p>적립금 적립 단위</p><ul><li>percent: 퍼센트</li><li>price: 통화 단위</li></ul></td></tr><tr><td>value</td><td></td><td><p>적립금 값</p><p>적립금 단위가 퍼센트일 경우 백분율로 계산</p></td></tr></tbody></table>

### Period Discount Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>group_type</td><td></td><td><p>할인적용대상</p><ul><li>회원+비회원</li><li>회원</li><li>그룹 명</li></ul></td></tr><tr><td>dc_price</td><td></td><td><p>할인 금액</p><p>단위가 퍼센트일 경우 백분율로 계산</p></td></tr><tr><td>dc_type</td><td></td><td><p>할인금액 단위</p><ul><li>percent: 퍼센트</li><li>price: 통화 단위</li></ul></td></tr></tbody></table>

### **ProdStockConfig** Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>stock_use</td><td></td><td>재고 사용여부</td></tr><tr><td>stock_unlimit</td><td></td><td>재고 소진 후 주문 가능 여부</td></tr><tr><td>stock_no_option</td><td></td><td>상품 재고 수량</td></tr><tr><td>sku_no_option</td><td></td><td>상품 재고번호(SKU)</td></tr></tbody></table>

### **ProdBadge Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>new</td><td></td><td>뱃지 - 신상품 여부</td></tr><tr><td>best</td><td></td><td>뱃지 - 베스트 여부</td></tr><tr><td>md</td><td></td><td>뱃지 - MD 추천 여부</td></tr><tr><td>hot</td><td></td><td>뱃지 - 주문폭주 여부</td></tr></tbody></table>

### **ProdSeoData Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>seo_title</td><td></td><td>SEO 제목</td></tr><tr><td>seo_description</td><td></td><td>SEO 설명</td></tr><tr><td>seo_access_bot</td><td></td><td>SEO 검색엔진 접근 제외 유무</td></tr></tbody></table>

### **ProdSyncData Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>pay_product_name</td><td></td><td>네이버, 카카오 쇼핑 노출용 상품명</td></tr><tr><td>event_words</td><td></td><td>네이버 쇼핑 이벤트 문구</td></tr><tr><td>naver_category</td><td></td><td>네이버 쇼핑 카테고리 ID</td></tr><tr><td>product_flag</td><td></td><td><p>네이버 쇼핑 판매 방식</p><ul><li>소매</li><li>도매</li><li>렌탈</li><li>대여</li><li>할부</li><li>예약판매</li><li>구매대행</li></ul></td></tr><tr><td>product_condition</td><td></td><td><p>네이버 쇼핑 상품상태</p><ul><li>신상품</li><li>중고</li><li>리퍼</li><li>전시</li><li>반품</li><li>스크래치</li></ul></td></tr><tr><td>import_flag</td><td></td><td>해외구매대행 여부</td></tr><tr><td>parallel_import</td><td></td><td>병행수입 여부</td></tr><tr><td>is_culture_benefit</td><td></td><td>도서공연비 소득공제</td></tr><tr><td>order_made</td><td></td><td>주문제작 여부</td></tr></tbody></table>

### **ProdEtcData Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>minimum_purchase_quantity</td><td></td><td>최소 구매 수량</td></tr><tr><td>maximum_purchase_quantity</td><td></td><td>1회 구매 시 최대 수량</td></tr><tr><td>member_maximum_purchase_quantity</td><td></td><td>1인 구매 시 최대 수량</td></tr><tr><td>optional_limit_type</td><td></td><td><p>0원 선택옵션 구매 시 최대 구매수량 제한 타입</p><ul><li>relative: 본상품 구매 수량만큼 구매 가능</li><li>limit: 최대 구매 수량 제한</li><li>unique: 1개만 구매 가능</li></ul></td></tr><tr><td>optional_limit</td><td></td><td>0원 선택옵션 구매 시 최대 구매수량 - 최대 구매 수량 제한</td></tr><tr><td>use_unipass_number</td><td></td><td><p>개인통관고유부호 사용 설정</p><ul><li>default: 기본 방법을 따름 (쇼핑 환경설정)</li><li>Y: 사용</li><li>N: 사용안함</li></ul></td></tr><tr><td>adult</td><td></td><td>미성년자 구매 제한</td></tr></tbody></table>
