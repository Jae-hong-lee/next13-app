# CSS

![Alt text](image.png)
app/layout.js를 보면 import './global.css' 코드가 있습니다.
layout.js는 전역적으로 적용되는 layout이기 때문에 이 파일은 모든 앱에 영향을 주고 있다.

> 전역적인 디자인을 적용하고 싶다면 app/global.css를 수정하면 된다.

### 절차

1. app/global.css 파일에 css 작성

```css
h1 a {
  text-decoration: none;
}
```
