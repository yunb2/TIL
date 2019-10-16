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
  npm run serve // Compiles and hot-reloads for development
  npm run build // Compiles and minifies for production
  ```

- 프로젝트 구조

  | 폴더/파일      |                                                              |      |
  | -------------- | ------------------------------------------------------------ | ---- |
  | node_modules   | 자바 스크립트 프레임워크에서는 여러 모듈을 조립해서 어플리케이션을 완성하는데, 이 모듈들을 모아두는 폴더 |      |
| package.json   | 해당 프로젝트에서 어떤 모듈을 사용할지 적어두는 파일         |      |
  |                | 이전에는 npm install이라는 명령어를 통해 package.json에 명시된 모듈들을 설치해야 했지만, Vue CLI 3.0부터는 프로젝트 생성시 자동으로 node_modules라는 폴더가 생성됨 |      |
  | public         | 기본이되는 index.html 파일이 존재하는 폴더                   |      |
  | src/assets     | 이미지, css 등의 파일들을 저장하는 폴더                      |      |
  | src/components |                                                              |      |
  | src/views      |                                                              |      |
  | src/App.vue    | 가장 기본이되는                                              |      |
  | src/main.js    | 어플리케이션 구동                                            |      |
  | src/router.js  | 라우터 제어                                                  |      |
  | src/store.js   | 전역상태 제어                                                |      |

- Vuetify 플러그인 설치

  ```
  vue add vuetify
  
  // vuetify 설정
  ? Choose a preset
   > Configure
  ? Use a pre-made template?
   > Y
  ? Use custum theme?
   > N
  ? Use custum properties?
   > N
  ? Select icon font
   > Font Awesome 5
  ? Use fonts as a dependency?
   > N
  ? Use a-la-carte components?
   > N
  ? Use babel/polyfill?
   > Y
  ? Select locale
   > en
  ```



