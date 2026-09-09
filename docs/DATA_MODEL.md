# MathEduApp — Data Model

## 1. 설계 원칙
- 학생 학습 기록은 SwiftData 로컬 저장을 기본으로 한다.
- 커리큘럼/문제은행은 초기에는 앱 번들 JSON 등 정적 데이터로 시작할 수 있다.
- 학습 분석이 가능하도록 단순 정답 여부 이상의 데이터를 저장한다.

## 2. 주요 모델

### StudentProfile
- id
- currentGrade
- dailyGoalMinutes
- createdAt

### Unit
- id
- grade
- title
- order

### Chapter
- id
- unitId
- title
- order

### Skill
- id
- chapterId
- title
- description
- order

### Problem
- id
- grade
- unitId
- chapterId
- skillId
- difficulty
- question
- answer
- solution
- sourceType
- sourceMetadata
- parentProblemId

### ProblemAttempt
가장 중요한 학습 로그 중 하나다.

- id
- problemId
- attemptedAt
- finalAnswer
- isCorrect
- elapsedSeconds
- hintCount
- retryCount
- mistakeType
- recognizedSteps
- handwritingReference

### SkillProgress
- id
- skillId
- masteryScore
- attemptCount
- correctCount
- firstTryCorrectCount
- lastAttemptAt
- nextReviewAt

### ReviewSchedule
- id
- skillId
- problemId
- dueAt
- reason
- completedAt

### StudySession
- id
- startedAt
- endedAt
- problemCount
- correctCount
- durationSeconds

## 3. MistakeType 예시
- conceptGap
- signError
- arithmeticError
- equationTransformationError
- interpretationError
- carelessError
- unknown

실제 분류 체계는 PoC 결과를 보고 조정한다.

## 4. Apple Pencil 데이터
필요에 따라 다음을 저장할 수 있다.
- PencilKit drawing data
- 렌더링 이미지
- 인식된 수식
- 구조화된 풀이 단계

모든 원본 필기를 영구 저장하는 것을 기본 전제로 하지 않는다.

## 5. 데이터 변경
모델 변경 시 기존 학습 데이터 migration 가능성을 고려한다.
초기 PoC에서도 의미 없이 모델명을 자주 변경하지 않는다.
