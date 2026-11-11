# 하온하린윤하네 가족여행 — 경주 1박2일 가이드맵

부산 동래에서 출발하는 경주 1박2일 가족여행 가이드. 빌드 과정 없는 단일 HTML 파일이고 지도는 **카카오맵**입니다.

**공개 주소:** https://kimddubuck.github.io/yunha_trip/

> 마쓰야마 4박5일 가이드(취소된 여행)는 `archive/matsuyama/`에 그대로 보관돼 있습니다.

## GitHub Pages 브랜치 바꾸기 — 1회

지금 Pages는 예전 브랜치(`claude/kind-feynman-8r8t7v`)를 서빙하고 있습니다. 경주 페이지가 보이게 하려면:

1. https://github.com/kimddubuck/yunha_trip/settings/pages 접속
2. **Branch**를 `claude/affectionate-tesla-xsxfv0` / `/ (root)`로 바꾸고 **Save**
3. 1~2분 뒤 https://kimddubuck.github.io/yunha_trip/ 에서 열립니다

이후에는 이 브랜치에 푸시할 때마다 자동으로 다시 배포됩니다.

## 카카오맵이 뜨게 하기 — 1회

`index.html`에 카카오 JavaScript 키가 이미 들어 있습니다. 키는 공개돼도 되는 값이지만 **등록한 도메인에서만** 동작하므로 카카오 개발자 콘솔에서 두 가지를 켜 줘야 합니다.

1. https://developers.kakao.com/console/app 접속 → 이 키가 속한 앱 선택
2. **앱 설정 → 플랫폼 → Web** 에서 사이트 도메인에 `https://kimddubuck.github.io` 추가 (저장)
3. **제품 설정 → 카카오맵** 에서 활성화 설정을 **ON** (2024년 12월부터 이걸 켜야 지도가 나옵니다)
4. 배포된 페이지를 새로고침. 지도가 안 뜨면 지도 자리에 이유가 한 줄 적혀 있고, 그 아래 '카카오맵 열기' 버튼 목록이 대신 나옵니다

폰에서 파일을 직접 열거나(`file://`) 다른 주소로 열면 도메인이 달라 지도가 안 나옵니다. 이건 정상입니다.

## 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 가이드맵 본문. 카카오맵(집 포함 핀 9곳 + 1·2일차 점선 동선) + 일정표 + 바꾼 것 + 장보기 + 윤하 팁 + 체크리스트 |
| `places.json` | 지도 핀 데이터. 이름·검색어·주소·좌표·일차·이야기·아기 팁. `role`이 `home`(집)·`stay`(숙소)인 핀은 동선의 양 끝이 되고, 나머지는 **배열 순서가 곧 방문 순서**입니다 |
| `HANDOVER.md` | 작업 인수인계서 — 여행 전제, 확인된 사실, 결정 이유, 다음 작업 |
| `archive/matsuyama/` | 취소된 마쓰야마 여행 자료 일체 |
| `.nojekyll` | Pages의 Jekyll 처리 건너뛰기 |

## 고치는 법

의존성도 빌드 단계도 없습니다.

- **시간·문구를 고칠 때** → `index.html`의 `#plan` 섹션(일정표)과 `<script>` 안 `GUIDE` 배열(안내원 대본) 두 군데를 같이 고칩니다.
- **장소를 더하거나 뺄 때** → `places.json`에 항목을 넣고(`approx:true`로 두면 페이지가 열릴 때 `address`로, 주소가 없으면 `query` 상호 검색으로 좌표를 스스로 찾습니다), `index.html` 일정표에 카드를 추가합니다. 카드의 `data-q`는 `places.json`의 `query`와 똑같아야 지도와 연결됩니다.
- **날짜를 바꿀 때** → 헤더 날짜 칸, 1·2일차 제목, 체크리스트 첫 줄.
- **집 주소를 바꿀 때** → `places.json`의 `집` 항목 `address`·`query`, 헤더 ‘출발 · 도착’ 칸, 일정표의 ‘집 출발’·‘집으로’ 카드.

검증 스크립트는 `HANDOVER.md`의 '검증 방법'에 있습니다.
