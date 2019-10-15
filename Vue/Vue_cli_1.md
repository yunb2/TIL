# Vue CLI 3.0

> <a href="https://youtu.be/G6rhxMuqnhU">맨땅에 개발하기 - Vue CLI 3.0 시작하기</a>

## 설치 및 세팅

- Vue CLI는 Vue 개발환경을 쉽게 구축하도록 도와주는 툴

- 개발환경 구축을 위해서는 Node.js가 필요

  ```
  node -v // node 버전확인
  npm install -g @vue/cli // npm을 통해 vue 설치
  sudo npm install -g @vue/cli // error 발생 시 관리자 권한으로 
  vue --version // vue 버전 확인
  ```

- 프로젝트 생성

  ```
  vue create [프로젝트명]
  
  // 프로젝트 설정
  ? Please pick a preset: 
   > Manually select features
  ? Check the features needed for your project:
   > Babel, Router, Vuex
  ? Use history mode for router?
   > Y
  ? Where do you perfer placing config for Babel, PostCSS, ESLint, etc.?
   > In package.json
  ? Save this as a preset for future project? (개발환경 저장여부)
   > N
  ```

- 프로젝트 실행

  ```
  cd [프로젝트 경로]
  vue run serve
  ```

- 프로젝트 구조

  ```
  
  ```

  