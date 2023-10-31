# emoji_rating

![emoji-rating](https://github.com/onhope/emoji_rating/assets/97660780/af67a5f0-3005-4d75-9b63-7ececcb87314)  
    
    
## 이모티콘으로 별점을 평가할 수 있도록 만들었습니다.  

<br>

## 기능
이모지를 클릭을 하면, 별점이 1개씩 채워지는 효과를 구현

<br>

-----------------------------------------------------------------------------------------------
 
## 사용한 라이브러리
### fontAwesome  
https://fontawesome.com/  
키워드 : angry, smile, star

### cdnjs    
자주 쓰는 CDN 모아둔 사이트  
https://cdnjs.com/

<br>

-----------------------------------------------------------------------------------------------

## 학습  
### 100% 와 100vh의 차이   

<br>

```
body {
  margin: 0;
  display: flex;
  justify-content: center;
  height: 100vh;
  align-items: center;
  background-color: yellow;
}
```

위의 코드는 중앙으로 정렬을 할 때 사용하는 코드로, height가 100vh 로 되어있다.   
왜 100%를 사용하지 않을까 의문이 들었다. 그러기 위해서는 %와 vh의 차이를 이해해야 한다.   

| |100%|100vh|
|------|---|---|
|의미|상위 엘리먼트에 대한 비율|뷰포트(viewport, 화면 크기)에 대한 비율|

<br>

**그러므로 Viewport Height의 100%를 설정하려면**
<br>

**1. 화면을 100%로 사용하고 싶은 요소에 height: 100vh** 
```
body {
  height: 100vh
}
```

<br>  

**2. 부모와 자식 요소에 똑같이 height: 100%** 
```
html {
  height: 100%;
}

body { 
  height: 100%;
}
```

<br>

### css : trassform

transform : 회전, 크기 조절, 기울이기, 이동 효과를 부여

```
transform: matrix(1, 2, 3, 4, 5, 6);
transform: translate(120px, 50%);
transform: scale(2, 0.5);
transform: rotate(0.5turn);
transform: skew(30deg, 20deg);
transform: scale(0.5) translate(-100%, -100%);
```

여기서는 translate를 속성값으로 사용하여, 별을 클릭시 이모지가 -50% 씩 이동을 하여 보이도록 만들었다. 

<br>

### Array.prototype.forEach()
: 배열순회 함수  
: 각 배열 요소에 대해 제공된 함수를 한 번씩 실행
<br>
```
forEach(callbackFn)
forEach(callbackFn, thisArg)
```
<br>

**callbackFn**는 
배열의 각 요소에 대해 실행 할 함수로 반환값은 사용되지 않음.   
다음의 인수를 사용하여 호출을 함
> element : 배열에서 처리 중인 현재 요소  
> index : 배열에서 처리 중인 현재 요소의 인덱스  
> array : forEach()를 호출한 배열
<br>

**thisArg**은 callbackFn을 실행할 때 this 값으로 사용할 값   
<br>  
#### 반복문과 유사하나 다른점 

|제목|for|foeEach()|
|------|---|---|
|break와 continue|o|x|
|배열의 값 누락|undefined 리턴|누락값 스킵|   

<br>    

### EventTarget.addEventListener()   
: 장점은 하나의 이벤트 대상에 복수의 동일 이벤트 타입 리스너를 등록할 수 있음   
```
<input type="button" id="target" value="button" />
<script>
    var t = document.getElementById('target');
    t.addEventListener('click', function(event){
        alert(1);
    });
    t.addEventListener('click', function(event){
        alert(2);
    });
</script>
```
: 이벤트 객체를 이용하면 복수의 엘리먼트에 하나의 리스너를 등록래서 재사용 가능  
```
<input type="button" id="target1" value="button1" />
<input type="button" id="target2" value="button2" />
<script>
    var t1 = document.getElementById('target1');
    var t2 = document.getElementById('target2');
    function btn_listener(event){
        switch(event.target.id){
            case 'target1':
                alert(1);
                break;
            case 'target2':
                alert(2);
                break;
        }
    }
    t1.addEventListener('click', btn_listener);
    t2.addEventListener('click', btn_listener);
</script>
```



<br>
<br>


학습출처 
: https://www.youtube.com/@JavaScriptKing 
: MDN 문서
: 생활코딩