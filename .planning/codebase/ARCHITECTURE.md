# Architecture

**Analysis Date:** 2026-02-08

## Pattern Overview

**Overall:** Documentation-Driven Learning Repository with Modular Organization

**Key Characteristics:**
- Git-based Markdown document storage system
- Two primary conceptual domains: Vibe-Coding (AI tooling) and 개발-학습 (General development)
- Constitution-based principles governing document structure and content
- Learning progression model: Goal → Concept → Practice → Summary
- Spec-Kit and GSD as foundational reference documentation

## Layers

**Documentation Layer:**
- Purpose: Organize and deliver learning content as Markdown files
- Location: `Vibe-Coding/`, `개발-학습/`
- Contains: Learning documents (.md files), organized by domain and tool
- Depends on: Git, Markdown standards, Constitution principles
- Used by: Learners accessing documentation via VS Code, GitHub, or Markdown viewers

**Specification/Planning Layer:**
- Purpose: Define requirements, structure, and implementation plans
- Location: `specs/001-learning-docs/`
- Contains: Spec files, implementation plans, data models, research docs
- Depends on: Feature specifications, requirements analysis
- Used by: Project planners and feature definition

**Supporting Infrastructure Layer:**
- Purpose: Configuration, tooling, and automation context
- Location: `.planning/codebase/`, `.specify/`, `.claude/`, `.obsidian/`
- Contains: Tool configurations, memory files, templates
- Depends on: Claude Code, Specify CLI, Obsidian
- Used by: Development tools and orchestration systems

## Data Flow

**Document Creation Flow:**

1. **Requirement Definition** (specs/001-learning-docs/)
   - User scenarios and acceptance criteria defined
   - Constitution check performed
   - Feature requirements specified

2. **Planning & Design**
   - Data model defined (data-model.md)
   - Folder structure planned
   - Document template agreed upon

3. **Implementation**
   - Markdown documents created following Constitution principles
   - Documents placed in appropriate category folders
   - Cross-document linking established

4. **Access & Learning**
   - Learners navigate document hierarchy
   - Follow structured learning progression
   - Access related documents via markdown links

**State Management:**
- Configuration: `.obsidian/` (Obsidian vault settings)
- Planning: `.planning/codebase/` (codebase analysis docs)
- Memory: `.specify/memory/` (Constitution and shared knowledge)
- Tool Config: `.claude/settings.local.json` (Claude Code settings)

## Key Abstractions

**Learning Document:**
- Purpose: Self-contained unit of learning content with standardized structure
- Examples: `Vibe-Coding/speckit/speckit-소개.md`, `Vibe-Coding/gsd/gsd-소개.md`
- Pattern: Frontmatter metadata (난이도, 작성일, 수정일) → Learning goals → Prerequisite knowledge → Concept explanation → Hands-on practice → Summary → Related documents

**Category Folder:**
- Purpose: Logical grouping of related learning documents
- Examples: `Vibe-Coding/` (tool-focused learning), `개발-학습/` (general development knowledge)
- Pattern: Domain-level organization with optional subcategories (e.g., `Vibe-Coding/speckit/`, `Vibe-Coding/gsd/`)

**Specification Document:**
- Purpose: Formalize requirements and design decisions before implementation
- Examples: `specs/001-learning-docs/spec.md`, `specs/001-learning-docs/plan.md`
- Pattern: User scenarios → Requirements → Success criteria → Data model → Implementation plan

## Entry Points

**Repository Root:**
- Location: `/Users/imheejung/Study/vibe-engineering-lab/`
- Triggers: Initial project access, documentation browsing
- Responsibilities: Contains primary directories, Git configuration, Claude configuration

**Vibe-Coding Directory:**
- Location: `Vibe-Coding/`
- Triggers: Learning about AI coding tools and techniques
- Responsibilities: Organize tool-specific documentation (Spec Kit, GSD, Claude Code)

**개발-학습 Directory:**
- Location: `개발-학습/`
- Triggers: Learning general development concepts and languages
- Responsibilities: Organize programming language and framework documentation

**Specification Directory:**
- Location: `specs/001-learning-docs/`
- Triggers: Feature planning and requirement definition
- Responsibilities: Store feature specifications, implementation plans, and research

## Error Handling

**Strategy:** Prevention through structured templates and Constitution-based validation

**Patterns:**
- Template validation: All documents follow documented structure (goals, concepts, practice, summary)
- Link validation: Cross-document markdown links use relative paths and verified structure
- Content validation: Constitution principles enforced (한국어 우선, 마크다운 표준, 실습 중심, 구조화된 학습, 점진적 심화)
- Format consistency: Code examples include language specification in code blocks

## Cross-Cutting Concerns

**Localization:** All documents written in Korean (한국어) with English technical terms preserved

**Documentation:** Markdown (GFM) format with structured metadata (난이도, 작성일, 수정일)

**Knowledge Management:** Constitution principles ensure consistency across all documents; cross-document linking enables knowledge discovery

**Version Control:** Git tracks document history; branching strategy supports feature development (001-learning-docs branch)

---

*Architecture analysis: 2026-02-08*
