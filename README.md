# 방역왕 대시보드

당근 카페 **바퀴벌레 vs 인간 | 셀프퇴치**의 월간 방역왕 TOP 10 공개 대시보드입니다.

## 월간 운영 흐름

1. 매월 1일 카페장 로그인 상태에서 당근 카페 관리자 > 게시글 관리 접속
2. Chrome DevTools > Sources > Snippets에 저장한 `방역왕 월간수집기` 실행
3. 수집기가 한국시간 기준 전월을 자동 인식
4. `bakwiaen-YYYY-MM-raw.json` 다운로드
5. JSON을 ChatGPT에 업로드
6. ChatGPT가 TOP 10 산출
7. `data/YYYY-MM.json`을 월별 보관하고 `data/latest.json`을 갱신
8. GitHub Pages 대시보드는 `latest.json`을 읽어 자동 표시

## 점수 기준

- 일반 게시글 +5점
- 가입인사 게시글 0점
- 유의미 댓글/대댓글 +2점
- 단순 반응·도배성 댓글 0점
- 카페장 닉네임 `인간` 전체 제외
- 동점: 유의미 댓글 수 → 일반 게시글 수 → 활동일 수

## 공개 범위

- TOP 10 닉네임, 점수, 게시글 수, 유의미 댓글 수, 전체 댓글 수
- TOP 3 강조
- 4~10위는 3위까지 필요한 점수 표시
- 지난달 TOP 3 표시
- 회원전용 게시글/댓글 원문은 외부에 공개하지 않음

## 파일 구조

- `index.html`: 대시보드 UI
- `data/latest.json`: 현재 대시보드가 읽는 최신 월 데이터
- `data/YYYY-MM.json`: 월별 아카이브
- `tools/bakwiaen_monthly_exporter.js`: 전월 자동 인식 수집기
