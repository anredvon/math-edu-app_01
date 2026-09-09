# MathEduApp — Development Plan

## 목표
2026-10-31 이전 전체 프로젝트 목표에 맞춰 MathEduApp을 병목 없이 병행 개발한다.

Local Coding Agent V3가 완성될 때까지 기다리지 않고 독립적인 설계/자료/PoC 작업을 진행한다.

## Phase 0 — Foundation
- GitHub `math-edu-app_01`
- 기존 Xcode `MathEduApp`
- PROJECT.md
- docs/
- design/
- 확정 UI reference
- 이미지 assets
- initial baseline commit

## Phase 1 — Product & Data Foundation
- 중1 Skill Tree 확정
- 문제 메타데이터 확정
- 문제은행 수집/정리 방식 확정
- SwiftData 모델 초안
- grading policy 확정

## Phase 2 — UI Skeleton
8개 핵심 화면의 navigation/skeleton:
1. 학년 선택
2. 중1 홈
3. 단원/Skill
4. 문제 풀이
5. 채점 결과
6. 오답노트
7. 학습 분석
8. 마이페이지

## Phase 3 — Pencil PoC
- PencilKit Canvas
- 펜/지우개/Undo
- 풀이 저장
- 수식 인식 실험
- 숫자/x/+/-/=/괄호/분수 검증

이 단계는 기술 위험을 조기에 확인하기 위한 PoC다.

## Phase 4 — Linear Equation Vertical Slice
중1 일차방정식 30~50문제로 완전한 학습 루프를 만든다.

`문제 → 풀이 → 채점 → 오답 분석 → 기록 → 복습`

## Phase 5 — Deterministic Grading
- 최종 답 검증
- 등식 동치 검증
- 단계별 풀이 검증
- 첫 오류 단계 탐지
- 기본 MistakeType 분류

## Phase 6 — GPT
- Proxy
- 저비용 모델
- 호출 제한
- 단계별 힌트
- 해설
- 오답 원인 분석
- 실패 fallback

## Phase 7 — Personalization
- SkillProgress
- 오늘의 학습
- 오답 자동 복습
- 1/3/7일 형태의 간격 반복
- 학습 분석

## Phase 8 — Middle School Grade 1 Expansion
PoC 결과가 안정된 뒤 중1 전체 단원으로 확대한다.

## Release Candidate 기준
- 실제 iPad에서 안정 실행
- Pencil 풀이 가능
- 기본 학습은 오프라인 가능
- 채점 신뢰성 확보
- 오답/복습 정상 작동
- 학습 기록 보존
- AI 장애가 기본 학습을 막지 않음
- 주요 회귀 테스트 통과
