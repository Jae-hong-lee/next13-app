# Next.js 란 무엇인가??

[Next.js 13 - 0. Next.js 란 무엇인가?](https://youtu.be/9KOaR6QMb9A?si=VN2iWq8Mro_MBj3t) with 생활코딩

Next.js는 웹 애플리케이션을 빌드하고 배포하는 강력한 도구, 모던한 웹 앱을 빠르고 효율적으로 구축할 수 있다!

### 수업에서 다루는 내용

- Next.js의 설치, 실행, 배포, 그리고 Vercel 플랫폼을 이용한 배포 방법
- CRUD(Create, Read, Update, Delete) 웹 앱의 구축
- Next.js의 라우팅 시스템에 대한 이해
- SPA(Single Page Application)
- SSR(Server Side Rendering) 개념
- Next.js를 API 서버로 사용하는 방법
- Server Component와 Client Component의 차이와 사용법
- Next.js에서의 환경 변수 사용 방법

### 목차

| 목차 |          Next.js 13           |
| :--: | :---------------------------: |
|  01  | [01](/Class-day/01/README.md) |
|  02  | [02](/Class-day/02/README.md) |
|  03  | [03](/Class-day/03/README.md) |
|  04  | [04](/Class-day/04/README.md) |
|  05  | [05](/Class-day/05/README.md) |
|  06  | [06](/Class-day/06/README.md) |
|  07  | [07](/Class-day/07/README.md) |
|  08  | [08](/Class-day/08/README.md) |
|  09  | [09](/Class-day/09/README.md) |
|  10  | [10](/Class-day/10/README.md) |
|  11  | [11](/Class-day/11/README.md) |
|  12  | [12](/Class-day/12/README.md) |
|  13  | [13](/Class-day/13/README.md) |
|  14  | [14](/Class-day/14/README.md) |
|  15  | [15](/Class-day/15/README.md) |
|  16  | [16](/Class-day/16/README.md) |
|  17  | [17](/Class-day/17/README.md) |

---

넥스트는 거대기업들도 사용할 정도로 검증된 `Full Stack Web Application FrameWork` 라고 설명하고 있다.

![Fullstack WepApplication FrameWork](/Class-day/00/image.png)

#### Web Application

이것은 웹앱을 만드는 도구라는 것을 알 수 있음

#### FrameWork

이것을 통해 규칙에 맞게 코드를 작성하면 준수한 웹앱이 만들어 진다는 소리

#### Full Stack

웹을 구성하는 프론트와 백엔드를 모두 가지고 있다는 뜻이다
사용자에게 보여지는 프론트는 React로 구현하고 백엔드는 `Express.js` 와 비슷한 형식에 시스템이 기본적으로 탑재되어있다.

### Nextjs 가 매력적인 이유

`SSR(Server Side Rendering)`을 지원한다는 것

react와 같은 js 기반의 애플리케이션은 js 로 동작하기 때문에 js를 다운로드를 하고 브라우저에서 js 실행이 되어야 화면이 표시된다. 그것을 클라이언트쪽에서 렌더링을 한다고 해서 CSR (Client Side Rendering)이라고 한다.

js 동작하지 않는 환경에서는 화면이 표시되지 않아서 검색엔진과 같은 컴퓨터들이 컨텐츠를 이용할 수 없다.
js 를 다운로드하고 실행하기 전까지 사용자에게 화면을 표시해 주지 않는 불편함도 있다.

SSR은 서버단에서 js를 실행된다. 브라우저로는 완성된 html 을 전송하기 때문에 js를 실행하지 않는 환경에서도 잘동작한다. (검색엔진 친화)
다운로드가 되는 순간 실행이 되기때문에 사용자 입장에서도 눈깜짝한 사이에 화면이 표시되는 경험을 할 수 있게함.
