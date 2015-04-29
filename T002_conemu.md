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

