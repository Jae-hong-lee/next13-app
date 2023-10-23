# 정적인 자원 사용하기 - public

nextjs 에서 이미지와 같은 정적인 컨텐츠를 사용하기 위해서는 어떻게 해야할까?

> 이미지, robots.txt, favicon.ico와 같은 파일을 static asset라고 합니다.

### 절차

1. public 폴더에 이미지를 삽입(hello.png)
2. `app/page.js` 에서 `/hello.png`를 이용해서 사용

```js
export default function Home() {
  return (
    <>
      <h2>Welcome</h2>
      Hello, WEB
      <p>
        <img src="/hello.png" width="80" alt="" />
      </p>
    </>
  );
}
```
