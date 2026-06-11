# CREMA Sales Email Generator — 배포 가이드

## Vercel 배포 (5분이면 완료)

### 1단계 — GitHub에 올리기
1. https://github.com 가입/로그인
2. New repository → `crema-sales-generator` 이름으로 생성
3. 이 폴더 파일 3개를 모두 업로드 (index.html, api/generate.js, vercel.json)

### 2단계 — Vercel 배포
1. https://vercel.com 가입/로그인 (GitHub 계정으로 가능)
2. "Add New Project" → GitHub 저장소 선택
3. Deploy 클릭

### 3단계 — API 키 환경변수 설정 (중요!)
1. Vercel 대시보드 → 프로젝트 → Settings → Environment Variables
2. 아래 값 추가:
   - Name: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...` (본인 API 키)
3. Save → Deployments → Redeploy

완료! `https://crema-xxx.vercel.app` URL로 접속하면 바로 동작합니다.

---

## 파일 구조
```
crema-project/
├── index.html        ← 프론트엔드 앱
├── api/
│   └── generate.js   ← API 프록시 (CORS 우회 + API 키 보호)
├── vercel.json       ← Vercel 설정
└── CLAUDE.md         ← 프로젝트 지식 (Claude Code용)
```
