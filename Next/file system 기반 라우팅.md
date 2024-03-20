## 파일 기반 네비게이션 기능
리액트에선 react-router라는 라이브러리를 사용하지만 Next.js에는 페이지 개념을 기반으로 구축된 파일 시스템 기반 라우터가 있다. 파일이 페이지 디렉토리에 추가되면 자동으로 경로로 사용할 수 있다. 페이지 디렉토리 내의 파일은 가장 일반적인 패턴을 정의하는 데 사용할 수 있다.

```js
pages/index.js -> /
pages/blog/index.js -> /blog
pages/blog/[slug].js -> /blog/:slug
pages/[username]/settings.js -> /:username/settings
pages/post/[...all].js -> /post/*
```