
## 小程序初体验（canvas倒计时）

### 核心代码

```javascript
function update(){
  var nextShowTimeSeconds = getCurrentShowTimeSeconds();

  var nextHours = parseInt(nextShowTimeSeconds/3600)
    , nextMinutes = parseInt( (nextShowTimeSeconds-nextHours*3600)/60 )
    , nextSeconds = nextShowTimeSeconds % 60;

  var curHours = parseInt(curShowTimeSeconds/3600)
    , curMinutes = parseInt( (curShowTimeSeconds-curHours*3600)/60 )
    , curSeconds = curShowTimeSeconds % 60;

  if(nextSeconds != curSeconds){
    if(parseInt(curHours/10) != parseInt(nextHours/10)){
      addBalls(MARGIN_LEFT+0,MARGIN_TOP,parseInt(curHours/10));
    }
    if(parseInt(curHours%10) != parseInt(nextHours%10)){
      addBalls(MARGIN_LEFT+15*(RADIUS+1),MARGIN_TOP,parseInt(curHours/10));
    }
    if(parseInt(curMinutes/10) != parseInt(nextMinutes/10)){
      addBalls(MARGIN_LEFT+39*(RADIUS+1),MARGIN_TOP,parseInt(curMinutes/10));
    }
    if(parseInt(curMinutes%10) != parseInt(nextMinutes%10)){
      addBalls(MARGIN_LEFT+54*(RADIUS+1),MARGIN_TOP,parseInt(curMinutes%10));
    }
    if(parseInt(curSeconds/10) != parseInt(nextSeconds/10)){
      addBalls(MARGIN_LEFT+78*(RADIUS+1),MARGIN_TOP,parseInt(curSeconds/10));
    }
    if(parseInt(curSeconds%10) != parseInt(nextSeconds%10)){
      addBalls(MARGIN_LEFT+93*(RADIUS+1),MARGIN_TOP,parseInt(nextSeconds%10));
    }


    curShowTimeSeconds = nextShowTimeSeconds;
  }

  updateBalls();
}
```

## 线上预览地址

[网页版炫酷倒计时](https://xuqiang521.github.io/Wechat/)
