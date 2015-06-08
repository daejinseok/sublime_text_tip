# Tip 004. log_commands(True)

Sublime Text이 Python으로 개발되었다고 생각하시는 분들이 많이 있습니다. 많은 기능이 Python스크립트로 구현되어 있지만, [Sublime Text의 개발자인 jskinner](https://news.ycombinator.com/item?id=2822114)에 따르면 C++로 작성된 Custom UI Toolkit이라고 합니다.

이 Toolkit에는 Python이 임베디드 되어있어 Python으로 개발되어 있다고 오해하시는 분들이 많은 것 같습니다. 많은 부분이 Python스크립트로 제어가능하도록 되어있어, Python을 어느정도 알고 있다면 약간의 노력과 의지로 Sublime Text에 원하는 기능을 무한대로 추가할 수 있습니다.

이번 팁에서 Sublime Text에 기능 추가, 분석, 오류확인 등 다양한 용도로 많은 도움이 되는 간단한 명령 하나 입니다.

```python
 sublime.log_commands(True)
```

sublime text의 콘솔창을 열고( Ctrl+` ), 위 명령을 입력하면 딱히 무엇이 변경되었는지 알 수 없습니다. 하지만 키보드 혹은 마우스을 클릭하는 순간 조용하던 콘솔창에 현재 입력된 Command와 인자 값들이 쭉 나타나기 시작합니다.

```python
>>> sublime.log_commands(True)
command: drag_select {"event": {"button": 1, "x": 488.5, "y": 118.5}}
```

나타나는 로그에 대해서 문서화 된 부분은 없지만, drag_select라는 command가 호출되었고, x:488.5 y:118.5 위치에 마우스 왼쪽버튼이 클릭되었다는 내용을 알 수 있듯이 대체로 이해하기 편하게 나타나는 것 같습니다. 여러분도 좋은 플러그인을 개발한다면 꼭 이해하기 쉽게 작성 부탁드립니다.

log_commands활성화 이후 sublime text에서 입력되는 모든 command와 인자가 나타나기 때문에 단축키 설정, 오류 발생시 인자 값, 심지어 sublime text가 어떻게 동작하는지에 대한 분석 등 여러가지 유용한 정보를 추적할 수 있습니다.

다시 기본값인 비활성화로 변경하고 싶다면, True값을 False로 변경하여 입력하면 됩니다.

```python
sublime.log_commands(False)
```

참고로 콘솔창이 Find패널 혹은 Replace패널이 호출될 때 자동으로 닫혀 조금 불편하지만, 다시 콘솔창을 열면됩니다.

끝.