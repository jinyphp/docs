# 테마 코드
---
이번 섹션은 테마의 기능이 코드상에서 어떻게 처리되는지에 대하여 좀더 자세하게 알아 보도록 합니다.  
개발자라면 코드를 통하여 좀더 동작의 처리를 쉽게 이해할 수 있습니다.  
또한, 코드 설명으로 `커미터` 및 지니PHP 오픈소스에 참여를 할 수 있도록 추가 정보를 제공합니다. 

<br>
## 페키지
---
지니PHP의 테마는 별도의 페키지로 구성되어 있습니다.  
페키지의 깃허브 저장소는 `https://github.com/jinyphp/theme.git` 입니다.

해당 패키지의 오픈소스 참여를 희망하시는 경우에는, 저장소를 `포크`하여 수정후에 `풀리퀘스트`를 보내주시면 됩니다. 


<br>
## 테마호출
---
지니PHP의 `view`는 테마명이 있는 경우에 이를 확인하여 테마 페키지를 호출하게 됩니다.  
테마 페키지의 호출은 `view` 패키지의 `viewShow.php`에서 처리하게 됩니다.

다음은 소스코드 일부 입니다.

```php
// 테마처리
if($theme = conf("site.theme")) {
    if (Registry::get("Packages")->isPackage("jiny/theme")) {

        // 테마 의존성 주입(view)
        // 뷰 객체가 생성되기 이전이기 때문에, 테마에 $this로 주입을 합니다.
        $this->Theme = Registry::create(\Jiny\Theme\Theme::class, "Theme", $this);
        
        if ($this->Theme->isTheme()) {
            $this->Theme->render($viewHtml);        
        }
    }
} else {
    // echo "테마가 지정되지 않았습니다.";
}
```

조건문과 헬퍼함수를 통하여 `site.ini` 설정에서 테마명이 있는지를 확인합니다.  
테마명이 있는 경우 테마 페키지의 인스턴스를 초기화 합니다.  

테마 인스턴스를 통하여 테마처리를 위임합니다.

<br>
<br>