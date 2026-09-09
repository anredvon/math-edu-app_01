# MathEduApp — Problem Bank

## 1. 목적
문제은행은 단순 문제 저장소가 아니라 Skill 기반 맞춤 학습의 기반 데이터다.

## 2. 주요 출처
서울 강북구 소재 중학교의 최근 약 5년 이내부터 현재까지 공개된 기출문제 등을 중심으로 조사한다.

공개 접근 가능하다는 사실과 자유로운 재배포 가능 여부는 동일하지 않으므로 출처와 사용 상태를 기록한다.

## 3. 문제 종류
- 공개 기출 원본
- 기출 기반 변형
- 동일 Skill 자체 제작
- 복습용 파생 문제

## 4. 권장 메타데이터
- id
- school
- grade
- year
- semester
- examType
- unit
- chapter
- skill
- difficulty
- problemType
- sourceType
- sourceReference
- usageStatus
- parentProblemId

## 5. 문제 예시
```json
{
  "id": "M1_EQ_LINEAR_001",
  "grade": 1,
  "unit": "문자와 식",
  "skill": "일차방정식-이항",
  "difficulty": 2,
  "sourceType": "self_authored",
  "question": "2x + 3 = 11을 풀어라.",
  "answer": "x = 4"
}
```

## 6. 품질 규칙
- 정답을 반드시 검증한다.
- Skill 태그를 확인한다.
- 동일/유사 문제 중복을 식별한다.
- 변형 문제는 가능하면 원본 관계를 기록한다.
- 난이도는 실제 학생 풀이 데이터에 따라 추후 보정 가능하다.
- 문제 출처를 가능한 한 잃지 않는다.

## 7. 초기 문제은행
PoC는 일차방정식 약 30~50문제로 시작한다.

초기 목표는 문제 수 확대보다 다음 검증이다.
- 문제 표시
- Apple Pencil 풀이
- 수식 인식
- 채점
- 단계 검증
- 오답 유형
- 재출제
