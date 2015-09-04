# Tip 005. from pydoc import help

python에서는 기본적으로 help라는 명령어로 도움말을 확인 할 수 있습니다.

```python
>>> help(print)
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
```

Sublime Text의 콘솔은 python 인터프린터와 거이 동일해서 sublime text의 객체나 메소드를 탐험할 때 공식 홈페이지의 문서보다 더 편한 경우가 많이 있습니다.

하지만 pydoc 모듈이 로드되지 않아서 바로 동작하지 않습니다. 아래와 같이 모듈로드 후에는 사용가능합니다.

```python
from pydoc import help
```

```python
>>> help(sublime)
Help on module sublime:

NAME
    sublime

CLASSES
    builtins.object
        Edit
        Region
        Selection
        Settings
        Sheet
        View
        Window
    ..... (중략) .....
```

단. 비문서화 된 기능은 언제 제거될지 모르지만, 문서화 되었다고 해서 또 영원히 유지되는 것은 없습니다. 세상이 원래 좀 그래요 :)


또한 Sublime Text가 설치된 곳에 보면 python3.3.zip이 보입니다. 이 파일은 파이썬을 설치하면 복사되는 파이썬 표준라이브러리(Python33\Lib)의 컴파일된 버전을 sublime text에서 사용하는 것만 압축한 것입니다.

혹시 콘솔에서 정말 자주 사용하고 싶은 모듈이 있다면 여기에 넣고 임포트하여 사용하시면 되지만, 업데이트시 초기화 되어버리니, 조금 귀찮지만 plugin화 해놓는 것이 안전합니다.

끝.