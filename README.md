# Vibe Engineering Lab

Claude Code와 AI 페어 프로그래밍을 위한 학습 및 실험 공간입니다.

## 개요

"Vibe Coding"을 넘어 Claude와 체계적으로 협업하기 위한 도구, 방법론, 스킬을 학습하고 실험합니다.

### 다루는 주제

- **Claude Code 기본**: MCP 서버, 페르소나 시스템, 명령어 체계
- **개발 방법론**: GSD, Spec Kit, SDD 등 AI 협업 워크플로우
- **MCP (Model Context Protocol)**: Context7, Sequential, Magic, Playwright 통합
- **SuperClaude 프레임워크**: 고급 명령어, 플래그, 오케스트레이션 패턴
- **실전 스킬**: 커밋 자동화, 문서 생성, 플로우 다이어그램, Daily Log 등

## 프로젝트 구조

```
vibe-engineering-lab/
├── Vibe-Coding/              # AI 개발 방법론 학습 문서
│   ├── gsd/                  # GSD 시스템
│   └── speckit/              # Spec Kit 도구
├── docs/                     # 학습 문서
│   ├── mcp/                  # MCP 서버 가이드
│   │   └── context7-mcp-guide.md
│   ├── skills/               # Claude 스킬 문서
│   └── SDD-vs-GSD.md         # 방법론 비교
├── specs/                    # 기능 명세
│   └── 001-learning-docs/
├── .planning/                # GSD 계획 문서
│   └── codebase/             # 코드베이스 분석
└── .specify/                 # Spec Kit 설정
```

## 학습 문서

### Claude Code 기본

| 카테고리 | 문서 | 설명 |
|----------|------|------|
| MCP 서버 | [Context7 가이드](docs/mcp/context7-mcp-guide.md) | 라이브러리 문서, 패턴, 베스트 프랙티스 제공 |
| MCP 서버 | Sequential, Magic, Playwright | 복잡한 분석, UI 생성, E2E 테스팅 |
| 페르소나 | Architect, Frontend, Backend 등 | 도메인별 전문 AI 페르소나 11종 |
| 명령어 | `/implement`, `/analyze`, `/improve` 등 | 작업별 최적화된 워크플로우 |

### 개발 방법론

| 문서 | 설명 |
|------|------|
| [GSD 소개](Vibe-Coding/gsd/gsd-소개.md) | Get Shit Done - 컨텍스트 엔지니어링 기반 개발 |
| [Spec Kit 소개](Vibe-Coding/speckit/speckit-소개.md) | 명세 중심 개발 CLI 도구 |
| [SDD vs GSD 비교](docs/SDD-vs-GSD.md) | 방법론 철학과 차이점 분석 |

### 실전 스킬 (Claude Code Skills)

프로젝트에 설치된 스킬들:

- **git-auto**: Git 커밋 메시지 자동 생성 및 push
- **seq-diagram**: Mermaid 시퀀스 다이어그램 생성
- **daily-log-github**: 커밋 활동 분석 후 GitHub Issue 생성
- **flow-doc**: API 요청/응답 흐름 문서화
- **git-report**: 일일 커밋 리포트 생성

## 시작하기

### Claude Code 기본 사용

```bash
# MCP 서버 자동 활성화 예시
/implement "React 컴포넌트"  # → Magic + Context7 활성화
/analyze --focus security     # → Sequential 활성화

# 페르소나 명시적 지정
/build --persona-frontend
/improve --persona-performance

# 스킬 사용
/git-auto "기능 구현 완료"
/seq-diagram src/api/auth.ts
```

### 개발 도구 설치

```bash
# GSD (Get Shit Done)
npx get-shit-done-cc --claude --global

# Spec Kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

### 워크플로우 예시

```bash
# GSD 방식: 단계별 오케스트레이션
/gsd:new-project
/gsd:plan-phase
/gsd:execute-phase

# Spec Kit 방식: 명세 중심 개발
specify init . --here --ai claude
speckit.specify "새 기능 설명"
speckit.implement
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

## 학습 로드맵

1. **Claude Code 기초**
   - MCP 서버 이해 (Context7, Sequential, Magic, Playwright)
   - 페르소나 시스템 활용
   - 기본 명령어 숙지

2. **스킬 활용**
   - git-auto, seq-diagram 등 실전 스킬 사용
   - 커스텀 스킬 개발

3. **개발 방법론**
   - GSD: 대규모 프로젝트, 체계적 접근
   - Spec Kit: 명세 중심, 빠른 프로토타이핑

4. **고급 패턴**
   - SuperClaude 프레임워크
   - 멀티 에이전트 오케스트레이션
   - 플래그 조합 및 최적화

## 참고 자료

### Claude Code 공식
- [Claude Code CLI 문서](https://docs.anthropic.com/claude-code)
- [MCP 프로토콜 사양](https://modelcontextprotocol.io)

### 커뮤니티 도구
- [GSD 공식 레포지토리](https://github.com/glittercowboy/get-shit-done)
- [Spec Kit 공식 레포지토리](https://github.com/github/spec-kit)
- [GSD Discord 커뮤니티](https://discord.gg/5JJgD5svVS)

## 라이선스

MIT License
