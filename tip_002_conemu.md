# Tip 002. ConEmu에 DOSKEY 매크로 설정하기

## ConEmu

요즘 Windows Command Line 사용에 있어 가장 사랑받는 프로그램이 ConEmu라고 생각한다. 아직 ConEmu를 사용해 보지 않았다며 꼭 사용해 보기 바란다.

https://code.google.com/p/conemu-maximus5/

## ConEmu 시작 스크립트

ConEmu의 설정에서 Startup부분을 살펴보면 보통 아래와 같이 되어 있다.

```batch
cmd.exe /k %ConEmuBaseDir%\CmdInit.cmd
```

매번 수행되어야 할 초기 작업이 있다면 CmdInit.cmd에 넣으면 됩니다. 단! CmdInit.cmd는 ConEmu업데이트 시 초기화 되어 버립니다. 따라서 CmdInit.cmd를 다른 이름으로 복사하고 그것을 설정에 추가하시면 됩니다.
 

## DOSKEY 매크로 추가

Tip001에서 사용된 매크로를 my_macro라는 파일로 작성하자, 파일위치는 어디든 상관없지만, ConEmu가 설치된 곳에 하면 좋치 않을까 생각한다.

```batch
subl=c:\bin\app\Sublime3\sublime_text.exe $*
```

그리고 CmdInit.cmd 아래와 같이 추가하면 끝.

```batch
doskey /macrofile="%ConEmuBaseDir%\..\my_macro"
```

이제 ConEmu상에서는 subl를 치면 Sublime이 실행되는 것을 볼 수 있다.

예정된 다음Tip 없음. 의견부탁드려요.