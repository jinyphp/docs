---
layout: setup
theme: jiny/page
---

# 프로젝트
이번에는 지니 인스톨러를 통하여 실제적인 프로젝트를 다운로드 받는 것에 대해서 알아 보도록 하겠습니다.
인스톨러가 설치가 되어 있다면 경로에 상관없이 `jiny`명령어를 사용할 수 있습니다.

<br>
## 프로젝트 생성
---
새로운 프로젝트를 생성합니다.  
```php
jiny new 프로젝트명
```

`new` 명령어는 새로운 프로젝트를 생성한다는 옵션 입니다. 옵션 다음에 프로젝트를 설치할 디렉토리 이름을 지정하면 됩니다.
명령을 실행하게 되면 다음과 같이 설치과정 화면이 출력됩니다.  

```php
$ jiny new demo1
Crafting application...
Dwonload version file = 0.2.0.zip

Loading composer repositories with package information
Installing dependencies (including require-dev) from lock file
Package operations: 20 installs, 0 updates, 0 removals
  - Installing erusev/parsedown (1.7.1): Loading from cache
  - Installing jiny/config (0.1.0): Loading from cache
  - Installing jiny/core (0.1.0): Loading from cache
  - Installing symfony/polyfill-ctype (v1.9.0): Loading from cache
  - Installing symfony/yaml (v4.1.4): Loading from cache
  - Installing webuni/front-matter (1.1.0): Loading from cache
  - Installing jiny/frontmatter (0.1.0): Loading from cache
  - Installing jiny/lamp (0.1.0): Loading from cache
  - Installing jiny/locale (0.1.0): Loading from cache
  - Installing jiny/menu (0.1.0): Loading from cache
  - Installing jiny/pages (0.1.0): Loading from cache
  - Installing jiny/router (0.1.0): Loading from cache
  - Installing jiny/template (0.1.0): Loading from cache
  - Installing jiny/theme (0.1.0): Loading from cache
  - Installing jiny/view (0.1.0): Loading from cache
  - Installing liquid/liquid (1.4.8): Loading from cache
  - Installing nadirhamid/docx-to-html (v0.0.1): Loading from cache
  - Installing nikic/fast-route (v1.3.0): Loading from cache
  - Installing sunra/php-simple-html-dom-parser (v1.5.2): Loading from cache
  - Installing symfony/filesystem (v4.1.4): Loading from cache
symfony/yaml suggests installing symfony/console (For validating YAML files using the lint command)
webuni/front-matter suggests installing nette/neon (If you want to use NEON as front matter)
webuni/front-matter suggests installing yosymfony/toml (If you want to use TOML as front matter)
Generating autoload files
Application ready! Build something amazing.
```

프로젝트의 설치명령을 실행하게 되면 먼저 최신 버전을 체크 합니다.  
최신의 버젼을 깃허브 공유사이트에서 코드를 다운로드 받는 과정을 수행합니다. 다운로드 과정이 다소 시간이 걸릴 수 있습니다.  

다운로드가 완료되면 인스톨러는 자동으로 프로젝트 폴더명으로 `zip`압축파일을 해제하게 됩니다.  
해제후 프로젝트 폴더로 이동하여 `composer install` 명령을 수행하여 의존 페키지들을 추가로 설치하게 됩니다.  

추가 의존 패키지를 설치는 다소 시간이 걸릴 수도 있습니다.  


<br>
## 다중 프로젝트
---
인스톨러를 통하여 프로젝트를 설치하는 것은 매우 편리한 방법중의 하나입니다.  
또한 여러개의 프로젝트를 생성하고 복제하는데 매우 편리합니다.  

<br>
## 동영상
---
좀더 쉽게 이해하기 위해서 유투브 동영상을 준비하였습니다. 지니PHP 유투브 체널을 구독하시면 더 많은 정보의 기술자료 동영상을 시청할 수 있습니다

<iframe width="560" height="315" src="https://www.youtube.com/embed/ipeSKoyI5CQ" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<br>
<br>
<br>
