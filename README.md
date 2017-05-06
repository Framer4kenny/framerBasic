# framerBasic
FramerBasic4kenny

### Color 설정 (3)
```
backgroundColor: "aqua"
backgroundColor: “transparent”
backgroundColor: "rgba(128,0,0,1)"
backgroundColor: "#ffa000"

```

### Background Color 변경 (3)
```
# 1. 디바이스 배경 활용
Framer.Device.background.backgroundColor = "tomato"

# 2. Screen이용
Screen.backgroundColor = "gray"

# 3. 레이어 활용
BG = new BackgroundLayer
	backgroundColor: "gray"
```

### Drag
- Drag 방향설정 (draggable.horizontal/vertical)
```
drag = new Layer
drag.draggable.enabled = true
drag.draggable.horizontal = false
```

### Scroll Lock
- 제대로 스크롤이 되지 않을 때 확인 (diretionLock)
```
myScroll = new ScrollComponent
myPage = new PageComponent
  superLayer: myScroll 

# 한방향으로만 스크롤 페이징되도록 제어
myScroll.directionLock = true
myPage.directionLock = true
```



### Sketch에서 Import 시 팁
- Import 이후 스크롤
- ScrollComponent.wrap(), Framer.Importer.load("")
```
# 사례1)
# Import file "tPXbanner"
sketch = Framer.Importer.load("imported/tPXbanner@1x")
# wrapping sketch content area  
scroll = ScrollComponent.wrap(sketch.tContent)

# 사례2)
# Import file "scrollTest"
sketch = Framer.Importer.load("imported/scrollTest@1x")
scrollBox = ScrollComponent.wrap sketch.scrollGroup
#스크롤 
scrollBox.scrollHorizontal = false
scrollBox.contentInset = 
	top: 20
	bottom: 200
```
- 스케치 임포트 시 이름을 변수로 사용
```
# sketch를 사용할 경우 레이어 이름을 변수로 바로 사용
Utils.globalLayers(sketch)
```

### Font 설정하기
```
labelTest = new Layer
	backgroundColor: "transparent"
	width: 450
	y: Align.center
	x: Align.center

labelTest.html = "HelloWorld!"
labelTest.style = 
	"font-size": "2.9em"
	"font-family": "HeveticaNeue" 
	"color" : "gray"
```

### Point 알아보기
- 드래그 위치 알기 (layerStartPoint)
```
layerA.on Events.DragStart, ->
	print layerA.draggable.layerStartPoint
```

### Event
- Event 설정
```
# 이벤트 설정 아래 2가지는 같은 뜻
toon.onClick (event, layer) ->
toon.on Events.Click, ->
```

### Animation 
- Animation Looping (Utils.interval)
```
layerA = new Layer
layerA.center()

layerA.states.add
	rotated:
		rotation:90
		borderRadius: 100

Utils.interval 2, ->
	layerA.states.next()
```

### Module 불러오기
- Module 변수 설정하고 require로 불러오기
- 예: keyboard Module 을 불러오는 경우,
```
# 아래는 Framer module파일 구성
keyboardModule = require "keyboard"
keyboardModule.myFunction()
```

### Modulate 
- 스크롤 시 배너 이동
- 모듈레이트 ()안에는 1)움직임1, 2)움직임1의 범위, 3) 움직임 1에 반응하는 변수의 범위 순으로 입력
```
scroll.onMove -> 
# 	print scroll.scrollY
	sketch.banner.y = Utils.modulate(scroll.scrollY, [0,500],[635,685],true)  
```

### 주석 달기
- 주석처리: 코드 앞에 # 표기
- 한번에 주석처리: command + /

### 스크롤 팁
```
pageBox = new PageComponent
	width: Screen.width
	height: Screen.height
	scrollHorizontal: true
	scrollVertical: false
	directionLock: true
```


Reference <br>
Framer 공식 유튜브: https://www.youtube.com/channel/UCW5gUZ7lKGrAbLOkHv2xfbw <br>
모바일 프로토타이핑 예제: https://wikibook.github.io/framer/ <br>
프레이머 팁: https://paper.dropbox.com/doc/Framer-Tips--nKh0wLp87mROmzHfRU47s <br>
