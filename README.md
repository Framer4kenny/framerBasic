# framerBasic Tip
FramerBasic4kenny

### Default 값 설정
```
# Framer.Defalut
Framer.Defaults.Layer.backgroundColor = "aqua"
Framer.Defaults.Layer.borderRadius = 10
Framer.Defaults.Animation = 
	curve: “spring(100,10,1)”
	
# Framer.Device
Framer.Device.contentScale = 0.5
Framer.Device.orientation = 90
Framer.Device.background.blur = 10
Framer.Device.deviceType = "iphone-5c-green"
```

### (Background) Color 변경 
- Background Color
```
# 1. 디바이스 배경 활용
Framer.Device.background.backgroundColor = "tomato"
# 2. Screen이용
Screen.backgroundColor = "gray"
# 3. 레이어 활용
BG = new BackgroundLayer
	backgroundColor: "gray"
```

- Color 설정 (3)
```
backgroundColor: "aqua"
backgroundColor: “transparent”
backgroundColor: "rgba(128,0,0,1)"
backgroundColor: "#ffa000"

```

### 기타 다양한 TIP
- mouse scroll
```
#mouse-scroll
ScrollBox.mouseWheelEnabled = true
```
- Layer 순서변경
   - bringToFront() / sendToBack() / placeBehind() / placeBefore()
    	* 레이어의 부모관계가 다른 경우 위 코드로 인덱스를 변경할 수 없다.

- this = @
```
#this의 대체 @
layer = new Layer
layer.onClick (layer,event) ->
	@animate
		properties:
			x: 100
```
- offset 용어
   - 컴퓨터용어로서의 Offset 은 상대적 이라는 의미로 사용됩니다.
   - javascript 에 offsetWidth 라는 용어도 있습니다. (상대적 너비 라는 의미)

- 레이어 한번에 일괄적용 (for ~in)
```
#한번에 레이어 적용하기 for ~ in
for layer in Framer.CurrentContext.layers
	layer.y += 100
```

- Event 설정
```
# 이벤트 설정 아래 2가지는 같은 뜻
toon.onClick (event, layer) ->
toon.on Events.Click, ->
```

- Module 불러오기
   - Module 변수 설정하고 require로 불러오기
   - 예: keyboard Module 을 불러오는 경우,
```
# 아래는 Framer module파일 구성
keyboardModule = require "keyboard"
keyboardModule.myFunction()
```

- 주석 달기
   - 주석처리: 코드 앞에 # 표기
   - 한번에 주석처리: command + /

**Github Wiki** <br>
팁 정리: https://github.com/Framer4kenny/framerBasic/wiki
<br>

**Reference** <br>
Framer 공식 유튜브: https://www.youtube.com/channel/UCW5gUZ7lKGrAbLOkHv2xfbw <br>
모바일 프로토타이핑 예제: https://wikibook.github.io/framer/ <br>
프레이머 팁: https://paper.dropbox.com/doc/Framer-Tips--nKh0wLp87mROmzHfRU47s <br>
