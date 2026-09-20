# 마쓰야마 4박5일 가이드맵

15개월 아기와 떠나는 부산 → 마쓰야마 가족여행 가이드. 빌드 과정 없는 단일 HTML 파일입니다.

**공개 주소:** https://kimddubuck.github.io/yunha_trip/ (아래 설정을 한 번 해야 켜집니다)

## GitHub Pages 켜기 — 최초 1회만

1. https://github.com/kimddubuck/yunha_trip/settings/pages 접속
2. **Source**를 `Deploy from a branch`로
3. **Branch**를 `claude/kind-feynman-8r8t7v` / `/ (root)`로 고르고 **Save**
4. 1~2분 뒤 https://kimddubuck.github.io/yunha_trip/ 에서 열립니다

이후에는 이 브랜치에 푸시할 때마다 자동으로 다시 배포됩니다. 별도 워크플로는 필요 없습니다.

> Actions 워크플로로 배포하는 방법도 있지만, 워크플로의 기본 토큰(`GITHUB_TOKEN`)으로는
> Pages 사이트를 **처음 생성**할 수 없습니다(`Resource not accessible by integration`).
> 어차피 위 설정을 한 번 거쳐야 하므로, 워크플로 없이 브랜치에서 바로 서빙하는 쪽이 단순합니다.

## 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 가이드맵 본문. 약도(인라인 SVG) + 구글맵 임베드 + 일정·음식·아기 팁·렌터카·체크리스트 |
| `matsuyama-places.csv` | 구글 '내 지도(My Maps)' 가져오기용 20곳 목록 |
| `HANDOVER.md` | 작업 인수인계서 — 여행 전제, 확인된 사실, 다음 작업 후보 |
| `.nojekyll` | Pages의 Jekyll 처리 건너뛰기 |

## 고치는 법

의존성도 빌드 단계도 없습니다. `index.html`을 브라우저로 직접 열어 확인하고, 이 브랜치에 푸시하면 끝입니다.
구조 확인용 스크립트는 `HANDOVER.md`의 '8. 검증 방법'에 있습니다.
