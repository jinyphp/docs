# 컨트롤러 실습
이번장에서는 실제적인 컨트롤러를 생성하는 방법에 대해서 실습을 해보도록 합니다.

다음은 기본적인 컨트롤러의 모습입니다.

```php
<?php
namespace App\Controllers;

use \Jiny\Core\Controllers\Controller;
use \Jiny\Core\Registry\Registry;

class HomeController extends Controller
{

    public function __construct($app=Null)
    {
        //controller
        $this->setApp($app);
    }

    // 기본실행 메서드
    public function index()
    {
        echo "Home 기본컨트롤러 실행<br>";
        return "Hi, Jiny!";
    }

    public function hello()
    { 
        return $this->view();      
    }

}
```

## 네임스페이스
컨트롤러는 기존 페키지들과 분리될 수 있도록 별도의 네임스페이스를 가지고 있습니다. 지니PHP의 네임스페이스는 `App\Controllers`입니다.

```php
namespace App\Controllers;
```

페이지 상단에 위와 같이 네임 스페이스를 선언하면 됩니다. 컨트롤러는 한개의 파일에 하나의 네임스페이스만을 지정하기 때문에 별도의 `{}`를 사용하지 않아도 됩니다.

## use
필요한 네임스페이스의 별칭을 선언합니다. 별칭을 사용하면 긴이름의 네임스페이스를 사용하지 않아도 클래스를 이용할 수 있습니다.

```php
use \Jiny\Core\Controllers\Controller;
use \Jiny\Core\Registry\Registry;
```

## 클래스명
다음은 `Home`이름을 가지는 컨트롤러를 선언하는 예제 입니다. 또한, 부모 컨트롤러를 상속받습니다.

```php
class HomeController extends Controller
{
}
```

## 초기화
컨트롤러가 생성될때 초기화 작업이 필요한 부분은 `__construct()`메소드 안에 작성을 하도록 합니다.

```php
public function __construct($app=Null)
{
    //controller
    $this->setApp($app);
}
```

초기화 매소드는 컨트롤러를 호출하는 `Application`의 인스턴스를 의존성 주입받아 처리를 같이 할 수 있습니다.

## 기본 메소드
기본적으로 호출되는 메소드를 선언합니다. 메소드의 이름은 `index()`입니다.

```php
// 기본실행 메서드
public function index()
{
    echo "Home 기본컨트롤러 실행<br>";
    return "Hi, Jiny!";
}
```
다음과 같이 처리 동작을 작성할 수 있습니다. 결과 값은 `return`을 통하여 response로 반환을 할 수 있습니다.


