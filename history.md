# 게임 제작과 AI 활용이 바뀐 과정

## 2~3월에 만든 개인 잠입 퍼즐

EscapeRoom에서 적의 시야를 피해 탐색하고 퍼즐을 푸는 흐름을 만들었습니다. 실패하면 잠시 조작을 막았다가 다시 움직일 수 있게 했습니다. 이미 해결한 퍼즐은 진행 상태를 남겼습니다.

[실패 후 다시 움직이는 과정](projects/escape-room/failure-and-retry.md)

## 4~5월에 맡은 상점과 인벤토리

Coin Survivor에서 아이템을 집고 놓는 동작을 합성보다 먼저 만들기로 했습니다. 회의 기록을 읽으면서 빠진 조작 안건도 보탰습니다. 무기를 팔 때는 같은 종류라도 판매한 레벨만 전투에서 빠지는지 직접 확인했습니다.

[조작 사례](projects/coin-survivor/inventory-pick-and-place.md)와 [판매 확인표](projects/coin-survivor/evidence/weapon-sale-play-mode.md)

## 6월에 고친 가방 표시와 정리한 회의 절차

Fisher에서는 지금 화면에서 선택한 것과 이미 보낸 요청을 구분해 처리했습니다. 멀티플레이에서 돌아왔을 때 가방에 이상한 값이 나타나자 팀과 함께 화면에 보이는 값과 저장된 값을 비교했습니다. 작업을 맡길 때는 손볼 범위를 먼저 적었고 회의 내용을 정리하는 절차는 다음 회의에서도 쓸 수 있게 남겼습니다.

[Fisher 사례](projects/fisher-idle-rpg/README.md)와 [회의와 작업 범위](workflow/team-notes.md)

## 7월에 다시 살핀 초반 밸런스

공모전을 준비하며 Coin Survivor를 다시 플레이했습니다. 초반 골드로 가방을 넓히면 아이템을 살 돈이 얼마나 남는지 영상과 웨이브별 시트를 보며 살폈습니다.

[상점에서 쓴 골드와 다음 전투](projects/coin-survivor/early-game-balance.md)

## 8월에 확인한 게임 동작과 기초 지식

EscapeRoom의 별도 소스 복사본을 대상으로 시작 씬과 대표 퍼즐의 실패 처리를 자동으로 검사했습니다. Unity와 C# 기초 문제에도 직접 답하면서 써 본 기능 중 제 말로 설명하기 어려운 부분을 찾았습니다.

[프로젝트 검사 기록](projects/escape-room/evidence/play-mode-checks.md)과 [직접 풀어 본 진단 문제](workflow/learning.md)

## 9~10월에 다시 들여다본 검색 결과와 계산 조건

검색에서 오래된 안내가 먼저 나오면 어떤 자료를 기준으로 삼아야 할지 다시 확인했습니다. Star Rail Lab에서는 장비를 바꿨을 때 이전 장비로 계산한 결과가 그대로 남지 않게 했습니다.

[자료 검색](workflow/search-review.md)과 [Star Rail Lab](game-tools/star-rail-lab/README.md)

## 11월에 바꾼 조사와 검토 방식

검토 지침을 비교할 때는 사례를 만드는 역할과 평가하는 역할을 나누고 어느 쪽이 새 지침인지 가렸습니다. 지원 자료 조사도 여러 대화에서 나눠 봤지만 실제 원문을 대조한 건수가 기대한 만큼 늘지 않아 한 대화로 돌아왔습니다. 와우 레벨업 안내에서는 꼭 해야 할 직업 퀘스트와 레벨이 모자랄 때 돌 던전을 구분했습니다.

- [Codex 작업 방식](workflow/codex.md)
- [quality-pass 사용법](workflow/quality-pass/README.md)
- [게임 도구와 검증 사례](game-tools/README.md)

[포트폴리오 첫 화면](README.md)
