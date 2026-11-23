# 게임 제작과 AI 활용 포트폴리오

게임을 직접 플레이하면서 선택을 막는 규칙이나 기대와 다르게 작동하는 기능을 찾습니다. 아래 사례에는 제가 어떤 조건을 정했고, Codex와 팀원이 어디를 맡았으며, 결과를 어떻게 확인했는지 담았습니다.

[포트폴리오 PDF · 제작 이력, AI 협업, 게임 플레이 기록](portfolio.pdf)

[2월부터 11월까지의 작업 이력](history.md) · [Codex 사용 방식의 변화](workflow/codex.md)

## 제작 참여 프로젝트

| 게임 | 형태 | 담당 범위 |
| --- | --- | --- |
| [Coin Survivor](cases/coin-survivor.md) | 팀 제작 · STOVE 출시 | 상점·인벤토리, 구매·판매 확인 조건, 초반 골드 분석 |
| [Fisher Idle RPG](cases/fisher.md) | 팀 제작 | 상점·요리·가방·도감의 클라이언트 UI와 요청 연결 |
| [EscapeRoom](cases/escape-room.md) | 개인 제작 | 잠입 감지와 퍼즐, 실패 후 복구 및 상태 전환 |

## 문제 해결 사례

| 사례 | 제가 한 판단 | 확인한 범위 |
| --- | --- | --- |
| [Coin Survivor · 판매한 무기가 전투에 남는 문제](cases/coin-survivor.md#판매한-무기가-전투에-남는-문제) | 판매한 레벨만 제거하고 같은 종류의 다른 레벨은 유지 | Unity Play Mode 직접 확인 |
| [Coin Survivor · 초반 골드로 어떤 선택이 가능한가](cases/coin-survivor.md#초반-골드로-어떤-선택이-가능한가) | 가방 확장비가 아이템 구매 여력을 잠식하는 구간을 찾아 초반 비용 조정을 제안 | 밸런스 표의 비교 항목 확인, 조정 효과 추가 확인 필요 |
| [Star Rail Lab · 입력 조건이 바뀌면 결과도 바뀌는가](cases/star-rail-lab.md) | 보유 장비와 콘텐츠 조건을 비교 요건으로 다시 정리 | 구현 기록과 검사 사례 확인, 실게임 대조 미완료 |

[게임 플레이 기록](play-experience.md)에는 시간이나 업적을 확인한 대표 게임을 정리했습니다.

## 산출물과 검증 기록

| 자료 | 볼 수 있는 내용 |
| --- | --- |
| [Coin Survivor Play Mode 확인표](evidence/coin-survivor-playmode.md) | 판매부터 구매·합성까지 확인한 동작, 방어구 미확인 범위 |
| [EscapeRoom 자동 검사 기록](evidence/escape-room-playmode.md) | SceneA 기본 실행, 입력 잠금과 실패 복구 확인 |
| [Star Rail Lab 코드 발췌와 검사 범위](evidence/star-rail-implementation.md) | 입력 변경과 뒤늦은 응답을 처리한 코드, 모델 계산과 실게임 검증의 범위 |
| [회의 전사와 팀 작업 기록](workflow/team-notes.md) | 전사에서 빠진 안건을 직접 보완하고 작업으로 연결한 과정 |
| [검색 도구 검토 기록](workflow/search-review.md) | 고정 검사 결과, 채택·중단·미확인의 판단 근거 |
| [Steam 플레이 시간이 표시된 162개 기록](play-library.md) | 기존 스냅샷에서 계정 링크를 제외하고 정리한 게임명과 시간 |
