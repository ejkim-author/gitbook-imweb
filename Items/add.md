# 상품 등록 및 수정

{% swagger method="post" path="" baseUrl="https://api.imweb.me/v2/shop/products" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}



{% swagger method="patch" path="{상품번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="수정 시 변경할 항목만 전달하세요." %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **요청 데이터**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>categories</td><td></td><td>상품 카테고리 코드<br><a href="getCategory.md">상품 카테고리 조회 API 바로가기</a></td></tr><tr><td>showcase</td><td></td><td><p>기획전 코드</p><p><a href="getShowcases.md">기획전 조회 API 바로가기</a></p></td></tr><tr><td>images</td><td></td><td><p>상품 이미지</p><p>이미지 URL로 등록하세요.</p></td></tr><tr><td>name</td><td></td><td>상품명</td></tr><tr><td>simple_content</td><td></td><td>요약 설명</td></tr><tr><td>content</td><td></td><td>상세 설명</td></tr><tr><td>use_mobile_prod_content</td><td></td><td>모바일 상세 설명 사용 여부</td></tr><tr><td>mobile_content</td><td></td><td><p>모바일 상세 설명</p><p>모바일 상세 설명 사용 여부가 true일 때만 필수</p></td></tr><tr><td>prod_status</td><td></td><td><p>상태</p><ul><li><strong>sale</strong>: 판매 중</li><li><strong>soldout:</strong> 품절</li><li><strong>nosale</strong>: 숨김</li></ul></td></tr><tr><td>prod_type</td><td></td><td><p>판매 방식 설정</p><ul><li><strong>normal</strong>: 일반 상품</li><li><del>digital: 디지털 상품</del></li><li><strong>subscribe</strong>: 회원그룹 이용권</li></ul></td></tr><tr><td>subscribe_group_code</td><td></td><td><p>대상 그룹 코드</p><p>회원그룹 이용권 시 필수</p></td></tr><tr><td>subscribe_period</td><td></td><td><p>그룹 유지 기간(일)</p><p>회원그룹 이용권 시 필수</p></td></tr><tr><td>is_badge_new</td><td></td><td>신상품</td></tr><tr><td>is_badge_best</td><td></td><td>베스트</td></tr><tr><td>is_badge_md</td><td></td><td>MD추천</td></tr><tr><td>is_badge_hot</td><td></td><td>주문 폭주</td></tr><tr><td>origin</td><td></td><td>원산지</td></tr><tr><td>maker</td><td></td><td>제조사</td></tr><tr><td>brand</td><td></td><td>브랜드</td></tr><tr><td>seo_title</td><td></td><td>SEO 검색엔진 최적화 - 제목</td></tr><tr><td>seo_description</td><td></td><td>SEO 검색엔진 최적화 - 메타 설명</td></tr><tr><td>seo_access_bot</td><td></td><td>SEO 검색엔진 최적화 - 검색엔진에서 제외 여부</td></tr><tr><td>price</td><td></td><td>상품 가격</td></tr><tr><td>price_org</td><td></td><td>할인 이전 가격</td></tr><tr><td>price_tax</td><td></td><td>세금 포함 여부</td></tr><tr><td>price_none</td><td></td><td>가격 없음 여부</td></tr><tr><td>prodinfo</td><td></td><td><p>상품 정보 고시 <a href="add.md#prodinfo">작성 예시</a></p><ul><li>product: 상품 정보 고시명</li><li><p>상품 정보 고시 추가 데이터</p><p><a href="../appendix/undefined-1.md">상품 정보 고시</a></p></li></ul></td></tr><tr><td>give_point_type</td><td></td><td><p>적립금 설정 타입</p><ul><li>common: 기본 설정을 따름</li><li>individual: 개별 적립금 설정</li></ul></td></tr><tr><td>give_point_value_type</td><td></td><td><p>적립금 단위</p><ul><li>percent: 퍼센트</li><li>price: 통화 단위</li></ul></td></tr><tr><td>give_point_value</td><td></td><td><p>적립금 값</p><p>적립금 값 타입이 percent일 경우 백분율 단위로 입력</p></td></tr><tr><td>product_discount_options</td><td></td><td><p>할인 사용 설정</p><ul><li>coupon: 쿠폰</li><li>point: 적립금</li><li>shopping_group_dc: 쇼핑등 급 할인</li><li>period: 즉시/기간 할인</li></ul></td></tr><tr><td>period_discount_data</td><td></td><td><p>즉시/기간 할인 설정</p><ul><li><p>group_type: 할인 적용 대상 </p><p>guest(회원+비회원)</p><p>member(회원)</p><p>그룹지정은 미지원</p></li><li>dc_price: 할인 금액</li><li>dc_type: 할인 금액 단위</li></ul></td></tr><tr><td>use_pre_sale</td><td></td><td>판매 기간 사용 유무</td></tr><tr><td>pre_sale_start_date</td><td></td><td><p>판매 기간 시작일</p><p>예) 2020-06-01 14:00:00</p></td></tr><tr><td>pre_sale_end_date</td><td></td><td><p>판매 기간 종료일</p><p>예) 2020-06-01 16:00:00</p></td></tr><tr><td>weight</td><td></td><td>상품 무게</td></tr><tr><td>custom_prod_code</td><td></td><td>자체 상품 코드</td></tr><tr><td>pay_product_name</td><td></td><td>외부 연동용 정보 - 네이버, 카카오 노출용 상품명</td></tr><tr><td>event_words</td><td></td><td>외부 연동용 정보 - 네이버 쇼핑 이벤트 문구</td></tr><tr><td>naver_category</td><td></td><td>외부 연동용 정보 - 네이버 쇼핑 카테고리 ID</td></tr><tr><td>condition</td><td></td><td><p>외부 연동용 정보 - 상품 상태</p><ul><li>신상품</li><li>중고</li><li>리퍼</li><li>전시</li><li>반품</li><li>스크래치</li></ul></td></tr><tr><td>product_flag</td><td></td><td><p>외부 연동용 정보 - 판매 방식</p><ul><li>소매</li><li>도매</li><li>렌탈</li><li>대여</li><li>할부</li><li>예약판매</li><li>구매대행</li></ul></td></tr><tr><td>order_made</td><td></td><td>외부 연동용 정보 - 주문 제작 상품</td></tr><tr><td>parallel_import</td><td></td><td>외부 연동용 정보 - 병행 수입</td></tr><tr><td>import_flag</td><td></td><td>외부 연동용 정보 - 해외 구매대행</td></tr><tr><td>is_culture_benefit</td><td></td><td>외부 연동용 정보 - 도서공연비 소득공제</td></tr><tr><td>minimum_purchase_quantity</td><td></td><td>최소 구매 수량</td></tr><tr><td>minimum_purchase_quantity</td><td></td><td>1회 구매 시 최대 수량</td></tr><tr><td>member_maximum_purchase_quantity</td><td></td><td>1인 구매 시 최대 수량</td></tr><tr><td>optional_limit_type</td><td></td><td><p>0원 선택 옵션 구매 시 최대 구매수량 제한 타입</p><ul><li>relative: 본상품 구매 수량만큼 구매 가능</li><li>limit: 최대 구매 수량 제한</li><li>unique: 1개만 구매 가능</li></ul></td></tr><tr><td>optional_limit</td><td></td><td>0원 선택 옵션 구매 시 최대 구매 수량 - 최대 구매 수량 제한</td></tr><tr><td>use_unipass_number</td><td></td><td><p>개인 통관 고유번호 사용 설정</p><ul><li>default: 기본 방법을 따름 (쇼핑 환경설정)</li><li>Y: 사용</li><li>N: 사용 안함</li></ul></td></tr><tr><td>adult</td><td></td><td>미성년자 구매 제한</td></tr><tr><td>display</td><td></td><td><p>외부 노출</p><ul><li>NAVER: 네이버 쇼핑</li><li>DAUM: 다음(카카오) 쇼핑하우</li><li>NPAY: 네이버페이 구매 가능</li><li>TALKPAY: 카카오페이 구매 가능</li><li>FACEBOOK: Facebook 다이나믹 광고</li><li>CRITEO: CRITEO 광고</li></ul></td></tr><tr><td>stock_use</td><td></td><td>재고 관리 사용 유무</td></tr><tr><td>stock_unlimit</td><td></td><td>재고 소진 후에도 주문 가능 유무</td></tr><tr><td>stock_no_option</td><td></td><td>본 상품 재고</td></tr><tr><td>sku_no_option</td><td></td><td>본 상품 재고 번호(SKU)</td></tr><tr><td>options</td><td></td><td>상품 옵션 데이터 <a href="add.md#options">작성예시</a></td></tr></tbody></table>

### prodinfo **작성 예시**

```
$data['prodinfo'] = [];
$data['prodinfo']['product'] = '구두';
$data['prodinfo']['material'] = '가죽';
$data['prodinfo']['color'] = '그레이';
$data['prodinfo']['size'] = '270';
...
```

### options **작성 예시**&#x20;

```
$data['options'] = [];
$data['options']['is_mix'] = false; // 조합형 옵션
$data['options']['list'] = [
	[		
		'is_require' => true,
		'type' => 'default', // 기본 옵션
		'name' => '테스트 옵션',
		'values' => ['A', 'B', 'C'],
	],
	[
		'is_require' => true,
		'type' => 'color', // 색상 옵션
		'name' => '테스트 옵션2',
		'values' => [
			[
				'name' => 'X',
				'data' => [
					'color' => '#AAA',
					'image_url' => ''
				]
			],
			[
				'name' => 'Y',
				'data' => [
					'color' => '#AAA',
					'image_url' => ''
				]
			],
			[
				'name' => 'Z',
				'data' => [
					'color' => '#AAA',
					'image_url' => ''
				]
			],
		]
	],
];
```

### **ProdOptions Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>is_mix</td><td></td><td>조합형 옵션 여부</td></tr><tr><td>list</td><td></td><td><p>옵션 구성</p><p><strong></strong><a href="add.md#prodseodata-data"><strong>ProdOptionsList Data</strong></a><strong></strong></p></td></tr></tbody></table>

### **ProdOptionsList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>옵션 타입</p><ul><li>default: 기본</li><li>input: 입력형</li><li>color: 색상</li></ul></td></tr><tr><td>name</td><td></td><td><p>옵션 구성</p><p><strong></strong><a href="add.md#prodseodata-data"><strong>ProdOptionsList Data</strong></a><strong></strong></p></td></tr><tr><td>values</td><td></td><td><p>옵션값 데이터</p><p>기본, 색상 옵션만 해당합니다.</p><p><a href="add.md#prodoptionslistvalue-data">ProdOptionsListValueData</a></p></td></tr><tr><td>is_require</td><td></td><td><p>필수 옵션 여부</p><p>입력형 옵션은 필수 옵션으로만 사용이 가능합니다.</p></td></tr></tbody></table>

### **ProdOptionsList Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>type</td><td></td><td><p>옵션 타입</p><ul><li>default: 기본</li><li>input: 입력형</li><li>color: 색상</li></ul></td></tr><tr><td>name</td><td></td><td>옵션명</td></tr><tr><td>values</td><td></td><td><p>옵션 값 데이터</p><p>기본, 색상 옵션만 해당됩니다.</p><p><a href="add.md#prodoptionslist-data-2">ProdOptionsListValueData</a></p></td></tr><tr><td>is_require</td><td></td><td><p>필수 옵션 여부</p><p>입력형 옵션은 필수 옵션으로만 사용이 가능합니다.</p></td></tr></tbody></table>

### **ProdOptionsListValue Data**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>name</td><td></td><td>옵션값 명</td></tr><tr><td>data</td><td></td><td><p>옵션 추가 데이터</p><p>옵션 추가 데이터가 필요한 옵션 타입의 경우 추가 데이터를 필수로 전달해주셔야 합니다.</p><p>색상: <a href="add.md#prodoptionslistvalue-data-1">ProdOptionsColorEtcData</a></p></td></tr></tbody></table>

### ProdOptionsColorEtc Dat**a**

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>color</td><td></td><td><p>색상코드</p><p>예) #00000</p></td></tr><tr><td>image_url</td><td></td><td>색상옵션 이미지 URL</td></tr></tbody></table>

