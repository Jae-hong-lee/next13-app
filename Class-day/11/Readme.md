# 읽기 기능 구현

> 10 수업
> 단순히 보여주는 것은 Server Component, 사용자와 상호작용하는 것은 Client Component라고 생각하면 된다.

데이터를 읽어서 출력할 뿐인 read 페이지는 Server Component로 가면된다.

### 절차

1. app/read/[id]/page.js 편집

```js
export default async function Read(props) {
  const id = props.params.id;
  const resp = await fetch(`http://localhost:9999/topics/${id}`);
  const topic = await resp.json();
  return (
    <>
      <h2>{topic.title}</h2>
      {topic.body}
    </>
  );
}
```

2.  http://localhost:3000/read/1 접속

이전과 같은 화면이 나오면 강력 새로고침을 해서 캐쉬를 지워주자

> Windows/Linux : Ctrl + Shift + R
> Mac : Cmd + Shift + R (safari : Cmd + Option + R)
