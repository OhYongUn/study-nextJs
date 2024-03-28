<h2>2.7</h2>

Pages and Layouts

React 모델을 사용하면 페이지를 일련의 컴포넌트로 분해할 수 있습니다. 이러한 컴포넌트 중 다수는 페이지 간에 재사용되는 경우가 많습니다.
예를 들어 모든 페이지에 동일한 네비게이션 바와 푸터가 있을 수 있습니다.
```
import Navbar from './navbar'
import Footer from './footer'

export default function Layout({ children }) {
return (
<>
< Navbar / >
< main >{children}< /main >
< Footer / >
</>
)
}
```
https://nextjs.org/docs/pages/building-your-application/routing/pages-and-layouts

<h2>2.8</h2>
Metadata
Next.js에는 향상된 SEO 및 웹 공유성을 위해 애플리케이션 메타데이터(ex: HTML head 엘리먼트 내의 meta 및 link 태그)를 정의하는 데 사용할 수 있는 메타데이터 API가 있습니다.
https://nextjs.org/docs/app/building-your-application/optimizing/metadata

Dynamic Metadata (동적 메타데이터)
generateMetadata 함수를 사용하여 동적 값이 필요한 메타데이터를 가져올 수 있습니다.
https://nextjs.org/docs/app/building-your-application/optimizing/metadata#dynamic-metadata
<h2>2.9</h2>
Dynamic Routes (App Router)

동적 세그먼트는 폴더 이름을 대괄호([folderName])로 묶어 생성할 수 있습니다.
```
// app/blog/[slug]/page.tsx
export default function Page({ params }: { params: { slug: string } }) {
return My Post: {params.slug}
}
```
https://nextjs.org/docs/app/building-your-application/routing/dynamic-routes

Dynamic Routes (Page Router)
https://nextjs.org/docs/pages/building-your-application/routing/dynamic-routes


<h2>2.3</h2>
fetch
Next.js는 기본 웹 fetch() API를 확장하여 서버의 각 요청이 자체 영구 캐싱 의미를 설정할 수 있도록 합니다.
https://nextjs.org/docs/app/api-reference/functions/fetch

Error Lens
VSCode에서 오류, 경고 및 기타 언어 진단을 강조하여 표시해주는 익스텐션
https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens
<h2>3.3</h2>
Loading UI and Streaming

특수 파일 loading.js는 React Suspense를 사용하여 의미 있는 로딩 UI를 만드는 데 도움이 됩니다.
이 규칙을 사용하면 route 세그먼트의 콘텐츠가 로드되는 동안 서버에서 즉시 로딩 상태를 표시할 수 있습니다. 렌더링이 완료되면 새 콘텐츠가 자동으로 교체됩니다.
즉시 로딩 상태는 탐색 시 즉시 표시되는 대체 UI입니다. 스켈레톤, 스피너 등 로딩 표시기나 표지 사진, 제목 등 미래 화면의 작지만 의미 있는 부분을 미리 렌더링할 수 있습니다.\

<h2>Parallel Requests</h2>
Promise.all()

Promise.all() 메서드는 순회 가능한 객체에 주어진 모든 프로미스가 이행한 후, 혹은 프로미스가 주어지지 않았을 때 이행하는 Promise를 반환합니다.
일반적으로 다음 코드를 계속 실행하기 전에 서로 연관된 비동기 작업 여러 개가 모두 이행되어야 하는 경우에 사용됩니다.
입력 값으로 들어온 프로미스 중 하나라도 거부 당하면 Promise.all()은 즉시 거부합니다.

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise/all

<h2>Suspense</h2>
Async Server Component TypeScript Error 오류 해결 방법

Its return type 'Promise' is not a valid JSX element.
async 가 포함된 서버 컴포넌트를 사용할 때 발생하는 타입스크립트 오류로 아래 두 가지 방법 중 하나로 해결할 수 있습니다.

1. typescript 5.1.3 버전 이상, @types/react 18.2.8 버전 이상 설치하기
   현재 @types/react는 설치되어 있지 않기 때문에
   npm i -D @types/react 로 설치 필요

2. 컴포넌트 위에 {/* @ts-expect-error Async Server Component */} 주석 추가하기
```
{/* @ts-expect-error Async Server Component */}
< MovieInfo id={id} / >
{/* @ts-expect-error Async Server Component */}
< MovieVideos id={id} / >
```
https://nextjs.org/docs/app/building-your-application/configuring/typescript#async-server-component-typescript-error

