# bluenote homepage

[bluenote99.com](https://www.bluenote99.com) 공식 홈페이지 소스입니다. Vercel이 `main` 브랜치를 보고 자동 배포합니다 (push 후 약 30초~1분).

## 파일 구조

```
homepage/
├── index.html          # 한국어 → https://www.bluenote99.com/
├── en/
│   └── index.html      # 영어 → https://www.bluenote99.com/en/
├── favicon.ico
├── README.md
└── .github/workflows/
    └── sync-check.yml  # 한/영 동기화 자동 체크
```

우측 상단의 **KOR / ENG** 토글로 두 페이지가 서로 연결됩니다.

---

## 한/영 동기화 규칙

> 카피·구조 변경은 **반드시 두 파일 동시에** 수정하세요.

`index.html` 또는 `en/index.html` 한쪽만 수정하면 두 언어 버전이 어긋납니다.

### ✅ 양쪽 모두 수정해야 하는 변경

- [ ] 메뉴 항목 추가/삭제 (네비게이션)
- [ ] 섹션 추가/삭제/순서 변경
- [ ] 카피 변경 (제목, 부제, 본문)
- [ ] 통계 숫자 업데이트 (18+, 3,600+ 등)
- [ ] 채널 카드 (LinkedIn, YouTube 등) 추가/삭제
- [ ] 연락처 정보 변경 (주소, 전화번호, 이메일)
- [ ] 폼 필드 추가/삭제
- [ ] 스타일 변경 (색상, 폰트, 레이아웃)

### ⚠️ 양쪽 다른 게 정상 (sync 불필요)

- 영어판은 Google Maps 링크, 한국어판은 Naver 지도 링크
- 영어 footer는 통신판매번호 없음 (국내 한정 표기)
- 메뉴/라벨 단어 선택 (예: "솔루션 / SOLUTIONS")

---

## 변경 절차

1. **두 파일 모두 같은 내용으로 수정**
2. 로컬 브라우저로 두 파일 열어 확인 (`index.html`, `en/index.html`)
3. commit & push (Vercel이 자동 배포)
4. 약 1분 후 라이브 양쪽 확인:
   - https://www.bluenote99.com/
   - https://www.bluenote99.com/en/
5. 토글 (KOR ↔ ENG) 동작 확인

---

## 자동 동기화 체크

`.github/workflows/sync-check.yml`이 main 브랜치 push 때마다 한쪽만 변경됐는지 검사합니다. 한쪽만 수정한 채 push하면 commit에 자동으로 reminder 코멘트가 달립니다 — 그 알림을 받으면 빠진 파일을 추가 commit으로 보완하세요.

---

## 자주 쓰는 git 명령어

```bash
# 변경 사항 확인
git status
git diff

# 두 파일 모두 stage
git add index.html en/index.html

# commit & push
git commit -m "Update copy in hero section"
git push origin main
```
