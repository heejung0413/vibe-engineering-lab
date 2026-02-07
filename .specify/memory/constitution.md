<!--
================================================================================
SYNC IMPACT REPORT
================================================================================
Version change: N/A (initial) → 1.0.0
Modified principles: N/A (initial creation)
Added sections:
  - Core Principles (5 principles for learning documentation)
  - 문서 작성 규칙 (Documentation Rules)
  - 학습 워크플로우 (Learning Workflow)
  - Governance
Removed sections: N/A
Templates requiring updates:
  - .specify/templates/plan-template.md: ⚠️ pending (Constitution Check section generic)
  - .specify/templates/spec-template.md: ✅ compatible (no changes needed)
  - .specify/templates/tasks-template.md: ✅ compatible (no changes needed)
Follow-up TODOs: None
================================================================================
-->

# Vibe Engineering Lab Constitution

## Core Principles

### I. 한국어 우선 (Korean First)

모든 학습 문서는 한국어로 작성한다.
- 기술 용어는 영어 원문을 병기할 수 있음 (예: "컴포넌트(Component)")
- 코드 예제 내 주석은 한국어로 작성
- 파일명은 영어 또는 영어-한국어 혼용 가능

### II. 마크다운 표준 (Markdown Standard)

모든 문서는 `.md` 파일 형식으로 작성한다.
- GitHub Flavored Markdown(GFM) 규격 준수
- 코드 블록에는 언어 지정 필수 (예: ```python)
- 이미지는 상대 경로 또는 외부 링크 사용

### III. 실습 중심 (Practice-Oriented)

학습 문서는 이론보다 실습 예제를 우선한다.
- 개념 설명 후 반드시 코드 예제 또는 실습 단계 포함
- "따라하기" 형식의 단계별 가이드 권장
- 실제 동작하는 코드 스니펫 제공

### IV. 구조화된 학습 (Structured Learning)

문서는 일관된 구조를 유지한다.
- 학습 목표 → 개념 설명 → 실습 → 정리 순서
- 각 문서는 하나의 주제에 집중
- 관련 문서 간 링크로 연결

### V. 점진적 심화 (Progressive Depth)

콘텐츠는 기초부터 심화까지 단계적으로 구성한다.
- 초보자도 이해할 수 있는 시작점 제공
- 난이도 표시 권장 (예: 입문/중급/고급)
- 사전 지식 요구사항 명시

## 문서 작성 규칙

- 한 문서의 길이는 가독성을 위해 적정 수준 유지
- 코드 예제는 복사-붙여넣기로 바로 실행 가능해야 함
- 외부 참조 시 출처 명시
- 최신 정보 유지를 위해 작성일/수정일 기록 권장

## 학습 워크플로우

1. **주제 선정**: 바이브코딩 또는 코딩 학습 중 기록할 내용 선택
2. **문서 작성**: 마크다운 형식으로 학습 내용 정리
3. **코드 검증**: 포함된 코드 예제가 실제 동작하는지 확인
4. **리뷰 및 개선**: 작성된 문서의 명확성과 완성도 점검

## Governance

이 Constitution은 프로젝트의 모든 문서 작성에 우선 적용된다.
- 원칙 수정 시 이 파일을 먼저 업데이트하고 버전을 갱신한다
- 버전 관리: MAJOR.MINOR.PATCH (Semantic Versioning)
  - MAJOR: 핵심 원칙 삭제 또는 근본적 변경
  - MINOR: 새 원칙 추가 또는 상세 지침 확장
  - PATCH: 문구 수정, 오타 교정, 비핵심적 개선
- 모든 기여자는 Constitution 준수 여부를 자가 점검한다

**Version**: 1.0.0 | **Ratified**: 2026-02-07 | **Last Amended**: 2026-02-07
