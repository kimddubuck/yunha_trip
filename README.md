# 마쓰야마 4박5일 가이드맵

15개월 아기와 떠나는 부산 → 마쓰야마 가족여행 가이드. 단일 HTML 파일입니다.

**공개 주소:** https://kimddubuck.github.io/yunha_trip/

## 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 가이드맵 본문. 약도(인라인 SVG) + 구글맵 임베드 + 일정·음식·아기 팁·렌터카·체크리스트 |
| `matsuyama-places.csv` | 구글 '내 지도(My Maps)' 가져오기용 20곳 목록 |
| `HANDOVER.md` | 작업 인수인계서 — 여행 전제, 확인된 사실, 다음 작업 후보 |
| `.github/workflows/pages.yml` | GitHub Pages 자동 배포 |

## 고치는 법

의존성이나 빌드 단계가 없습니다. `index.html`을 직접 열어 확인하고, 기본 브랜치에 푸시하면 자동 배포됩니다.

구조 확인용 스크립트는 `HANDOVER.md`의 '8. 검증 방법'에 있습니다(파일명만 `index.html`로 바꿔서 실행).
