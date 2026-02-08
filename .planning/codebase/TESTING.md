# Testing Patterns

**Analysis Date:** 2026-02-08

## Overview

This is a **Markdown-only documentation project**. Traditional code testing frameworks (Jest, Vitest, pytest, etc.) are not applicable. Quality assurance focuses on:

1. **Manual Content Validation** - Human review against specification
2. **Markdown Rendering Verification** - Display consistency across platforms
3. **Link Validation** - Functional cross-document navigation
4. **Code Example Verification** - Executable examples in documentation
5. **Checklist-Based Acceptance** - Structured validation against requirements

## Test Framework

**No automated test runner.** Quality assurance is specification-driven and manual.

**Validation Approach:**
- Manual review against acceptance criteria in `spec.md`
- Checklist-based validation from `quickstart.md`
- Human testing across rendering platforms (GitHub, VS Code, Obsidian)

**Run Commands:**

```bash
# No automated tests. Instead, follow these manual procedures:

# 1. Render test - Open in GitHub web browser
git add . && git commit -m "test: check rendering"
git push origin [branch]
# Visit: https://github.com/[user]/[repo]/blob/[branch]/[path]/file.md

# 2. Local preview - VS Code with Markdown Preview
# Use: Cmd+Shift+V (macOS) or Ctrl+Shift+V (Windows/Linux)

# 3. Link validation - Check all relative links are correct
# Manual: Click each link in rendered output

# 4. Code example verification - Execute code blocks manually
# See "Code Example Testing" section below
```

## Test Structure

**Specification-Driven Validation** (from `spec.md`):

The project uses Spec Kit's own specification system (from `specs/001-learning-docs/spec.md`):

```yaml
Feature: 바이브코딩 및 개발 학습 문서

User Stories:
  - Story 1: 바이브코딩 기술 문서 작성
  - Story 2: 개발 학습 문서 작성
  - Story 3: 문서 간 탐색 및 연결

Acceptance Scenarios:
  Scenario 1: New document creation with structure
    Given: 빈 폴더
    When: 새 문서 작성
    Then: 정해진 구조로 저장됨

  Scenario 2: Code examples with clarity
    Given: 바이브코딩 세션에서 기술 발견
    When: 문서화
    Then: 코드 예제와 명확한 설명 포함

Success Criteria:
  - SC-001: 새 문서 작성 시간 < 10분
  - SC-002: 100% 문서가 Constitution 원칙 준수
  - SC-003: 정보 검색 시간 < 2분
  - SC-004: 모든 코드 예제 실행 가능
```

## Manual Validation Checklist

**Pre-Commit Validation** (from `quickstart.md`):

```markdown
## 검증 체크리스트

- [ ] 한국어로 작성되었는가?
- [ ] 마크다운 형식을 따르는가?
- [ ] 코드 블록에 언어가 지정되었는가?
- [ ] 실습 예제가 포함되었는가?
- [ ] 학습 목표 → 개념 → 실습 → 정리 구조인가?
```

**Structure Validation:**

```markdown
Mandatory sections check:
- [ ] H1 Title present
- [ ] Metadata block (난이도, 작성일, 수정일)
- [ ] 학습 목표 section with bullet list
- [ ] 사전 지식 section with prerequisites
- [ ] Main content section (e.g., 개념 설명, [주제명])
- [ ] 실습 section with code examples and steps
- [ ] 정리 section with key takeaways
- [ ] 관련 문서 section with cross-links
```

**Content Quality Validation:**

```markdown
For each code block:
- [ ] Language specified (bash, python, typescript, etc.)
- [ ] Example is syntactically correct
- [ ] Example is copyable (no special characters)
- [ ] Example was tested to run successfully
- [ ] Expected output documented (if applicable)

For each link:
- [ ] Link path is correct relative to current document
- [ ] Target file exists in repository
- [ ] Link text is descriptive (not "click here")
- [ ] External links use full HTTPS URLs
```

## Code Example Testing

**Framework:** Manual execution

**Patterns:**

### 1. Bash/Shell Examples

Location: `Vibe-Coding/speckit/speckit-소개.md` (Lines 82-118)

Pattern:
```bash
# Descriptive comment
command-name --option value

# Output or result shown in comment below
# Expected output...
```

**Testing approach:**
- Copy command directly from code block
- Paste into terminal and execute
- Verify output matches documentation
- Run before committing document

Example from project:
```bash
# Test Spec Kit installation
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Verify
specify --help
```

### 2. Python Examples

Location: Example location in future documentation

Pattern:
```python
# Clear example with comments
import module

result = function_call()
print(result)  # Shows expected output
```

**Testing approach:**
- Create temporary test file
- Copy code block exactly
- Execute with Python interpreter
- Verify output matches documentation

### 3. TypeScript/JavaScript Examples

Location: Example location in future documentation

Pattern:
```typescript
// Type-safe example
interface Example {
  name: string;
}

const example: Example = { name: "value" };
```

**Testing approach:**
- Verify syntax with TypeScript compiler
- Run with Node.js if executable
- Check against documented behavior

### 4. XML/Data Structure Examples

Location: `Vibe-Coding/gsd/gsd-소개.md` (Lines 70-78)

Pattern:
```xml
<task type="auto">
  <name>작업 이름</name>
  <files>경로</files>
  <action>작업 설명</action>
</task>
```

**Testing approach:**
- Validate XML structure (well-formed tags)
- Verify all required fields present
- Check against schema if applicable

## Link Validation

**Pattern:** Relative path links for internal documents

**Test locations:**
- `speckit-소개.md` (Line 253): `[Spec Kit 소개](../speckit/speckit-소개.md)`
- `gsd-소개.md` (Line 174): `[Spec Kit 소개 문서](../speckit/speckit-소개.md)`

**Validation checklist:**

For each link in `## 관련 문서` section:
1. Verify relative path is correct
2. Confirm target file exists
3. Test click in rendered output (GitHub/VS Code)
4. Verify target file renders correctly
5. Check for broken link chains

**Testing approach:**

```bash
# Manual link validation
# 1. In GitHub web UI: Visit document → click each link in "관련 문서"
# 2. In VS Code: Open Markdown preview → Cmd/Ctrl+click each link
# 3. Local check: Verify all referenced files exist

# Example validation for gsd-소개.md
ls -la Vibe-Coding/speckit/speckit-소개.md  # Verify file exists
cat Vibe-Coding/gsd/gsd-소개.md | grep "관련 문서" -A 5  # Check links format
```

## Metadata Validation

**Pattern:** Three required metadata fields

**Test locations:** All `.md` files must have:

```markdown
> 난이도: [입문|중급|고급]
> 작성일: YYYY-MM-DD
> 수정일: YYYY-MM-DD
```

**Validation checklist:**

- [ ] 난이도 is one of: 입문, 중급, 고급 (typos = fail)
- [ ] 작성일 is ISO date format (YYYY-MM-DD)
- [ ] 수정일 is ISO date format, >= 작성일
- [ ] 수정일 matches actual file modification if updated
- [ ] Metadata appears immediately after H1 title
- [ ] Each metadata field on separate line with `>`

**Testing approach:**

```bash
# Automated metadata check (bash)
for file in Vibe-Coding/**/*.md Vibe-Coding/*.md 개발-학습/**/*.md; do
  [ -f "$file" ] || continue
  echo "Checking: $file"

  # Check 난이도
  grep "^> 난이도:" "$file" || echo "  ❌ Missing 난이도"

  # Check 작성일 format
  grep "^> 작성일: [0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}$" "$file" || \
    echo "  ❌ Invalid 작성일 format"

  # Check 수정일 format
  grep "^> 수정일: [0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}$" "$file" || \
    echo "  ❌ Invalid 수정일 format"
done
```

## Markdown Rendering Test

**Scope:** Verify document renders correctly on all platforms

**Test locations:**
1. GitHub web browser (primary)
2. VS Code with Markdown Preview
3. Obsidian (if using)

**Validation checklist:**

- [ ] Headings render with correct hierarchy
- [ ] Code blocks display with syntax highlighting
- [ ] Tables render with proper alignment
- [ ] Links are clickable
- [ ] Images display correctly (if used)
- [ ] Line breaks and spacing are correct
- [ ] Unicode Korean text displays properly
- [ ] Special characters render without corruption

**Testing approach:**

```bash
# 1. Push to GitHub and view raw markdown
git push origin [branch]
# Visit: https://github.com/[user]/vibe-engineering-lab/blob/[branch]/Vibe-Coding/speckit/speckit-소개.md

# 2. Test in VS Code
# Open file → Cmd+Shift+V (macOS) or Ctrl+Shift+V (Windows/Linux)

# 3. Test in multiple browsers if critical
# Firefox, Chrome, Safari should render identically
```

## Constitution Compliance Testing

**Framework:** Specification-based validation against 5 core principles

**Test locations:** `spec.md` Lines 77-85 define success criteria

**Validation Matrix:**

| Principle | Test | Location | Pass Condition |
|-----------|------|----------|---|
| I. 한국어 우선 | Content language check | Entire document | ≥95% Korean text |
| II. 마크다운 표준 | Format validation | File extension + syntax | .md + GFM compliant |
| III. 실습 중심 | Code examples present | 실습 section | ≥1 executable example |
| IV. 구조화된 학습 | Section ordering | Document flow | 목표→개념→실습→정리 |
| V. 점진적 심화 | Complexity progression | Content depth | Logical progression |

**Testing approach:**

Manual checklist for each document:

```markdown
Constitution Compliance Check:

I. 한국어 우선
  - [ ] Primary content is in Korean
  - [ ] English technical terms explained in Korean
  - [ ] English acceptable for tool/framework names

II. 마크다운 표준
  - [ ] File extension is .md
  - [ ] GitHub Flavored Markdown compliant
  - [ ] Code blocks have language specified

III. 실습 중심
  - [ ] 실습 section exists
  - [ ] At least one command example included
  - [ ] At least one code example included
  - [ ] Examples are copyable

IV. 구조화된 학습
  - [ ] 학습 목표 section exists with bullet points
  - [ ] 개념 설명 section exists
  - [ ] 실습 section exists with steps
  - [ ] 정리 section exists with summary bullets
  - [ ] Sections appear in correct order

V. 점진적 심화
  - [ ] Content starts with basics
  - [ ] Complexity increases progressively
  - [ ] Advanced topics appear later
  - [ ] Links to related documents for deeper learning
```

## Test Coverage

**What IS tested:**
- ✅ Document structure adherence
- ✅ Metadata completeness and format
- ✅ Code example executability
- ✅ Link navigation functionality
- ✅ Constitution principle compliance
- ✅ Rendering across platforms

**What is NOT tested (N/A to Markdown project):**
- ❌ Unit tests (no code units)
- ❌ Integration tests (no APIs)
- ❌ Performance tests (static files)
- ❌ Security tests (read-only documents)

**Coverage Target:** 100% of documents pass specification checklist before merge

## Acceptance Criteria

**From `spec.md` SC-001 through SC-004:**

```yaml
SC-001: 신입 사용자가 10분 안에 새 문서 작성 시작 가능
  Test: Follow quickstart.md instructions, measure time
  Pass: Complete first document under 10 minutes

SC-002: 작성된 문서 100%가 Constitution 5원칙 준수
  Test: Run Constitution compliance checklist on all documents
  Pass: All documents pass all 5 principle checks

SC-003: 학습자가 2분 안에 기존 문서에서 정보 찾기 가능
  Test: Sample 5 users, have them find specific info
  Pass: All users complete task in ≤2 minutes

SC-004: 모든 코드 예제가 복사-붙여넣기로 실행 가능
  Test: Copy each code block, execute directly
  Pass: All examples run without modification
```

## Continuous Validation

**Pre-commit hook** (recommended):

Create `.git/hooks/pre-commit`:

```bash
#!/bin/bash
# Validate markdown files before commit

for file in $(git diff --cached --name-only | grep '\.md$'); do
  echo "Validating: $file"

  # Check 난이도 present
  grep -q "^> 난이도:" "$file" || {
    echo "❌ $file missing 난이도"
    exit 1
  }

  # Check date format
  grep -q "^> 작성일: [0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}" "$file" || {
    echo "❌ $file invalid 작성일 format"
    exit 1
  }

  echo "✅ $file passed validation"
done

exit 0
```

**Manual review checklist** before merge:
- [ ] All manual validation tests pass
- [ ] Constitution compliance verified
- [ ] Links tested and functional
- [ ] Code examples executed successfully
- [ ] Metadata validated
- [ ] Markdown renders correctly on GitHub

---

*Testing analysis: 2026-02-08*
