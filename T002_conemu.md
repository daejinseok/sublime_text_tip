# Tip002. ConEmu에 DOSKEY 매크로 설정하기

## ConEmu

요즘 Windows의 cmd.exe를 사용에 있어 가장 사랑받는 프로그램이 ConEmu라고 생각한다. 혹시 cmd.exe를 많이 사용하는데 아직 ConEmu를 사용해 보지 않았다며 꼭 설치해 보기 바란다.

https://code.google.com/p/conemu-maximus5/

## ConEmu 시작 스크립트

ConEmu의 설정에서 Startup부분을 살펴보면 보통 아래와 같이 되어 있다.

```batch
cmd.exe /k %ConEmuBaseDir%\CmdInit.cmd
```

즉 CmdInit.cmd에 command line에서 사용할 각종 설정을 추가하면 된다.

## DOSKEY 매크로 추가

Tip001에서 사용된 매크로를 my_macro라는 파일로 작성하자, 파일위치는 어디든 상관없지만, ConEmu가 설치된 곳에 하면 좋치 않을까 생각한다.

```
subl=c:\bin\app\Sublime3\sublime_text.exe $*
```

그리고 CmdInit.cmd에 아래와 같이 추가하면 끝.

```batch
doskey /macrofile="%ConEmuBaseDir%\..\my_macro"
```

이제 ConEmu상에서는 어디든 subl를 치면 Sublime이 실행되는 것을 볼 수 있다.

다음 Tip은 예정에 없음. 의견 바람 ㅎㅎ