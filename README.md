# url-shortener-front

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Vite](https://vite.dev/) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production
vite.config.js 에서 build {} 경로를 로컬 백엔드의 static 으로 지정
```js
build: {
    outDir: '../url-shortener-back/src/main/resources/static',
  },
```

```sh
npm run build
```

스프링 부트와 api 요청 처리를 위해 axios 패키지 설치 필수
```sh
npm list axios
npm install axios
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
