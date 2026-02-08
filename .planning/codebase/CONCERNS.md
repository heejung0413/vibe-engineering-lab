# Codebase Concerns

**Analysis Date:** 2026-02-08

## Tech Debt

**Incomplete Feature Implementation:**
- Issue: GSD 도구 (`Vibe-Coding/gsd/gsd-소개.md`) 문서는 작성되었지만, 계획서에는 추가적인 GSD 설명 문서들이 예정되어 있으나 구현되지 않음
- Files: `specs/001-learning-docs/data-model.md` (lines 40-41), `specs/001-learning-docs/tasks.md` (lines 58, 143)
- Impact: 바이브코딩 기술 폴더의 불완전한 상태. 사용자가 예상하는 완전한 문서 세트가 없음
- Fix approach: 계획된 Spec Kit 워크플로우 문서(`speckit-워크플로우.md`, `speckit-명령어.md`) 추가 작성 또는 현재 단계에서 필요없다면 계획 문서 업데이트

**Mismatch Between Plan and Implementation:**
- Issue: Data model 파일에서는 `Vibe-Coding/` 하위에 `claude-code/` 폴더 계획이 있으나, 실제로는 `gsd/` 폴더만 생성됨
- Files: `specs/001-learning-docs/data-model.md` (lines 40-41), 실제 구조는 `Vibe-Coding/speckit/`, `Vibe-Coding/gsd/`
- Impact: 문서에 명시된 계획과 실제 구현의 불일치로 인한 혼동. 향후 공동 작업 시 방향 불명확
- Fix approach: Data model 업데이트하여 실제 하위폴더 구조와 맞추거나, claude-code 폴더 생성 계획을 명시적으로 `향후` 섹션으로 표시

**Missing Documentation Structure:**
- Issue: User Story 2 (개발 학습 문서) 구현이 T012 수준에서 미완료 상태. `개발-학습/README.md` 파일이 없음
- Files: `specs/001-learning-docs/tasks.md` (lines 74-75)
- Impact: 개발 학습 폴더가 생성되었으나 설명 문서 없음. 새로운 학습자는 폴더의 목적과 사용법을 이해하기 어려움
- Fix approach: `개발-학습/README.md` 파일 작성하여 폴더 목적, 구조, 사용 지침 설명

## Known Issues

**User Story 3 Blocker:**
- Symptoms: User Story 3 (문서 간 탐색 및 연결)이 실행될 수 없음. T013, T014 작업은 US1 완료 의존 상태
- Files: `specs/001-learning-docs/tasks.md` (lines 89-91, 119-120)
- Trigger: T013, T014 체크박스에서 `[US3]` 작업이 있으나, T009-T010 (US1 검증) 작업 완료 전까지 병렬 실행 불가
- Workaround: T009-T010 작업을 먼저 완료하면 T013-T014 실행 가능. 또는 순서 변경 필요

**CLAUDE.md Auto-Generated Status:**
- Symptoms: `CLAUDE.md` 파일이 "Auto-generated from all feature plans"로 표시되지만, 파일이 정적이고 프로젝트 구조 예시가 부정확
- Files: `/Users/imheejung/Study/vibe-engineering-lab/CLAUDE.md` (lines 1, 11-13)
- Trigger: 파일이 마지막 업데이트 2026-02-07인데, 이후 변경사항이 반영되지 않음
- Workaround: CLAUDE.md 수동 업데이트 필요. src/, tests/ 디렉토리는 이 프로젝트에 존재하지 않으며, 실제 구조는 `Vibe-Coding/`, `개발-학습/`, `specs/`

## Documentation Quality Issues

**Inconsistent Cross-References:**
- Issue: `gsd-소개.md`에서 Spec Kit 소개 문서로 링크 시도하나 (line 253), 상대 경로가 정확함. 하지만 반대 방향 링크가 `speckit-소개.md`에 없음
- Files: `Vibe-Coding/gsd/gsd-소개.md` (line 253), `Vibe-Coding/speckit/speckit-소개.md`
- Impact: 양방향 문서 네비게이션 불완전. User Story 3 (문서 간 탐색)이 부분적으로만 구현됨
- Fix approach: `speckit-소개.md` 문서 상단 "관련 문서" 섹션에 GSD 문서로 역링크 추가

**Missing Constitution Verification:**
- Issue: T009, T010 작업에서 Constitution 원칙 준수 검증이 명시되어 있으나, 실제 검증 기준이 불명확
- Files: `specs/001-learning-docs/tasks.md` (lines 59-60), `specs/001-learning-docs/spec.md` (line 82)
- Impact: 작업 완료 기준이 모호함. 다음 담당자가 T009-T010을 어떻게 검증해야 할지 알 수 없음
- Fix approach: `quickstart.md`에 Constitution 검증 체크리스트 추가 또는 `specs/001-learning-docs/checklists/requirements.md`에 명확한 검증 기준 추가

**Incomplete Content References:**
- Issue: 계획 문서에서 언급하는 파일들 중 일부가 "향후 추가" 상태로 남아있음. Data model에서 예상되는 하위폴더 구조(`python/`, `typescript/`)가 실제로 없음
- Files: `specs/001-learning-docs/data-model.md` (lines 42-43), 실제 폴더 구조 확인 결과 미생성
- Impact: 문서의 예시와 실제 상황의 괴리. 혼동 가능성
- Fix approach: Data model을 "현재 상태"와 "향후 계획" 섹션으로 분리하여 관리

## Fragile Areas

**Task Dependency Chain:**
- Files: `specs/001-learning-docs/tasks.md` (Phase 1-5)
- Why fragile: 강력한 순서 의존성이 있음. Phase 2 (T005-T006) 완료 없이는 Phase 3 이상 진행 불가. 한 작업 실패 시 전체 파이프라인 영향
- Safe modification: 병렬 실행 가능한 작업 식별 (T007-T008, T011-T012 등)을 더 명확히 표시. 워크플로우 순서도(dependency diagram) 추가
- Test coverage: Phase 간 의존성 검증. 특히 T005-T006 검증 완료 기준 명확화

**Hard-coded Documentation Structure:**
- Files: `Vibe-Coding/speckit/speckit-소개.md`, `Vibe-Coding/gsd/gsd-소개.md`
- Why fragile: 모든 문서가 고정된 템플릿 구조(학습 목표 → 사전 지식 → 개념 → 실습 → 정리 → 관련 문서)를 따름. 예외적인 내용 구조 필요 시 조정 어려움
- Safe modification: 템플릿을 "권장" 구조로 변경하되, 특수한 주제의 경우 변형 허용. 문서 시작 부분에 "구조 예외 사유"를 명시하도록 권고
- Test coverage: 새 문서 작성 시 Constitution 5가지 원칙 준수만 확인하면 되도록 가이드 개선

## Test Coverage Gaps

**No Automated Markdown Validation:**
- What's not tested: 마크다운 문법 정확성, GFM 규격 준수, 코드 블록 언어 지정, 상대 경로 링크 유효성
- Files: `specs/001-learning-docs/tasks.md` (T015-T016은 수동 검증)
- Risk: 문서 품질 저하, 깨진 링크, 유효하지 않은 마크다운이 커밋될 수 있음
- Priority: Medium - 문서 프로젝트이므로 수동 검증도 가능하지만, 자동 체크 도구 사용 권장

**No Verification of Cross-Document Consistency:**
- What's not tested: 여러 문서에 걸친 용어 일관성, 기술 정보 정확성, 버전 호환성
- Files: `Vibe-Coding/speckit/speckit-소개.md`, `Vibe-Coding/gsd/gsd-소개.md`
- Risk: 문서 간 모순, 오래된 기술 정보 유지로 인한 학습자 혼동
- Priority: Low - 초기 단계로 문서 수가 적지만, 향후 성장 시 체계 필요

**Missing Pre-commit Validation:**
- What's not tested: 마크다운 렌더링 확인, 모든 내부 링크 유효성, 코드 예제 실행 가능성 (향후)
- Files: 모든 `.md` 파일
- Risk: 유효하지 않은 문서가 git에 커밋될 수 있음
- Priority: Medium - Task T015-T016 현재 수동이므로, 자동화 도구 추가 권장

## Missing Critical Features

**User Story 1 Partial Completion:**
- Problem: Task T007 (speckit 문서)는 완료되었으나, T008 (gsd 문서)의 상태가 불명확. 작업 체크박스는 미완료이나 파일은 존재함
- Blocks: T009-T010 (검증 작업) 실행 불가능. 이는 T013-T014 (US3 작업) 차단
- Priority: High - 현재 프로젝트의 주요 기능 완성도 영향

**README Files Missing:**
- Problem: `Vibe-Coding/` 최상위 폴더에 `README.md` 없음. `개발-학습/` 폴더도 마찬가지
- Blocks: 새로운 사용자나 기여자가 프로젝트 목적과 사용법 이해 어려움
- Priority: High - 문서 프로젝트의 시작점 역할

**No Index or Navigation Document:**
- Problem: 모든 문서를 한눈에 보고 탐색할 수 있는 인덱스 문서 없음. T014에서 계획되었으나 미완료
- Blocks: 문서 검색성 저하
- Priority: Medium - 초기 문서 수는 적지만, 향후 문서 증가 시 필수

## Dependencies at Risk

**External Tool Documentation Accuracy:**
- Risk: `speckit-소개.md`, `gsd-소개.md`에서 외부 도구(Spec Kit, GSD)의 최신 버전 정보를 포함. 도구 업데이트 시 문서 내용 검증 필요
- Impact: 문서의 코드 예제, 명령어, 옵션이 구식이 될 수 있음
- Migration plan: 매 분기마다 외부 도구 버전 확인 및 문서 업데이트. 문서에 "마지막 검증 버전" 명시 권고

**Git 저장소 내 마크다운 렌더링:**
- Risk: GitHub, GitLab 등 다양한 플랫폼에서 마크다운 렌더링 차이 가능. 상대 경로 링크 호환성 문제 가능
- Impact: 일부 플랫폼에서 링크 작동 불가, 이미지 미표시, 표 렌더링 오류
- Migration plan: `.md` 파일 이동 시 상대 경로 모두 재검증. GFM 표준 준수 확인

## Scaling Limits

**Manual Task Tracking:**
- Current capacity: 30개 작업까지는 tasks.md로 관리 가능
- Limit: 100개 작업 초과 시 추적 어려움
- Scaling path: 향후 프로젝트 규모 증가 시 GitHub Issues, Projects 보드로 전환 권고

**Single-Branch Documentation Structure:**
- Current capacity: 2개 주요 폴더 (Vibe-Coding, 개발-학습), 최대 4개 하위폴더
- Limit: 20개 이상 주제별 폴더 필요 시 현재 구조로는 네비게이션 복잡
- Scaling path: 향후 카테고리 확장 시 계층적 구조 재설계 필요. 예: `Vibe-Coding/{speckit,gsd,claude-code}/`, `개발-학습/{frontend,backend,devops}/`

**No Automated Content Generation:**
- Current capacity: 수동으로 2-3개 문서 작성 및 관리 가능
- Limit: 10개 이상 문서로 확장 시 관리 부담 증가
- Scaling path: 향후 템플릿 자동화, 문서 생성 스크립트 추가 고려

---

*Concerns audit: 2026-02-08*
