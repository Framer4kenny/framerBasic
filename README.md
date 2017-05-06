# framerBasic
FramerBasic4kenny

### Color 설정
```
backgroundColor: "rgba(128,0,0,1)"
backgroundColor: "aqua"
backgroundColor: "#ffa000"
backgroundColor: “transparent”

```

### Background Color 변경 방법 2가지
```
Screen.backgroundColor = "gray"

BG = new BackgroundLayer
	backgroundColor: "gray"
```

### Drag
- Drag 방향설정
```
drag = new Layer
drag.draggable.enabled = true
drag.draggable.horizontal = false
```


### Sketch에서 Import 시 팁
- Import 이후 스크롤
- ScrollComponent.wrap(), Framer.Importer.load("")
```
# Import file "tPXbanner"
sketch = Framer.Importer.load("imported/tPXbanner@1x")

# wrapping sketch content area  
scroll = ScrollComponent.wrap(sketch.tContent)
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
Framer 공식 유튜브: https://www.youtube.com/channel/UCW5gUZ7lKGrAbLOkHv2xfbw
모바일 프로토타이핑 예제: https://wikibook.github.io/framer/
프레이머 팁: https://paper.dropbox.com/doc/Framer-Tips--nKh0wLp87mROmzHfRU47s
