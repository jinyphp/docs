# 동작원리
실제적으로 `Application`과 `부트스트래핑`의 처리를 통하여 컨트롤러가 호출되는 과정에 대해서 코드를 이용하여 알아보록 합니다.

## 사이클
Application 코어는 컨트롤러의 이름을 저장하는 프로퍼티 변수가 하나 존재합니다.

```php
public $_controller;
```

처음으로 프레임워크가 시작되는 `Application`은 부트스트래핑을 통하여 url에서 지정한 컨트롤러의 이름을 찾아 오게 됩니다. 

## 컨트롤러 체크
프레임워크는 컨트롤러가 존재하는지를 다음과 같이 코드에서 확인을 하게 됩니다.

```php
// 컨트롤러 호출
// 컨트롤러가 없는 경우 기본 컨트롤러 동작      
if (!empty($this->_controller)) {
    return $this->controller();
} else {
    //output("컨트롤러가 비여 있습니다.\n");
    return $this->default();       
}
``` 

컨트롤러의 이름이 있는 경우, 실제적인 컨트롤러를 생성하는 메소드를 호출하게 됩니다.
만일 컨트롤러가 없는 경우에는 기본 컨트롤러로 실행이 됩니다. 기본 컨트롤러는 pages 페키지의 컨트롤러 입니다.

## 인스턴스 생성
다음은 실제 컨트롤러를 생성하는 메소드의 루틴입니다.

```php
/**
 * 컨트롤러를 호출합니다.
 */
public function controller()
{
    // 컨트롤러 클래스 파일이 존재여부를 확인후에 처리함
    $controllerPath = DS."App".DS."Controllers".DS;
    $extention = ".php";
    
    $filename = ROOT.$controllerPath.$this->_controller.$extention;
    if (file_exists($filename)) {           
        // 인스턴스 생성, 재저장 합니다.
        $name = "\App\Controllers\\".$this->_controller;
        $this->_controller = new $name ($this);
        
        Registry::set("controller", $this->_controller);
        // 메서드 실행 반환
        return $this->method();

    } else {
        // echo "$filename 컨트롤러 파일이 존재하지 않습니다.<br>";
        return $this->default();                             
    }
}
```

컨트롤러의 이름은 캐멀케이스 이름형태로 되어 있습니다. 컨트롤러의 이름을 이용하여 실제적인 컨트롤러 파일의 경로를 확인을 합니다.
컨트로러의 파일일 있는지 검사를 합니다.

`new` 키워드를 통하여 실제적인 컨트롤러의 인스턴스를 생성합니다.
인스턴스의 생성이 성공하면, 매소드 호출을 처리합니다.

### 네임스페이스
컨트롤러를 호출할때 네임스페이스 지정은 상관하지 않아도 됩니다. 

## 메소드
컨트롤러의 인스턴스가 생성이 되었다면, 실제적인 메소드 호출을 하도록 합니다.
매소드는 지정 매소드가 있고, 기본 호출 메소드 2가지 종류가 있습니다.

```php
/**
 * 매서드를 호출합니다.
 * 콜백함수을 이용하여 호출.
 */
public function method()
{
    if (method_exists($this->_controller, $this->_action)) {
    
        return call_user_func_array(
            [
                $this->_controller, 
                $this->_action
            ], 
            $this->_prams);
        
    } else {
        echo "컨트롤러에 메서드가 존재하지 않습니다. ";
        echo "stopping";
        exit;
    } 
}
```

`method_exists()`함수를 통하여 인스턴스 안에 호출하고자 하는 매소드가 존재하는지 확인을 합니다.
매소드 확인후에는 콜백 호출 함수를 통하여 객체를 호출하게 됩니다.

`call_user_func_array()`는 콜백 함수를 호출을 합니다. 첫번째 인자를 배열로 전달을 하게 되면 클래스의 메소드를 호출할 수 있습니다.
두번째 값은 콜백으로 전달되는 배열 데이터 값입니다.

