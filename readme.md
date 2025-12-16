# 서영은 | Developer

[Email](mailto:0dmd@naver.com) · [GitHub](https://github.com/Seoyoungeun) · [Notion/Portfolio]([LINK])

---

## Profile
- CS 기반(자료구조/알고리즘/운영체제 등) 위에서 **설계 → 구현 → 검증** 흐름으로 개발합니다.
- 팀 프로젝트에서 “안 되는 이유”를 **재현/로그/근거**로 정리해 해결하고, **명세와 기준**으로 협업 효율을 올려왔습니다.
- 실시간 데이터가 중요한 서비스에서 **임베디드 → 서버 → 대시보드** 흐름을 설계하고 연동한 경험이 있습니다.

---

## Education
- **삼성 청년 SW 아카데미(SSAFY)** | 2025.02 ~ 2025.12  
- **경북대학교 컴퓨터학부(글로벌SW융합전공)** | 2018.03 ~ 2025.02  

## Experience
- **HL만도 인도 인턴십** | 2024.07 ~ 2024.08  

---

### Main
- **Java / Spring Boot**
  - REST API 설계/구현, 예외/검증 처리, 연동 이슈 트러블슈팅
- **MySQL**
  - DB 스키마 관리, 데이터 정합성 유지, 기능 구현에 맞춘 테이블/관계 관리
- **Git / Notion**
  - 협업을 위한 이슈/명세/작업관리, 브랜치 기반 개발/충돌 해결
- **Redis**
  - 프로젝트 단위 활용 경험(캐시/세션/토큰 등으로 확장 가능)
- **C/C++**

---

## Featured Projects

# 1) RoboFlow — AI 판별 기반 부품 분류 + 실시간 모니터링 대시보드
- **기간**: 2025.10 ~ 2025.11 | **인원**: 6명
- **프로젝트 요약**: 로봇/컨베이어벨트에서 부품을 확인하고, AI로 정상품 여부를 판단해 기준에 따라 분류하는 시스템
- **내 역할**: **대시보드 담당(설계/구현/연동)**  
  - **임베디드 → 서버 → 대시보드** 데이터 흐름 설계 및 연동
- **시연 영상**: https://www.youtube.com/watch?v=5s3s2IyodoI

### Tech
- **FE**: React, TailwindCSS  
- **BE**: Spring Boot, STOMP, WebSocket  
- **Streaming**: WebRTC(UDP)  
- **Embedded → Web 전송**: MQTT  

### 핵심 구현
- 생산 라인 상태를 **한 화면에서 즉시 파악**할 수 있도록 대시보드 UI/데이터 구조 설계
- **새로고침 없이 즉시 반영**되는 실시간 업데이트 흐름 구성(STOMP/WebSocket)
- 지연이 큰 방식 대신 **UDP 기반 WebRTC 스트리밍**으로 전환하여 모니터링 품질 개선

<details>
<summary><b>문제 해결 과정 (Problem → Cause → Fix → Result)</b></summary>

- **Problem 1**: 화면이 새로고침 없이 즉시 반영되어야 하는데, 기존 방식만으로는 실시간성이 부족
  - **Fix**: STOMP/WebSocket을 처음 도입하여 이벤트 기반으로 상태/KPI를 push
  - **Result**: 사용자 새로고침 없이 값이 즉시 반영되는 대시보드 구현

- **Problem 2**: TCP 방식 카메라 연결이 느려 실시간 모니터링에 부적합
  - **Fix**: UDP 기반으로 전환하고 WebRTC 적용(라즈베리파이 카메라 송출)
  - **Result**: 지연이 줄어든 스트리밍 구조 확보(초기 시행착오 해결)

- **트러블슈팅 경험**: 실시간 통신에서 **네트워크/포트/CORS** 이슈를 직접 겪고 해결하며 운영 관점 역량 강화
</details>

### 배운 점
- 실시간 서비스는 기능 구현뿐 아니라 네트워크 경로/포트/브라우저 정책(CORS)까지 포함한 설계가 핵심
- “데이터 흐름”을 먼저 정리하면 UI/서버 구현이 흔들리지 않음

---

# 2) FocusMate — 협업 기반 서비스(백엔드 API/DB 담당)
- **기간**: 2025.08 ~ 2025.09 | **인원**: 5명
- **내 역할**: **BE API 개발, DB 관리**
- **Repo**: [링크 추가]

### 내가 맡은 핵심
- 기능 구현을 위한 **백엔드 API 설계/개발**
- 서비스 데이터 흐름을 고려한 **DB 스키마/데이터 관리**
- **SMTP 활용 기능 적용**(메일 전송 흐름 구현)

### 배운 점
- 협업에서 “개발 속도”는 코드보다 명세(합의된 기준)가 좌우한다는 점을 체감
- API 연동 이슈를 줄이기 위해 API 명세서의 중요성을 경험
- SMTP 적용을 통해 외부 시스템 연동의 기본(환경설정/예외/보안)을 학습

## 3) AUTOSAR LED Blink — AUTOSAR vs Non-AUTOSAR 비교 구현 (S32K146)

기간: 2024.07 ~ 2024.08
Repo: [https://github.com/Seoyoungeun/autosar/tree/main](https://github.com/Seoyoungeun/autosar/tree/main)

프로젝트 요약: 차량 SW 환경에서 **Non-AUTOSAR(레지스터 직접 제어)** 방식과 **AUTOSAR(표준화된 설정/생성 기반)** 방식으로 LED Blinking을 구현·비교하며, “설정 → 생성 → 구현 → 검증” 개발 흐름을 학습
(목표: 자동차 회사마다 다른 개발 규격을 **AUTOSAR 표준으로 통일**하는 이유를 이해하고 적용)

내 역할: 제공받은 샘플 코드를 기반으로 **동작 요구사항에 맞게 코드/설정을 수정**하고, Non-AUTOSAR ↔ AUTOSAR 구현 차이를 비교 정리

* 요구사항: **스위치를 한 번 누르면(토글) LED가 5초 간격으로 점멸 시작**, 다시 누르면 점멸 정지

### Tech

* HW: NXP S32K146
* Non-AUTOSAR: C(레지스터 직접 제어 기반 샘플 코드 수정)
* AUTOSAR: **EB tresos**(Port/Dio 설정 → Generate) + 샘플 코드 수정
* Build/Run: make 기반 빌드 및 보드 실행/검증
  
### 핵심 구현

* **Non-AUTOSAR**

  * 스위치 입력을 디바운싱/상태 전환 기준으로 처리하여 **토글 상태(state)** 를 유지
  * 토글 ON 상태에서 **5초 주기 점멸 로직**이 동작하도록 샘플 코드 수정(주기적 LED 토글)

* **AUTOSAR**

  * EB tresos에서 Port/Dio 설정으로 LED/Switch 핀을 매핑하고 Generate 수행
  * 생성된 구조 위에서 스위치 입력에 따라 **토글 상태(state) 전환** 및 5초 주기 점멸 로직이 동작하도록 샘플 코드 수정
  * “표준 설정/생성 + 애플리케이션 로직”으로 역할이 분리되는 구조를 경험

<details>
<summary><b>문제 해결 과정 (Problem → Cause → Fix → Result)</b></summary>
**Problem 1:** AUTOSAR는 코드만 수정해서는 동작 구조를 이해하기 어렵고, 설정/생성 단계 누락 시 정상 동작하지 않음

* **Cause:** AUTOSAR는 “코드 작성” 이전에 **설정(Configure) → 생성(Generate)** 단계가 필수이며, 이 산출물이 런타임 동작을 좌우
* **Fix:** EB tresos에서 핀/모듈 설정을 먼저 고정 → Generate → 샘플 코드에서 토글/주기 로직 반영 → 실행으로 흐름을 단계화
* **Result:** AUTOSAR의 핵심이 “코드”가 아니라 **표준 설정/생성 파이프라인**임을 체감하고 재현 가능한 개발 절차를 확보

**Problem 2:** Non-AUTOSAR는 구현이 빠르지만 회사/프로젝트마다 코드 구조와 규격이 달라 재사용/협업 비용이 증가할 수 있음

* **Fix:** AUTOSAR 표준 구조를 기준으로 동일 요구사항(토글 + 5초 점멸)을 구현·비교하며, **규격 통일의 필요성**을 요구사항 구현과 함께 정리
* **Result:** 자동차 SW에서 AUTOSAR는 기술 선택을 넘어 **조직/회사 간 표준화로 유지보수성을 확보**하는 전략임을 개발 관점에서 이해
</details>

### 배운 점

* AUTOSAR는 코드 수정만이 아니라 **설정(Configure) → 생성(Generate) → 로직 구현 → 검증** 흐름이 핵심
* 임베디드 품질은 “동작”이 아니라, 실패 원인을 단계별로 좁히는 **재현 가능한 검증 절차**에서 결정됨
* 표준화(AUTOSAR)는 회사마다 다른 규격을 맞춰 **협업/재사용/유지보수 비용을 줄이기 위한 기반**임을 체감


# 4) KNU Mobile App — 경북대 시설 대여/관리(모바일)

* **기간**: 2023.09 ~ 2023.11 | **인원**: 5명
* **Repo**: [https://github.com/KNUMobileTeamProject/KNUSportsCenter](https://github.com/KNUMobileTeamProject/KNUSportsCenter)
* **역할/기여도**: **Firebase Authentication 기반 인증(회원가입/로그인) + UID 기반 사용자 데이터 분리 설계/연동**, 일부 화면 흐름 구성
* **기술**: Kotlin(Android), Firebase Authentication, Firebase Realtime Database, RecyclerView, Material Date Picker, Google Maps SDK

#### 개요

* 경북대학교 체육진흥센터(시설/강좌) 정보를 조회하고, 사용자가 **강좌 신청 / 시설 이용 신청**을 진행한 뒤 **신청 내역을 확인**할 수 있는 모바일 앱입니다.
* “필요한 정보를 빠르게 확인”할 수 있도록 사용자 흐름 중심으로 화면/기능을 구성했습니다.

---

#### 내가 맡은 핵심

* **Firebase Authentication** 기반 회원가입/로그인 연동 구현(입력 검증 포함)
* 인증된 사용자 식별자인 **UID를 기준으로 데이터가 분리 저장**되도록 구조 설계(`usrs/{uid}/...`)
* 사용자별 **신청 내역(applied_courses / applied_facilities)**이 섞이지 않도록 초기 노드 생성 및 연동
* 로그인 사용자만 접근 가능하도록 일부 **화면 진입/전환 흐름** 구성

---

#### 핵심 구현

* 강좌 신청: 사용자 신청 리스트 저장 + **중복 신청 방지** + 신청 인원(StudentCount) 갱신
* 시설 이용 신청: **Material Date Picker** 기반 날짜 선택(과거 날짜 제한) + 사용자 신청 리스트 저장 + **중복 신청 방지**
* 신청 내역 확인: **RecyclerView** 기반 목록 표시(강좌/시설 신청 내역)
* 지도: **Google Maps SDK**로 센터 위치 표시

<details>
<summary><b>문제 해결 과정 (Problem → Cause → Fix → Result)</b></summary>
* **Problem 1**: 여러 사용자가 사용할 때 신청 내역이 섞일 위험

  * **Fix**: Auth의 `uid`를 기준 키로 삼아 `usrs/{uid}/...` 구조로 데이터 분리
  * **Result**: 사용자별 신청 내역이 명확히 분리되어 개인화/기록/권한 확장 기반 확보

* **Problem 2**: 시설 예약에서 잘못된 입력(과거 날짜 등)으로 데이터 품질이 깨질 수 있음

  * **Fix**: Material Date Picker로 날짜 입력을 통제하고 과거 날짜 선택을 제한
  * **Result**: 입력 오류 감소 및 신청 데이터 일관성 강화
</details>

#### 배운 점

* 인증(UID)을 기준으로 데이터 구조를 먼저 잡으면, 이후 **개인화/기록/권한 관리** 기능으로 확장하기 쉬움
* 모바일에서는 기능 구현뿐 아니라 **입력 통제/예외 흐름 설계**가 UX 품질을 좌우함


---
