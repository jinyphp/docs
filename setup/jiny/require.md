---
layout: setup
theme: jiny/page
---


# 설치
---
이번장에서는 지니PHP를 설치하는 벙법에 대해서 설명을 합니다.  
모든 설치과정은 응용프로그램을 시작하는 첫단추 입니다.  

<br>
## 요구사항
---
지니PHP는 윈도우, 맥환경에서 설치하여 개발환경을 구축할 수 있습니다. 물론 실제 운영중인 리눅스와 같은 서버에 설치하여 동작을 시킬 수도 있습니다.  
하지만, 먼저 로컬 개발환경을 구축후에 배포 형태로 사이트를 운영하는 것이 좋습니다.  

<br>
### PHP설치
---
지니PHP 를 설치하기 위해서는 PHP 7.0 이상의 버전을 컴퓨터에 설치하셔야 합니다.  
낮은 버전은 PHP 최신 문법 적용을 받지 않아, 오류가 발생할 수도 있습니다.  
PHP설치는 공식 PHP.net 사이트 보다는 비트나미의 `WAPM`, `MAPM` 을 다운로드 받아 설치하는 것을 추천합니다.  

<br>
### 컴포저
---
지니PHP는 PHP의 페키징 기술을 같이 응용하여 개발되어진 프래임워크입니다.  
또한 지니PHP의 많은 기능들은 별도의 패키지로 만들어져서 같이 배포를 하고 있습니다.  
컴포저는 PHP의 패키지 관리 소프트웨어로 https://getcomposer.org 에서 무료로 다운로드 받아 설치를 하실 수 있습니다. 

자신의 운영체제 환경에 맞게 윈도우, 맥용 버전을 설치할 수 있습니다.  

<br>
## 설치
---
지니PHP는 3가지 방식으로 프레임워크를 설치할 수 있습니다.  
설치관리자를 이용하는 방법 이외에도 직접 `컴포저-프로젝트`를 이용하여 다운로드 받을 수 있습니다.  
깃허브의 공개 저장소를 복제하여 현재 개발중인 상태의 코드로도 설치를 할 수 있습니다.  

<br>
### 설치관리자
PHP와 컴포저 설치가 되어 있다면 전용 `지니PHP` 설치 인스톨러를 다운로드 할 수 있습니다. 전용 설치관리자는 프로젝트별로 `지니PHP` 기본 코드를 다운로드 하고 환경을 구축할 수 있습니다.  

전용 설치관리자는 컴포저를 이용하여 설치가 되어 집니다. 터미널을 샐행하여 다음과 같이 명령을 입력합니다.  

```php
composer global require jiny/installer
```

설치관리자를 글로벌 환경으로 코드를 설치합니다. 글로벌로 설정을 하게되면, 실행 경로와 상관없이 `지니PHP` 설치관리자를 실행할 수 있습니다.  
설치가 완료가 되었으면 적당한 프로젝트 폴더를 생성후에 다음과 같이 명령을 입력합니다.  

```php
jiny new 프로젝트명
```

위와 같이 명령을 입력하면 자동적으로 깃허브 서버에서 최신의 `jinyPHP` 코드를 다운로드 받아 설치를 하게 됩니다.  
또한, 다운로드가 완료된 경우에는 자동적으로 컴포저를 실행하여 추가 페키지를 같이 설치하게 됩니다.  

<br>
### 컴포저 프로젝트
프로젝트는 직접 페키지스트에 등록된 패키지를 다운로드 받아 설치를 하는 방식입니다.  
컴포저를 통하여 패키지를 가지고 오기 때문에, 먼저 컴포저가 설치가 되어 있어야 합니다.  
컴포저는 라이브러리를 패키지화여 의존성을 관리 합니다. 패키지를 /vendor 폴더에 설치하는것 대신에 프로젝트 형태로 배포를 할 수 있습니다.  

프로젝트를 배포하는 방법은
```php
composer create-project jiny/jiny 폴더명
``` 

위의 명령을 입력하면 패티지를 프로젝트 형태로 설치를 합니다. 설치파일과 해당 프로젝트의 관련 패키지들을 동시에 설치를 할 수 있습니다.  

```php
$ composer create-project jiny/jiny 0.1.5
Installing jiny/jiny (0.1.4)
  - Installing jiny/jiny (0.1.4): Loading from cache
Created project in 0.1.5
Loading composer repositories with package information
Installing dependencies (including require-dev) from lock file
Package operations: 17 installs, 0 updates, 0 removals
  - Installing erusev/parsedown (1.7.1): Loading from cache
  - Installing jiny/config (0.0.4): Loading from cache
  - Installing jiny/core (0.0.5): Loading from cache
  - Installing symfony/polyfill-ctype (v1.8.0): Loading from cache
  - Installing symfony/yaml (v4.1.0): Loading from cache
  - Installing webuni/front-matter (1.1.0): Loading from cache
  - Installing jiny/frontmatter (0.0.3): Loading from cache
  - Installing jiny/lamp (0.0.1): Loading from cache
  - Installing jiny/locale (0.0.2): Loading from cache
  - Installing jiny/menu (0.0.2): Loading from cache
  - Installing jiny/pages (0.0.3): Loading from cache
  - Installing jiny/template (0.0.3): Loading from cache
  - Installing jiny/theme (0.0.3): Loading from cache
  - Installing liquid/liquid (1.4.8): Loading from cache
  - Installing nadirhamid/docx-to-html (v0.0.1): Loading from cache
  - Installing sunra/php-simple-html-dom-parser (v1.5.2): Loading from cache
  - Installing symfony/filesystem (v4.1.0): Loading from cache
symfony/yaml suggests installing symfony/console (For validating YAML files using the lint command)
webuni/front-matter suggests installing nette/neon (If you want to use NEON as front matter)
webuni/front-matter suggests installing yosymfony/toml (If you want to use TOML as front matter)
Generating autoload files
```

컴포저의 `create-project` 옵션은 패키지를 `vendor`에 설치하지 않고, 프로젝트 형태로 코드를 다운로드 받습니다.  
`jiny/jiny` 패키지는 라이브러리 형태의 패키지가 아닌 프로젝트형 패키지 입니다.
`jiny/jiny` 패키지는 추가 관련 페키지들을 필요로 합니다.  
관련 페키지들은 기본 프로젝트가 생성시 제외되어 있습니다. 컴포저를 통하여 관련 페키지를 설치합니다.

```php
composer install
```

지니PHP에서 필요로 하는 추가 페키지들을 다운로드 받아 설치를 하게 됩니다.

<br>
### 깃허브 클론
---
깃허브를 통하여 직접 지니PHP를 설치할 수 있습니다. 지니PHP의 코드와 관련 패키지들은 모두 깃허브에 공개되어 있습니다.  
깃허브의 코드를 직접 복제를 하여 설치하게 되면, 현재 개발중인 버전으로 설치될 확율이 많습니다.  
이런경우에는 테크 기능을 이용하여 특정 버전을 선택하여 복제를 할 수 있습니다.

```php
git clone -b 버젼 https://github.com/jinyphp/jiny.git 설치폴더
```

깃 복제를 하여 설치를 하게 되면, git에서 관리되는 이력또한 같이 설치가 되어지게 됩니다.  

<br>
<br>
<br>
<br>