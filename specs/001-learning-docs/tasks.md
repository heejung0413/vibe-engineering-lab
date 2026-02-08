# Tasks: 바이브코딩 및 개발 학습 문서

**Input**: Design documents from `/specs/001-learning-docs/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, quickstart.md

**Tests**: 테스트 작업은 포함하지 않음 (문서 프로젝트이므로 수동 검증)

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Documentation project**: `Vibe-Coding/`, `개발-학습/` at repository root
- Paths shown below follow the plan.md structure

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: 프로젝트 폴더 구조 초기화

- [ ] T001 Create Vibe-Coding/ 폴더 at repository root
- [ ] T002 [P] Create 개발-학습/ 폴더 at repository root
- [ ] T003 [P] Create Vibe-Coding/speckit/ 하위 폴더
- [ ] T004 [P] Create Vibe-Coding/gsd/ 하위 폴더

**Checkpoint**: 기본 폴더 구조 완성

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: 문서 작성을 위한 템플릿 및 가이드라인 준비

**⚠️ CRITICAL**: 문서 작성 전 템플릿 이해 필요

- [ ] T005 Review data-model.md의 문서 구조 템플릿 확인
- [ ] T006 Review Constitution 원칙 5가지 숙지 (한국어, 마크다운, 실습 중심, 구조화, 점진적 심화)

**Checkpoint**: Foundation ready - 문서 작성 가능

---

## Phase 3: User Story 1 - 바이브코딩 기술 문서 작성 (Priority: P1) 🎯 MVP

**Goal**: 바이브코딩 폴더에 기술 문서를 작성하여 학습 내용을 체계적으로 기록

**Independent Test**: Vibe-Coding/ 폴더의 문서만으로 특정 기술을 이해하고 적용할 수 있는지 확인

### Implementation for User Story 1

- [ ] T007 [US1] Write Spec Kit 소개 문서 in Vibe-Coding/speckit/speckit-소개.md (완료됨)
- [ ] T008 [P] [US1] Write GSD(Get Shit Done) 소개 문서 in Vibe-Coding/gsd/gsd-소개.md
- [ ] T009 [US1] Verify speckit-소개.md follows Constitution principles (한국어, 구조화, 실습 중심)
- [ ] T010 [US1] Verify gsd-소개.md follows Constitution principles

**Checkpoint**: User Story 1 완료 - 바이브코딩 기술 문서 2개 작성 및 검증

---

## Phase 4: User Story 2 - 개발 학습 문서 작성 (Priority: P2)

**Goal**: 개발 학습 폴더에 일반적인 개발 지식 문서 작성

**Independent Test**: 개발-학습/ 폴더의 문서만으로 특정 개념을 복습할 수 있는지 확인

### Implementation for User Story 2

- [ ] T011 [P] [US2] Create 개발-학습/README.md with folder structure explanation
- [ ] T012 [US2] Create first learning document (향후 추가 예정)

**Checkpoint**: User Story 2 완료 - 개발 학습 폴더 기본 구조 완성

---

## Phase 5: User Story 3 - 문서 간 탐색 및 연결 (Priority: P3)

**Goal**: 관련 문서 간 링크를 추가하여 지식 연결

**Independent Test**: 문서 간 링크를 통해 원활하게 탐색 가능한지 확인

### Implementation for User Story 3

- [ ] T013 [US3] Add cross-reference links between speckit-소개.md and gsd-소개.md
- [ ] T014 [US3] Create Vibe-Coding/README.md with index of all documents

**Checkpoint**: 모든 User Story 완료 - 문서 간 탐색 가능

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: 전체 문서 품질 개선 및 최종 검증

- [ ] T015 [P] Verify all documents follow GFM markdown standard
- [ ] T016 [P] Verify all code blocks have language specification
- [ ] T017 Run quickstart.md validation - 새 문서 작성 프로세스 테스트
- [ ] T018 Constitution compliance final check

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion
- **User Stories (Phase 3+)**: All depend on Foundational phase completion
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational - No dependencies on other stories
- **User Story 2 (P2)**: Can start after Foundational - Independent from US1
- **User Story 3 (P3)**: Depends on US1 completion (needs documents to link)

### Parallel Opportunities

- T001, T002, T003, T004 can run in parallel (different folders)
- T007, T008 can run in parallel (different files)
- T011, T012 can run in parallel (different files)
- T015, T016 can run in parallel (different validation tasks)

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (폴더 생성)
2. Complete Phase 2: Foundational (템플릿 확인)
3. Complete Phase 3: User Story 1 (Spec Kit + GSD 문서)
4. **STOP and VALIDATE**: 문서가 Constitution 원칙을 준수하는지 확인
5. 필요시 배포/공유

### Current Priority Task

**T008**: GSD(Get Shit Done) 소개 문서 작성 - `Vibe-Coding/gsd/gsd-소개.md`

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- 각 문서는 독립적으로 가치를 제공해야 함
- Constitution 원칙 준수 필수: 한국어, 마크다운, 실습 중심, 구조화, 점진적 심화
- Commit after each document completion
