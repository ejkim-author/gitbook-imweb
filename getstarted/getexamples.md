# API 호출 예제

{% tabs %}
{% tab title="CURL" %}
```
curl -X GET -H "Content-Type: application/json" -H "access-token: {ACCESS_TOKEN}" -d '{"version":"latest"}' https://api.imweb.me/v2/shop/products
```
{% endtab %}

{% tab title="PHP" %}
```php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://api.imweb.me/v2/shop/products');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1) ;
curl_setopt($ch, CURLOPT_HTTPHEADER, ['access-token: {ACCESS_TOKEN}']);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(['version' => 'latest']));
$res = curl_exec($ch);
curl_close($ch);
```
{% endtab %}
{% endtabs %}

### 요청 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>version</td><td></td><td><strong>요청 Rest API 버전</strong><br>가장 최신 버전을 사용하시려면 <strong>공백</strong> 또는 <strong>latest</strong>로 전달해주세요.</td></tr><tr><td>offset</td><td></td><td><p><strong>시작 페이지</strong></p><p>기본값 : 1 <br>목록 조회 API 요청 시 페이징 처리를 위한 데이터입니다.</p></td></tr><tr><td>limit</td><td></td><td><p><strong>페이지 사이즈</strong></p><p>기본값 : 25 <br>최대값 : 100 <br>목록 조회 API 요청 시 페이징 처리를 위한 데이터입니다.</p></td></tr><tr><td>...</td><td></td><td><p><strong>추가 요청 데이터</strong></p><p>각 기능에 맞는 추가 요청 데이터를 전달해주셔야 합니다.</p></td></tr></tbody></table>

### 응답 데이터

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>msg</td><td></td><td>API 응답 메세지</td></tr><tr><td>code</td><td></td><td>API 응답 코드</td></tr><tr><td>request_count</td><td></td><td>API 요청 가능 횟수</td></tr><tr><td>version</td><td></td><td>API 버전</td></tr><tr><td>data</td><td></td><td>API 응답 데이</td></tr></tbody></table>

#### 예시

```javascript
Array
(
    [msg] => SUCCESS
    [code] => 200
    [request_count] => 4
    [version] => 2.0
    [data] => Array
        (
            [list] => Array
                (
                    [0] => Array
                        (
                            [no] => 13805
                            [categories] => Array
                                (
                                    [0] => s201801045a4dc150f0580
                                )

                            [custom_prod_code] => 13805
                            [name] => Rest API 이미지 업로드 테스트
                            [content] => 상품설명
                            [content_plain] => 상품설명
...
```

### Pagenation Data

<table><thead><tr><th>항목</th><th data-type="select">타입</th><th>설명</th></tr></thead><tbody><tr><td>data_count</td><td></td><td>데이터 총 갯수</td></tr><tr><td>current_page</td><td></td><td>현재 페이지 번호</td></tr><tr><td>total_page</td><td></td><td>총 페이지 갯수</td></tr><tr><td>pagesize</td><td></td><td>페이지 당 데이터 갯수</td></tr></tbody></table>
