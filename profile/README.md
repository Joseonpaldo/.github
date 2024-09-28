# 조선팔도(Joseonpaldo)
개발일정: 7/19/2024 ~ 9/18/2024

~~[https://joseonpaldo.site (폐쇠중)](https://joseonpaldo.site)~~


조선의 팔도를 테마로 한 전략 보드게임입니다. 모노폴리와 윷놀이를 결합한 독창적인 방식으로, 팔도의 다양한 지역을 탐험하며 경쟁합니다. 황금열쇠와 같은 미니게임들이 일부 칸들에 포진해있어 게임 진행이 더욱 대채로워지며, 매번 새로운 도전을 제공합니다.

## Team
| Name | Role | Github |
| :--- | :---: | :--- |
| 정민석 | Main Game, Frontend |  |
| 배동우 | Login, Backend |  |
| 이병현 | Lobby, Chat, Frontend |  |
| 이현성 | Deployment, Backend | https://github.com/themerous |
| 정환용 | Login, Backend |  |
| 최시현 | Minigame(Solo) |  |
| 허승필 | Minigame(Multi) |  |

## Tech Stack
### Frontend
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white)
![Axios](https://img.shields.io/badge/-Axios-5A29E4?style=flat-square&logo=axios&logoColor=white)
![Socket.IO](https://img.shields.io/badge/-Socket.IO-010101?style=flat-square&logo=socket.io&logoColor=white)
![StompJS](https://img.shields.io/badge/-StompJS-7E57C2?style=flat-square)
![Material UI](https://img.shields.io/badge/-Material--UI-0081CB?style=flat-square&logo=material-ui&logoColor=white)
![pnpm](https://img.shields.io/badge/-pnpm-F69220?style=flat-square&logo=pnpm&logoColor=white)
### Backend
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/-Express-000000?style=flat-square&logo=express&logoColor=white)
![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/-Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![OAuth2](https://img.shields.io/badge/-OAuth2-EB5424?style=flat-square&logo=oauth&logoColor=white)
![OpenID Connect](https://img.shields.io/badge/-OpenID%20Connect-F70000?style=flat-square&logo=openidconnect&logoColor=white)
![JWT](https://img.shields.io/badge/-JWT-000000?style=flat-square&logo=JSON-web-tokens&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/-Spring%20Data%20JPA-007396?style=flat-square)
![Gradle](https://img.shields.io/badge/-Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![WebSocket](https://img.shields.io/badge/-WebSocket-000000?style=flat-square)
![Socket.IO](https://img.shields.io/badge/-Socket.IO-010101?style=flat-square&logo=socket.io&logoColor=white)
![StompJS](https://img.shields.io/badge/-StompJS-7E57C2?style=flat-square)
![GSON](https://img.shields.io/badge/-GSON-000000?style=flat-square)
![EasyJSON](https://img.shields.io/badge/-EasyJSON-FF9900?style=flat-square)
![Swagger](https://img.shields.io/badge/-Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=white)
### DevOps
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Naver Cloud](https://img.shields.io/badge/-Naver%20Cloud-03C75A?style=flat-square&logo=naver&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![DNS](https://img.shields.io/badge/-DNS-334455?style=flat-square)
![SSL](https://img.shields.io/badge/-SSL-0033CC?style=flat-square&logo=letsencrypt&logoColor=white)
### Databases
![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
### Tools
![Visual Studio Code](https://img.shields.io/badge/-VSCode-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![IntelliJ IDEA](https://img.shields.io/badge/-IntelliJ%20IDEA-000000?style=flat-square&logo=intellij-idea&logoColor=white)
![DataGrip](https://img.shields.io/badge/-DataGrip-000000?style=flat-square&logo=datagrip&logoColor=white)
![Trello](https://img.shields.io/badge/-Trello-0052CC?style=flat-square&logo=trello&logoColor=white)
![Notion](https://img.shields.io/badge/-Notion-000000?style=flat-square&logo=notion&logoColor=white)
![Google Docs](https://img.shields.io/badge/-Google%20Docs-4285F4?style=flat-square&logo=google-docs&logoColor=white)

## 목차
- [소개영상](#소개영상)
- [ERD](#erd)
- [Schedule](#schedule)
- [Deployment](#deployment)
- [Main Application](#main-application)
- [API 명세서](#api-명세서)

## 소개영상

## ERD
작업중

## Schedule
작업중

## Deployment
### Servers
이미지가 들어갈 공간(1)

- DNS/SSL
  - 가비아 네이밍 서버를 통한 DNS 구축
  - 네이버 Certificate Manager를 통하여 SSL 인증서 발급
- Load Balancer
  - 네이버 클라우드의 Application Loadbalancer를 사용
  - Path분기를 통하여 서비스별로 분기점 설정
    - /api  : CRUD및 로그인/로그아웃 로직을 실행
    - /ws   : 채팅 및 메인게임의 웹소켓 통신을 담당
    - /nws  : 미니게임들이 구현된 서버
    - /     : 클라이언트 페이지
- Servers
    - 총 두개의 서버를 사용하여 각 서버에서 복수의 Docker Container활용

### CI/CD
이미지가 들어갈 공간(2)
- Github Action를 활용한 CI/CD 프로세스 구축
  - CI : Main branch로 push또는 pull request처리가 이루어지면 repository의 내역을 토대로 build를 실행. 빌드 성공시 Dockerfile을 토대로 Docker Image를 제작하여 네이버 클라우드의 Container Reqistry로 이미지를 전송
  - CD : 네이버 클라우드 CLI를 통하여 현 깃허브 액션 실행서버에서 배포 서버로의 접근 권한 부여 후 ssh 접속을 통한 원격 접속. 이후 네이버 클라우드 Container Registry에서 신규 이미지를 pull한 후 현재 사용중인 컨테이너를 정지하고 새로 pull한 이미지를 바탕으로 새 컨테이너 실행. 작업 완료 후 불필요한 이미지 버젼 제거 및 서버 접근권한 제거
- 총 4개의 Repository를 이용하여 각 Repository별로 각개의 서비스를 구축
  - JoseonpaldoFront  : NextJS 14 기반의 프론트엔드 서버
  - JoseonpaldoBack   : 로그인 인증 및 CRUD들이 이루어지는 SpringBoot 기반의 백엔드 서버
  - maingmaews        : 메인 게임의 웹소켓 통신 및 채팅기능을 처리하는 Springboot 기반의 백엔드 서버
  - minigamews        : 미니게임들의 웹소켓 통신 및 SSE를 처리하는 ExpressJS 기반의 백엔드 서버

## Main Application
### 로그인
이미지 들어갈 공간(3)


### Home
이미지 들어갈 공간(4)

### Lobby
이미지 들어갈 공간(5)

### Main Game

### Mini Game
이미지 들어갈 공간(6)

## API 명세서
### Swagger
이미지 들어갈 공간(7)
