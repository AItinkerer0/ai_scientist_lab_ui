# AI Scientist Lab · UI

AI Scientist Lab 소개·데모 **랜딩 페이지**. 단일 self-contained HTML 한 장으로, 검정 배경 위 3D dot 파티클 필드가 스크롤에 따라 자율 연구 파이프라인의 8단계(Plan → Literature → Hypothesis → Data → Analysis → Paper → Review → Record)를 시각화한다.

## Status

- **Last reviewed:** 2026-07-17
- **Maturity:** 정적 프론트 데모 (단일 `index.html`)
- **이 저장소가 하는 일 / 하지 않는 일**
  - ✅ 브라우저에서 스크립트된 SIM 시연(자동 스크롤, 카드 출력 타이핑, 비용·시간 티커 애니메이션)
  - ❌ 백엔드 서버 없음 · API 호출 없음 · 실데이터 로드 없음 · 모델 추론 없음
  - ❌ 화면에 표시되는 단계 출력·elapsed·cost 누적은 **합성 데모 값**이며 실제 파이프라인 결과·청구가 아니다
  - ❌ 이 저장소만으로 “연구 토픽을 실제로 끝까지 실행”할 수 없다

> ⚠️ **SIM 경계 (필수 읽기)**
> 페이지 본문·도움말·확인 다이얼로그에는 “real time and cost”, “real data”, “pipeline runs itself end to end”, “Every step has been logged” 같은 **제품 내러티브 문구**가 들어 있다. 그 문장은 전체 연구 파이프라인 제품 경험을 설명하는 카피이며, **이 HTML이 그 작업을 수행한다는 뜻이 아니다.**
> 카드 하단 라벨은 명시적으로 `SIM · synthetic demo output`이고, RUN 시퀀스는 로컬 타이머로 합성 출력을 채운 뒤 “Run complete” UI로 끝난다. 백엔드·실데이터·실비용 청구는 없다.

Private 백엔드/파이프라인 저장소 내부는 이 공개 저장소 범위 밖이며, 여기서 링크하거나 구현 세부사항을 단정하지 않는다.

## 보기

- 라이브: https://aitinkerer0.github.io/ai_scientist_lab_ui/
- 로컬 (미실행 안내): `index.html`을 브라우저로 열거나, 저장소 루트에서 정적 서버로 서빙
  ```bash
  python3 -m http.server
  # 브라우저에서 http://localhost:8000 접속
  ```

## 사용

- 스크롤로 단계 전환 (데스크탑 폭에서 좌측에 진행 레일 표시)
- 좌상단 `?` — 사용법·주의사항 도움말 (첫 방문 시 자동 표시; 닫으면 `localStorage` 키 `astlab_help_seen`에 기록)
- 토픽 입력 후 **RUN** — 확인창을 거쳐 **자동 스크롤 SIM 시연** (실실행 아님)

## 네트워크 · 저장 · 의존성

| 구분 | 내용 |
|------|------|
| 의존성 | 순수 HTML/CSS/Canvas. 빌드·패키지 매니저 없음 |
| 네트워크 | 글꼴 CSS 1건: jsDelivr Pretendard CDN (`pretendard@v1.3.9`). 그 외 `fetch`/XHR/WebSocket 없음 |
| 로컬 저장 | `localStorage` — 도움말 “이미 봄” 플래그만 (`astlab_help_seen`) |
| 비용 티커 | `STAGE_COST` 등 하드코딩된 합성 수치로 누적 표시 (실제 과금 아님) |

## 구성

- `index.html` — UI·3D 필드·8단계 카드·RUN 시퀀스 전부
- `LICENSE` — MIT
- `README.md` — 이 문서

## License

MIT (`LICENSE` 파일 기준).

---

제가 이런 분야를 접한 지 얼마 안 돼서 부족한 점이 많습니다. 고칠 점이나 알려주실 내용이 있다면 issue나 PR로 남겨주시면 너무 감사하겠습니다.
