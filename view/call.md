# 뷰 호출
뷰는 독립적인 클래스 객체입니다.
뷰를 호출하는 곳은 크게 `컨트롤러`와 `라우터` 입니다. 

뷰를 호출하는 방법은 직접 클래스의 인스턴스를 생성하거나, `view()`헬퍼를 사용하는 것입니다.

## 컨트롤러 연계
`뷰`는 컨트롤러 클래스와 밀접한 관계가 있습니다.
컨트롤러는 입력된 url에 대한 동작처리를 하는 클래스 입니다. 동작을 수행한 후에 결과를 하면에 출력을 해야 하는데, 이때 뷰를 사용할 수 있습니다.

### 메소드
사용자 컨트롤러는 코어에서 제공되는 `controller`를 상속받으며, 이 상속에서 뷰를 호출할 수 있는 서브 메소드를 제공합니다.
서브메소드를 실행하는 방법은 다음과 같습니다.

```php
return $this->view(뷰파일, 데이터);
```

### 헬퍼함수
별도로 제공되는 헬퍼 함수를 통하여 뷰를 호출할 수 있습니다.
주로 `view()`함수를 통하여 호출하는 방법을 많이 사용합니다.


## 라우터 호출
컨트롤러가 없는 url의 경우 직접 라우터에서 `view()`함수를 호출할 수 있습니다.


## 인자값
클래스에서 호출이 가능한 `view`메서드는 두개의 인자값을 가지고 있습니다. 

첫번째는 출력화면의 디자인을 가지고 있는 뷰 파일명 입니다.
뷰 파일은 리소스 폴더안에 위치합니다.

두번째 인자는 데이터 입니다. 데이터는 처리한 값을 뷰에게 전달하는 역활을 합니다.


## 레이아웃
컨덴츠 페이지 리소스들은 단일로 작성되는 경우도 있고 또 다른 중간 레이아웃이 존재할 수도 있습니다.


## 뷰의 반환
뷰가 호출이 되었다고 해서 직접 브라우저 화면에 결과가 출력되는 것은 아닙니다. 실제적인 브라우저로의 화면반환은 `response`에서 처리하게 됩니다.
따라서 `view()`의 반환값을 다시 `return`하여 response로 전달을 해야 합니다.