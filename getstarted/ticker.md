---
description: 본 섹션에서는 아임웹 API를 사용하기 위해 사전에 준비해야 하는 사항에 대하여 설명합니다.
---

# 사전 준비 사항

아임웹 API는 아임웹에서 개설한 사용자 사이트의 키 정보를 기반으로 동작하므로, 아임웹 API를 사용하기에 앞서 아래의 사항을 준비하십시오.

## 사이트 개설하기

외부 클라이언트 측에서 아임웹 사이트에 등록된 사용자 정보를 조회하거나, 추가 및 수정할 때 아임웹 API를 요청합니다. 따라서 아임웹 API를 사용하려면 사용자 정보를 저장할 사이트를 먼저개설해야 합니다.

아래의 순서로 사이트를 개설하십시오.

1] [아임웹](https://imweb.me) 사이트에 접속하여 회원 가입 및 로그인을 진행합니다.

2] **내사이트** 메뉴에서 **\[무료 사이트 개설]**을 클릭합니다.\
<img src="../.gitbook/assets/image (1).png" alt="" data-size="original">

3] 내 사이트에 사용할 템플릿 선택하고 **사이트 이름** 및 **URL** 기입과 같은 이후 개설 절차를 진행합니다.



## 키 발급하기

아임웹 API로 아이웹 사용자 사이트의 정보에 접근하려면, 유효한 키 정보를 가지고  인증 절차를 거쳐야 합니다.

아래와 같은 순서로 키 정보에 해당하는 **API Key**와 **Secret Key**를  발급 받으십시오.

1. 아직 [아임웹](https://imweb.me)에서 사이트를 개설하지 않으셨다면 사이트를 개설합니다.
2.  아임웸에서 개설한 [내사이트](https://imweb.me/mysite)에서 **관리**를 클릭하여 관리자(admin) 페이지로 이동합니다.

    <figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
3.  관리자 페이지에서 **환경설정 > 외부 서비스 연동 (API)**으로 이동합니다.

    <figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
4.  **API key 발급받기**를 클릭하면 아래와 같은 **API Key**와 **Secret Key**가 생성된 것을 확인할 수 있습니다.

    <figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
발급받은 위의 두 키는 사이트 단위로 생성할 수 있으므로, 여러 개사이트를 운영한다면 사이트 별로 키를 구분하여 사용하시기 바랍니다.
{% endhint %}





임웹에서 개설한 사용자 사이트의 키 정보를 기반으로 동작하므로, 아임웹 API를 사용하려면 사용자 사이트에서 **API Key**와 **Secret Key**를 발급 받아야 합니다.
