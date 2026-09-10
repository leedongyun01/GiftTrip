# ✈️ GiftTrip (기프트립)

> **"당신만을 위한 맞춤형 해외 여행 일정 & AI 코스 추천 서비스"**  
> **GiftTrip**은 사용자 취향, 구성원, 예산 및 여행 스타일에 맞춰 **최적의 10개국 여행 코스**를 추천하고, **PDF 일정표 공유 & 체크리스트**까지 일괄 제공하는 **맞춤형 여행 플랫폼**입니다.
>
> [논문](https://github.com/leedongyun01/GiftTrip/blob/main/Thesis_GiftTrip.hwp)

<br/>

![Tech Stack](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react&logoColor=black)
![Backend](https://img.shields.io/badge/Backend-Node.js-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Framework-Express-000000?logo=express&logoColor=white)
![AI](https://img.shields.io/badge/AI-OpenAI_GPT-412991?logo=openai&logoColor=white)
![Build](https://img.shields.io/badge/Tool-Vite-646CFF?logo=vite&logoColor=white)

---

## 📌 목차 (Table of Contents)

1. [프로젝트 소개](#-프로젝트-소개)
2. [주요 기능 (Key Features)](#-주요-기능-key-features)
3. [기술 스택 (Tech Stack)](#-기술-스택-tech-stack)
4. [서비스 흐름도 (User Flow)](#-서비스-흐름도-user-flow)
5. [시작 가이드 (Getting Started)](#-시작-가이드-getting-started)
6. [환경 변수 설정 (.env)](#-환경-변수-설정-env)

---

## 💡 프로젝트 소개

**GiftTrip**은 복잡한 해외 여행 계획 수립 과정을 단축해 주는 **스마트 여행 플래너**입니다.

* 📅 **개발 기간**: 2025.09.03 ~ 2025.11.12
* 👥 **참가 인원**: 3명
* 🇯🇵 🇨🇳 🇹🇼 🇺🇸 🇨🇦 🇫🇷 🇬🇧 🇩🇪 🇮🇹 🇪🇸 등 **주요 10개국** 여행 데이터를 기반으로 동작합니다.
* 동행자, 예산, 일정, 여행 스타일에 따른 **OpenAI LLM AI 코스 추천**을 지원합니다.
* 국가별 비자 정보 및 준비물이 자동으로 정리된 **여행 체크리스트 모달 & PDF 다운로드**를 제공합니다.
* 생성된 최종 일정표는 **PDF 첨부 메일 전송** 및 **공유 가능한 링크** 형태로 간편히 공유할 수 있습니다.

---

## ✨ 주요 기능 (Key Features)

### 1. 🌏 10개국 글로벌 여행지 선택 (Page 00 ~ 01)
* 일본, 중국, 대만, 미국, 캐나다, 프랑스, 영국, 독일, 이탈리아, 스페인 지원
* 여행 기간, 예산 범위, 동행인 구성(솔로, 커플, 가족, 친구 등), 선호 여행 스타일 선택

### 2. 🤖 AI (OpenAI LLM) 기반 코스 & 리뷰 생성 Engine (Page 02 ~ 03)
* 선택된 여행 조건에 맞춰 실시간 AI 맞춤 도시 및 3/5/7일 일정 코스 제안
* `ReviewEngine.cjs`: OpenAI API 연동 및 TTL 기반 스마트 Caching으로 빠른 응답속도와 비용 최적화 제공

### 3. 🗺️ 카테고리별 일정 커스텀 설계 (Page 04 ~ 05)
* **Activity / Food / Stay / Spots** 4가지 카테고리별 명소 탐색 및 일정 추가
* 일정 내 이동 동선 확인, 스토어 관심등록(Bookmark), 리뷰 및 상세 정보 확인

### 4. 📋 국가별 맞춤 체크리스트 & PDF (Page 06)
* 공통 준비물 + 선택 국가별 필수 서류/비자 및 팁 자동 렌더링
* 작성된 준비물 리스트를 **PDF 파일 다운로드** 가능

### 5. ✉️ 일정표 메일 발송 & 링크 공유 (Page 07)
* 완성된 최종 일정을 PDF 형태로 **Nodemailer SMTP**를 이용해 사용자 이메일로 전송
* 고유 공유 링크 생성 (`page7Share.cjs`)을 통한 편리한 팀원 공유

### 6. 🛠️ 관리자(Admin) 대시보드 & 서버 엔진
* `AdminPage.cjs`, `AdminLogger.cjs`: 서버 API 요청 로깅, 관리자 페이지 및 분석
* `UpLoadingImages.cjs`: 명소 및 업로드 이미지 동적 바인딩 및 정적 자원 관리

---

## 🛠 기술 스택 (Tech Stack)

### Frontend
* **Core**: React (JSX), JavaScript (ES6+)
* **Styling**: Modern CSS3, Flexbox/Grid, Responsive Web Design
* **Build Tool**: Vite / React Scripts
* **Libraries**: React Router DOM, html2pdf.js / jsPDF

### Backend
* **Runtime**: Node.js
* **Framework**: Express.js (`.cjs` CommonJS Module Router Architecture)
* **AI Integration**: OpenAI API (`openai` npm package)
* **Mail & File Processing**: Nodemailer, Multer (Memory Storage)
* **Environment**: `dotenv`, CORS

---

## 🔄 서비스 흐름도 (User Flow)

```
[Page 00: 국가 선택] ➔ [Page 01: 조건 설정(예산/동행/일정)] ➔ [Page 02~03: AI 코스 추천 (LLM)]
                                                                     │
[Page 07: 메일 발송/공유] ⬅ [Page 06: 체크리스트/PDF] ⬅ [Page 04~05: 카테고리별 상세 구성]
```

---

## 🚀 시작 가이드 (Getting Started)

### 1. Repository 클론
```bash
git clone https://github.com/leedongyun01/GiftTrip.git
cd GiftTrip
```

### 2. 패키지 설치
```bash
npm install
```

### 3. 백엔드 서버 실행
```bash
node nodejs/server.cjs
```
> 서버가 실행되면 `http://localhost:3000` 에서 API 및 정적 파일 서버가 동작합니다.

### 4. 프론트엔드 실행 (개발 모드)
```bash
npm run dev
```

---

## 🔑 환경 변수 설정 (.env)

`nodejs/` 디렉토리 또는 루트 디렉토리에 `.env` 파일을 생성하고 아래 항목을 설정합니다:

```env
# OpenAI API Key (AI 추천 및 리뷰 엔진에 활용)
OPENAI_API_KEY=your_openai_api_key_here

# SMTP 메일 발송 설정 (Page 07 PDF 메일링)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password

# 캐시 설정 (선택 사항)
REVIEW_CACHE_TTL_MS=900000
REVIEW_CACHE_MAX=500
```

---

<p center>Copyright © 2026 GiftTrip Team. All rights reserved.</p>
