# Antigravity & Agent Global Configuration

이 저장소는 **Antigravity, Gemini, Claude Code** 등 AI 코딩 에이전트가 공통으로 참조할 수 있는 **전역 설정(Global Configuration)**을 관리합니다.
**교육적 멘토링**, **체계적 로깅**, **기술적 표준**을 강제하여 에이전트를 단순한 코더가 아닌 "Senior Partner"로 격상시키는 것을 목표로 합니다.

## 📂 Directory Structure

- **[`rules.md`](./rules.md)**: **The Constitution**. 에이전트의 페르소나, 인지 프로토콜, 언어 규칙 정의. (필수 로드)
- **[`logging_policy.md`](./logging_policy.md)**: 프로젝트 로그/회고 시스템 규약.
- **[`memory.md`](./memory.md)**: 전역적 선호도 및 교훈 저장소.
- **[`workflows/`](./workflows/)**:
    - [`dev_routine.md`](./workflows/dev_routine.md): 기능 구현 표준 워크플로우 (Plan -> Skeleton -> Logic -> Test)
    - [`create_daily_log.md`](./workflows/create_daily_log.md): 일일 로그 작성
    - [`weekly_aggregation.md`](./workflows/weekly_aggregation.md): 주간 로그 압축
- **[`templates/`](./templates/)**:
    - [`architecture.md`](./templates/architecture.md): 프로젝트 구조 파악용
    - [`project_readme.md`](./templates/project_readme.md): 표준 README 서식
    - [`standard_gitignore`](./templates/standard_gitignore): 표준 Git 제외 목록

---

## 🛠️ 1. Setup (설정 방법)

Antigravity에 이 설정을 적용하는 두 가지 방법이 있습니다.

### Method A: Global Instruction (권장)
모든 프로젝트에서 항상 이 규칙을 적용하려면 Antigravity 설정에 등록합니다.

1.  Antigravity 우측 하단 **Settings** 아이콘 클릭.
2.  **Agent** > **Manage** > **Global Instructions** 입력란에 아래 내용 복사:
    ```markdown
    # SYSTEM: Global Agent Protocol
    Load & Follow: ~/.agent/rules.md

    ## Core Protocols
    1. **Cognitive Process**: [Plan] -> [Global/Local View] -> [Multi-Persona Review] -> [Execute]
    2. **Verification**: No Code Without Verification (Test/Script).
    3. **Persona**: Educational Mentor (Why -> How -> What).
    4. **Memory**: Check `~/.agent/memory.md` generally.
    ```

### Method B: Symlink (프로젝트별 적용)
특정 프로젝트에서만 적용하거나 파일 시스템 기반으로 확실하게 참조시키려면, 프로젝트 루트에 심볼릭 링크를 생성합니다.

```bash
cd /path/to/your/project
ln -s ~/.agent ./.agent
```
*에이전트가 `.agent` 폴더를 발견하면 자동으로 규칙을 읽을 가능성이 높습니다.*

---

## 💻 2. Usage Examples (사용 예시)

설정 적용 후, 에이전트와 대화하는 모범 사례입니다.

### Case A: New Feature (기능 구현)
> "새로운 로그인 페이지를 만들어줘. `dev_routine` 워크플로우를 따라가고, `architecture.md`를 참고해."

**Agent 행동**:
1.  `<plan>` 블록을 출력하여 설계 (Plan).
2.  HTML/CSS 스켈레톤 작성 (Skeleton).
3.  JS 로직 연결 및 단위 테스트 작성 (Logic + Test).
4.  최종 검증 및 `git commit` 제안 (Polish).

### Case B: Refactoring (리팩토링)
> "이 `AuthService` 클래스가 너무 비대해. `rules.md`의 모듈화 원칙에 따라 리팩토링 해줘. 다중 관점(Multi-Persona)으로 검토해줘."

**Agent 행동**:
1.  **Zoom Out**: 전체 인증 흐름에 미치는 영향 분석.
2.  **Multi-Persona**: "아키텍트 관점에서는 분리가 좋지만, 보안 관점에서는 세션 처리가 복잡해질 수 있음" 경고.
3.  안전한 리팩토링 수행.

### Case C: Debugging (디버깅)
> "로그인이 안 돼. `logging_policy.md`에 따라 오늘의 에러를 분석하고 기록해줘."

**Agent 행동**:
1.  문제 원인 파악 (Why).
2.  해결책 제시 (How).
3.  `daily/YYYY-MM-DD.md` 파일에 `Technical Insights` 항목으로 기록.

---

## 🎨 3. Customization (규칙 확장)

프로젝트마다 특별한 규칙이 필요할 수 있습니다. `~/.agent`를 직접 수정하지 말고, 프로젝트 내에 확장 파일을 만드세요.

1.  프로젝트 루트에 `.agent/project_rules.md` 생성 (GitIgnore 처리 권장 안 함).
2.  내용 작성:
    ```markdown
    # Project Specific Rules
    - 이 프로젝트는 `rules.md`를 따르되, 다음 예외를 둡니다.
    - **Language**: 주석도 모두 한글로 작성하세요 (팀 규칙).
    - **Framework**: TailwindCSS 대신 Styled-Components만 사용 필수.
    ```
3.  프롬프트에 추가: "Global Rule과 Project Rule을 모두 참고해."

---

## 📚 4. References & Benchmarks

이 설정은 다음 웹 검색 결과와 업계 표준을 기반으로 설계되었습니다.

| Category | Source Keywords | Applied Features |
| :--- | :--- | :--- |
| **Persona** | `Senior Developer System Prompts` ([Medium](https://medium.com), [DSStream](https://dsstream.com)) | **Role Definition**: "Code Monkey"가 아닌 "Educational Mentor"로 설정. `Why->How->What` 설명 구조 채택. |
| **Verification** | `Cursor Rules for Production` ([Cursor.directory](https://cursor.directory), [TrueNorth](https://truenorthdevllc.com)) | **Test Protocol**: 모든 로직 변경 시 테스트 필수 (Test First/Beside). **Explicit Context**: `@file` 등 명시적 참조 강조. |
| **Architecture** | `Large Project AI Patterns` ([Google](https://google.com), [BitSrc](https://bitsrc.io)) | **Pre-Computation**: 작업 전 `<plan>` 수립 및 Macro/Micro View 조망. **Memory**: `memory.md`를 통한 장기적 패턴 학습. |
| **Workflow** | `Chain of Thought`, `TDD` | **Dev Routine**: 단계적 구현(Skeleton -> Logic) 및 `<plan>` 강제 출력. |
