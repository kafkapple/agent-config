---
description: 표준 기능 개발 절차 (Small Commits Pattern)
---

# Development Routine: Small Commits

이 워크플로우는 `rules.md`의 **Small Commits** 원칙을 시스템적으로 수행하기 위한 가이드입니다.

## Step 1: Plan & Design
1.  사용자의 요청을 분석하고 **Implementation Plan**을 작성합니다.
2.  **Chat Output Requirement**: 대화창에 반드시 다음과 같은 `<plan>` 블록을 출력하여 명시적인 계획을 세웁니다.
    ```xml
    <plan>
    1. [User Request] Analysis...
    2. [Architecture] Impact on global system...
    3. [Step-by-Step] ...
    </plan>
    ```
3.  사용자에게 승인을 요청합니다.

## Step 2: Skeleton Implementation
// Focus: Structure (HTML/View), No Logic
1.  UI 컴포넌트구조 또는 기본 클래스/인터페이스만 정의합니다.
2.  스타일(CSS)이나 로직(Functions)은 비어있거나 모의(Mock) 상태로 둡니다.
3.  이 단계에서 파일 생성/배치가 올바른지 확인합니다.

## Step 3: Logic Connection (with Test)
// Focus: Functionality (TS/JS/Python) & Verification
1.  **Test First/Beside**: 가능하면 실패하는 테스트 케이스를 먼저 작성하거나, 최소한 검증 스크립트를 준비합니다.
2.  실제 비즈니스 로직을 구현하여 Step 2의 구조와 연결합니다.
3.  **Verify**: 작성한 테스트를 실행하여 Pass를 확인합니다. (터미널 실행 결과 확인 필수)

## Step 4: Polish & Refine
// Focus: UX/UI, Optimization, Cleanup
1.  CSS 스타일링을 다듬습니다.
2.  코드 포맷팅, 주석(English), 불필요한 로그를 정리합니다.
## Step 5: Git Checkpoint (Version Control)
1.  작업 단위(Feature/Fix)가 완성되면 사용자에게 **Git Commit**을 제안합니다.
    ```bash
    git add src/changed_file.py
    git commit -m "feat: implement login logic with validation"
    ```
2.  가능하면 사용자가 그대로 복사/붙여넣기 할 수 있는 명령어를 제공합니다.
