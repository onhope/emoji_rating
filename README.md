# emoji_rating

![emoji-rating](https://github.com/onhope/emoji_rating/assets/97660780/af67a5f0-3005-4d75-9b63-7ececcb87314)  
    
    
### 이모티콘으로 별점을 평가할 수 있도록 만들었습니다.  

<br>

### 기능
이모지를 클릭을 하면, 별점이 1개씩 채워지는 효과를 구현

<br>

-------------------------------------------------------------------------------------------------------------------- 
 
### 사용한 라이브러리
#### fontAwesome  
https://fontawesome.com/  
키워드 : angry, smile, star

#### cdnjs    
자주 쓰는 CDN 모아둔 사이트  
https://cdnjs.com/

<br>

--------------------------------------------------------------------------------------------------------------------

### 학습  
#### 100% 와 100vh의 차이   

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
<br>
학습출처 : https://www.youtube.com/@JavaScriptKing   
