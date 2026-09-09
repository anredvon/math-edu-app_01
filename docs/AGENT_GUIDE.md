# MathEduApp — Local Coding Agent Guide

## 1. 목적
이 문서는 Local Coding Agent가 MathEduApp을 수정할 때 따라야 하는 기본 작업 계약이다.

에이전트 자체는 MathEduApp 전용이 아니며, 이 문서는 **이 프로젝트 안에서만 적용되는 규칙**이다.

## 2. 작업 시작 전 Context Loading
다음 순서로 확인한다.

1. `/PROJECT.md`
2. `/docs/AGENT_GUIDE.md`
3. 작업과 직접 관련된 `/docs/*.md`
4. UI 작업이면 `/design/DESIGN_SYSTEM.md`
5. UI flow 관련이면 `/design/UI_FLOW.md`
6. 필요한 경우 `/design/reference/`
7. `/MathEduApp/` 실제 소스
8. 관련 Unit/UI Tests

## 3. 작업 기본 흐름
`Requirement`
→ `Explore`
→ `Context`
→ `Plan`
→ `Edit`
→ `Semantic Verify`
→ `Build`
→ `Test`
→ `Failure Analysis`
→ `Limited Retry`
→ `Report`

## 4. 변경 규칙
- 요구사항과 관계없는 파일은 가능한 한 수정하지 않는다.
- 기존 정상 기능을 유지한다.
- 무관한 대규모 리팩터링을 동시에 하지 않는다.
- 한 번에 검증 가능한 크기로 작업한다.
- 데이터 모델 변경 시 migration 영향을 확인한다.
- UI 변경 시 확정 디자인 문서를 확인한다.
- AI 기능은 `AI_ARCHITECTURE.md`를 따른다.
- 문제/Skill 변경은 `CURRICULUM.md`, `PROBLEM_BANK.md`를 확인한다.

## 5. 안전 규칙
- 수정 전 repository 상태를 확인한다.
- 기존 사용자 변경사항을 임의로 삭제하지 않는다.
- Build 실패를 성공으로 보고하지 않는다.
- Test 실패를 숨기지 않는다.
- 검증 실패 시 무한 반복하지 않는다.
- 실패한 변경은 필요 시 rollback 가능해야 한다.
- 임의의 요구사항 축소로 PASS 처리하지 않는다.

## 6. UI 규칙
UI 작업 전:
- `design/reference/math_app_ui_reference.png`
- `design/DESIGN_SYSTEM.md`
- `design/UI_FLOW.md`

를 확인한다.

기준 이미지와 다른 방향의 대규모 스타일 변경은 별도 요구가 없으면 하지 않는다.

## 7. 완료 조건
작업 완료 보고에는 다음을 포함한다.
- 요구사항별 구현 여부
- 변경 파일
- 핵심 변경 내용
- Build 결과
- Test 결과
- Semantic verification 결과
- 미해결 문제
- 남은 위험
- rollback 여부

## 8. 완료 판정
코드가 수정되었다는 사실만으로 완료가 아니다.

최소한:
**요구사항 충족 + 소스 검증 + Build + 관련 Test + 회귀 위험 확인**
이 충족되어야 완료로 판단한다.
