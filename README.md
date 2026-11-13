![header](https://capsule-render.vercel.app/api?type=Waving\&section=header\&height=260\&text=HStar0124\&fontAlignX=50\&fontAlignY=45\&color=gradient\&fontSize=90\&fontColor=ffffff\&desc=Real-time%20Backend%20%C2%B7%20C%2B%2B)

## 👋 Hi, I'm HStar

C++로 **실시간 음성 AI 게이트웨이**를 만드는 백엔드 개발자입니다.
외부 시스템이 느려지거나 죽어도 서비스는 버티게 만드는 일, 그리고 재현되지 않는 버그를 끝까지 쫓는 일을 좋아합니다.

- 🔭 **지금 하는 일:** 콜센터의 STT/TTS 엔진과 상담 시스템 사이에서 음성을 실시간으로 중계하는 게이트웨이 개발
- 🌱 **요즘 파고드는 것:** 멀티스레드 경쟁 상태, 장애 격리 설계, AI 코딩 도구로 개발 흐름 만들기

---

## 📝 일하면서 배운 것들

### 1. 취소한 타이머가 살아남는 이유

asio에서 `expires_from_now()`는 만료 시각만 정할 뿐, 타이머를 무장하지 않습니다.

```cpp
timer.expires_from_now(timeout);   // ① 만료 시각만 정함
// ← 이 사이에 다른 스레드가 cancel() 하면? 취소할 대기가 없어 아무 일도 안 일어남
timer.async_wait(onTimeout);       // ② 이제야 무장 → 방금의 취소를 넘어 살아남음
```

24시간에 한 번, 이렇게 살아남은 타이머 하나가 소멸자의 `join()`을 붙잡아 이벤트 루프 전체가 10초 동안 멈췄습니다.
헬스체크는 계속 정상이었습니다. 타이머 조작을 한 임계구역으로 묶고, 종료가 시작되면 다시 무장하지 못하게 막아 해결했습니다.

> 재현하지 못한 수정은 고쳤다고 말할 수 없다. 재현 120/120 → 수정 후 0/120을 확인하고 나서야 닫았습니다.

### 2. 카운터는 한 번 틀리면 계속 틀린다

이중화 서버끼리 동시 세션 수를 Redis로 공유할 때, `INCR` / `DECR` 대신 **세션마다 키를 만들고 TTL을 걸었습니다.**
비정상 종료로 `DECR`이 한 번만 빠져도 카운터는 영원히 어긋나지만, TTL은 시간이 지나면 스스로 맞춰집니다.

Redis가 1초 안에 답하지 않으면 통화를 **거절하지 않고 받습니다(Fail-Open).**
세션 수가 잠시 넘치는 것보다, 고객 전화를 못 받는 쪽이 훨씬 큰 손실이기 때문입니다.

### 3. 느린 요청 하나가 큐 전체를 세운다

평소 수십 ms이던 API가 가끔 2초씩 걸리자, 하나뿐인 발송 큐 뒤로 모든 통화가 줄을 서며 지연이 수십 분까지 쌓였습니다.
스레드만 늘리면 한 통화 안의 이벤트 순서가 섞입니다.

```
call-id ──hash──▶ queue[i] ──▶ 전용 스레드 1개
```

통화를 해시로 특정 큐에 고정하고 큐마다 스레드를 하나씩 두어, **통화 안에서는 순서를, 통화 사이에서는 병렬을** 얻었습니다.
지연은 평균 수십 ms로 돌아왔고, 이제 API가 느려져도 그 큐 하나만 잠깐 밀립니다.

---

## 🤖 AI와 일하는 방식

```
설계 (Codex) → 구현 (Claude Code) → 검수 (구현에 참여하지 않은 별도 세션) → 리뷰 · 빌드 · 테스트 (직접)
```

한 모델이 짜고 스스로 검토하면 자기 실수를 못 봅니다. 그래서 역할을 나누고, 마지막 검증은 사람이 합니다.

---

## 🚀 Featured Project

### [HStar Project](https://github.com/hstar0124/hstar-project)

C++ 비동기 TCP 소켓 서버와 ASP.NET Core API 서버를 직접 설계하며 서버 간 통신과 비동기 네트워크 프로그래밍을 실험한 프로젝트입니다.

<img src="https://github.com/hstar0124/hstar-project/assets/57317290/cdd2701d-590f-49ac-83a5-f8d310cf3005" width="650"/>

- Swap Queue로 락 경합 최소화, DB 작업은 큐에 적재해 멀티스레드로 처리
- 대기열로 동시 접속자 수 제한, 중복 로그인 감지 시 기존 연결 종료
- Redis 세션 키로 API 서버와 소켓 서버 간 세션 의존성 분리
- Protobuf 직렬화로 JSON 대비 패킷 크기 약 2/3 감소

---

## 🛠 Tech

**Main**
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>
<img src="https://img.shields.io/badge/gRPC-244C5A?style=flat-square&logo=google&logoColor=white"/>
<img src="https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white"/>
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black"/>

**Also**
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Protobuf-4285F4?style=flat-square&logo=google&logoColor=white"/>

---

## 💼 Career

| 기간 | 회사 | 한 일 |
| --- | --- | --- |
| 2024.08 ~ | 라피치 | 실시간 음성 AI 게이트웨이 (C++) |
| 2023.06 ~ 2024.01 | 두다지 | 데이터 수집 자동화 (Python) |
| 2020.10 ~ 2022.04 | 아이엠오 | 하루 200만 건 규모 메시징 시스템 (Java) |

<details>
<summary><b>📦 Previous Projects</b></summary>

### [Whagile](https://github.com/hstar0124/whagile) · 2022.06 ~ 2022.07

React / Node.js / Express 기반 협업 웹 애플리케이션. JWT 인증, MySQL 스키마 설계, Docker Compose, AWS EC2 배포

### [GroupWhale](https://github.com/hstar0124/group-whale) · 2020.04 ~ 2020.05

Spring 기반 그룹웨어. Spring Security + BCrypt, Oracle / MyBatis

### [Second Rental](https://github.com/hstar0124/second-rental) · 2020.02 ~ 2020.03

Java Servlet / JSP 기반 중고 대여 서비스. WebSocket 1:1 실시간 채팅

</details>
