---
title: SSG, SSR, CSR, ISR이 뭔가요?
date: "2023-01-19 22:46:30"
---

# SSG, SSR, CSR, ISR이란?

SSG(Static Site Generation)

### SSG 특징

- 빌드시 HTML에 데이터를 담아서 미리 파일을 만들고 접속하는 사람들에게 보여주는 형태(정적 페이지)
- 보통 블로그나 마케팅 목적으로 사용, 동적페이지가 필요하면 사용하지 않는다.
- 한번 만들고 변화가 없는 서비스에 적합
- 서버 부하가 적고 응답 속도가 빠름
- 데이터를 변경하고자 한다면 빌드를 다시 해서 올려야함
- 유명 Static Site Generators
  - Jekyll
  - Hugo
  - Docusaurus
  - Gatsby

SSR(Sever Side Rendering)

### SSR 특징

- 서버 부하 큼

CSR(Client Side Rendering)

### CSR 특징

- 초기 로딩 늦음
- SEO에 취약함

ISR(Incremental Static Regeneration)

### ISR 특징

- 빌드 시점에 페이지 생성(SSG와 동일)
- 일정 시간이 지난 후 페이지 새로 생성(최신 데이터 Update)
