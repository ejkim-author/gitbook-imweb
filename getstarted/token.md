# 액세스 토큰 발급받기

{% hint style="info" %}
API Key와 Secret Key를 통해 인증이 완료되면 액세스 토큰을 발급받을 수 있습니다. 발급받은 액세스 토큰은 모든 Rest API 요청 시 요청 헤더에 포함하여 전달해주셔야 합니다. 제휴사의 경우 업체 코드를 헤더로 전달해주셔야 합니다.
{% endhint %}

### 토큰 발급

{% swagger baseUrl="https://api.imweb.me" path="/v2/auth" method="get" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="ACCESS_AFFILIATE" type="string" %}
**제휴사 업체 코드**

\




\


제휴사의 경우에만 입력합니다.

\


제휴사 코드는 담당자에게 문의바랍니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" %}
API Key
{% endswagger-parameter %}

{% swagger-parameter in="query" name="secret" type="string" %}
Secret Key
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{"msg":"SUCCESS","code":200,"access_token":"{ACCESS_TOKEN}"}
```
{% endswagger-response %}
{% endswagger %}

### 호출 예시

{% tabs %}
{% tab title="CURL" %}
```bash
curl -d '{"key": "{API_KEY}", "secret":"{SECRET}"}' https://api.imweb.me/v2/auth
```
{% endtab %}

{% tab title="PHP" %}
```bash
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://api.imweb.me/v2/auth');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1) ;
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode([
	'key'=> '{API_KEY}',
	'secret'=> '{SECRET}',
]));
$res = curl_exec($ch);
curl_close($ch);
```
{% endtab %}
{% endtabs %}

### 응답 데이터

```
{"msg":"SUCCESS","code":200,"access_token":"{ACCESS_TOKEN}"}
```

| 항목            | 타입      | 설명     |
| ------------- | ------- | ------ |
| msg           | string  | 응답 메세지 |
| code          | integer | 응답 코드  |
| access\_token | string  | 액세스 토큰 |
