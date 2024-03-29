# 공책 Note, Book
#### 독서 기록 서비스 공책
<table>
  <tr>
    <th width="100">기여도</th>
    <td>100% (개인 프로젝트)</td>
  </tr>
  <tr>
    <th>작업 기간</th>
    <td>2024.01.10 ~ 2024.02.13 개발 배포 완료<br>리팩토링, 기능 추가 및 보완을 통한 버전 관리 진행 중</td>
  </tr>
</table>
<br>

![notebook-pc](https://github.com/spaceyoung/notebook/assets/154400292/8e22be77-4de3-40bb-9f1f-8aa5182009ee)
<p align="center"><img src="https://github.com/spaceyoung/notebook/assets/154400292/98633aa4-d03a-40cb-8af1-e442b3464d02" width="420" /></p>
<br>

## 📕 배포 주소
[https://notebook-service.vercel.app](https://notebook-service.vercel.app/#/)
<br>
<br>
## 💡 작업 기록 및 회고
[https://padlet.com/myoungever/padlet-1](https://padlet.com/myoungever/padlet-1pebk43tm5u1ezu8)
<br>
<br>
## 🔎 개요
공책(Note, Book)은 **도서 검색 및 기록을 통해 자신만의 독서 기록을 관리할 수 있는 웹 앱**입니다. **알라딘의 Open API**를 활용하여 찾고 싶은 **도서를 검색**하고 **상세 정보**를 확인할 수 있으며, **독서 상태와 플랫폼, 독서 기간, 읽은 페이지, 개인적인 감상 및 생각** 등을 기록할 수 있습니다.

2024년 새해 목표 중 하나로 '독서 습관 기르기'를 계획하여, 이에 대한 기록 및 동기부여와 **CRUD 기능**을 직접 구현하고 **Open API**와 연계해 확장하기 위해서 작업한 프로젝트입니다. **기획부터 화면 구현, 배포까지 스스로 진행**하는 걸 목표로 삼았습니다.
<br>
<br>
## 🖥 구현 화면
| 회원 가입 | 로그인 | 홈(나의 기록) | 도서 검색 |
|---|---|---|---|
| <img src="https://github.com/spaceyoung/notebook/assets/154400292/fbfc45c6-5a70-4be5-87a7-0bd5971b014a" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/36e901dc-e4c9-4689-bbd3-c23214258585" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/5b33857d-da0d-44b2-b939-f5048bea74b1" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/6856f0c9-9713-46f9-b859-ae1d12fab9a4" /> |
<br>

| 무한 스크롤 및 더 보기 | 도서 기록 | 독서 중 기록 수정 -> 독서 완료 | 독서 완료 기록 수정 -> 독서 중 |
|---|---|---|---|
| <img src="https://github.com/spaceyoung/notebook/assets/154400292/2e5b14b1-d878-4408-831e-d6b93cc0e1a1" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/833b8d88-44f0-47da-a387-f8c1fccc2de4" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/a775a173-f57e-4efd-a2ca-fc5a38d62cb3" /> | <img src="https://github.com/spaceyoung/notebook/assets/154400292/6cc195cc-811f-4f8c-b709-0aa337662729" /> |
<br>

## 🛠 사용 기술
```
* Language
    - JavaScript

* Framework
    - Vue.js
    - Vuetify3

* Library
    - Vue router
    - Axios
    - Pinia
    - Vue 3 Lottie

* Database
    - Firebase

* Tools
    - Figma
    - Github
    - Vercel
    - Visual Studio Code
```
<br>

## ✨ 구현 기능
- **로그인/회원 가입**
    - **Firebase 인증**을 통한 **로그인/회원 가입** 및 **구글 소셜 로그인** 연동
    - 라우트 수준의 **내비게이션 가드**를 활용하여 사용자의 **로그인 유지 여부**에 따른 서비스 첫 접속 경로 구분

- **마이 페이지(나의 기록)**
    - 구글 소셜 첫 로그인 또는 회원 가입 시 사용자의 정보를 DB에 저장, 이를 통한 **독서 기록 데이터 조회 및 관리** 개인화
    - **동적 컴포넌트**를 이용한 독서 중/독서 완료 탭 전환 기능

- **도서 검색**
    - **알라딘 Open API**를 활용하여 사용자가 입력한 검색어에 따라 **도서명/작가명으로 도서 검색**
    - 검색된 도서 데이터를 JSON 형식으로 저장 후, 화면에 리스트 형식으로 결과 출력
    - **동적으로 API를 조회하고, 검색 결과를 생성 및 출력**하여 **검색 결과 더 보기 및 무한 스크롤 기능** 구현

- **도서 상세 정보 및 독서 기록 페이지**
    - 도서의 고유한 ISBN 값으로 Open API를 재호출하여 해당하는 도서의 상세 정보를 받아와 저장, 화면에 출력
    - **Firebase DB**를 활용하여 **로그인한 사용자의 독서 기록 정보 CRUD** 기능 구현
    - 독서 기록 폼의 '독서 시작/완료일', '읽은 페이지 수' 입력 필드에 **사용자 입력값 유효성 검증** 적용
    - 각 route에 **lazy loading**을 적용하여 **초기 화면의 로딩을 1초가량 단축**

- **배포 및 CI/CD**
    - **Github Actions, Vercel**를 활용하여 빌드부터 배포까지의 **워크플로우 자동화**
    - **Git flow의 branch 전략**을 도입하여 **체계적인 개발 단계를 구축**, 배포 안정성을 높이면서 **버전 관리** 진행

- **리팩토링 및 유지 보수**
    - 초기에 설계한 컴포넌트 구조를 통일성 있게 재구성하고, 꾸준히 리팩토링 방안을 고민하면서 **유지 보수 효율 및 확장성 향상**
    - **기능에 따라 스토어를 분리**, 사용자 인증 정보, API 호출을 제외한 **단일 컴포넌트 내의 상태값은 지역으로 관리**하여 초기의 불규칙하고 무분별한 전역 상태 관리를 감소
    - API key, Firebase SDK를 **환경 변수** 처리하여 보안 유지
<br>

## 💣 트러블 슈팅
- **도서 검색 결과 랜덤 출력**

<table>
  <tr>
    <th width="100">문제 배경</th>
    <td>같은 검색어를 입력해도 검색 시마다 검색 결과 리스트 순서가 일정하지 않고 랜덤하게 뒤바뀌는 현상 발생.</td>
  </tr>
  <tr>
    <th>문제 원인</th>
    <td>검색 결과 데이터를 받아와 저장하는 과정에서 순차적 처리가 이루어지지 않음.</td>
  </tr>
  <tr>
    <th>해결 과정</th>
    <td>async await으로 불러온 검색 결과 순서가 일정했기에, 받아온 데이터를 forEach 문으로 배열에 저장하는 과정에 문제가 있다고 판단. 반복문의 비동기 처리에 관하여 찾아본 결과, forEach 문은 순차 처리를 하지 않는다는 것을 깨닫고 for…of 문으로 바꾸어 문제 해결.</td>
  </tr>
  <tr>
    <th>알게 된 점</th>
    <td>forEach 문의 동작 원리와 배열에 비동기 작업을 실행할 때의 순차 처리와 병렬 처리 방법을 알게 됨.</td>
  </tr>
</table>
<br>

- **도서 검색 결과, 독서 기록 입력/수정 페이지 새로고침 오류**
<table>
  <tr>
    <th width="100">문제 배경</th>
    <td>도서 검색 결과, 독서 기록 입력/수정 페이지에서 새로고침을 누르면 404 페이지로 넘어가는 오류 발생.</td>
  </tr>
  <tr>
    <th>문제 원인</th>
    <td>Pinia를 사용해 저장한 state 객체 정보가 새로고침 시 초기화됨.</td>
  </tr>
  <tr>
    <th>해결 과정</th>
    <td>JavaScript로 To Do List를 만들어 볼 때 웹 스토리지를 사용하여 데이터를 저장했던 방법을 떠올리고, pinia-plugin-persistedstate 라이브러리를 추가 설치해서 데이터를 로컬 스토리지에 저장해 문제 해결.</td>
  </tr>
  <tr>
    <th>알게 된 점</th>
    <td>웹 스토리지 API를 통해 데이터의 지속성을 유지하는 방법을 다시 한번 상기할 수 있었음.</td>
  </tr>
</table>
<br>

- **배포 환경에서의 CORS 오류**
<table>
  <tr>
    <th width="100">문제 배경</th>
    <td>배포 사이트에서 도서 검색 시 CORS 오류가 발생하여 검색 기능을 이용할 수 없는 상황 발생.</td>
  </tr>
  <tr>
    <th>문제 원인</th>
    <td>Vite 개발 환경에서 적용한 proxy 설정이 Build 후의 정적 파일에서는 적용되지 않음.</td>
  </tr>
  <tr>
    <th>해결 과정</th>
    <td>Github Actions로 배포까지의 과정을 자동화하고, 최종 배포 플랫폼인 Vercel에서 proxy를 설정하여 문제를 해결.</td>
  </tr>
  <tr>
    <th>알게 된 점</th>
    <td>Vercel, Netlify, Nginx 등 정적 파일 배포를 지원하는 다양한 서비스 및 웹서버의 존재에 대해 알게 됨. 또한, proxy와 관련된 추가적인 학습을 통해 Forward proxy/Reverse proxy의 개념과 차이를 깨달음.</td>
  </tr>
</table>
