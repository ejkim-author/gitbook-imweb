# Step 3: 액세스 토큰 발급받기

API Key와 Secret Key를 발급받아 인증 절차를 완료하면 액세스 토큰을 발급받을 수 있습니다.

아래와 같은 API를 요청하여 액세스 토큰을 발급받습니다.

{% swagger baseUrl="https://api.imweb.me" path="/v2/auth" method="get" summary="액세스 토큰 조회" %}
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

{% swagger-parameter in="body" name="api" required="true" %}
API Key
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secret" required="true" %}
Secret Key
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```
{"msg":"SUCCESS","code":200,"access_token":"{ACCESS_TOKEN}"}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="success" %}
사용자가 제휴사인 경우, 해당하는 업체 코드를 요청 파라미터의헤더 값으로 전달합니다.
{% endhint %}

{% hint style="warning" %}
발급받은 액세스 토큰은 본 문서에서 설명하는 모든 아임웹 API 요청 시, 요청 파라미터의헤더값으로 전달해야 합니다.
{% endhint %}

### 요청 예시

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

### 응답 데이터 예시

액세스 토큰 발급 요청에 대한 성공 응답 데이터는 아래와 같습니다.

```
{"msg":"SUCCESS","code":200,"access_token":"{ACCESS_TOKEN}"}
```

| 항목            | 타입      | 설명     |
| ------------- | ------- | ------ |
| msg           | string  | 응답 메세지 |
| code          | integer | 응답 코드  |
| access\_token | string  | 액세스 토큰 |

