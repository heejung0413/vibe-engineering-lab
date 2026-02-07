# Spec Kit 소개

> 난이도: 입문
> 작성일: 2026-02-07
> 수정일: 2026-02-07

## 학습 목표

이 문서를 통해 다음을 배울 수 있습니다:

- Spec Kit이 무엇인지 이해한다
- 명세 기반 개발(Spec-Driven Development)의 개념을 파악한다
- Spec Kit의 핵심 워크플로우를 익힌다
- 설치 및 기본 사용법을 습득한다

## 사전 지식

- 기본적인 커맨드라인(터미널) 사용법
- Git 기초 지식
- 마크다운 문법 이해

## Spec Kit이란?

Spec Kit은 **명세 기반 개발(Spec-Driven Development)**을 지원하는 오픈소스 CLI 도구입니다.

### 기존 방식 vs 명세 기반 개발

| 구분    | 기존 방식 (코드 우선)  | 명세 기반 개발            |
| ------- | ---------------------- | ------------------------- |
| 순서    | 바로 코드 작성 시작    | 명세 작성 → 계획 → 구현   |
| 문서화  | 코드 완성 후 문서 작성 | 문서가 개발의 시작점      |
| AI 활용 | 코드 생성에 집중       | 명세 해석과 구조화에 집중 |

### 핵심 철학

> "명세가 실행 가능해져서 작동 중인 구현으로 직접 변환됩니다"

명세(Specification)가 단순한 참고 문서가 아니라 **개발의 중심**이 됩니다.

## 핵심 워크플로우 (5단계)

Spec Kit은 5개의 핵심 명령어로 구성된 워크플로우를 제공합니다:

```
┌─────────────────┐
│ 1. constitution │  프로젝트 원칙 정의
└────────┬────────┘
         ▼
┌─────────────────┐
│   2. specify    │  기능 요구사항 명세
└────────┬────────┘
         ▼
┌─────────────────┐
│    3. plan      │  기술 스택/아키텍처 계획
└────────┬────────┘
         ▼
┌─────────────────┐
│    4. tasks     │  작업 목록 생성
└────────┬────────┘
         ▼
┌─────────────────┐
│  5. implement   │  실제 구현
└─────────────────┘
```

### 각 단계별 설명

| 단계 | 명령어                  | 목적                                   | 출력물               |
| ---- | ----------------------- | -------------------------------------- | -------------------- |
| 1    | `/speckit.constitution` | 프로젝트의 핵심 원칙과 가이드라인 정의 | constitution.md      |
| 2    | `/speckit.specify`      | 빌드하려는 기능의 요구사항 상세 기술   | spec.md              |
| 3    | `/speckit.plan`         | 기술 스택, 아키텍처, 데이터 모델 설계  | plan.md, research.md |
| 4    | `/speckit.tasks`        | 구현 가능한 작업 목록 자동 생성        | tasks.md             |
| 5    | `/speckit.implement`    | 작업을 순차적으로 실행하여 기능 구현   | 실제 코드            |

## 실습

### 단계 1: 설치

Python 3.11 이상과 uv가 필요합니다.

```bash
# uv 설치 (없는 경우)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Spec Kit 영구 설치 (권장)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

설치 확인:

```bash
specify --help
```

### 단계 2: 새 프로젝트 생성

```bash
# 새 프로젝트 디렉토리 생성
specify init my-project --ai claude

# 또는 현재 디렉토리에서 초기화
specify init . --here --ai claude
```

주요 옵션:

- `--ai`: 사용할 AI 에이전트 지정 (claude, copilot, cursor 등)
- `--here` 또는 `.`: 현재 디렉토리에서 초기화
- `--force`: 확인 없이 진행

### 단계 3: 시스템 체크

```bash
specify check
```

이 명령어는 필요한 도구(Git, Python 등)가 올바르게 설치되었는지 확인합니다.

### 단계 4: 워크플로우 실행

AI 에이전트(예: Claude Code)에서 다음 명령어를 순차적으로 실행:

```
/speckit.constitution 코드 품질과 테스트 중시

/speckit.specify 사용자 로그인 기능 구현

/speckit.plan

/speckit.tasks

/speckit.implement
```

## 지원 AI 에이전트

Spec Kit은 17개 이상의 AI 도구를 지원합니다:

**완전 지원 (슬래시 명령어 사용 가능)**:

- Claude Code
- GitHub Copilot
- Cursor
- Gemini
- Windsurf
- Qwen
- Roo Code

**제한적 지원**:

- Amazon Q Developer CLI (슬래시 명령어 미지원)

## 보조 명령어

기본 5단계 외에 유용한 보조 명령어:

| 명령어               | 목적                      |
| -------------------- | ------------------------- |
| `/speckit.clarify`   | 불명확한 요구사항 명확화  |
| `/speckit.analyze`   | 아티팩트 간 일관성 검증   |
| `/speckit.checklist` | 품질 검증 체크리스트 생성 |

## 정리

- **Spec Kit**은 명세 기반 개발을 지원하는 CLI 도구
- **5단계 워크플로우**: constitution → specify → plan → tasks → implement
- 명세가 단순 문서가 아닌 **개발의 중심**이 됨
- AI 에이전트와 연동하여 구조화된 개발 가능
- 17개 이상의 AI 도구 지원

## 관련 문서

- [Spec Kit 공식 레포지토리](https://github.com/heejung0413/spec-kit)
- [명세 기반 개발 방법론](https://github.com/github/spec-kit/blob/main/spec-driven.md)
