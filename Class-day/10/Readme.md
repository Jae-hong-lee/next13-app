# 글목록 가져오기

nextjs에서 서버쪽의 데이터를 가져와서(fetch) 이를 UI에 반영하는 방법을 살펴보자.

![Alt text](image.png)

단순히 보여주는 것은 Server Component, 사용자와 상호작용하는 것은 Client Component

nextjs 는 기본적으로 서버컴포넌트로 간주된다.
서버 컴포넌트에 useState, useEffect와 같은 훅은 사용할 수 없고 Client Component에서만 작동된다.
