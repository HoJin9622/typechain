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

## 함수의 매개변수

```ts
const name = "Hojin",
  age = 24,
  gender = "male";

const sayHi = (name, age, gender?) => {
  console.log(`Hello ${name}, you are ${age}, you are a ${gender}`);
};

sayHi(name, age);
```

sayHi 함수의 gender 뒤에 ?를 붙이지 않으면 실행 시 에러가 발생된다.

일반적인 js라면 Hello Hojin, you are 24, you are a undefined로 출력이 된다.

여기서 gender 뒤에 ? 를 붙이게되면 gender라는 매개변수는 선택적이 될 수 있음을 의미한다.
