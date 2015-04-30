# Tip001. Windows에서 CLI만들기

Sublime Text(이하 Sublime) 3 Build 3066에서 subl.exe가 추가되었지만 subl.exe를 실행하면 잠깐 검은창이 실행되었다가 사라지면서 실행되는 것을 볼 수 있다. 물론 subl.exe로 인해 Sublime디렉토리를 path경로에 추가하면 간단히 CLI가 구성되지만, 더 낳은 대안이라 생각되는 Tip를 적어본다.

## UNIX기반 CLI

UNIX기반 시스템들은 아래와 같이 bin디렉토리에 링크를 생성하여 CLI를 만든다. ( 아래는 OSX일 경우 )

```Bash
ln –s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl
/usr/local/bin/subl
```

## 일반적인 Windows CLI

Windows에서 CLI를 만드는 방벙은 아래와 같다. (Windows에서도 링크 및 하드링크가 있지만 UNIX처럼 동작하지 않으며, MSDN메뉴얼에서나 볼 수 있으며, 사용하는 사람있으면 제보바람. )

1. sublime text디렉토리를 path경로에 추가하는 방법
2. batch파일을( 혹은 [ exe](https://scotch.io/tutorials/open-sublime-text-from-the-command-line-using-subl-exe-windows)를 만들거나.. ) 작성하여 path가 설정된 디렉토리에 복사하는 방법

1번은 많은 어플리케이션이 사용하는 방법이지만, path가 복잡해지면 path설정된 순서로 프로그램을 찾아 실행되는데 가끔 나쁜 어플리케이션은 자신의 폴더를 가장 앞부분에 설정에 원치않는 동작을 하게하는 원흉이 되기도한다.

2번은 특별한 단점은 없지만, 간혹 실행위치에 민감한 어플리케이션은 pushd, popd로 약간의 스크립트 작업을 해줘야 한다.


## DOSKEY

Command Line(cmd.exe)에서만 사용한다면 Sublime Text의 CLI를 가장 편하게 만드는 방법은 DOSKEY의 매크로를 이용하는 방법이라 생각한다. 설정은 아래와 같다. (참고로 끝부분의 $*는 subl뒤에 전달되는 모든 문자열을 전달하기 위한 것이다.)

```batch
doskey subl=c:\bin\app\Sublime3\sublime_text.exe $*
```

이게 끝이다. 얼마나 간단하고 아름다운가! 물론 매번 실행해야 하는 단점이 있지만 그건 다음 Tip으로 넘기고. 이번장은 여기까지.

참고로 저는 subl보다 sl를 더 선호 한다. ^^v