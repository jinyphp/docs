# 템플릿 테마적용
---
`지니PHP`는  테마 파일에서도 템플릿 언어를 적용하여 처리할 수 있습니다.  
템플릿 코드를 통하여 테마에서도 다양한 데이터를 결합하여 처리 동작을 할 수 있습니다.

<br>
## 템플릿
---
지니PHP는 다양한 템플릿 문법들을 지원합니다. 대표적으로 `Liquid`가 있습니다.  
`Liquid`를 이용하면 `해더파일`에 메뉴를 추가하는 등의 작업을 하실 수 있습니다.

<br>
## 사이트 로고삽입
---
`site.ini`의 값들은 `site.***`형태로 객체 값을 읽어 올 수 있습니다.

다음은 `liquid`를 통하여 해더영역에 로고를 삽입하는 예제 입니다.
```
<div class="navbar-header">
    <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
    </button>
    <a class="navbar-brand" href="/">{ { site.logo } }</a>
</div>
```

와 같이 사이트 설정값의 로고 정보를 Liquid 문법을 사용하여 삽입을 합니다.