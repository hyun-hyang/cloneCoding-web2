# cloneCoding-web2
2022 클론코딩 대회 웹2조 입니다
## _네이버 블로그 화면 구현_

[![대회공지](https://avatars.githubusercontent.com/u/12232098?s=200&v=4)](https://saber-pullover-010.notion.site/5502610adcda46bfaa9896eef4b91e96)


**대회 진행:** 2022년 8월 17일(수) ~ 21일(일), 총 5일

## Introduction
**Language : Workframe: React**

제공받은 api를 활용해 **네이버 블로그** 화면을 구현해보았습니다.
- 블로그 메인 화면 구현
- 블로그 댓글 화면 구현 (선택)

### 조건
- 버튼 클릭 기능(단순히 도형 그려넣기X)이 확인되어야 하지만, 눌렀을 때 다른 화면으로 넘어가는 작업은 구현하지 않아도 됨
- 아이콘: 완전히 똑같은 모양 아니어도 됨
- 폭(너비, 가로) 길이는 아이폰 13 규격으로 진행
- 직접 네이버 블로그 앱에서 컴포넌트 작동 방식/디자인 고민

## api 정리
![api정리](/api%EC%A0%95%EB%A6%AC.jpg)

## Installation

It requires [Node.js](https://nodejs.org/)  to run.

Change directory to the project directory, and start the server :

```sh
cd naverblog_clonecoding
npm install --global yarn
npm install axios
npm install
yarn start
```

Open [http://localhost:3000](http://localhost:3000) to view it in your browser. 

if already port-3000 is using, just kill the server and retry  it :
```sh
cd naverblog_clonecoding
npx kill-port 3000
yarn start
```

# 네이버 블로그 만들기

## 만들어야할 컴포넌트

### BlogTemplate

- 설명: 모든 컴포넌트를 차곡차곡 올릴 템플릿. 하얀색 박스. 아이폰 13 규격에 맞춰 사이즈 제단

### BannerTemplate

- 설명: map을 사용하여 banner api를 렌더링
  
### Banner

- 설명: api에서 banner 정보 받아다가 출력.

### PostList

- 설명: 개별 포스트들을 모아둔 배열을 map을 사용하여 포스트를 렌더링
- context: 뷰 방식 클릭 유무 상태
- 기능: 뷰 방식 하나 클릭하면 진한 회색으로 변하기

### Post

- 설명: api에서 Posts 정보 받아다가 출력.
- context:  커서가 pointer로 변하는 부분들 클릭 유무 상태
- 기능: 커서가 pointer로 변하는 부분은 모두 클릭했을 때 콘솔창에 클릭했다고 뜨게 하기

## 변경 사항

### 폰트 사이즈

- 문제 상황: 폰트 사이즈가 10px 미만으로 내려가지 않음.
- 원인: 구글 설정>모양>글꼴맞춤설정>최소글꼴크기 옵션이 디폴트 10px로 맞춰져 있어서.
- 해결: 해당 코드 참조.

```javaScript
  font-size:10px;
  -webkit-transform:scale(0.5); //0.5 -> 50%
  display: inline-block;
```

### img 폴더 위치 변경

img 폴더 위치를 naverblog_clonecoding -> public으로 변경

### context관련 js 추가 ->>>> 만들다가 실패

- 클릭 상태를 관리하기 위해서 context 파일 추가함!
- 만들다가 실패해서 그냥 버튼 클릭하면 콘솔창에 뜨도록 코드 짜둠.
