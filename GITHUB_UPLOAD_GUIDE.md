# 🚀 GitHub 업로드 가이드 · Medical Japan 2026

이 폴더를 GitHub에 업로드하여 사이트를 온라인에 배포하는 방법입니다.
**개발자 도움 없이 웹 브라우저만으로 완료 가능**합니다.

---

## 📦 폴더 구조 (배포 준비 완료)

```
medicaljapan-2026/
├── index.html                    ← 메인 랜딩페이지
├── buyer-guide.html              ← 바이어 가이드 (한국어)
├── buyer-guide-jp.html           ← バイヤーガイド (일본어)
├── 404.html                      ← 404 에러 페이지
├── README.md                     ← 프로젝트 설명
├── GITHUB_UPLOAD_GUIDE.md        ← 이 가이드
├── robots.txt                    ← SEO 크롤러 설정
├── sitemap.xml                   ← SEO 사이트맵
├── .gitignore
├── netlify.toml                  ← Netlify 배포 설정 (선택)
├── render.yaml                   ← Render 배포 설정 (선택)
├── vercel.json                   ← Vercel 배포 설정 (선택)
│
├── assets/                       ← 이미지 34장 (기업/제품/파빌리온)
│   ├── bigbreathe-product.png    (35KB · 951×1000 고화질)
│   ├── o2lab-dynamic-balance-main.jpg
│   ├── carenco-fisica-device.png
│   ├── carenco-fisica-app.png
│   ├── aion-sf01-blue.png ... (BINATTI 5제품)
│   ├── co-dail-2.jpg
│   ├── mj-aerial.jpg / mj-showfloor.jpg / korea-pavilion.jpg
│   └── ... 총 34장
│
└── brochures/                    ← 브로셔 7개 파일
    ├── brochure.css              ← 공통 CSS
    ├── Medical Japan 2026 Company Brochure.html      (요약 6P)
    ├── Medical Japan 2026 - 전체 브로셔 합본.html    (전체 42P) ★
    ├── ghinnotech.html           (지에이치이노텍 12P)
    ├── o2lab.html                (오투랩 8P)
    ├── carenco.html              (케어엔코 6P)
    ├── aion.html                 (아이온 10P)
    └── dail.html                 (다일 6P)
```

**총 파일 수: 53개 · 총 용량: 약 4MB**

---

## 🔧 방법 1: 웹 브라우저로 직접 업로드 (가장 쉬움 · 추천)

### 1단계 · 리포지토리 준비

이미 리포지토리를 만드셨다면:
- **URL**: https://github.com/jmconnected-kr/medicaljapan-2026
- 이 경로로 접속하세요.

**아직 리포지토리가 없다면:**
1. https://github.com/new 접속
2. **Repository name**: `medicaljapan-2026`
3. **Public** 선택 (Render 자동 배포에 필요)
4. **Add a README file** 체크 해제
5. **Create repository** 클릭

### 2단계 · 파일 업로드

1. 리포지토리 페이지에서 상단의 **"Add file"** → **"Upload files"** 클릭
2. 로컬 컴퓨터에서 `medicaljapan-2026` 폴더 안의 **모든 내용물을 선택하여 드래그**
   - ⚠️ `medicaljapan-2026` 폴더 자체가 아니라 **폴더 내부의 파일과 하위폴더**를 업로드
   - 즉 `index.html`, `assets/`, `brochures/` 등이 리포지토리 최상단에 위치해야 함
3. 페이지 하단 **Commit changes** 영역:
   - Commit message: `Deploy: Medical Japan 2026 v2.0 · 5개사 브로셔 + 전체 합본`
   - **Commit changes** 버튼 클릭

### 3단계 · 대기

- 대용량 파일이 있어 업로드에 **1~3분** 소요
- 진행 표시줄이 완료되면 리포지토리 최상단에 `index.html`, `assets/` 등이 보여야 함

---

## 🔧 방법 2: Git 명령어로 업로드 (개발자용)

```bash
# 1. 리포지토리 클론 또는 초기화
cd /path/to/medicaljapan-2026
git init
git remote add origin https://github.com/jmconnected-kr/medicaljapan-2026.git

# 2. 모든 파일 추가
git add .

# 3. 커밋
git commit -m "Deploy: Medical Japan 2026 v2.0 · 5개사 브로셔 + 전체 합본"

# 4. 푸시
git branch -M main
git push -u origin main --force
```

---

## 🌐 자동 배포 확인

### Render (설정되어 있을 시)
- **자동 재배포 소요 시간**: 30초 ~ 2분
- 접속: https://medicaljapan-kr.org (또는 Render가 준 URL)
- 대시보드: https://dashboard.render.com/

### Netlify · Vercel (설정 파일 포함됨)
- `netlify.toml` · `vercel.json`이 폴더에 있어 두 플랫폼도 지원
- 각 플랫폼에서 리포지토리 연결만 하면 자동 배포

---

## ✅ 업로드 후 최종 확인 체크리스트

배포 URL(예: https://medicaljapan-kr.org)에 접속해서:

- [ ] 메인 페이지가 정상 로드
- [ ] 히어로 이미지가 표시됨
- [ ] "전체 합본 (42P) ★" 버튼 클릭 시 브로셔 열림
- [ ] Floor Plan에 KP-01 ~ KP-05 5개 부스가 보임
- [ ] 참가기업 5개 카드가 표시됨
- [ ] 각 사 브로셔 버튼 클릭 시 12P/8P/6P/10P/6P 로드
- [ ] 바이어 가이드 KR/JP 언어 전환 정상
- [ ] 사전등록 폼 표시 (제출은 백엔드 연결 필요)

---

## 🔄 이후 업데이트 방법

파일을 수정한 후 다시 반영하려면:

**웹으로:**
1. 리포지토리 → 수정할 파일 클릭 → 연필 아이콘 (Edit)
2. 수정 후 **Commit changes**

또는 여러 파일을 한 번에:
1. **Add file** → **Upload files** → 새 파일 드래그
2. 기존 파일과 이름 같으면 자동 덮어쓰기

**Git으로:**
```bash
git add .
git commit -m "Update: xxx"
git push
```

---

## 🎯 도메인 연결 (medicaljapan-kr.org)

이미 연결되어 있다면 건너뛰세요. 없다면:

### Render의 경우
1. Render 대시보드 → 서비스 선택 → **Settings** → **Custom Domain**
2. `medicaljapan-kr.org` 입력 → **Save**
3. 도메인 등록 회사(가비아·후이즈 등)에서 DNS 설정:
   - Type: `CNAME`
   - Name: `@` (또는 `www`)
   - Value: Render가 알려준 값 (예: `medicaljapan-2026.onrender.com`)
4. DNS 전파 최대 24시간 (보통 30분 내)

---

## 📞 문제 발생 시

- 업로드 실패: 파일 하나씩 업로드해 보기
- 자동 배포 실패: Render 대시보드 → **Events** 탭에서 에러 로그 확인
- 이미지 안 보임: 파일명에 한글/공백 있는지 확인 (한글 파일명은 URL 인코딩 필요)

---

**배포 준비 완료!** 🎉  
GitHub 업로드 후 30초~2분 내에 사이트가 최신 버전으로 갱신됩니다.
