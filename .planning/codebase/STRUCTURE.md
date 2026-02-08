# Codebase Structure

**Analysis Date:** 2026-02-08

## Directory Layout

```
vibe-engineering-lab/
├── Vibe-Coding/                    # AI 코딩 도구 학습 문서
│   ├── gsd/
│   │   └── gsd-소개.md             # GSD (Get Shit Done) 소개 문서
│   └── speckit/
│       └── speckit-소개.md         # Spec Kit 소개 문서
├── 개발-학습/                      # 일반 개발 학습 문서 (향후 확대)
├── specs/                          # 기능 사양서 및 계획
│   └── 001-learning-docs/          # 학습 문서 기능 명세
│       ├── spec.md                 # 기능 요구사항 명세
│       ├── plan.md                 # 구현 계획
│       ├── data-model.md           # 데이터 모델 및 구조
│       ├── research.md             # 리서치 및 분석
│       ├── quickstart.md           # 빠른 시작 가이드
│       ├── tasks.md                # 구현 작업 목록
│       └── checklists/
│           └── requirements.md     # 요구사항 체크리스트
├── .planning/                      # 코드베이스 분석 및 계획
│   └── codebase/                   # GSD 맵핑된 분석 문서
│       └── (ARCHITECTURE.md, STRUCTURE.md 등)
├── .specify/                       # Spec Kit 설정 및 템플릿
│   ├── memory/
│   │   └── constitution.md         # 프로젝트 원칙 정의
│   └── templates/                  # 문서 템플릿
│       ├── spec-template.md
│       ├── plan-template.md
│       ├── checklist-template.md
│       └── tasks-template.md
├── .claude/                        # Claude Code 설정
│   ├── settings.local.json         # 로컬 설정
│   └── commands/                   # 커스텀 슬래시 명령어
│       ├── speckit.*.md            # Spec Kit 관련 명령어
│       └── (기타 명령어)
├── .obsidian/                      # Obsidian 볼트 설정
│   ├── workspace.json              # 워크스페이스 설정
│   ├── app.json                    # 애플리케이션 설정
│   ├── appearance.json             # 테마 및 외관
│   └── core-plugins.json           # 플러그인 활성화 상태
├── CLAUDE.md                       # 프로젝트 개발 가이드라인
├── .git/                           # Git 저장소
└── .gitignore                      # Git 무시 규칙
```

## Directory Purposes

**Vibe-Coding/:**
- Purpose: AI 코딩 도구 (GSD, Spec Kit, Claude Code 등) 학습 문서 저장
- Contains: 도구별 하위 디렉토리, 각 도구의 한국어 설명 문서
- Key files: `gsd/gsd-소개.md`, `speckit/speckit-소개.md`

**개발-학습/:**
- Purpose: 일반 개발 지식 (프로그래밍 언어, 프레임워크 등) 학습 문서 저장
- Contains: 향후 Python, TypeScript 등 언어별 하위 디렉토리 생성 예정
- Key files: (현재 비어있음, 향후 문서 추가 예정)

**specs/001-learning-docs/:**
- Purpose: 학습 문서 기능의 요구사항 정의 및 구현 계획
- Contains: 기능 사양서, 데이터 모델, 구현 계획, 작업 목록
- Key files: `spec.md` (기능 정의), `plan.md` (구현 계획), `data-model.md` (구조 정의)

**.planning/codebase/:**
- Purpose: GSD `/gsd:map-codebase` 명령어로 생성되는 코드베이스 분석 문서
- Contains: ARCHITECTURE.md, STRUCTURE.md, CONVENTIONS.md, TESTING.md, CONCERNS.md 등
- Key files: 이 디렉토리의 분석 문서들이 `/gsd:plan-phase` 및 `/gsd:execute-phase`에서 참조됨

**.specify/:**
- Purpose: Spec Kit 도구 설정 및 프로젝트 헌법(Constitution) 저장
- Contains: 프로젝트 원칙, 문서 템플릿, 커스텀 명령어
- Key files: `memory/constitution.md` (프로젝트 원칙), `templates/*.md` (문서 템플릿)

**.claude/:**
- Purpose: Claude Code 슬래시 명령어 및 설정
- Contains: Spec Kit 및 GSD 관련 커스텀 명령어, 로컬 설정
- Key files: `commands/speckit.*.md` (Spec Kit 명령어), `settings.local.json` (설정)

**.obsidian/:**
- Purpose: Obsidian 마크다운 에디터 설정 (옵션)
- Contains: 볼트 설정, 테마, 플러그인 활성화 상태
- Key files: `workspace.json`, `appearance.json`

## Key File Locations

**Entry Points:**
- `Vibe-Coding/gsd/gsd-소개.md`: GSD 도구 소개 및 학습 진입점
- `Vibe-Coding/speckit/speckit-소개.md`: Spec Kit 도구 소개 및 학습 진입점
- `specs/001-learning-docs/spec.md`: 학습 문서 기능 요구사항 정의

**Configuration:**
- `CLAUDE.md`: 프로젝트 개발 가이드라인 및 활성 기술 스택
- `.specify/memory/constitution.md`: 프로젝트 핵심 원칙 (한국어 우선, 마크다운 표준 등)
- `.claude/settings.local.json`: Claude Code 로컬 설정

**Core Logic:**
- `specs/001-learning-docs/plan.md`: 구현 계획 및 프로젝트 구조 결정
- `specs/001-learning-docs/data-model.md`: 문서 구조 템플릿 및 엔티티 정의

**Testing/Validation:**
- `specs/001-learning-docs/spec.md`: User Story 및 Acceptance Scenario (테스트 기준)
- `specs/001-learning-docs/checklists/requirements.md`: 요구사항 체크리스트

## Naming Conventions

**Files:**
- Pattern: `[제목]-[설명].md` (한국어 허용)
- Examples: `gsd-소개.md`, `speckit-소개.md`, `data-model.md`
- Convention: 마크다운 파일은 `.md` 확장자, 한국어 파일명 허용

**Directories:**
- Pattern: 영어 또는 한국어 모두 허용, 하이픈 또는 공백으로 단어 구분
- Examples: `Vibe-Coding/`, `개발-학습/`, `gsd/`, `speckit/`
- Convention: 도구명이나 카테고리를 명확하게 나타내는 이름 사용

**Document Frontmatter (메타데이터):**
- Pattern: `> 난이도: [입문/중급/고급]`
- Pattern: `> 작성일: YYYY-MM-DD`
- Pattern: `> 수정일: YYYY-MM-DD`

## Where to Add New Code

**New Learning Document (새 학습 문서):**
- Primary code: `Vibe-Coding/[tool-name]/[document-name].md` (도구 학습) 또는 `개발-학습/[category]/[document-name].md` (일반 개발)
- Structure: 다음 템플릿 따르기:
  ```markdown
  # [제목]

  > 난이도: [입문/중급/고급]
  > 작성일: YYYY-MM-DD
  > 수정일: YYYY-MM-DD

  ## 학습 목표
  [배울 내용 목록]

  ## 사전 지식
  [필요한 배경 지식]

  ## [개념/설명 섹션]
  [핵심 내용]

  ## 실습
  [단계별 예제]

  ## 정리
  [핵심 포인트 요약]

  ## 관련 문서
  [다른 문서 링크]
  ```

**New Tool Category (새 도구 카테고리):**
- Primary code: `Vibe-Coding/[new-tool]/` 디렉토리 생성 후 문서 추가
- Example: `Vibe-Coding/claude-code/` 생성 후 `claude-code-소개.md` 추가

**New Development Language (새 개발 언어):**
- Primary code: `개발-학습/[language]/` 디렉토리 생성 후 문서 추가
- Example: `개발-학습/python/` 생성 후 언어별 학습 문서 추가

**New Feature Specification (새 기능 명세):**
- Primary code: `specs/[phase-number]/` 디렉토리 생성
- Include: `spec.md`, `plan.md`, `data-model.md`, `tasks.md`
- Example: `specs/002-database-docs/` 디렉토리 구조 따르기

## Special Directories

**specs/001-learning-docs/ (Feature Branch: 001-learning-docs):**
- Purpose: 학습 문서 기능의 전체 명세 및 구현 추적
- Generated: No (수동 작성)
- Committed: Yes (Git 추적됨)
- Contents: 기능 요구사항, 구현 계획, 데이터 모델, 작업 목록

**.planning/codebase/:**
- Purpose: `/gsd:map-codebase` 분석 결과 저장
- Generated: Yes (GSD 명령어로 생성)
- Committed: Yes (Git 추적됨)
- Contents: ARCHITECTURE.md, STRUCTURE.md, CONVENTIONS.md, TESTING.md, CONCERNS.md

**.specify/memory/:**
- Purpose: 프로젝트 헌법 및 장기 메모리
- Generated: No (수동 작성)
- Committed: Yes (Git 추적됨)
- Contents: Constitution 원칙, 프로젝트 메모리

**.claude/commands/:**
- Purpose: Claude Code 슬래시 명령어 정의
- Generated: No (수동 작성)
- Committed: Yes (Git 추적됨)
- Contents: Spec Kit, GSD 관련 커스텀 명령어

**.obsidian/:**
- Purpose: Obsidian 볼트 메타데이터
- Generated: Yes (Obsidian에서 생성)
- Committed: Yes (옵션, 협업 시 유용)
- Contents: 설정, 워크스페이스, 플러그인 활성화 상태

## Document Linking Pattern

**Internal Cross-References:**
- Pattern: 상대 경로 마크다운 링크 사용
- Example: `[Spec Kit 소개](../speckit/speckit-소개.md)`
- Convention: `[표시 텍스트](../directory/filename.md)` 형식으로 상대 경로 링크 사용

**Document Organization:**
- 계층적 폴더 구조로 관련 문서 그룹화
- "관련 문서" 섹션에서 명시적 링크 제공
- 학습 순서를 고려한 링크 배치 (기초 → 심화)

---

*Structure analysis: 2026-02-08*
