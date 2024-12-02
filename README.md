# 장두혁 (백엔드 개발자)


## **Contact**
- **Email :** jjd0324@gmail.com
- **Phone :** 010-5623-5318
- **Portfolio :** https://blog.jangdu.site/portfolio
- **Github :** https://github.com/jangdu
- **Blog :** https://blog.jangdu.site (개발 진행중)
---
# Projects

## Drinkit   팀프로젝트  2023.08 ~ 2023.09 (5주)

혼술하는 사람들을 위한 주류 쇼핑몰 팀 프로젝트 ( 4인 )

- Github : https://github.com/jangdu/Develop-Drinkit

#### 주요 기술

- Nest.js, React, webRTC, [socket.io](http://socket.io), PostgreSQL, Redis, RDS Read Replica, Elastic search, Open AI

#### 주요 구현 내용

React를 사용한 프론트엔드 구현

- SPA관련 라이브러리를 처음 사용해보는 **[팀원들이 구현 가능하도록 기본적인 문법 및 기능 소개](https://blog.jangdu.site/posts/19)**
- [ContextAPI를 활용한 장바구니 기능 구현](https://github.com/jangdu/Drinkit_frontend/blob/main/src/context/CartContext.js) :
    - 휘발성이 강한 장바구니 추가, 삭제 기능 등을 클라이언트에서 처리해 서버의 부담 최소화

화상채팅 :

- **WebRTC, Socket.io를 사용해 최대 4명이 실시간 소통가능한 화상채팅 구현**
    - 피어들이 직접 미디어를 교환하는 **메쉬 방식 구현**
        - 수용가능한 인원이 소수인 채팅방을 메쉬 방식으로 구현해 서버의 부담을 최소화
        - 테스트결과 10명까지는 클라이언트끼리 직접 미디어를 교환해도 브라우저의 무리가 발생하지 않아 선택
    - 브라우저나 채팅창이 닫히는 상황을 React에서 확인하지 못해, 정지된 비디오를 지우지 못하는 문제 발생
        
        → 공식문서를 통해 [NestGateway의 handleDisconnect를 사용](https://github.com/jangdu/Drinkit-webRTC/blob/c0edfa524892baba4361020d23f717392dfb2195/src/chat/chat.gateway.ts#L41)해서 연결이 끊어지는 상황을 클라이언트에 전송 후 처리하는 방식으로 해결
        
- 휘발성이 강한 현재 열려있는 채팅방 목록을 **Redis를 활용해 메모리에 저장하여 응답 속도 개선(750ms → 340ms)**

**부하분산 및 가용성 확보 :**

- Route53의 A레코드 가중치 기반 라우팅 정책을 사용해서 DB부하 분산
- 스냅샷 방식으로 ReadReplica에 대한 동기화 진행, 평균 0.8초 동기화
- RDS Read Replica의 복제본을 승격시키는 방식을 사용해 재해상황에도 가용성을 확보할 수 있도록 구현

[자세히 보기]: https://github.com/jangdu/Develop-Drinkit "자세히 보기"

