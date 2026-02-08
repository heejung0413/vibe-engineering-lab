# Coding Conventions

**Analysis Date:** 2026-02-08

## Overview

This is a **Markdown-only documentation project** focused on technical learning materials. All code conventions relate to Markdown document structure and content organization. The project contains no source code files (no .ts, .js, .py, etc.).

## Naming Patterns

**Files:**
- Format: `kebab-case-korean.md` (Korean hyphenation with .md extension)
- Examples: `speckit-소개.md`, `gsd-소개.md`, `speckit-워크플로우.md`
- Pattern: English tool/concept name in kebab-case followed by hyphen and Korean description

**Directories:**
- English topics: `Vibe-Coding/speckit/`, `Vibe-Coding/gsd/`
- Korean topics: `개발-학습/`, `Vibe-Coding/` (mixed bilingual naming allowed per Constitution principle I)
- Pattern: Topic names at top level, specific tool/area as subdirectories

**Headings:**
- H1 (`#`): Document title in Korean with optional English subtitle
- H2 (`##`): Section headers like "학습 목표", "개념 설명", "실습", "정리"
- H3 (`###`): Subsection headers for detailed breakdowns
- Pattern: Korean preferred, English in parentheses for technical terms

**Metadata:**
- Quoted metadata block at top: `> 난이도: [입문/중급/고급]`
- Format: `> Key: Value` on separate lines
- Examples: `> 난이도: 입문`, `> 작성일: 2026-02-07`, `> 수정일: 2026-02-07`

## Document Structure

**Mandatory Template Structure** (from `data-model.md`):

```markdown
# [Title in Korean]

> 난이도: [입문/중급/고급]
> 작성일: YYYY-MM-DD
> 수정일: YYYY-MM-DD

## 학습 목표

이 문서를 통해 다음을 배울 수 있습니다:
- 목표 1
- 목표 2

## 사전 지식

- [필요한 사전 지식 또는 관련 문서 링크]

## [핵심 개념 섹션]

[내용]

## 실습

### 단계 1: [제목]

[설명 및 코드 예제]

### 단계 2: [제목]

[설명 및 코드 예제]

## 정리

- 핵심 포인트 1
- 핵심 포인트 2

## 관련 문서

- [관련 문서 1](../path/to/doc1.md)
- [관련 문서 2](../path/to/doc2.md)
```

**Observed Structure Sections** (in order):
1. Title (H1)
2. Metadata block (난이도, 작성일, 수정일)
3. 학습 목표 - bullet list of learning outcomes
4. 사전 지식 - prerequisites and related topics
5. 개념 설명 or subject-specific section - main content
6. 실습 - hands-on exercises with code examples
7. 정리 - key takeaways summary
8. 관련 문서 - cross-document links

## Code Style

**Markdown Formatting:**
- Use **bold** (`**text**`) for emphasis on key terms
- Use `inline code` (backticks) for commands, file paths, tool names
- Use code fences with language specification: ` ```bash `, ` ```python `, ` ```typescript `
- Line length: No strict limit observed, but keep lines readable (under 120 characters preferred)

**Lists:**
- Unordered: Use `-` for bullet points
- Ordered: Use `1.`, `2.`, etc. for sequential steps
- Description lists: Use `| key | value |` table format for term definitions

**Tables:**
- Use pipe separators: `| Header | Header |`
- Include alignment row: `|---|---|` or `|:---|:---|:---:|`
- Use for comparison matrices, feature lists, and structured data

**Code Blocks:**
- Always specify language: ` ```bash `, ` ```python `, ` ```typescript `, ` ```xml `
- Include language in markdown: ` ```markdown `, ` ```json `
- For shell commands, use `bash` tag
- For no-language blocks, use ` ```text ` or ` ``` `

**Links:**
- Internal links use relative paths: `[text](../path/to/doc.md)`
- External links use full URLs: `[text](https://github.com/...)`
- Link text should be descriptive (not "click here")

## Naming Conventions

**Technical Terms:**
- Primary language: Korean with English in parentheses or inline
- Pattern: `Spec Kit은 (명세 기반 개발)`
- Tool names remain English: Spec Kit, GSD, Claude Code, Spec-Driven Development
- For consistency, repeat tool names without translation

**Metadata Field Names (Korean):**
- 난이도 (difficulty: 입문/중급/고급)
- 작성일 (creation date)
- 수정일 (modification date)
- 학습 목표 (learning objectives)
- 사전 지식 (prerequisites)
- 개념 설명 (concept explanation)
- 실습 (practice/exercises)
- 정리 (summary)
- 관련 문서 (related documents)

## Import Organization

**Cross-Document References:**
- Always use relative paths from current document location
- Example from `Vibe-Coding/speckit/speckit-소개.md`:
  ```markdown
  [관련 문서](../gsd/gsd-소개.md)
  ```
- Pattern: Go up appropriate directory levels (`../`) then down to target file

**External References:**
- Link to official repositories and documentation
- Example: `[Spec Kit 공식 레포지토리](https://github.com/github/spec-kit)`
- Include full HTTPS URLs for clarity

## Comments

**When to Comment:**
- Not applicable to Markdown documents (no executable code)
- Use section headers instead of comments
- Use blockquotes (`>`) for important notes or warnings

**Blockquote Usage:**
- Metadata: `> 난이도: 입문`
- Key principles: `> "명세가 실행 가능해져서 작동 중인 구현으로 직접 변환됩니다"`
- Important notes: `> **주의**: [Important information]`
- Philosophy statements or core concepts

## Constitution Principles (Required Adherence)

All documents must follow these 5 principles from project specification:

**I. 한국어 우선 (Korean Priority)**
- All primary content in Korean
- English technical terms acceptable with Korean explanation
- File names can mix Korean and English

**II. 마크다운 표준 (Markdown Standard)**
- Use `.md` extension exclusively
- Follow GitHub Flavored Markdown (GFM) specification
- Always specify code block language

**III. 실습 중심 (Practice-Oriented)**
- Include executable command examples with syntax highlighting
- Provide copyable code snippets in code blocks
- Test code examples before documentation

**IV. 구조화된 학습 (Structured Learning)**
- Follow: 학습 목표 → 개념 설명 → 실습 → 정리
- Use consistent section hierarchy
- Build understanding progressively

**V. 점진적 심화 (Progressive Complexity)**
- Start with basic concepts
- Progress to intermediate understanding
- Include advanced topics in separate documents or sections
- Link related documents at appropriate complexity levels

## Metadata Fields

**Required Fields (all documents):**
- 난이도: One of `입문` (beginner), `중급` (intermediate), `고급` (advanced)
- 작성일: ISO format `YYYY-MM-DD`
- 수정일: ISO format `YYYY-MM-DD` (update when content changes)

**Optional Fields:**
- 버전: Version number if tracking (e.g., `1.0`, `2.1`)
- 대상: Target audience if applicable
- 선행학습: Additional prerequisites

**Metadata Location:**
- Always in quoted block immediately after H1 title
- Use `>` prefix for each line
- One field per line, separated by colons

## File Organization Best Practices

**Folder Hierarchy:**
- Two top-level categories: `Vibe-Coding/` and `개발-학습/`
- Under each, organize by tool or subject: `Vibe-Coding/speckit/`, `Vibe-Coding/gsd/`
- Flat structure within each folder (avoid deep nesting >3 levels)

**File Naming:**
- Keep filenames short but descriptive (under 50 characters)
- Use lowercase for English portions
- Use hyphens, not underscores or spaces
- Include Korean descriptions for clarity

**Related Documents Section:**
- Place at end of every document
- Use relative paths for navigation
- Group links by relationship type if multiple categories

---

*Convention analysis: 2026-02-08*
