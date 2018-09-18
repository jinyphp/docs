# 테마

## 테마 적용하기
지니PHP에서 테마를 적요하는 것은 매우 간단합니다.

사이트의 환경설정 파일에서 테마명만 지정하면 됩니다.

```php
theme = "jiny/page"
```

지니 view는 최종적으로 랜더링된 페이지를 사이트 전체의 스타일에 맞는 테마로 포장되어 화면에 출력 하게 됩니다.



### 테마처리
지니 view 패키지의 `viewShow.php`는 다음과 같이 테마 설정값에 대해서 처리를 구분합니다.

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

만일 사이트에 테마를 적용하지 않기를 원하신다면 설정을 주석처리 하시면 됩니다.


## 커스탬 테마
커스텀 테마를 적용하기 위해서는 먼저 기본 테마가 설정되어 있어야 합니다. 기본테마가 활성화 되어 있지 않으면, 테마의 처리 루틴으로 진입을 하지 않습니다.


