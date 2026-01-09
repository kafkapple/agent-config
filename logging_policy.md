# Logging & Summarization Policy

이 문서는 프로젝트의 진행 상황을 체계적으로 기록하고, 지식을 축적하기 위한 **로깅 시스템**의 규약입니다.

## 1. Structure Hierarchy (계층 구조)

로그는 **시간**과 **압축 수준**에 따라 계층적으로 관리됩니다.

```
~/.agent/logging/
├── daily/                  # Raw Logs (매일 생성)
│   ├── YYYY-MM-DD_ProjectName.md
│   └── ...
├── weekly/                 # Compressed Summaries (주간 요약)
│   ├── YYYY-Www_Summary.md
│   └── ...
└── knowledge_base/         # Condensed Insights (영구 보존)
    ├── patterns.md
    └── architecture.md
```

## 2. Daily Log Protocol (일일 로그)

- **파일명**: `YYYY-MM-DD_{ProjectName}.md`
- **작성 시점**: 하루의 작업을 마칠 때 또는 주요 마일스톤 달성 시.
- **필수 섹션**:
    1.  **One-line Summary**: 오늘의 핵심 성과 (1줄).
    2.  **Completed Tasks**: 구체적으로 완료한 작업 목록.
    3.  **Technical Insights**: 새롭게 알게 된 사실, 트러블슈팅 경험 (How/Why).
    4.  **Next Steps**: 내일 이어갈 작업.

## 3. Aggregation Cycle (요약 주기)

### Level 1: Weekly Compression (주간 압축)
- **Trigger**: 매주 말 또는 Daily Log가 5~7개 쌓였을 때.
- **Action**:
    - 7일치 로그를 읽고 **하나의 주간 요약 문서**(`YYYY-Www_Summary.md`)로 압축합니다.
    - 단순 나열이 아닌, **주제별(Feature, Bug, Refactor)**로 재구성합니다.
    - 기술적 교훈(Insights)은 별도로 추출하여 `memory.md` 또는 `knowledge_base/`에 업데이트할 후보로 선정합니다.

### Level 2: Knowledge Instruction (지식화)
- **Trigger**: 월간 또는 프로젝트 종료 시.
- **Action**:
    - 주간 요약본들을 다시 압축하여 **전역 패턴(Global Patterns)**으로 승격시킵니다.
    - 이는 향후 에이전트가 참고할 `memory.md`의 자산이 됩니다.

## 4. Documentation Style
- **Format**: Markdown
- **Language**: 한국어 요약 위주 + 핵심 키워드 영어.
- **Objective**: "미래의 나(또는 에이전트)가 이 문서를 보고 3초 안에 상황을 파악하고 작업을 이어갈 수 있는가?"
