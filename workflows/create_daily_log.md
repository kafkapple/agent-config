---
description: 일일 로그 작성 및 저장 워크플로우
---

# Workflow: Create Daily Log

하루의 작업을 마무래 때 이 워크플로우를 실행하세요.

## Step 1: Gather Context
1.  오늘 수정된 파일 목록(`git diff --stat` 등)을 확인합니다.
2.  `task.md`에서 완료된(`[x]`) 항목들을 확인합니다.
3.  오늘 발생한 주요 에러나 이슈를 회상합니다.

## Step 2: Draft Log Content
`~/.agent/logging/daily/YYYY-MM-DD_{Project}.md` 파일을 생성하고 아래 템플릿을 채웁니다.

```markdown
# Daily Log: [Date] - [Project]

## 1. One-line Summary
- (오늘의 핵심 성과 한 줄 요약)

## 2. Completed Tasks
- [x] (Task 1)
- [x] (Task 2)

## 3. Technical Insights (Why & How)
- **Issue**: (문제 상황)
- **Solution**: (해결책 및 원리 설명)
- **Lesson**: (배운 점)

## 4. Next Steps
- [ ] (내일 할 일)
```

## Step 3: Verify & Save
1.  내용이 정확한지 확인하고 파일을 저장합니다.
2.  사용자에게 "오늘의 로그가 작성되었습니다"라고 알립니다.
