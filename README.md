# introduce-jobs

세미나 「AI 테크기업 직무 이해」 실습용 직무 적합성 Self-Assessment 앱.
순수 정적 페이지(`public/index.html` 하나)로 서버·DB가 필요 없고, 답변은 브라우저 localStorage에만 저장됩니다.

- 26문항(13개 성향·역량 × 2) → 12개 직무 일치도, Top 3, 레이더 차트, 보완 포인트, 인쇄/PDF, 결과 링크 공유(`#r=26자리`)
- 직무 도감(12개): SW·AI 엔지니어 / PM / 데이터 분석가 / 마케팅 / DevRel / 영업 / BD / 세일즈 엔지니어 / 컨설턴트 / FDE / 서포트 엔지니어 / CSM
- 각 직무에는 채용공고 검색용 `keywords`(짧은 단어 배열)가 있습니다. 화면 표시용 `signals`와 별개로, 직무 프로필 내보내기(JSON·PDF)에서 검색 키워드로 쓰입니다.

## 데이터 저장 원칙
- 진단 응답과 결과는 사용자 브라우저(localStorage)에만 저장됩니다.
- 서버·DB로 응답이나 결과를 보내지 않습니다.
- 외부 분석 도구(GA 등)나 추적 스크립트를 추가하지 않습니다.

## 수정
`public/index.html` 상단 스크립트의 `DIMS`(차원), `QUESTIONS`(문항), `ROLES`(직무 정의·차원별 가중치 `w`)를 고치면 됩니다.

## 로컬 실행 / 배포
```bash
npx wrangler dev      # 로컬 확인 (http://localhost:8787)
npx wrangler deploy   # 수동 배포
```
Cloudflare 대시보드의 Git 연동으로 `main` 푸시 시 자동 배포됩니다 (Deploy command: `npx wrangler deploy`).
