---
layout: setup
theme: jiny/page
---

# 지니 인스톨러
---
개발자는 한개의 사이트뿐만 아니라 여러개의 웹서비스를 동시에 개발관리하게 됩니다. 매번, 새로운 프로젝트를 시작하는데 프레임워크를 설치하는 과정은 불편할 것입니다.  

지니PHP는 새로운 웹프로젝트를 쉽게 시작할 수 있도록 전용 프로젝트 인스톨러를 제공합니다.  
또한 전용 인스톨러를 통하여 지니PHP를 쉽게 설치를 할 수 있습니다.

<br>
## 인스톨러 설치
---
지니PHP의 인스톨러는 컴포저를 통하여 같이 배포를 하고 있습니다.  
인스톨러를 설치하기 위해서는 미리 서버/로컬컴퓨터에 `컴포저` 환경설정이 되어 있어야 합니다. 컴포저 환경설정은 [컴포저 설치](/setup/composer)를 참고하시길 바랍니다. 

인스톨러를 설치하기 위해서 터미널 창을 실행하십시요. 터미널 창에서 다음과 같이 명령하면 전용 인스톨러를 다운로드 할 수 있습니다.
```php
composer global require jiny/installer
```

인스톨러의 설치는 global 옵션을 이용하여 설치를 합니다. global 옵션을 사용하게 되면, 실행경로에 상관없이 `jiny`명령어를 사용할 수 있습니다.  
`jiny`는 지니PHP의 인스톨러 명령어 입니다.

명령을 입력하면 다음과 같이 화면이 출력하면서 자동 설치가 이루어 지게 됩니다.

```php
Changed current directory to C:/Users/infoh/AppData/Roaming/Composer
Using version ^0.1.0 for jinyphp/installer
./composer.json has been updated
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 1 install, 0 updates, 0 removals
  - Installing jinyphp/installer (0.0.1): Downloading (100%)
Writing lock file
Generating autoload files
```

컴포저는 `해외서버`를 통하여 페키지를 검사하고, 깃허브와 같은 저장장소에서 소스를 다운로드 받게 됩니다.  
사용 환경에 따라서 시간이 걸릴 수 있습니다.  

컴포저의 실행이 느린 경우에는 다른 `미러 서버`를 설정하여 사용할 수 도 있습니다.  
미러서버에 대한 설정은 관련 자료를 참고해 주시길 바랍니다.

<br>
## 동영상
---
설치방법을 좀더 쉽게 이해하기 위해서 유투브 동영상을 준비하였습니다. 지니PHP 유투브 체널을 구독하시면 더 많은 정보의 기술자료 동영상을 시청할 수 있습니다.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/CkW_Z8eX0C4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<br>
## 설치 경로
---
지니PHP 인스톨러는 글로벌로 설치를 권장합니다. 컴포저를 통하여 글로벌로 설치하게 되면 다음과 같은 경로에 설치가 됩니다.  

* 윈도우의 경우
```
~/AppData/Roaming/Composer/vendor/jiny/installer
```


<br>
<br>
<br>