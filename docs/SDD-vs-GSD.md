# SDD vs GSD: AI 기반 개발 방법론 비교

## 개요

AI 코딩 도구의 발전과 함께 "Vibe Coding"의 한계를 극복하기 위한 체계적인 개발 방법론들이 등장했습니다. 대표적으로 **SDD(Spec-Driven Development)**와 **GSD(Get Shit Done)**가 있으며, 각각 다른 철학과 접근 방식을 가지고 있습니다.

---

## SDD (Spec-Driven Development)

### 정의

SDD는 **명세(Specification)를 중심**으로 하는 개발 방법론입니다. 코드가 아닌 명세가 "단일 진실 공급원(Single Source of Truth)"이 되어, 설계 → 명세 작성 → 구현의 순서로 진행됩니다.

### 핵심 원칙

1. **명세 우선**: 코드 작성 전 요구사항을 Markdown 파일로 정형화
2. **설계와 구현 분리**: 계획 단계에서 AI가 설계 문서 생성, 검토 후 구현
3. **Human-in-the-Loop**: 명세 검토 및 검증에 인간 개입 필수
4. **실행 가능한 계약**: 명세 자체가 테스트 가능한 계약서 역할

### 대표 도구

- **BMAD**: 엔터프라이즈 팀을 위한 종합적 SDD 프레임워크
- **GitHub Spec-Kit**: GitHub 기반 명세 관리 도구
- **Kiro**: AWS의 SDD 지원 IDE

### 장점

- 대규모 팀에서 일관된 개발 프로세스 유지
- 요구사항 추적성 확보
- 문서화가 자연스럽게 동반됨

### 단점

- 높은 초기 오버헤드
- Waterfall 시대의 "문서 먼저" 접근법 재현이라는 비판
- 레거시 코드베이스에 도입이 어려움
- 프로젝트가 커질수록 명세와 코드 간 괴리 발생 가능

---

## GSD (Get Shit Done)

### 정의

GSD는 **실용성과 단순함**을 최우선으로 하는 개발 방법론입니다. 복잡한 워크플로우 없이 AI 코딩 도구(특히 Claude Code)를 효과적으로 활용하는 데 초점을 맞춥니다.

### 탄생 배경

> "나는 솔로 개발자다. 코드를 직접 작성하지 않는다 - Claude Code가 한다. 그런데 다른 SDD 도구들은 스프린트 세레모니, 스토리 포인트, 회고, Jira 워크플로우로 모든 걸 복잡하게 만드는 것 같았다."

### 핵심 철학

```
복잡성은 시스템 안에 있다, 당신의 워크플로우에 있지 않다.

뒷단에서: 컨텍스트 엔지니어링, XML 프롬프트 포맷팅, 서브에이전트 오케스트레이션, 상태 관리
사용자가 보는 것: 그냥 작동하는 몇 가지 명령어
```

### 주요 특징

1. **최소한의 학습 곡선**: 복잡한 설정 없이 바로 시작
2. **컨텍스트 엔지니어링**: AI가 일관된 결과를 내도록 문맥 관리
3. **서브에이전트 병렬 처리**: 복잡한 작업을 병렬로 분산 처리
4. **상태 관리**: 세션 간 컨텍스트 유지

### 작동 방식

| 단계 | 설명 |
|------|------|
| `map-codebase` | 기존 코드베이스 분석 및 문서화 |
| `new-project` | 프로젝트 초기화 및 로드맵 생성 |
| `plan-phase` | 각 단계별 실행 계획 수립 |
| `execute-phase` | 계획에 따른 자동 실행 |
| `verify-work` | 결과물 검증 |

### 장점

- 솔로 개발자나 소규모 팀에 최적화
- 즉시 생산성 확보
- "엔터프라이즈 역할극" 없이 실질적 결과 도출
- 기존 프로세스를 방해하지 않음

### 단점

- 대규모 팀 협업에는 추가적인 조율 필요
- 명시적 문서화 강제가 적음
- Claude Code에 종속적

---

## 핵심 비교표

| 측면 | SDD | GSD |
|------|-----|-----|
| **대상** | 엔터프라이즈 팀, 기존 애자일 프로세스 보유 조직 | 솔로 개발자, 소규모 팀 |
| **복잡도** | 높음 (정형화된 명세 필요) | 낮음 (명령어 기반 단순 워크플로우) |
| **학습 곡선** | 가파름 | 완만함 |
| **문서화** | 명세가 핵심 산출물 | 필요 시 자동 생성 |
| **유연성** | 구조화된 프로세스 | 상황에 맞게 조절 가능 |
| **AI 의존도** | AI는 실행 도구 | AI가 핵심 파트너 |
| **적합한 프로젝트** | 신규 대규모 프로젝트 | 신규/기존 모든 규모 |

---

## 어떤 것을 선택해야 할까?

### SDD를 선택하세요 if:

- 대규모 팀에서 일관된 개발 프로세스가 필요
- 규제 준수나 감사 추적이 필수인 프로젝트
- 장기간 유지보수가 예상되는 엔터프라이즈 시스템
- 명확한 요구사항 문서화가 계약상 필요

### GSD를 선택하세요 if:

- 솔로 개발자이거나 소규모 팀
- 빠른 프로토타이핑이나 MVP 개발
- 기존 워크플로우를 유지하면서 AI 도구 활용 원함
- "그냥 작동하는" 실용적 솔루션 선호

---

## 결론

SDD와 GSD는 상호 배타적이지 않습니다.

- **SDD**는 "무엇을 만들 것인가"에 대한 명확한 정의를 제공
- **GSD**는 "어떻게 효율적으로 만들 것인가"에 대한 실행 전략을 제공

프로젝트 특성과 팀 규모에 따라 두 방법론의 장점을 조합하여 사용하는 것이 가장 효과적입니다. 중요한 것은 "Vibe Coding"의 비일관성을 극복하고, AI 도구를 체계적으로 활용하는 것입니다.

---

## 참고 자료

- [Goodbye Vibe Coding: Spec-Driven Development Framework](https://pasqualepillitteri.it/en/news/158/framework-ai-spec-driven-development-guide-bmad-gsd-ralph-loop)
- [Spec Driven Development: When Architecture Becomes Executable - InfoQ](https://www.infoq.com/articles/spec-driven-development/)
- [Spec Driven Development (SDD) - A initial review - DEV Community](https://dev.to/danielsogl/spec-driven-development-sdd-a-initial-review-2llp)
- [GitHub - glittercowboy/get-shit-done](https://github.com/glittercowboy/get-shit-done)
- [Spec-driven development: Unpacking 2025's key new AI-assisted engineering practices - Thoughtworks](https://www.thoughtworks.com/en-us/insights/blog/agile-engineering-practices/spec-driven-development-unpacking-2025-new-engineering-practices)
- [Specification-Driven Development // SDD - Medium](https://evoailabs.medium.com/specification-driven-development-sdd-66a14368f9d6)
- [Diving Into Spec-Driven Development With GitHub Spec Kit - Microsoft](https://developer.microsoft.com/blog/spec-driven-development-spec-kit)
