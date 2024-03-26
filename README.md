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
즉시 로딩 상태는 탐색 시 즉시 표시되는 대체 UI입니다. 스켈레톤, 스피너 등 로딩 표시기나 표지 사진, 제목 등 미래 화면의 작지만 의미 있는 부분을 미리 렌더링할 수 있습니다.