# TypeChain

## Setting

```zsh
yarn global add typescript
```

먼저 typescript를 global로 설치한다.

그 후 tsconfig.json 파일을 생성해준다.

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "ES2015",
    "sourceMap": true
  },
  "include": ["index.ts"],
  "exclude": ["node_modules"]
}
```

tsconfig.json 파일의 내용으로는 다음과 같이 입력한다.

- module: 모듈 설정
- target: 사용할 ECMAScript 버전 설정
- sourceMap: 소스맵(\*.map) 파일 생성 여부

```json
"scripts": {
    "start": "node index.js",
    "prestart": "tsc"
}
```

다음으로는 package.json 파일의 scripts에 start로 node index.js 를 추가해주고

prestart에 tsc를 주어 start 되기전에 tsc를 실행한다.

tsc는 ts파일을 컴파일 옵션에 따라서 컴파일을 실행한다.
