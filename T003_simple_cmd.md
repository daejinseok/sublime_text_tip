# Tip003. 간단한 명령을 추가해 보자.

개인적으로 에디터들의 다양한 기능을 사랑한다. 그 중에 최고를 뽀으라면 단연 vi의 [점명령](http://daejinseok.github.io/2014/05/27/pvim-101-tip1-meet_the_dot_command.html) 이라고 생각한다. 그 다음은 많은 에디터에서 지원하는 [스니핏](http://daejinseok.github.io/2014/06/01/subl-snippet.html) 정도 이다.

하지만 에디터에 나만의 명령을 추가하는 것이야 말로 진정 나만의 무기로 만드는 최고의 방법이 아닐까 생각한다.

[sublime text의 비공식 메뉴얼](http://docs.sublimetext.info/en/latest/basic_concepts.html)에 아래와 같은 문장이 있다.

Sublime Text is a versatile editor for programmers, but you don’t need to be one in order to use it, and you don’t need to configure it extensively to be productive—it’s an efficient tool out of the box. Hackers, however, will appreciate all the customization and extensibility opportunities.

Sublime Text는 프로그래머를 위한 기능이 다양한 에디터이지만 그 기능만 사용할 필요도 없고, 효과적인 툴로 만들기 위해 많은 설정을 할 필요도 없다. 여러분(Hackers)이 모든 것을 수정하고 확장하는 것을 환영한다.
(제가 느낀의미는 이러한데, 혹시 틀렸다면 피드백 부탁드립니다. -_-;;)

## 그래서 어떤 명령을 추가하나?

시작은 "Hello Sublime Text!" 해보자.


## hello.py를 어디에 작성해야 되나.

명령목록(Ctrl+Shift+P)를 눌러 "Browse Package"를 입력하면 Sublime Text에서 사용하는 각종 패키지, 플러그인가 나오며 특히 User폴더에는 현재 에디터의 설정을 담고 있는 "Preferences.sublime-settings"가 나온다.

hello.py의 위치는 Packages폴더 아래의 어디든 상관없지만, Hello폴더를 만들고 아래와 같이 hello.py를 작성하자.

