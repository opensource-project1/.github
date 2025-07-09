# 사용자 가이드 (User Guide)

## 서비스 소개

**방해금지 모드 웹 서비스**는 집중 시간을 방해하는 웹사이트를 차단하고, 할 일을 관리하며, 집중 세션을 기록할 수 있는 서비스입니다.
이 서비스는 **집중력 향상**, **목표 달성**, **시간 관리**를 돕습니다.

---

## 주요 기능

### 사이트 차단

* 차단할 사이트 URL을 등록하면, 선택한 시간 동안 해당 사이트 접속이 차단됩니다.
* URL은 여러 개 등록할 수 있으며, 삭제 및 수정 가능합니다.
* 자주 차단하는 사이트는 자동으로 저장되어 다음에 쉽게 선택할 수 있습니다.

### 집중 세션

* 원하는 시간을 설정해 집중 세션을 시작할 수 있습니다.
* 집중 중에는 등록된 사이트가 차단됩니다.
* 긴급 상황 시 "긴급 종료 요청" 기능으로 세션을 조기 종료할 수 있습니다.

### 할 일 플래너

* 오늘의 할 일을 작성하고 완료 여부를 체크할 수 있습니다.
* 완료한 항목과 남은 항목을 한눈에 볼 수 있습니다.

### 마이페이지

* 오늘의 총 집중 시간
* 완료한 할 일 개수 / 전체 할 일 개수
* 차단된 사이트 목록
* 세션 기록

---

## 시작 방법

1. **회원가입/로그인** 후 사용 가능합니다.
2. **차단할 사이트 URL**을 등록하세요.
3. **집중 세션**을 시작하세요.
4. **할 일 플래너**에 오늘의 할 일을 작성하세요.
5. 필요하면 **긴급 종료**를 요청할 수 있습니다.

---

## 사용 환경

* 웹 브라우저
* PC, 노트북

---

# 개발자 가이드 (Developer Guide)

## 기술 스택

* **Backend**: NestJS, TypeScript
* **DB**: MySQL (Prisma ORM)
* **Frontend**: React, JavaScript
* **Deployment**: AWS EC2, RDS, github Actions

---

## 주요 API 명세 (간단 요약)

| 리소스              | 메서드/엔드포인트                          | 설명          |
| ---------------- | ---------------------------------- | ----------- |
| Auth             | POST /api/auth/google/login        | 구글 로그인       |
| Block            | POST /api/block                    | 차단 URL 등록   |
|                  | GET /api/block                     | 차단 URL 조회   |
|                  | GET /api/block/{id}                | 차단 URL 삭제  |
| Focus            | POST /api/focus                    | 집중 세션(타이머) 시작    |
|                  | GET /api/focus?date=YYYY-MM-DD     | 오늘 세션 조회      |
| EmergencyRequest | GET /api/emergency                 | 긴급 요청 목록 조회    |
|                  | POST /api/emergency                | 긴급 종료 요청    |
| Todo             | POST /api/todo                     | 오늘의 플래너 작성      |
|                  | GET /api/todo?date=YYYY-MM-DD      | 오늘의 플래너 목록 조회      |
|                  | PATCH /api/todo/{id}               | 플래너 수정      |
|                  | DELETE /api/todo/{id}              | 플래너 항목 삭제      |
| MyPage           | GET /api/my-page                   | 통계/마이페이지 조회 |

> **자세한 명세는 `http://ec2-3-35-37-148.ap-northeast-2.compute.amazonaws.com:3000/api-docs` 참조**

---

## DB 테이블 구조

* User, Block, Focus, Todo, EmergencyRequest, UserSetting, FocusLog

---

## 페이지 구조
<pre>
/pages
  ├── login.js
  ├── main.js
  ├── mypage.js
  ├── record.js
  ├── timer.js </pre>

> **css는 `assets/styles` 폴더에서, 이미지들은 `public` 폴더에 넣고 사용**

---

## 사용한 오픈소스

- NestJS: Node.js 기반의 백엔드 프레임워크

- Prisma: DB 접근을 위한 ORM 라이브러리

- TypeScript: JavaScript의 상위 집합 언어, 정적 타입 지원

- PM2: Node.js 애플리케이션의 프로세스 매니저

- GitHub Actions: 워크플로우 기반의 CI/CD 자동화 도구

- JWT (jsonwebtoken): 인증/인가를 위한 토큰 처리 라이브러리

- ESLint, Prettier: 코드 스타일 및 품질 관리 도구

---

## 배포 환경

### 백엔드
- PM2를 사용한 프로세스 관리
- Prisma ORM 사용
- AWS EC2 서버 배포
- GitHub Actions를 통한 CI/CD 자동 배포

### 프론트엔드
- 로컬 환경에서만 사용

---

# 기여 가이드 (Contribution Guide)

- 올가닉 Organization 리포지토리에 main, dev, 기능별 브랜치 생성.
- 개발 완료 후 PR 요청 → 코드 리뷰 진행.
- 리뷰 승인 후 Merge.
- 커밋 컨벤션 준수


