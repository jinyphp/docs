# 데이터 읽기
---
프레임워크 안에서 메뉴를 읽은 방법은 매우 간단합니다. `menu()` 헬퍼 함수만 호출하면 됩니다.

## 헬퍼호출
---
헬퍼함수의 특징은 어느곳에서 쉽게 함수를 호출할 수 있다는 것입니다.
다음은 `pages` 컨트롤러에서 메뉴를 호출하는 부분의 일부입니다.

```php
// 메뉴 데이터를 읽어옵니다.
$viewData['menus'] = menu();
```

`menu()` 함수는 메뉴의 파일을 읽어서 배열로 반환합니다. 

위와 같이 메뉴의 데이터를 읽어서, `뷰`의 데이터에게 전달을 하면 뷰는 메뉴의 데이터를 같이 `템플릿`으로 전달합니다.
템플릿은 전달받은 메뉴 데이터를 처리하여 메뉴를 구성할 수 있습니다.

뷰의 데이터 배열의 `키`는 템플릿에서 인식할 수 있는 키값이 됩니다.


## 템플릿 처리
---
뷰로 부터 전달받은 메뉴 데이터를 템플릿에서 처리를 할 수 있습니다.

다음은 테마 해더에서 메뉴를 처리하는 Liquid 템플릿 처리의 예 입니다.

```php
<div class="collapse navbar-collapse" id="navbarResponsive">
            
    {% if menus %}
        <ul class="navbar-nav ml-auto">
        {% for menu in menus %}
            <li class="nav-item">
                <a class="nav-link" href='{{ menu.href }}'>
                {% if sys.language == "en" %}
                    {{ menu.en }}
                {% else %}
                    {{ menu.ko }}
                {% endif %}
                </a>
            </li>      
        {% endfor %}
        </ul>
    {% endif %}
    
</div>
```

Liquid 템플릿 언어에서는 뷰로 전달되는 배열의 `키`값으로 선택을 하게 됩니다.
기본적으로 메뉴의 키값은 `menus`로 사용을 합니다.

키 이름을 변경하고자 할때에는 뷰의 배열의 키명을 변경하면 됩니다.
