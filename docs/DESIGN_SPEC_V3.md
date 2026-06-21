# SJ Applied Tech: Batch 36 — V3 Design Spec

## 1. 새 UI 와이어프레임 텍스트 설계

밝은 흰색 계열 UI를 기준으로 한다. 공포는 배경과 숫자에서 오고, UI 자체는 읽기 쉽고 깨끗해야 한다.

```text
┌──────────────────────────────────────────────────────────────────────────────┐
│ TOP BAR                                                                       │
│ [로고/타이틀]          [날짜/시간] [생존 N일]          [정지][1x][6x][12x]     │
│ [현금] [매출채권 AR] [미지급금 AP] [부채] [월 번] [압박]                     │
├──────────────┬───────────────────────────────────────────────┬───────────────┤
│ LEFT RAIL    │ CENTER FULL LOCATION VIEW                      │ RIGHT PANEL   │
│              │                                                │               │
│ 현장 방문     │ 현재 방문 공간의 큰 일러스트/배경                │ 현재 공간의     │
│ [현장]       │                                                │ 상태/투자/설명 │
│ [조립실]     │ [공간 제목] [핵심 상태 배지]                     │               │
│ [사무실]     │                                                │ 현장: 가동/안전 │
│ [설계실]     │ 공간별 보는 재미:                               │ 조립: 36대 배치 │
│              │ - 현장: MCT/CNC 현장                             │ 사무: 현금흐름  │
│ 생존 액션     │ - 조립실: 12·12·12 배치 진행                    │ 설계: 표준화    │
│ [납기 압박]   │ - 사무실: 숫자의 전장                            │               │
│ [결제 홀드]   │ - 설계실: 미래 비용 절감                          │ [투자 버튼]     │
│ [채권 할인]   │                                                │               │
│ [대책회의]    │ 좌하단: 이벤트 로그                               │               │
│ [클레임]      │ 중앙: 위기 배너                                   │               │
│ [휴게실]      │ 우하단: 고양이/강아지/부엉이 직원                  │               │
└──────────────┴───────────────────────────────────────────────┴───────────────┘
```

### 설계 원칙

- 아래쪽 HUD를 제거하고 모든 주요 자원은 상단으로 올린다.
- 중앙은 하나의 큰 공간만 보여준다. 회사 전체를 한 화면에 넣지 않는다.
- 왼쪽은 “어디를 볼지”와 “무슨 조치를 할지”만 담당한다.
- 오른쪽은 현재 공간에 맞는 세부 정보와 투자만 보여준다.
- 버튼 설명은 짧게 유지하고, 긴 설명은 hover tooltip 또는 사이드 패널 문장으로 처리한다.

## 2. 공간 4개별 게임 기능표

| 공간 | 역할 | 보는 재미 | 주요 지표 | 주요 투자 | 감정 |
|---|---|---|---|---|---|
| 현장 | MCT/CNC 절삭, 생산 기반 | 장비가 돌아가는 현장 이미지 | MCT Lv, CNC Lv, 안전, 산재, 압박 | MCT 셋업, CNC 지그, QC/안전 | 긴장, 가동감 |
| 조립실 | SMT 스크린 프린터 풀아쎄이 | 12칸씩 채워지는 배치 보드 | Batch 1/2/3, 완료, 불량, 출하 | 조립 표준화, 구매/자재, QC/안전 | 성취, 일정 압박 |
| 사무실 | 현금흐름과 법무 판단 | 숫자가 정리된 흰색 패널 | 현금, AR, AP, 부채, 법무, 협력사 | 자금 회수, 사무실 운영 | 공포, 책임 |
| 설계실 | 미래 비용 절감 | CAD/도면/표준화 느낌 | 설계 Lv, QA Lv, 불량, 다음 배치 | 설계 개선, QC/안전, 조립 표준화 | 희망, 투자 |

## 3. 조립실 36대 배치 시스템 설계

총 36대를 하나의 큰 주문으로 보고, 12대씩 세 배치가 병렬로 진행된다.

```text
Batch 1: 프레임             12대
Batch 2: 내부 조립 · PLC     12대
Batch 3: Idle Run           12대
총합                         36대
```

### 각 배치의 의미

| 배치 | 단계 | 주된 영향 변수 | 실패 리스크 |
|---|---|---|---|
| Batch 1 | 프레임 | MCT, CNC, 구매/자재 | 지그 불량, 프레임 지연 |
| Batch 2 | 내부 조립 · PLC | 조립 표준화, 설계, QA | 배선 오류, PLC 셋업 지연 |
| Batch 3 | Idle Run | QA, 설계, 조립 | 테스트 실패, 재작업, 출하 지연 |

### 플레이 감각

- 플레이어는 조립실에서 36칸이 채워지는 것을 본다.
- Batch 3의 완료품만 출하되어 매출채권으로 잡힌다.
- 납기 압박은 진행 속도를 올리지만 안전과 사기를 깎는다.
- 설계실 투자는 당장 돈을 만들지 않지만 PLC/Idle Run 속도와 불량률을 개선한다.
- QC/안전 투자는 산재와 클레임 확률을 낮춘다.

## 4. index.html 수정 지시안

### 변경 완료 항목

- 하단 HUD 제거, 상단 자원 스트립으로 이동.
- 밝은 흰색/회색 UI로 재설계.
- 왼쪽 상단에 현장 방문 탭 4개 추가.
- 기존 한 화면 통합 맵을 네 공간 방문형 구조로 변경.
- 오른쪽 패널을 현재 공간별 상태/투자 패널로 변경.
- 생존 액션 버튼 설명을 짧게 축약.
- 사용자 생성 아이콘을 실제 버튼/탭 이미지로 적용.
- 시간 속도를 빠르게 조정: 1x/6x/12x.
- 조립실에 12·12·12 총 36대 배치 보드 추가.
- 고양이/강아지/부엉이 직원 이미지를 중앙 하단에 배치.

### 코드 구조

```text
/assets/
  location_workshop.png
  korea_industrial_bg.png
  char_cat.png
  char_dog.png
  char_owl.png
  icon_deadline.png
  icon_payables.png
  icon_factoring.png
  icon_meeting.png
  icon_break.png
  icon_claim.png
  icon_visit_workshop.png
  icon_visit_assembly.png
  icon_visit_office.png
  icon_visit_design.png
  machine_mct.png
  machine_cnc.png
  machine_bench.png
/index.html
/DESIGN_SPEC_V3.md
```

## 5. 적용된 아이콘 프롬프트 방향

이번 버전에 실제 적용한 아이콘 세트는 다음 목적에 매핑했다.

| 아이콘 | 게임 내 적용 |
|---|---|
| 스톱워치 + 크레이트 | 납기 압박 |
| 인보이스 + 클립 + 박스 | 결제 홀드 |
| 인보이스 절단 + 코인 + 은행 | 채권 할인 |
| 회의 테이블 + 경고등 | 대책회의 |
| 라면 + 커피 + 안전모 | 휴게실 |
| 봉투 + 도장 + 밴드 | 클레임 무마 |
| MCT/CNC 장비 | 현장 방문 |
| 조립 벤치/PLC | 조립실 방문 |
| 사무 책상 | 사무실 방문 |
| 엔지니어링 책상 | 설계실 방문 |

### 다음 생성 프롬프트 권장

아이콘을 추가로 뽑을 때는 개별 생성보다 5개씩 묶음 시트가 비용 효율이 좋다.

```text
Create a 5-icon sprite sheet for a bright UI Korean industrial survival tycoon game. Cute dark-comedy tone, clean outline, soft shading, readable at 64x64, no text, no logo, no watermark, transparent background. Each icon should be isolated with generous spacing and consistent scale. Style matches cute cat dog owl factory workers, MCT CNC machines, SMT screen printer assembly, Korean small manufacturing company.

Icons: [ICON LIST HERE]
```

추가로 필요한 아이콘 후보:

1. 은행 압박
2. 세무 감사
3. 산업재해
4. PLC 오류
5. Idle Run 실패
6. 협력사 납품 중단
7. 도면 개정
8. 지그 재가공
9. 구조조정
10. 해외 탈출 루트
