# Vibe Engineering Lab

AI 기반 개발 방법론과 도구를 학습하고 실험하는 연구 공간입니다.

## 개요

"Vibe Coding"의 한계를 극복하고, AI 코딩 도구를 체계적으로 활용하기 위한 방법론들을 탐구합니다.

### 다루는 주제

- **SDD (Spec-Driven Development)**: 명세 중심 개발 방법론
- **GSD (Get Shit Done)**: 컨텍스트 엔지니어링 기반 실용적 개발 시스템
- **Spec Kit**: 명세 기반 개발 CLI 도구
- **AI 코딩 도구 비교 및 활용법**

## 프로젝트 구조

```
vibe-engineering-lab/
├── Vibe-Coding/              # AI 개발 방법론 학습 문서
│   ├── gsd/                  # GSD 관련 문서
│   │   └── gsd-소개.md
│   └── speckit/              # Spec Kit 관련 문서
│       └── speckit-소개.md
├── docs/                     # 추가 문서
│   └── SDD-vs-GSD.md         # SDD와 GSD 비교 분석
├── specs/                    # 기능 명세 및 계획
│   └── 001-learning-docs/    # 학습 문서 프로젝트 명세
├── .planning/                # GSD 프로젝트 계획 문서
│   └── codebase/             # 코드베이스 분석 문서
└── .specify/                 # Spec Kit 설정 및 템플릿
```

## 학습 문서

### 방법론 소개

| 문서 | 설명 |
|------|------|
| [GSD 소개](Vibe-Coding/gsd/gsd-소개.md) | Get Shit Done 시스템 입문 가이드 |
| [Spec Kit 소개](Vibe-Coding/speckit/speckit-소개.md) | Spec Kit CLI 도구 입문 가이드 |
| [SDD vs GSD 비교](docs/SDD-vs-GSD.md) | 두 방법론의 철학과 차이점 분석 |

### 핵심 개념

#### GSD (Get Shit Done)

Claude Code를 위한 컨텍스트 엔지니어링 시스템

```
new-project → discuss-phase → plan-phase → execute-phase → verify-work
```

**특징**:
- 멀티 에이전트 오케스트레이션 (리서처, 플래너, 실행자, 검증자)
- 원자적 작업 단위로 분할
- 작업당 개별 커밋

#### Spec Kit

명세 기반 개발 CLI 도구

```
constitution → specify → plan → tasks → implement
```

**특징**:
- 명세가 개발의 중심
- 17개 이상의 AI 도구 지원
- 구조화된 5단계 워크플로우

## 시작하기

### GSD 설치

```bash
npx get-shit-done-cc --claude --global
```

### Spec Kit 설치

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

### 프로젝트 초기화

```bash
# GSD 방식
/gsd:new-project

# Spec Kit 방식
specify init . --here --ai claude
```

## 코드베이스 분석

`.planning/codebase/` 디렉토리에 자동 생성된 분석 문서:

| 문서 | 내용 |
|------|------|
| STACK.md | 기술 스택, 의존성 |
| ARCHITECTURE.md | 시스템 설계, 패턴 |
| STRUCTURE.md | 디렉토리 구조 |
| CONVENTIONS.md | 코드 스타일, 규칙 |
| TESTING.md | 테스트 구조 |
| INTEGRATIONS.md | 외부 서비스 연동 |
| CONCERNS.md | 기술 부채, 개선점 |

## 참고 자료

- [GSD 공식 레포지토리](https://github.com/glittercowboy/get-shit-done)
- [Spec Kit 공식 레포지토리](https://github.com/github/spec-kit)
- [GSD Discord 커뮤니티](https://discord.gg/5JJgD5svVS)

## 라이선스

MIT License
