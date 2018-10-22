# 복수 테마
---
기본적으로 테마는 하나만 선택되어 동작을 합니다.  
공통적으로 사용하는 테마는 `site.ini`에서 하게 됩니다. 하지만, 가끔식 일부 몇개의 페이지는 다른 테마를 사용하고 싶은 경우가 발생합니다.  

이런경우 커스텀 테마를 이용하여 하나의 사이트에 두개 이상의 테마를 적용할 수 있습니다.

<br>
## 커스텀 테마
---
특정 페이지 리소스에만 다른 테마를 적용하고자 할때 커스텀 테마 기능을 적용할 수 있습니다.  
커스텀 테마는 리소스 페이지의 `머리말`기능을 이용하여 처리를 합니다.  

<br>
### 머리말 설정
---
머리말은 페이지마다 설정값을 부여할때 매우 유용한 문서 포맷입니다. 머리말에서 커스텀 테마 설정할때는 `theme` 키워드를 사용합니다.  

다음은 리소스에 `jiny/admin` 테마를 적용하는 예제 입니다.

```php
theme: jiny/admin
```

이와 같이 머리말 데이터를 추가하면 `view`의 `theme`랜더링 처리 부분에서 커스텀 테마 설정을 우선적으로 선택하여 처리를 하게 됩니다.

<br>
## 응용사례
---
웹서비스를 개발하다 보면 복수의 테마 적용이 필요한 경우가 많이 발생을 합니다.  

대표적으로 사용자에게 보여주는 `frontend`부분과 `backend`부분을 모두 하나의 도메인으로 관리할때 매우 유용합니다.  
통상적으로 `backend`는 `http://도메인/admin` 형태로 접속하는 경우가 많이 있습니다. 하지만 `backend`의 디자인과 화면 구성은 `frontend`와 많이 다르게 됩니다.  

복수테마를 이용하여 이를 구분하고, 테마를 나누어 적용을 할 수 있습니다.

<br>
## 주의
---
`커스텀 테마`를 적용하기 위해서는 먼저 `기본 테마`가 설정되어 있어야 합니다.  
기본테마가 활성화 되어 있지 않으면, 테마의 처리 루틴으로 진입을 하지 않습니다.  

이와 관련되어 더 자세한 정보가 필요한면 테마부분 `소스코드`를 참고하시면 됩니다.

<br>
<br>