# Tip 003. EasyMotion PlugIn

커서를 순식간에 원하는 위치로 이동하는 마술의 Plugin입니다. 설명보다는 실제 한번 해보는 것이 더 빠름니다. EasyMotion를 설치하고 아무 파일이나 열어보세요.


## 간단히

![이동전 화면](tip_003\001.png)

저는 "FindSameFile.db"에서 Same를 same으로 변경하기 위해 커서를 S위로 옮기겠습니다. 설정된 단축키를 입력 후 이동하고자 하는 위치의 문자(s)를 입력합니다.

|OS       | 단축키   | 이동하고자하는 문자
|---------|----------|---------------------
|Win/Linux| Ctrl + ; | s
|OSX      | Cmd + ;  | s

![단축키 입력 후 화면](tip_003\002.png)

s,S 문자들이 a,b,c,d...로 보이며, i를 누르면 커서가 이동합니다.

![이동 후 화면](tip_003\003.png)



## 위험!!

해당 커서를 이동하지 않고, 파일을 저장하게 되면, 현재의 변경된 문자가 그대로 저장됩니다. 꼭!!! 이동하세요.



## 자세히

조금 더 자세히 살펴볼까요?, 다시 한번 s를 찾아봅시다.

![다시 s](tip_003\004.png)

EasyMotion은 현재의 커서에서 왼쪽 그리고 위쪽방향으로 이동하면서 대소문자를 구분하지 않고 입력되 문자와 일치하는 첫 위치를 'a'로 변경하고, 다시 현재의 커서에서 오른쪽 아래방향으로 이동하면서 일치하는 위치를 'b'를 변경합니다. 즉 현재커서에 가깝게 a,b,c,d...가 분포되도록 합니다.

또한 당연(?)하다고 생각할 수 있지만 한글은 지원하지 않습니다. ( 엔터, 숫자, 특수문자는 지원합니다. ) 한글을 지원안하는 이유는 EasyMotion문제라기 보다, sublime text에서 이벤트 단축키가 조합된 한글을 지원하지 않아서 입니다. ( 조합된 한글 단축키를 지원하는 시스템 본 적있으세요? )

## Select

단축키 입력시 Shift와 함께 누르면, 현재의 위치에서 이동까지 선택됩니다.
( 왠지 유용할 것 같지만 잘 사용안하는 기능이 될 것 같기도 하고... )

|OS       | 단축키   
|---------|----------
|Win/Linux| Ctrl + Shift + ;
|OSX      | Cmd + Shift + ;


## 위치 문자 변경

a,b,c,d...로 변경되는 문자를 아래와 같이 설정을 추가하면 다른문자로 변경할 수 있습니다.

```
"placeholder_chars" : "jkl;asdfHGJKL:ASDFHG"
```


끝. 메르스 조심하세요.

---

#### 나의 sublime text

제가 sublime text에 빠져있을 때, 같은 사무실에 계시던 유차장님은 emacs에 빠져있었습니다. 그 때 저에게 sublime text에서는 이런 것 되냐며 자랑하던 것이 EasyMotion의 emacs버전인 AceJump였습니다. 불행히 그 때는 sublime text 3 갓 나온 상태라 EasyMotion이 2에서만 동작하고 3에서는 동작하지 않았는데, 2014년도에 4월에 추가되었네요.

EasyMotion가 3에서 너무 사용하고 싶어, 플러그인을 분석했던 것이 sublime text를 더욱 자세히 알게된 계기가 된 것 같네요.

#### Vintage모드를 사용한다면 f를 변경하세요.
Vintage모드를 사용하신다면 f를 아래와 같이 변경하여 EasyMotion를 사용할 수 있습니다.

Data\Packages\User\Default.sublime-keymap 아래와 같이 추가하세요. ( 파일이 없다면 새로 만들어야 합니다.)

```json
[
    ...
    
    { "keys": ["f", "<character>"], 
      "command": "easy_motion",
      "args": {"select_text": false},
      "context": [{"key": "setting.command_mode"}]
    },
    
    ...
]
```