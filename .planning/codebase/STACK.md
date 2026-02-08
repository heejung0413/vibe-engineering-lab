# Technology Stack

**Analysis Date:** 2026-02-08

## Languages

**Primary:**
- Markdown (GitHub Flavored Markdown) - Documentation, learning guides, specifications
- English/Korean (Natural Language) - Content for documentation files

**Secondary:**
- Bash - Scripts in `.specify/scripts/bash/` for project automation

## Runtime

**Environment:**
- Node.js (implied via GSD CLI reference - `npx get-shit-done-cc`)
- macOS/Unix (development environment, based on project structure)

**Package Manager:**
- npm (referenced in GSD installation instructions)
- Lockfile: Not present in codebase (documentation-only project)

## Frameworks

**Core:**
- GSD (Get Shit Done) - Meta-prompting and context engineering system for Claude Code
  - Used for project orchestration and workflow management
  - Enables multi-agent development workflows
- Spec Kit - Feature specification and planning framework
  - Complements GSD for specification writing
  - Used alongside GSD for comprehensive development methodology

**Documentation:**
- GitHub Flavored Markdown (GFM) - Standard markup for all documentation

**Development Tools:**
- Obsidian - Knowledge management and documentation editor (`.obsidian/` directory present)
- Claude Code - AI coding assistant (primary tool for GSD integration)
- OpenCode, Gemini CLI - Alternative runtimes supported by GSD

## Key Dependencies

**Critical:**
- `get-shit-done-cc` (npm package) - GSD framework implementation
  - Installation: `npx get-shit-done-cc`
  - Provides `/gsd:*` command suite for workflow orchestration
  - Must-have for project execution

**Infrastructure:**
- Git - Version control system
  - Atomic commit strategy per GSD methodology
  - `.git/` directory with active master branch

**Configuration Management:**
- CLAUDE.md - Project-level development guidelines (auto-generated from feature plans)
- `.claude/` directory - Local Claude Code configuration
- `.specify/` directory - Spec Kit configuration and templates

## Configuration

**Environment:**
- Not required (documentation-only project)
- No `.env` files present
- No secrets management needed

**Build:**
- No build configuration files (non-compiled project)
- Project is documentation-based with no compilation step

**Documentation Configuration:**
- `CLAUDE.md` - Auto-generated from feature plans
  - Lists active technologies
  - Defines project structure expectations
  - Documents code style conventions

## Platform Requirements

**Development:**
- macOS (Darwin 25.2.0) - Development platform
- Basic command-line tools (bash, git)
- Obsidian application (optional, for editing)
- Claude Code IDE with permissions configuration

**Local Configuration Files:**
- `.claude/settings.local.json` - Permissions for bash scripts in `.specify/scripts/bash/`
  - Allows: `ls`, `create-new-feature.sh`, `setup-plan.sh`, `update-agent-context.sh`, `git checkout`, `check-prerequisites.sh`

**Production:**
- Deployment target: Local documentation repository + Git remote
- No server/hosting infrastructure required

---

*Stack analysis: 2026-02-08*
