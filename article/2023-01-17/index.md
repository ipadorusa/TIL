---
title: ESLint 종류
date: "2023-01-17 22:46:30"
---

# ESLint 종류 찾기

가이드 문서 종류

- ESLint getting-started: [ESLint getting-started](https://eslint.org/docs/latest/use/getting-started)

## ESLint 종류

- eslint-config-react-app: [eslint-config-react-app](https://www.npmjs.com/package/eslint-config-react-app)

  - Create React App 에 설치되는 Lint
  - peerDependencies
    - 검색 결과 없음(어디선가 명시적으로 사용될듯)
  - rule 관련링크: [rule-link](https://github.com/facebook/create-react-app/blob/main/packages/eslint-config-react-app/index.js)

- eslint-config-airbnb: [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)

  - peerDependencies
    - eslint-plugin-import
    - eslint-plugin-jsx-a11y
    - eslint-plugin-react
    - eslint-plugin-react-hooks
  - rules: eslint-config-airbnb-base + eslint-config-airbnb

- eslint-config-standard: [eslint-config-standard](https://github.com/standard/eslint-config-standard)
  - peerDependencies
    - eslint-plugin-import
    - eslint-plugin-n
    - eslint-plugin-promise
  - rules: [rule-link](https://github.com/standard/eslint-config-standard/blob/master/.eslintrc.json)

## ESLint와 Perttier를 역할별 용도

### eslint-config-prettier

prettier에서 관리 해 줄 수 있는 코드 스타일의 ESLint 규칙을 비활성화시켜준다. 즉, eslint 중 prettier와 충돌(중복)이 일어나는 모든 rules을 무시(turn off)한다.
이것을 사용하게 된다면 ESLint는 자바스크립트 문법 관련된 것들만 관리하게 되고, 코드 스타일 관련 작업은 prettier가 담당한다. 현재 적용된 대로라면 airbnb스타일에 맞게 포멧팅과 문법 검사를 맡게된 ESLint는 이 패키지로 인해 중복되는 포멧팅 규칙은 prettier에게 맡기고 나머지 부분에 대해서는 airbnb 컨벤션에 맞게 포멧팅과 문법 검사를 실행하는 것이다.

### eslint-plugin-prettier

Prettier를 ESLint 규칙에 맞게 실행하게 오류를 ESLint의 오류로 나타나게 해주는 기능을 가진 패키지이다. 즉, Prettier가 ESLint 규칙을 바탕으로 검사를 하다가 결과로 나오는 오류를 ESLint 오류로 보여주게 한다.
이 패키지를 작동시키기 위해서 eslint-config-prettier 패키지를 설정하는 것이라고 생각해도 된다. 왜냐하면 eslint-plugin-prettier 플러그인이 완벽하게 작동하기 위해서는 formatting에 관련한 모든 ESLint 규칙들을 꺼놔야한다. 그러지 않으면 lint error를 피할 수 없다고 공식문서에 나와있다.

#### 정리

정리하면 eslint-plugin-prettier 플러그인 설치를 통해 모든 Prettier 규칙 이 ESLint 규칙으로 추가된다고 볼 수 있기 때문에 ESLint 하나만 실행해도 문법검사와 formatting을 함께 실행 시킬 수 있다. 하지만 formatting에 관하여 충돌되는 부분이 있으면 안되므로 eslint-config-prettier 패키지 설치를 통해 해결하는 것이다. 이제부터 이 두개의 플러그인 패키지를 설치하고 설정을 적용할 것이다.

#### peerDependencies 확인 방법

```bash
npm info "eslint-config-airbnb@latest" peerDependencies
```

##### 참조

- 참조 사이트 1: [React-ESLint-설정-종류-및-airbnb-설정](https://velog.io/@jma1020/React-ESLint-%EC%84%A4%EC%A0%95-%EC%A2%85%EB%A5%98-%EB%B0%8F-airbnb-%EC%84%A4%EC%A0%95)
- 참조 사이트 2: [ESLint 조금 더 잘 활용하기](https://tech.kakao.com/2019/12/05/make-better-use-of-eslint/)
- 참조 사이트 3: [eslint-plugin-jsdoc](https://github.com/gajus/eslint-plugin-jsdoc)
