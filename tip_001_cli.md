# Tip 001. Windows에서 CLI 구성하기

| CLI가 뭐지 ? |
| -- |
| [위키 참조] 명령 줄 인터페이스(CLI, Command line interface) 또는 명령어 인터페이스는 텍스트 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 뜻한다. 즉, 작업 명령은 사용자가 컴퓨터 키보드 등을 통해 문자열의 형태로 입력하며, 컴퓨터로부터의 출력 역시 문자열의 형태로 주어진다. Windows 사용자에게 cmd.exe로 생각하면 된다. |

Sublime Text 3 Build 3066에서 subl.exe가 추가되어 경로를 path에 추가하면 CLI가 구성된다. 하지만 subl.exe로 실행하면 조금 보기 싫은 검은 창이 나타났다가 사라지면서 실행되는 것을 볼 수 있다.

이번 Tip은 Windows 기반(cmd.exe)에서 위 문제점을 해결한 CLI 구성을 살펴본다.

## UNIX 기반 CLI

UNIX 기반 시스템들은 아래와 같이 bin 디렉터리에 링크를 생성하여 간단히 CLI 구성이 가능하다. (아래는 OSX일 경우)

```Bash
ln –s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl
/usr/local/bin/subl
```

## 일반적인 Windows CLI

Windows CLI를 만드는 방법은 보통 아래와 같다.

1. sublime text 디렉터리를 경로에 추가하는 방법
2. batch 파일을( 혹은 [ exe](https://scotch.io/tutorials/open-sublime-text-from-the-command-line-using-subl-exe-windows)를 만들거나.. ) 작성하여 path가 설정된 디렉터리에 복사하는 방법

1번은 많은 애플리케이션이 사용하는 방법이지만, path가 복잡해진다는 단점이 있다. 가끔 특정 애플리케이션은 자신의 경로를 가장 앞 부분에 설정하여 해당 애플리케이션만 실행되고 다른 애플리케이션의 정상적인 실행을 막는 원인이 되기도 한다.

2번은 기능 상 단점은 없지만, subl.exe같이 검은 창이 잠시 뜨거나, 또는 실행 시 경로 위치에 민감한 애플리케이션은 pushd, popd로 실행 시 경로를 유지할 수 있도록 작업을 해줘야 한다.


## DOSKEY

Command Line(cmd.exe)에서만 사용한다면 Sublime Text의 CLI를 가장 편하게 만드는 방법은 DOSKEY의 매크로를 이용하는 방법이라 생각한다. 설정은 아래와 같다. (참고로 끝 부분의 $*는 subl 뒤에 전달되는 모든 문자열을 전달하기 위한 것이다.)

```batch
doskey subl=c:\bin\app\Sublime3\sublime_text.exe $*
```

이게 끝이다. 얼마나 간단하고 아름다운가! 물론 매번 실행해야 하는 단점이 있지만 그건 다음 Tip으로 넘긴다.

참고 1. 저는 subl보다 sl를 더 선호 한다. 에디터를 실행하기 위해 두 글자 이상 입력해야 한다는 것은 인생을 낭비하고 있다는 생각이 든다.

참고 2. Command Line 외에서는 TypeAndRun, Launchy 같은 애플리케이션 런쳐를 사용하자. 개인적으로 작성하여 사용하는  [iGo](https://github.com/daejinseok/iGo)라는 것도 소개해 본다. ^^