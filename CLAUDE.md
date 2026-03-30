# Vivatory — Claude Code Context

## 프로젝트 개요
개인 건강 데이터 퍼블리싱 파이프라인.
원시 데이터 → 구조화된 시각화 → 브랜드 보이스 서사 → 웹 퍼블리케이션.

---

## 페이지 구조 (IA)

```
vivatory/
├── index.html                        ← 홈 (브랜드 소개)
├── tools/
│   └── index.html                    ← Tools = Periodic Chart Trial
└── cases/
    └── periodic-chart/
        └── index.html                ← Cases = 차트 시각화 (Denev 실제 데이터)
```

**URL 구조 (GitHub Pages)**
- 홈: `https://caseofdenev.github.io/vivatory/`
- 툴: `https://caseofdenev.github.io/vivatory/tools/`
- 케이스: `https://caseofdenev.github.io/vivatory/cases/periodic-chart/`

---

## 디자인 시스템

### 컬러
```css
--vv-purple:   #3C1775   /* Primary */
--vv-purple-2: #4A247F   /* Hover */
--vv-accent:   #6B4BA3   /* Accent */
--vv-bg:       #F3F2F4   /* Background */
--vv-text:     #1a1018   /* Body text */
--vv-muted:    #7a6f83   /* Muted text */
--vv-border:   rgba(60, 23, 117, 0.15)
```

### 타이포그래피
- EN 헤더 / 브랜드명: `Times Newer Roman` (serif)
- KO 헤더: `Paperlogy Bold`
- 본문 (KO + EN): `Pretendard`

### 폰트 경로 (루트 기준 상대경로)
```
루트(index.html)           → ./fonts/...
tools/index.html           → ../fonts/...
cases/periodic-chart/      → ../../fonts/...
```

### 디자인 원칙
- 모서리: 직각 (border-radius 없음, 단 date input은 예외로 6px 허용)
- 보더: `0.5px solid var(--vv-border)`
- 여백 우선 — 노이즈 최소화
- 타이포그래피가 위계를 담당

---

## 톤 & 보이스

### 작성 원칙
- 짧고 절제된 문장
- 의미를 암시, 과설명 금지
- 감정적으로 중립, 차갑지 않게

### 금지
- 친근한 말투 / 과설명 / 동기부여 클리셰 / 장식적 감정

### 예시 (좋음)
```
입력은 단순하다.
데이터가 쌓이고, 패턴이 드러난다.
```

### 예시 (나쁨)
```
쉽고 간편하게 주기를 관리해보세요! 건강한 삶을 향한 첫 걸음입니다.
```

---

## NAV 구조 (공통)

```html
<nav>
  <a class="nav-logo" href="/vivatory/">
    Vivatory
    <span>비바토리</span>
  </a>
  <div class="nav-links">
    <a href="/vivatory/">Home</a>
    <a href="/vivatory/tools/">Tools</a>
    <a href="/vivatory/cases/">Cases</a>
  </div>
  <a class="nav-cta" href="#">시작하기</a>
</nav>
```

> Cases 링크: `/vivatory/cases/periodic-chart/`

---

## 브랜드 구조

**Vivatory 비바토리** — 개념적, 제품 중심, 궤적 설계. 낮은 서사 밀도.
**Denev 데네브** — 개인적, 관찰적, 케이스 중심. 높은 서사 밀도.

슬로건 (수정 금지):
- EN: `Draw your trajectory towards better health`
- KO: `더 건강한 당신을 향한 궤적을 그립니다`

---

## 배포

```bash
# 변경 후 항상 이 순서로
git add [파일명]
git commit -m "커밋 메시지"
git push origin main
```

- 저장소: `https://github.com/caseofdenev/vivatory`
- GitHub Pages 반영: push 후 1–2분 소요
- **git은 Dave(또는 Denev)가 터미널에서 직접 실행** — Claude Code는 파일만 준비

---

## 작업 분담 원칙

| 작업 유형 | 도구 |
|---|---|
| 색상·링크·텍스트 수정 | Claude Code (여기) |
| 파일 생성·삭제·이동 | Claude Code (여기) |
| 디자인 방향 결정 | Cowork |
| 브랜드 보이스 카피 | Cowork |
| 구조 설계·IA 변경 | Cowork |
