# 생성 기능 구현 - Client component

생성 기능을 구현하기 위해서는 onSubmit과 같은 사용자와 상호작용하는 코드가 필요하다.
이런 코드는 서버 쪽에서 실행할 수 없기 때문에 클라이언트 쪽으로 전송되어서 실행되어야 한다. 여기서는 클라이언트 컴포넌트를 만드는 방법을 살펴보자.

> ++ 유저와 상호작용을 하는 기능으로 Server Component가 아닌 Client Component에서 사용할 수 있다.

### 절차

1. create 에 layout을 우선 삭제하자.
   중첩 layout을 설명하기 위해 만든 임시파일이니까 삭제.
   > 에러가 뜬다면 개발서버를 껏다가 다시켜보기 or .next 폴더를 지우고 다시 개발모드실행(그럼 처음부터 다시 만들어서 보여주게 됨)
2. create/page.js 부분 수정하기

```js
// Server -> Client
"use client";

import { useRouter } from "next/navigation";

export default function Create() {
  const router = useRouter();
  return (
    <form
      onSubmit={async (e) => {
        e.preventDefault();
        const title = e.target.title.value;
        const body = e.target.body.value;
        const options = {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({ title, body }),
        };

        const resp = await fetch("http://localhost:9999/topics/", options);
        const topic = await resp.json();
        // console.log("file: page.js:19 ~ Create ~ topic:", topic);
        router.push(`/read/${topic.id}`);
        router.refresh();
      }}
    >
      <h2>Create</h2>
      <p>
        <input type="text" name="title" placeholder="title" />
      </p>
      <p>
        <textarea name="body" placeholder="body"></textarea>
      </p>
      <p>
        <input type="submit" value="create" />
      </p>
    </form>
  );
}
```

`'use client'`
위의 코드를 사용하면 client component로 전환
클라이언트 컴포넌트가 되면 useEffect, useState, onSubmit과 같은 코드를 사용할 수 있게 된다.

`e.preventDefault()`
기본적으로 웹이 동작하는 방법은 서버쪽으로 데이터를 전송하기 때문에 페이지가 전환된다. 이것을 방지할 때 사용하는 것,
이 함수를 호출하게 된다면 onSubmit을 실행됬을때 기본적인 동작을 막는 것.

`fetch`
서버쪽으로 데이터를 전송해서 데이터를 추가하기 위해서 option 값이 필요해서 option객체 작성해서 같이 보내줌.
이렇게 데이터를 생성하게 되면 방금 생성된 id값을 가지고 있는 글로 우리는 리디렉션을 시켜줘야한다. `useRouter()`
(방금 생성된 데이터로 페이지 이동)

`useRouter()`
useRouter를 사용하여 라우터 객체 생성, useRouter는 Client 에서만 사용가능.

> nextjs 13에서 바뀐 것. `useRouter()` 가져오려면 'next/router'가 아닌 'next/navigation'에서 가져와야 함.
> next/router : 12 방식, 페이지 라우터 방식
> next/navigation : 13방식 , new
> `useRouter()`은 push메서드를 사용하여 경로 이동.

`router.push()` + `router.refresh()`
push를 사용하면 페이지 리로드 없이 사용자 화면을 해당페이지로 이동, refresh를 사용하면 서버 컴포넌트를 서버쪽에서 다시 랜더링해서 새로 고침 할 수 있다.
여기서는 app/layout.js을 새로고침하기 위해 사용된 코드.
