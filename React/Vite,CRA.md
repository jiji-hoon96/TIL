# CRA vs Vite

# 1. Vite

- ES 모듈을 사용하며, 개발 서버에서 모듈 번들링을 하지 않는다.
  - ES Module
    - ECMAScript 에서 도입된 자바스크립트 모듈 시스템
    - 코드를 여러 개의 독립적인 파일로 분할하여 관리하고 재사용할 수 있는 구조를 제공
    - 정적인 모듈 시스템 : 모듈의 의존성과 내보내기를 실행하기 전에 미리 분석,해석
    - import, export 를 이용해서 모듈을 가져오고 내보냄
- 개별 모듈에 대해 빠른 핫 모듈 리로딩(HMR)을 지원하며, 빌드 시간을 크게 줄여줌
  ![https://velog.velcdn.com/images/ho2yahh/post/0d91ec38-2d7d-4ce0-86ed-a2ceee1708a7/image.gif](https://velog.velcdn.com/images/ho2yahh/post/0d91ec38-2d7d-4ce0-86ed-a2ceee1708a7/image.gif)
  - **수정된 파일만 다시 빌드하고 리로드(esbuild 를 사용)**할 수 있다. 개발 과정을 매우 빠르게 만들어 줌
  - Vite도 처음에만 전체를 번들링 후 다음 부터는 변경사항만 번들링함
- 더 간단하고 직관적인 설정을 가지고 있음.
- 기본적으로 설정 파일이 필요하지 않으며, 필요한 경우 vite.config.js 파일을 생성하여 추가적인 설정을 할 수 있다.
- 플러그인 시스템을 통해 다양한 기능을 확장 가능.
  - TypeScript, CSS 전처리기, 상태 관리 라이브러리 등의 플러그인을 쉽게 추가할 수 있습니다.
- Vite 는 Koa 라는 서버를 사용

    <aside>

  💡 **Koa**

  - Node.js 웹 애플리케이션을 위한 미들웨어 프레임 워크
  - ES6 의 async/await 문법과 제네레이터를 사용하여 비동기 코드를 처리하는데 중점을 두고 설계됨
  - 경량화 되어있어서 유연하고 효율적인 웹 애플리케이션을 개발 가능

    </aside>


- Vite 는 CommonJS 나 UMD 방식을 ESM 방식으로 컨버팅

    <aside>

  💡 **CommonJS, UMD, ESM, Converting**

  1. CommonJS

  - Node.js 의 모듈 시스템
  - require() 을 사용해 가져오고, module. exports 객체를 사용해 내보낸다.
  - CommonJS 는 동기적으로 모듈을 로딩하고 실행

  2. UMD(Universal Module Definition)

  - 여러 환경에서 사용 가능한 범용 모듈 시스템을 정의하는 패턴
  - CommonJS 방식으로 모듈 가져오도록 시도하고, 지원되지 않으면 직접 모듈을 노출

  3. ESM(ECMAScript Modules)

  - 자바스크립트 모듈 시스템
  - import, export 키워드를 사용하여 모듈을 가져옴
  - ESM 은 정적인 모듈 시스템으로 의존성과 내보내기를 실행전에 미리 분석

  4. Converting

  - 한 모듈 시스템의 코드를 다른 모듈 시스템의 코드로 변환하는 과정
  - Vite 는 CommonJS , UMD 방식 ⇒ ESM 방식으로 변환하여사용 (효율적이고 빠른 모듈 로딩을 위해서)

    </aside>


# 2. CRA

- Create React App은 기본적으로 Webpack을 사용하여 애플리케이션을 번들링

<aside>

💡 **Webpack**

- 모듈 번들러, 클라이언트에서 JS 파일을 묶어서 하나의 파일로 사용하기 위해서 사용
- 구성요소

  > Entry : 각 모듈들이 바라보는 최상위 JS 파일. Webpack 은 Entry 를 통해 필요한 모듈을 로딩하고 하나의 파일로 묶는다.

  > Output : 번들링 결과물을 어디에 생성하고 네이밍 할지 정의

  > Loader : JS가 아닌 여러 가지 타입의 파일들을 웹팩이 이해할 수 있도록 해줌, ES6 문법을 ES5로 변환해주기도 함(Babel)

  > Plugins : 번들링 된 결과물에 대해 적용할 수 있는 속성, 결과물의 형태를 바꾸는 역할을 함

      ex) Uglify bundle(코드 난독화), Minify CSS(css to js파일을 별도의 bundle로 분리)

</aside>

- 모든 파일을 번들로 묶고 최적화된 결과물을 생성
- CRA의 개발 서버도 핫 모듈 리로딩을 제공하지만, Vite보다는 성능 면에서 약간 뒤쳐짐
- CRA는 초기 설정이 이미 완료되어 있어 사용자가 직접 설정을 건드릴 필요가 없다.
- 하지만 필요에 따라 설정을 커스터마이즈할 수 있는 **react-scripts**를 사용할 수도 있다,
- CRA는 초기 프로젝트 설정에서 이미 대부분의 기능을 제공하므로 추가적인 설정이 필요하지 않다.
- 다만 커스텀 기능을 구현하려면 eject 명령을 통해 프로젝트를 추출해야 할 수도 있다,
- CRA는 React 생태계의 많은 도구와 라이브러리와 호환되도록 설계되어 있다.
- React의 공식 툴로 인기가 있으며, 다양한 커뮤니티와 지원이 활발합니다.
