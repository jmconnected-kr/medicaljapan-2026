# Handoff: Medical Japan 2026 연계 수출상담회 홈페이지

## Overview

**Medical Japan 2026 Tokyo 연계 수출상담회**의 공식 홈페이지 · 참가기업 브로셔 · 바이어 가이드 (KR/JP) 세트입니다.

- **주최**: RX Japan GK (전시회) / 부산테크노파크 (한국관 운영)
- **일정**: 2026. 10. 7 (수) ~ 10. 9 (금) · 10:00 – 17:00 (JST)
- **장소**: Makuhari Messe, Chiba, Japan · Korea Pavilion
- **참가기업**: 지에이치이노텍 · (주)오투랩 · (주)케어엔코 · 아이온 · 다일
- **상담**: 기업당 5건 내외 · 총 20건 내외

## About the Design Files

본 번들에 포함된 파일들은 **HTML로 제작된 디자인 시안(prototypes)**으로, 최종적인 룩앤필과 인터랙션을 보여줍니다. **프로덕션 코드로 그대로 복사할 목적이 아닌, 대상 코드베이스의 기존 환경 (React/Vue/Next.js 등)에서 재현하기 위한 레퍼런스**로 사용해야 합니다.

다만 아래 파일들은 **자체 완결형 HTML**로 작성되어 있어, 정적 웹 호스팅 (GitHub Pages · Vercel · Netlify · Cloudflare Pages 등)으로 즉시 배포도 가능합니다:

- 외부 의존성: Google Fonts (Inter, Pretendard, Noto Sans JP), JSDelivr CDN
- 자바스크립트: 순수 JS (프레임워크 불필요), Cloudflare email obfuscation
- 이미지: `assets/` 폴더에 로컬 포함
- 인쇄 (PDF 저장): `@page` CSS + `?print=1` 쿼리 지원

## Fidelity

**High-fidelity (Hi-Fi)** — 최종 색상, 타이포그래피, 스페이싱, 인터랙션이 모두 확정된 픽셀-완성도의 시안입니다. 개발자는 코드베이스의 기존 컴포넌트 라이브러리를 사용해 **픽셀-퍼펙트로 재현**해야 합니다.

## Deployment Options

### 옵션 1 · 정적 웹 호스팅 (가장 빠름 · 권장)

번들 폴더 전체를 그대로 정적 호스팅에 업로드하면 즉시 배포됩니다.

**추천 서비스**:
- **GitHub Pages** — GitHub 리포지토리 무료 배포 · 커스텀 도메인 지원
- **Vercel** — `vercel deploy` 명령 한 번으로 배포 · Preview URL 자동 생성
- **Netlify** — 드래그앤드롭 배포 지원 · Form Handling 내장 (사전등록 폼에 유용)
- **Cloudflare Pages** — 무료 · 글로벌 CDN

**진입점**: `Medical Japan 2026.html` (index.html로 이름 변경 권장)

### 옵션 2 · Genspark Code 이관

Genspark Code로 이관하면:
- 서버사이드 로직 추가 (사전등록 폼 → DB 저장, 이메일 발송)
- 관리자 페이지 (참가기업 리스트 CMS)
- 다국어 (i18n) 라우팅
- Analytics 통합
- 커스텀 도메인 · SSL

### 옵션 3 · 프로덕션 코드베이스 통합

React/Next.js 등 기존 코드베이스에 통합하려면 아래 "Screens / Views" 섹션을 참조.

## Screens / Views

### 1. `Medical Japan 2026.html` — 메인 랜딩페이지

**구조 (위→아래)**:

1. **Top Bar (다크 네이비)**
   - 좌: 일자 · 장소 · 주최 정보
   - 우: 📗 Buyer Guide 링크 · KR/JP 언어 스위치

2. **Header (Sticky · 반투명 네이비 → 흰색 전환)**
   - 로고 (그라디언트 사각 + 심박 아이콘)
   - 네비: 행사 개요 / 프로그램 / 상담회장 / 참가기업 / 바이어 가이드 / 참가 신청
   - 스크롤 60px 이상 시 흰 배경으로 전환

3. **Hero (다크 네이비 + 대각선 다이아몬드 오버레이)**
   - 좌측: "MEDICAL JAPAN 2026 TOKYO" 대형 헤드라인 (골드) + 골드 pill + 메타 3행 + CTA 3개
   - 우측: **6장 이미지 캐러셀** (5초 자동 재생, 좌우 화살표, 도트 인디케이터, 스와이프 지원)
     - 슬라이드: 마쿠하리 항공샷 → 외관 → Korea Pavilion → 5개사 실사

4. **행사 개요 (Show Overview) — 흰 배경**
   - 좌·우 2단 카드
     - 좌: Official Event · MEDICAL JAPAN 2026 TOKYO (다크 리본, 7행 정보)
     - 우: Our Event · 연계 수출상담회 (보라 리본, 7행 정보)
   - 7개 전문전시회 그리드 (4x2)
   - 일자별 운영 계획 표 (Day 1/2/3)
   - 공식 안내 자료 링크 박스 (외부 12개)
   - 통계 카드 4개 (650+ / 17,000+ / 5개사 / 20건)

5. **주요 프로그램 (Main Program)**
   - 그라디언트 헤더 스트라이프 (마젠타→보라) + 4개 프로그램 카드
     - 1:1 수출상담회 / Elderly Care & Welfare Conference / Digital Health Sessions / Rehab & Physical Therapy Symposium / Health Screening Conference / Networking Reception (모두 Medical Japan 공식 병행 프로그램)

6. **품목 분야 (Exhibit Items)**
   - 8개 카테고리 카드 그리드 (아이콘 + 국문 + 영문 + 설명)

7. **상담회장 배치도 (Floor Plan)**
   - SVG 부스 맵 (Korea IVD Cluster 특별관 강조)
   - 범례 + 시안 안내 노트

8. **참가기업 · 바이어 리스트 (Exhibitor & Buyer)**
   - 상단 배너: 통합 브로셔 CTA (진보라 그라디언트)
   - 탭 전환 (Exhibitors 5 / Buyers 120)
   - **5개 참가기업 카드** (실사 제품 이미지 + 부스 배지 + 사양 메타 + 상세 설명 + 인증/수출 태그)
   - 바이어 하이라이트 3개 카드 + 14개 바이어 테이블

9. **사전등록 폼**
   - 좌: 혜택 안내 4개
   - 우: 신청 폼 (회사명 KR/EN · 담당자 · 부서 · 이메일 · 연락처 · 관심품목 8개 칩 · 문의 · 개인정보 동의)

10. **Footer (다크 네이비)**
    - 4단 그리드: 브랜드 / 바로가기 / 안내서 다운로드 / 문의처
    - 파트너 pill 3단 (전시회 주최 / 한국관 운영 / 후원)
    - 저작권 · 이용약관 · 개인정보처리방침

### 2. `buyer-guide.html` — 바이어 가이드 (한국어) · A4 12페이지

1. 표지 (네이비 + 골드 pill)
2. 목차 (10개 섹션 그리드 + 사전등록 QR)
3. 환영사 + KPI 4개 + 방문 특전 5가지
4. 행사 개요 (Official × Ours 2단 + 7개 전문전시회)
5. 5개 참가기업 스냅샷 (실사 이미지 + 부스 + 태그)
6. 3일 상담 일정 (Day 1/2/3 타임라인)
7. 전시장 · Korea Pavilion 위치 (Official × Korea 2단 카드)
8. 가는 길 (도쿄역/나리타/하네다 3개 access 카드 + 실제 노선도 지도)
9. 현장 편의시설 (8개 아이콘 카드 + Business Lounge 전용 서비스)
10. 1:1 미팅 프로세스 (5단계 타임라인 + QR)
11. 통역 · VIP 지원 (Language × VIP 2단 + 지원팀 3인)
12. 호텔 · 체크리스트 · 문의처

### 3. `buyer-guide-jp.html` — バイヤーガイド (日本語) · 동일 구조

- Noto Sans JP 폰트 사용
- `lang="ja"` 속성
- 지명 일본어 표기 (幕張メッセ · 海浜幕張駅 · 東京駅 · 成田/羽田空港 · 釜山テクノパーク)
- 상단 툴바에 KR/JP 언어 스위치

### 4. `brochures/Medical Japan 2026 Company Brochure.html` — 참가기업 통합 브로셔 · A4 6페이지

1. 표지 (네이비 + Medical Japan 대형 타이포 + 5개사 그리드)
2-6. 각 기업 1페이지 (실사 이미지 + 제품 · 스펙 · 인증 · 컨택트)

### 5. `brochures/{ghinnotech, o2lab, carenco, aion, dail}.html` — 개별 기업 브로셔 (각 6페이지)

각 기업당 표지 · 개요 · 대표제품 · 사양·인증 · 시장·실적 · 문의 6페이지 구성.

## Interactions & Behavior

### Hero Carousel
- **자동 재생**: 5초 간격
- **네비**: 좌/우 화살표, 도트 인디케이터 (활성 상태: 24px 골드 pill)
- **마우스 호버 시 일시정지**
- **터치 스와이프**: 50px 이상 이동 시 페이지 전환
- **카운터**: `01 / 06` 형식

### Header Scroll
- 스크롤 60px 이상: `is-scrolled` 클래스 추가 → 배경 흰색 전환

### Tab Switcher (참가기업/바이어)
- `data-tab` 속성으로 매칭
- `aria-selected` 접근성 처리

### 브로셔 & 바이어 가이드 인쇄
- `?print=1` 쿼리로 접속 시 자동 인쇄 대화상자 오픈
- `@page { size: A4; margin: 0 }` + `page-break-inside: avoid`
- 배경 그래픽 인쇄 유지: `-webkit-print-color-adjust: exact`

### 폼 검증
- HTML5 `required` 속성 (회사명 · 담당자 · 이메일 · 연락처 · 개인정보 동의)
- `<input type=email>` · `<input type=tel>` 브라우저 기본 검증
- 제출 시 alert (실제 서비스는 백엔드 연동 필요)

## State Management (배포 시 추가 필요)

현재는 정적 페이지. 실제 서비스 배포 시 필요한 상태/데이터:

1. **사전등록 폼 → DB**: 회사명, 담당자명, 이메일, 연락처, 관심품목, 개인정보 동의 시각
2. **이메일 알림**: 신청 후 사무국 회신 자동화
3. **참가기업 CMS**: 5개사 데이터를 하드코딩 없이 관리자 페이지에서 수정 가능하도록
4. **바이어 매칭 시스템**: 바이어 등록 → KOTRA/부산테크노파크 심사 → 매칭 → 확정 이메일

## Design Tokens

### Colors

```css
/* Navy (Official Medical Japan style) */
--navy-900: #0A153F;
--navy-800: #0F1E5A;
--navy-700: #1A2C7A;

/* Accent (Gold) */
--gold: #F5A623;
--gold-2: #E88E00;
--cyan: #38B6E0;

/* Purple (Korea Pavilion / brand) */
--purple-900: #3E1E80;
--purple-800: #4B27A4;
--purple-700: #5B34C4;
--purple-600: #6C46DB;
--purple-500: #8562E6;
--purple-400: #A98EEF;

/* Lilac (subtle backgrounds) */
--lilac-100: #EDE7FB;
--lilac-50:  #F6F2FE;
--lilac-25:  #FBF9FF;

/* Ink (text) */
--ink-900: #141327;
--ink-700: #3B3852;
--ink-500: #6E6B84;
--ink-400: #8B889F;

/* Neutrals */
--line: #E7E3F1;
--line-strong: #D9D3EA;
--gray-50: #F5F5F7;

/* Program stripe accent */
--magenta: #D93A88;

/* Green (export badges) */
--green-tint: #E8F5EE;
--green-ink: #1F8A5B;
```

### Typography

```css
--font-sans: "Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
--font-en:   "Inter", var(--font-sans);
--font-jp:   "Noto Sans JP", "Hiragino Sans", "Yu Gothic UI", var(--font-sans);
```

- Body: 16px / 1.55 / letter-spacing -0.01em
- H1 hero: clamp(48px, 6.5vw, 84px), font-weight 800, letter-spacing -0.035em
- H2 section: clamp(30px, 3.4vw, 44px)
- Section head: 22px bold + 15px English (medium)
- Brochure body: 10pt (12pt = 이 페이지 인쇄용)

### Spacing

```
- Section padding: 96–120px vertical
- Container: max-width 1180px, padding 20–40px (clamp)
- Card padding: 22–40px
- Grid gap: 12–24px (density-dependent)
```

### Border Radius

```
--radius-sm:  6px
--radius-md: 10px
--radius-lg: 16px
--radius-xl: 24px
```

### Shadows

```css
--shadow-sm: 0 1px 2px rgba(20,19,39,.05);
--shadow-md: 0 8px 24px rgba(76,53,180,.08);
--shadow-lg: 0 24px 60px rgba(76,53,180,.14);
```

## Assets

`assets/` 폴더에 포함된 이미지 (실사 · 라이선스 검증됨):

| 파일 | 설명 | 출처 |
|---|---|---|
| `mj-aerial.jpg` | 마쿠하리 메세 항공샷 | m-messe.co.jp 공식 |
| `mj-panorama.jpg` | 마쿠하리 메세 외관 | Alamy stock |
| `mj-showfloor.jpg` | 전시장 내부 | 참고용 |
| `korea-pavilion.jpg` | Korea Pavilion 부스 예시 | TrueBlue Exhibits |
| `access-map.jpg` | 도쿄→마쿠하리 노선도 | Inter BEE 공식 |
| `co-ghinnotech.jpg` | Bigbreathe IMT/PEP 제품 | Amazon 판매 이미지 |
| `co-o2lab.jpg` | Dynamic Balance 장비 | 오투랩 언론 자료 |
| `co-carenco.jpg` | Fisica 앱 UI | carenco.kr 공식 |
| `co-aion.jpg` | BINATTI 지팡이 | stickpang.com 공식 |
| `co-dail-2.jpg` | 초코핏 더비 슈즈 | manolouis.com |

**⚠️ 상업 배포 시 유의사항**: 이미지 라이선스는 검증되었으나 실제 상업 배포 전 각 저작권자에게 최종 사용 승인을 받거나, 참가기업으로부터 자체 촬영 이미지를 확보하는 것을 권장합니다.

## Files (전체 파일 목록)

### 진입점
- `Medical Japan 2026.html` — 메인 랜딩페이지 (index.html로 이름 변경 권장)

### 브로셔
- `brochures/Medical Japan 2026 Company Brochure.html` — 5개사 통합 (A4 6P)
- `brochures/ghinnotech.html` — 지에이치이노텍 개별
- `brochures/o2lab.html` — 오투랩 개별
- `brochures/carenco.html` — 케어엔코 개별
- `brochures/aion.html` — 아이온 개별
- `brochures/dail.html` — 다일 개별
- `brochures/brochure.css` — 개별 브로셔 공용 스타일

### 바이어 가이드
- `buyer-guide.html` — 한국어 (A4 12P)
- `buyer-guide-jp.html` — 日本語 (A4 12P)

### 자산
- `assets/*.jpg` — 실사 이미지 10장

## Quick Deploy Guide

### GitHub Pages 배포 예시

1. `Medical Japan 2026.html` → `index.html`로 이름 변경 (공백 없이 URL 안전)
2. 이 폴더를 GitHub 리포지토리로 푸시
3. Settings → Pages → Source: Deploy from branch → `main` / `/root` → Save
4. 몇 분 후 `https://<username>.github.io/<repo>/` 로 접근 가능

### Vercel 배포 예시

```bash
npm i -g vercel
cd design_handoff_medical_japan_2026
vercel deploy --prod
```

### 커스텀 도메인 (예: medicaljapan-kr.org)

1. 도메인 구입 (가비아, 후이즈 등)
2. DNS A/CNAME 레코드 설정
3. GitHub Pages / Vercel / Netlify 각 서비스의 Custom Domain 설정에 등록
4. SSL 자동 발급 (Let's Encrypt)

## 배포 전 체크리스트

### ✅ 이미 완료된 항목
- [x] `index.html` 파일명 (모든 상대 링크 자동 반영됨)
- [x] SEO/OG 메타 태그 (description, og:*, twitter:*, canonical)
- [x] Favicon (SVG 인라인 · 태극 마크)
- [x] robots.txt · sitemap.xml (루트에 위치)
- [x] 404 페이지 (`404.html`)
- [x] Vercel/Netlify 설정 (캐싱 · 보안 헤더)
- [x] GitHub Actions Pages 배포 워크플로우
- [x] `medicaljapan@btp.or.kr` — Cloudflare obfuscation 완전 제거, base64 인코딩된 mailto 링크로 안전 처리
- [x] 사전등록 폼 fallback — 백엔드 미연결 시 사용자 메일 클라이언트로 자동 fallback + 데모 안내 배너
- [x] Sticky 헤더 대응 `scroll-padding-top: 96px`
- [x] Floor plan 모바일 가로 스크롤 힌트 (900px 이하)
- [x] 접근성: alt 텍스트, ARIA 라벨, 폼 라벨 연결

### 🔧 배포자가 확인/설정할 항목
- [ ] `medicaljapan@btp.or.kr` 이메일 실제 발신 계정 활성화
- [ ] 전화번호 · 주소 · 담당자명 최종 확인 (`+82-2-3460-7396`, `+81-70-XXXX-XXXX` 등)
- [ ] Google Analytics / GA4 / Naver Analytics 스니펫 삽입 (`</head>` 위)
- [ ] 참가기업 이미지 저작권 재확인 (또는 자체 촬영본으로 교체)
- [ ] 실제 부스 번호 (Medical Japan 전용 Floor Map 공개 후) 최종 반영
- [ ] canonical URL / OG URL 을 실제 도메인으로 수정 (현재: `medicaljapan-kr.org`)
- [ ] 사전등록 폼 백엔드 연결 (Formspree / Netlify Forms / Google Forms) — HTML 주석 참고

### 폼 백엔드 옵션
현재 폼은 백엔드 미연결 시 자동으로 사용자의 이메일 클라이언트를 열어 `medicaljapan@btp.or.kr`로 전송되도록 fallback이 구현되어 있습니다. 배포 시 다음 중 하나로 확장 가능:

1. **Formspree** (가장 쉬움 · 무료 50건/월)
   ```html
   <form action="https://formspree.io/f/{FORM_ID}" method="POST">
   ```
2. **Netlify Forms** (Netlify 배포 시 무료 100건/월)
   ```html
   <form name="preregistration" data-netlify="true" method="POST">
   ```
3. **Google Forms Backend** (무료 · 무제한)
   - Google Forms 생성 → 각 입력 필드에 대응하는 entry ID 확인 → form action에 매핑
4. **자체 API 서버** (SendGrid, AWS SES 등과 연결)

## 추가 개발이 필요한 기능

정적 페이지로는 커버되지 않는 부분 — 서버/CMS 필요:

1. **사전등록 폼 백엔드** — Netlify Forms, Formspree, 자체 API
2. **관리자 페이지** — 참가기업/바이어/일정 CMS
3. **다국어 라우팅** — `/kr/*` · `/ja/*` · `/en/*` (현재는 파일 분리)
4. **이메일 자동 발송** — 신청 접수 확인 · 일정 확정 안내
5. **매칭 시스템** — 바이어 등록 → 심사 → 기업 매칭 → 캘린더 통합
6. **Analytics · Tracking**

이런 기능이 필요하시면 이 번들을 **Genspark Code**로 이관하시면 통합 개발이 가능합니다.
