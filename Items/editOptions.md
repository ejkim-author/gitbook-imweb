# 상품 옵션 수정

{% swagger method="patch" path="{상품번호}/options/{옵션번호}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

{% swagger method="patch" path="{상품번호}/options/{옵션코드}" baseUrl="https://api.imweb.me/v2/shop/products/" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## **요청 데이**터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>name</td><td></td><td>옵션명</td></tr><tr><td>value_list</td><td></td><td><p>옵션값 데이터</p><p><strong></strong><a href="editOptions.md#prodoptionvaluedata"><strong>OptionValueData</strong></a><strong></strong></p></td></tr></tbody></table>

### value\_list 예시

```
$data = [
	'name' => '변경할 옵션명',
	'value_list' => [
		'{옵션값 코드}' => [
			'name' => '변경할 옵션값명'
		]
	]
];
```

### **OptionValueDat**a

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>name</td><td></td><td>옵션값 명</td></tr></tbody></table>
