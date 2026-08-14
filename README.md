![header](https://capsule-render.vercel.app/api?type=Waving\&section=header\&height=300\&text=HStar0124\&fontAlignX=50\&fontAlignY=45\&color=gradient\&fontSize=100\&fontColor=ffffff\&desc=Backend%20%2F%20Server%20Developer)

## 👋 About Me

안녕하세요. **실시간성과 안정성을 중요하게 생각하는 백엔드 / 서버 개발자**입니다.

Java를 시작으로 Python을 거쳐 현재는 **C++ 기반의 실시간 음성 AI 게이트웨이(RTGW)** 를 개발하고 있습니다.

도메인은 메시징, 데이터 수집 자동화, AI 음성 처리로 변화해왔지만 주로 다음과 같은 문제를 해결해왔습니다.

* 대규모 트래픽 환경에서의 안정적인 서버 처리
* 외부 시스템의 지연 및 장애가 핵심 서비스로 전파되지 않는 구조 설계
* gRPC, WebSocket, TCP, REST 기반의 시스템 연동
* 비동기 처리와 Queue를 활용한 실시간 처리 경로 분리
* Redis 기반 세션 관리 및 Active-Active 환경 대응
* 운영 환경에서 발생하는 장애 분석과 리소스 문제 해결
* 레거시 시스템 리팩토링 및 테스트 코드 도입

현재는 일평균 약 **5만 Call / 10만 Session 규모의 실시간 음성 처리 시스템**을 개발하고 운영하며,
STT/TTS 엔진과 상담 시스템 사이의 실시간 트래픽을 안정적으로 중계하는 일을 하고 있습니다.

언어나 프레임워크보다 **문제에 적합한 기술을 선택하는 것**을 중요하게 생각하며,
장애를 사후 대응하는 것보다 **장애가 서비스 전체로 전파되지 않도록 구조적으로 설계하는 것**에 관심이 많습니다.

최근에는 Claude Code를 비롯한 AI 개발 도구를 코드 탐색, 반복 구현, 테스트 작성 및 리뷰 보조에 활용하며 개발 생산성을 높이고 있습니다.

---

## 🛠 Tech Stack

### Languages

<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>

### Backend & Communication

<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/gRPC-244C5A?style=flat-square&logo=google&logoColor=white"/>
<img src="https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white"/>
<img src="https://img.shields.io/badge/REST_API-009688?style=flat-square"/>
<img src="https://img.shields.io/badge/Protobuf-4285F4?style=flat-square&logo=google&logoColor=white"/>

### Data

<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white"/>

### Infrastructure & Tools

<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/>
<img src="https://img.shields.io/badge/GitLab-FC6D26?style=flat-square&logo=gitlab&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white"/>

---

## 💼 Experience

### 라피치 | Backend / Server Developer

**2024.08 ~ Present**

실시간 음성 AI 게이트웨이(RTGW)의 설계, 개발 및 운영을 담당하고 있습니다.

STT/TTS 엔진과 상담 시스템 사이에서 실시간 음성 트래픽을 중계하며
**C++, gRPC, WebSocket, TCP, REST API, Redis** 등을 활용하고 있습니다.

#### 주요 경험

* 일평균 약 **5만 Call / 10만 Session** 규모의 실시간 음성 트래픽 처리
* 3종의 서로 다른 STT 엔진을 하나의 RTGW에서 운영할 수 있도록 **Plugin 구조 설계**
* Redis 기반 중앙 Session 관리 및 **Active-Active 환경 대응**
* Redis 장애가 실시간 통화로 전파되지 않도록 **Fail-Open 정책 설계**
* 실시간 gRPC 처리 경로와 외부 REST 연동을 분리한 **비동기 처리 구조 설계**
* Queue 기반 전송 구조를 통한 이벤트 데이터 **순서 보장 및 장애 대응**
* 외부 API 요청 집중으로 발생하는 병목을 완화하기 위한 **Sharding 구조 적용**
* File Descriptor 누수 및 장시간 점유되는 gRPC Channel 등 운영 환경의 리소스 문제 분석 및 해결
* 운영 서버 설치, 배포, 모니터링 및 장애 대응

#### 주요 프로젝트

**한국전력 지능형 고객센터 | 2026.04 ~ 2026.08**

* STT 기반 실시간 상담 대화록 처리 시스템 구축
* 일평균 약 5만 Call / 10만 Session 규모 트래픽 처리
* 상담 종료 시 집중되는 TA REST API 요청에 Sharding 구조 적용
* 녹취, RTGW, TA 등 다중 시스템 간 로그 및 트래픽 흐름 기반 장애 분석
* 구축부터 운영 안정화까지 전 과정 수행

**LGU+ AICC 고도화 | 2025.05 ~ Present**

* Exaone, ixi, Selvas 등 3종 STT 엔진 통합
* gRPC 기반 RTGW를 Plugin 구조로 확장
* 신규 ixi STT Plugin 설계부터 운영 반영까지 담당
* Redis 기반 중앙 Session 관리 및 Active-Active 구조 지원
* Redis Fail-Open 정책 및 설정 파일 Hot Reload 구조 적용

**우리투자증권 | 2025.06 ~ 2025.07**

* 실시간 gRPC 처리 흐름과 외부 REST 전송 경로 분리
* 비동기 Queue 기반 데이터 전송 및 순서 보장
* 이벤트 기반 실시간 Calllog 저장 구조 설계
* 설정 파일 내 민감 정보 AES-256 암호화 적용

**KT AICC 고도화 | 2025.01 ~ 2025.02**

* Java 17 / Spring Boot 3 기반 전면 업그레이드
* Hibernate 6 Migration 및 Entity / Query 구조 개선
* Maven → Gradle Migration
* Application Memory 사용량 약 **15% 감소**
* Build Time 약 **30% 단축**

---

### 두다지 | Backend Developer

**2023.06 ~ 2024.01**

C++ 기반 자동 수집 애플리케이션을 Python으로 마이그레이션하고
수집 실패 원인 분석 및 시스템 구조 개선을 담당했습니다.

* C++ → Python Migration
* 반복 및 중복 코드 모듈화
* 테스트 코드 도입을 통한 실패 지점 가시화
* 관계형 데이터베이스 분석 및 재설계
* AWS Ubuntu 환경 개발 및 배포
* 기존 수집 실패 대상 중 약 **70%를 추가 수집 가능하도록 개선**
* 불필요한 소스 코드 **30% 이상 감소**

---

### 아이엠오 | Backend Developer

**2020.10 ~ 2022.04**

일평균 **200만 건 이상**이 발송되는 문자 및 알림톡 시스템을 개발하고 운영했습니다.

#### 메시징 시스템

* 대규모 메시지 발송 Application 개발 및 장애 대응
* Spike Traffic 발생 시 Application이 Down되는 문제 분석 및 해결
* DB Connection 반환 누락 등 Resource Leak 문제 해결
* 기업별 메시징 Application Customizing
* CentOS 기반 IDC 환경 운영 및 배포
* 테스트가 존재하지 않던 Legacy Codebase에 테스트 도입
* **Line Coverage 0% → 65%**

#### 카카오 알림톡 API

* Servlet 기반 API Server → Spring Boot Migration
* RDB 설계 및 관리
* 중복 코드 모듈화 및 리팩토링
* API URI 재설계를 통해 불필요한 Endpoint 약 **40% 제거**
* 카카오 알림톡 Spec 변경에 따른 유지보수 비용 감소

---

## 🚀 Side Projects

### HStar Project

**2024.04 ~ 2024.07**

🔗 https://github.com/hstar0124/hstar-project

C++ Socket Server와 C# ASP.NET Core API Server를 직접 설계하며
서버 간 통신과 비동기 네트워크 프로그래밍을 실험한 프로젝트입니다.

### Architecture

<img src="https://github.com/hstar0124/hstar-project/assets/57317290/cdd2701d-590f-49ac-83a5-f8d310cf3005" width="650"/>

### Socket Server

<img src="https://github.com/user-attachments/assets/7a8baf3f-605c-4cb0-ab09-27693a5fa7e2" width="770"/>

#### API Server

* 로그인 및 User CRUD API 구현
* Protobuf 기반 HTTP Body 직렬화 / 역직렬화
* JSON 대비 Packet Size 약 **2/3 감소**
* Password Hash + Salt 적용
* Read / Write Service 분리를 통한 복잡성 관리
* ASP.NET Core + Entity Framework Core 기반 API 구현

#### Socket Server

* C++ 기반 비동기 TCP Socket Server 구현
* Redis Session Key 기반 로그인 처리
* API Server와 Socket Server 간 Session 의존성 분리
* Swap Queue 구조를 활용한 Lock 최소화
* 접속자 수 제한을 위한 User Waiting Queue 구현
* Duplicate Login 감지 및 기존 Connection 종료
* DB 작업을 Queue에 적재하여 Multi-thread 처리
* Protobuf 기반 Packet 직렬화

---

<details>
<summary><b>📦 Previous Projects</b></summary>

### Whagile

**2022.06 ~ 2022.07**

🔗 https://github.com/hstar0124/whagile

* React / Node.js / Express 기반 Web Application
* JWT 기반 Authentication
* MySQL Schema 설계
* Docker / Docker Compose 기반 실행 환경 구성
* AWS EC2 배포

### GroupWhale

**2020.04 ~ 2020.05**

🔗 https://github.com/hstar0124/group-whale

* Spring 기반 Groupware Web Application
* 로그인 / 회원 / 조직도 / Feed 게시판 구현
* Spring Security + BCrypt
* Oracle / MyBatis 기반 DB 처리
* jQuery / Ajax 활용

### Second Rental

**2020.02 ~ 2020.03**

🔗 https://github.com/hstar0124/second-rental

* Java Servlet / JSP 기반 Web Application
* WebSocket 기반 1:1 실시간 채팅
* 상품 / 장바구니 / Wishlist 기능
* Oracle / MyBatis 기반 DB 처리

</details>

---

## 🎯 What I'm Interested In

* High Performance Server
* Real-time Processing
* Distributed Systems
* Fault Tolerance
* Asynchronous Architecture
* Network Programming
* AI Backend / AI Infrastructure
* STT / TTS / LLM Integration
* System Architecture & Refactoring
