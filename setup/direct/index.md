---
layout: setup
theme: jiny/page
---

# 직접설치
---
전용 인스톨러를 통하지 않고 직접 소스코드를 다운로드 받아 지니PHP를 설치할 수 있습니다.  

<br>
## 프로젝트 다운로드
---
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
## 깃허브 클론
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