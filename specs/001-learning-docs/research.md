# Research: 바이브코딩 및 개발 학습 문서

**Feature**: 001-learning-docs
**Date**: 2026-02-07

## 연구 주제

### 1. Spec Kit 도구 분석

**Decision**: Spec Kit은 명세 기반 개발(Spec-Driven Development)을 지원하는 오픈소스 CLI 도구

**Rationale**:
- 기존 "코드 우선" 방식 대신 "명세 우선" 방식 채택
- AI 에이전트와 연동하여 구조화된 개발 워크플로우 제공
- 17개 이상의 AI 도구 지원 (Claude Code, GitHub Copilot, Cursor 등)

**Alternatives considered**:
- 일반 프로젝트 템플릿: 명세 기반 워크플로우 미지원
- 수동 문서화: 일관성 부족, 자동화 미흡

### 2. 핵심 워크플로우 (5단계)

| 단계 | 명령어 | 목적 |
|------|--------|------|
| 1 | `/speckit.constitution` | 프로젝트 원칙 및 가이드라인 정의 |
| 2 | `/speckit.specify` | 기능 요구사항 명세 작성 |
| 3 | `/speckit.plan` | 기술 스택과 아키텍처 계획 |
| 4 | `/speckit.tasks` | 실행 가능한 작업 목록 생성 |
| 5 | `/speckit.implement` | 작업 실행 및 기능 구현 |

### 3. 설치 방법

**Decision**: uv 도구를 사용한 설치 권장

```bash
# 영구 설치 (권장)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# 일회성 실행
uvx --from git+https://github.com/github/spec-kit.git specify init my-project
```

**Requirements**:
- Python 3.11 이상
- Git
- uv (Python 패키지 관리자)

### 4. 지원 AI 에이전트

**완전 지원**:
- Claude Code
- GitHub Copilot
- Cursor
- Gemini
- Windsurf
- Qwen
- Roo Code

**제한적 지원**:
- Amazon Q Developer CLI (슬래시 명령어 미지원)

## 결론

Spec Kit은 바이브코딩 학습에 핵심적인 도구로, 구조화된 개발 방법론을 제공한다. 이 프로젝트의 첫 번째 학습 문서로 Spec Kit 사용법을 정리하는 것이 적절하다.
