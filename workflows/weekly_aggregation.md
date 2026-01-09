---
description: 주간 로그 요약 및 지식 압축 워크플로우
---

# Workflow: Weekly Aggregation

매주 말, 또는 Daily Log가 7개 이상 쌓였을 때 실행합니다.

## Step 1: Review Daily Logs
1.  `~/.agent/logging/daily/` 폴더의 최근 7일치 로그를 읽습니다.
2.  공통된 패턴, 반복된 실수, 주요 성과를 파악합니다.

## Step 2: Compress & Categorize
`~/.agent/logging/weekly/YYYY-W{WeekNum}_Summary.md` 파일을 생성합니다.

- **Tasks**: 날짜별 나열이 아닌, **기능(Feature)** 단위로 묶어서 요약합니다.
- **Insights**: 개별 로그의 Insight를 통합하여 **일반화된 지식**으로 정제합니다.

## Step 3: Update Global Memory (Optional)
- 주간 요약 중, 프로젝트를 넘어서 계속 기억해야 할 중요한 원칙이 있다면 `~/.agent/memory.md`에 추가합니다.

## Step 4: Archive
- 처리가 끝난 Daily Log들은 `~/.agent/logging/daily/archived/` 폴더(필요 시 생성)로 이동시키거나 유지합니다.
