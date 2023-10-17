# 라우팅 - Next.js의 도로교통 시스템

> 사용자가 접속한 URL의 path에 따라서 콘텐츠를 응답해주는 작업을 '라우팅' 이라고 합니다. 어떤 프레임워크든 그 중심에는 반드시 라우팅이 있습니다. 이것은 웹개발의 가장 중요한 요소 중 하나입니다.

![Alt text](image.png)
domain: 도메인 네임, 주소
path : 경로 ("/dashboard/analytics/")
segment : 경로를 이루고 있는 각각의 요소("dashboard","analytics")

저 경로에 따라서 어떤 컨텐츠를 어떤 방식으로 보여줄 것 인가를 **라우팅** 이라함

## 절차

![Alt text](image-1.png)

1. 처음에 "/create" 로 접속하면 "Not found" 페이지가 출력된다.
2. app 및에 create라는 폴더를 만들고 약속된 이름에 파일(page.js)를 만들고 컴포넌트를 만들게 된다면

```js
export default function Create() {
  return <>Create!!</>;
}
```

3. "/create"로 다시 접속하면 정삭적으로 create 페이지가 출력된다.

## 알 수 있는 것
