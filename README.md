# 장두혁 (백엔드 개발자)

### **Contact**
- **Email :** jjd0324@gmail.com
- **Phone :** 010-5623-5318
- **Portfolio :** https://blog.jangdu.site/portfolio
- **Github :** https://github.com/jangdu
- **Blog :** https://blog.jangdu.site (개발 진행중)
---
## Projects

### 1. JangduLog 개인 블로그 프로젝트 ( 2023.03 ~ )

개발 잘하시는 분들이 운영하시는 개인 블로그들에 대한 동경으로 시작한 개인 블로그 프로젝트

- url : https://blog.jangdu.site (진행중)
- Skill : Nest.js, React.js, MySQL, S3, Lambda, CloudFront, CodeDeploy, GithubAction
- github:
  - backend : https://github.com/jangdu/jangduLog_backend
  - frontend : https://github.com/jangdu/jangduLog_frontend

#### 주요 구현 내용

- **firebase -> nest.js :** React를 활용한 프론트엔드 구현, firebase를 통한 간단한 DB구축 ( 2023.03 ) 이후 데이터 관리 및 기능 추가 시 불편 **->** **nest.js, mysql(typeorm)로 백엔드 구현 ( 2023.09 ~ )**
- CloudFront, S3, EC2, RDS를 사용한 배포 **->** 반복적인 빌드, 배포의 불편 **->** CodeDeploy를 사용해 **CI/CD** **배포 자동화를 통해 효율적인 개발 환경 구성** (https://blog.jangdu.site/posts/7)
- **Redis :** 가장 조회가 많이 일어나는 첫 페이지를 캐싱해 응답속도 개선 **( 240ms -> 92ms )**

---

### 2. Drinkit   팀프로젝트  2023.08 ~ 2023.09 (5주)

혼술하는 사람들을 위한 주류 쇼핑몰 팀 프로젝트 ( 4인 )

- URL : https://drinkit.site/
- Github : https://github.com/jangdu/Develop-Drinkit

#### 주요 기술

- Nest.js, React, webRTC, [socket.io](http://socket.io), PostgreSQL, Redis, RDS Read Replica, Elastic search, Open AI

#### 주요 구현 내용

**프론트엔드** : React를 활용한 구현

- React를 사용해 본 경험이 있어, 처음 사용해보는 **팀원들이 구현 가능하도록 기본적인 문법 소개**

**화상채팅** : WebRTC, Socket.io를 사용해 구현

- 시그널링 서버를 사용해서 연결된 피어들이 직접 미디어를 교환해 서버의 부담을 최소화하는 메쉬 방식으로 구현

**Redis** : 채팅방 목록, RefreshToken을 **Redis를 활용해서 응답속도 개선 ( 750ms -> 340ms )**

**RDS Read Replica :** 메인 DB 읽기 요청을 분산해 사용자가 몰릴 때 DB가 다운되는 경우의 문제 개선

**Load Balancer** : 메인 서버를 두개로 나누어, 각 서버의 부하를 줄여 트래픽 분산 처리 및 배포 시 중단 문제 개선

[자세히 보기]: https://github.com/jangdu/Develop-Drinkit "자세히 보기"

