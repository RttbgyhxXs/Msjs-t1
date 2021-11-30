## 搭建鏡像按鈕
<p><a href="https://dashboard.heroku.com/new?template=https://github.com/dietrichr/test"> <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy to Heroku" /></a></p>

## 填寫信息

| 屬性 | 值 |
|-----|----|
| 協議 | vless |
| UUID | 自己設置的UUID |
| PATH | 填`/`或者`不填` |
| 傳輸協議 | ws |
| 安全類型 | TLS |
| 服務器地址 | `heroku網址`或者`CDN網址` |

## 搭建CDN反向代理
```
addEventListener(
      "fetch",event => {
         let url=new URL(event.request.url);
         url.hostname="XXX.herokuapp.com";
         let request=new Request(url,event.request);
         event. respondWith(
           fetch(request)
         )
      }
) 
```
