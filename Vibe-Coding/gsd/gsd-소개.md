# GSD (Get Shit Done) 소개

> 난이도: 입문
> 작성일: 2026-02-07
> 수정일: 2026-02-07

## 학습 목표

이 문서를 통해 다음을 배울 수 있습니다:

- GSD가 무엇인지 이해한다
- 컨텍스트 엔지니어링(Context Engineering)의 개념을 파악한다
- GSD의 6단계 워크플로우를 익힌다
- 설치 및 기본 사용법을 습득한다

## 사전 지식

- 기본적인 커맨드라인(터미널) 사용법
- Git 기초 지식
- Claude Code 또는 유사 AI 코딩 도구 경험

## GSD란?

**GSD (Get Shit Done)**는 Claude Code, OpenCode, Gemini CLI를 위한 **메타 프롬프팅 및 컨텍스트 엔지니어링 시스템**입니다.

### 해결하는 문제

AI 코딩 도구를 사용할 때 흔히 겪는 문제:

| 문제 | 원인 | GSD의 해결책 |
|------|------|-------------|
| AI 응답 품질 저하 | 컨텍스트 윈도우가 채워지면서 발생 | 각 작업마다 200K 토큰의 신선한 컨텍스트 제공 |
| 복잡한 작업 관리 어려움 | 큰 작업을 한 번에 처리하려 함 | 원자적(atomic) 작업 단위로 분할 |
| 일관성 없는 결과물 | 명확한 명세 없이 진행 | 체계적인 명세 기반 개발 |

### 핵심 철학

> "가볍지만 강력한 (Light-weight and Powerful)"

복잡한 엔터프라이즈 프로세스 없이도 효율적인 개발 워크플로우를 제공합니다.

## 핵심 개념

### 1. 멀티 에이전트 오케스트레이션

GSD는 각 단계마다 특화된 에이전트들을 사용합니다:

```
┌─────────────┐
│  리서처     │  스택, 아키텍처, 함정 조사 (4개 병렬)
└──────┬──────┘
       ▼
┌─────────────┐
│  플래너     │  계획 생성 및 검증
└──────┬──────┘
       ▼
┌─────────────┐
│  실행자     │  원자적 작업 구현 (각각 200K 토큰)
└──────┬──────┘
       ▼
┌─────────────┐
│  검증자     │  요구사항 대비 검증 및 디버깅
└─────────────┘
```

### 2. XML 기반 작업 구조

모든 작업은 명확한 XML 구조로 정의됩니다:

```xml
<task type="auto">
  <name>사용자 인증 구현</name>
  <files>src/auth/login.ts</files>
  <action>JWT 기반 로그인 로직 구현</action>
  <verify>로그인 성공 시 토큰 반환 확인</verify>
  <done>테스트 통과 및 코드 리뷰 완료</done>
</task>
```

### 3. 컨텍스트 파일 시스템

GSD는 다음 파일들을 자동으로 관리합니다:

| 파일 | 용도 | 항상 로드 |
|------|------|----------|
| `PROJECT.md` | 프로젝트 비전과 목표 | ✅ |
| `REQUIREMENTS.md` | v1/v2 요구사항 | ✅ |
| `ROADMAP.md` | 진행 상황 추적 | - |
| `STATE.md` | 의사결정, 세션 간 메모리 | - |
| `research/` | 생태계 지식 | - |
| `todos/` | 나중 작업용 아이디어 | - |

## 핵심 워크플로우 (6단계)

### 전체 흐름

```
┌──────────────────┐
│ 1. new-project   │  프로젝트 초기화
└────────┬─────────┘
         ▼
┌──────────────────┐
│ 2. discuss-phase │  의사결정 캡처
└────────┬─────────┘
         ▼
┌──────────────────┐
│ 3. plan-phase    │  리서치 + 계획
└────────┬─────────┘
         ▼
┌──────────────────┐
│ 4. execute-phase │  병렬 실행
└────────┬─────────┘
         ▼
┌──────────────────┐
│ 5. verify-work   │  사용자 검증
└────────┬─────────┘
         ▼
┌──────────────────┐
│ 6. 반복/완료     │  다음 단계 또는 릴리스
└──────────────────┘
```

### 각 단계별 설명

| 단계 | 명령어 | 목적 | 출력물 |
|------|--------|------|--------|
| 1 | `/gsd:new-project` | 프로젝트 초기화, 질문, 리서치, 요구사항 정의 | PROJECT.md, REQUIREMENTS.md, ROADMAP.md, STATE.md |
| 2 | `/gsd:discuss-phase [N]` | 구현 전 의사결정 캡처 | {phase}-CONTEXT.md |
| 3 | `/gsd:plan-phase [N]` | 리서치 + 계획 + 검증 | {phase}-RESEARCH.md, {phase}-{N}-PLAN.md |
| 4 | `/gsd:execute-phase <N>` | 병렬 실행 및 개별 커밋 | {phase}-{N}-SUMMARY.md, {phase}-VERIFICATION.md |
| 5 | `/gsd:verify-work [N]` | 사용자 수용 테스팅 (UAT) | {phase}-UAT.md |
| 6 | `/gsd:complete-milestone` | 마일스톤 아카이빙, 릴리스 태깅 | - |

## 실습

### 단계 1: 설치

```bash
# 대화식 설치
npx get-shit-done-cc
```

설치 중 선택 사항:
1. **런타임**: Claude Code, OpenCode, Gemini CLI, 또는 모두
2. **위치**: 전역(`~/.claude/`) 또는 로컬(`./.claude/`)

비대화식 설치:

```bash
# Claude Code - 전역 설치 (권장)
npx get-shit-done-cc --claude --global

# Claude Code - 로컬 설치
npx get-shit-done-cc --claude --local

# 모든 런타임
npx get-shit-done-cc --all --global
```

### 단계 2: 권장 설정

Skip Permissions 모드 사용 (매번 승인 요청 방지):

```bash
claude --dangerously-skip-permissions
```

### 단계 3: 새 프로젝트 시작

```bash
# Claude Code에서 실행
/gsd:new-project
```

이 명령어가 수행하는 작업:
1. 아이디어에 대해 질문
2. 병렬 에이전트가 도메인 리서치
3. v1, v2, 범위 외 요구사항 분류
4. 로드맵 생성

### 단계 4: 단계별 개발

```bash
# 1단계 의사결정 논의
/gsd:discuss-phase 1

# 1단계 계획 수립
/gsd:plan-phase 1

# 1단계 실행
/gsd:execute-phase 1

# 1단계 검증
/gsd:verify-work 1

# 2단계로 반복...
/gsd:discuss-phase 2
```

## 주요 명령어 정리

### 핵심 워크플로우

| 명령어 | 기능 |
|--------|------|
| `/gsd:new-project` | 전체 프로젝트 초기화 |
| `/gsd:discuss-phase [N]` | 구현 의사결정 캡처 |
| `/gsd:plan-phase [N]` | 리서치 + 계획 + 검증 |
| `/gsd:execute-phase <N>` | 병렬 실행 및 커밋 |
| `/gsd:verify-work [N]` | 사용자 검증 |
| `/gsd:quick` | 빠른 ad-hoc 작업 |

### 네비게이션

| 명령어 | 기능 |
|--------|------|
| `/gsd:progress` | 현재 위치 및 다음 단계 확인 |
| `/gsd:help` | 모든 명령어 및 사용 가이드 |
| `/gsd:map-codebase` | 기존 코드베이스 분석 |

### 단계 관리

| 명령어 | 기능 |
|--------|------|
| `/gsd:add-phase` | 로드맵에 단계 추가 |
| `/gsd:insert-phase [N]` | 긴급 작업 삽입 |
| `/gsd:remove-phase [N]` | 미래 단계 제거 |

## GSD vs Spec Kit 비교

| 특성 | GSD | Spec Kit |
|------|-----|----------|
| 초점 | 컨텍스트 관리 + 실행 | 명세 작성 + 계획 |
| 에이전트 | 멀티 에이전트 (리서처, 플래너, 실행자, 검증자) | 단일 에이전트 |
| 작업 단위 | XML 기반 원자적 작업 | 태스크 목록 (tasks.md) |
| 커밋 전략 | 작업당 개별 커밋 | 수동 커밋 |
| 검증 | 내장 UAT 워크플로우 | checklist, analyze 명령어 |

두 도구는 상호 보완적으로 사용할 수 있습니다.

## 정리

- **GSD (Get Shit Done)**는 AI 코딩 도구를 위한 컨텍스트 엔지니어링 시스템
- **컨텍스트 로트 문제 해결**: 각 실행자가 200K 토큰의 신선한 컨텍스트 사용
- **6단계 워크플로우**: new-project → discuss → plan → execute → verify → 반복
- **멀티 에이전트**: 리서처, 플래너, 실행자, 검증자로 역할 분담
- **원자적 커밋**: 각 작업마다 개별 커밋으로 추적 용이

## 관련 문서

- [GSD 공식 레포지토리](https://github.com/glittercowboy/get-shit-done)
- [GSD Discord 커뮤니티](https://discord.gg/5JJgD5svVS)
- [Spec Kit 소개](../speckit/speckit-소개.md)
