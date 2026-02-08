# External Integrations

**Analysis Date:** 2026-02-08

## APIs & External Services

**AI Coding Platforms:**
- Claude Code (Anthropic) - Primary AI coding assistant for GSD workflow
  - CLI integration: Native command support (`/gsd:*` commands)
  - Permission model: Managed via `.claude/settings.local.json`
  - Auth: GitHub-based (implied via git integration)
- OpenCode - Alternative runtime for GSD framework
  - Optional integration
  - Configured via GSD installation choice
- Gemini CLI (Google) - Alternative runtime for GSD framework
  - Optional integration
  - Configured via GSD installation choice

**GSD Framework Services:**
- get-shit-done-cc (npm package registry)
  - Installation: `npx get-shit-done-cc`
  - Delivery: npm package registry
  - Auth: Public package (no auth required)
  - Purpose: Multi-agent orchestration, context engineering, atomic task management

## Data Storage

**Databases:**
- Not applicable - Documentation-only project
- No database connections present

**File Storage:**
- Local filesystem only
  - Project root directory structure
  - `.planning/codebase/` for analysis documents
  - `.specify/` for templates and configuration
  - `Vibe-Coding/` for learning documentation
  - Git repository as version control store

**Caching:**
- None - No caching layer in place

## Authentication & Identity

**Auth Provider:**
- GitHub (implied)
  - Git repository authentication for remote push/pull
  - OAuth via git credentials
  - Not explicitly configured in codebase

**Auth Implementation:**
- System-level git credentials
- No application-level authentication
- GSD respects user permissions via Claude Code IDE permissions model

## Monitoring & Observability

**Error Tracking:**
- None configured

**Logs:**
- Bash scripts in `.specify/scripts/bash/` may generate logs (not tracked in codebase)
- GSD execution logs managed by Claude Code IDE
- No centralized logging infrastructure

**Documentation & Issue Tracking:**
- GitHub Issues (implied) - Feature tracking via GSD workflow
- GitHub Discussions (potential) - Knowledge sharing

## CI/CD & Deployment

**Hosting:**
- GitHub Repository (private/public)
  - Remote: Not specified in codebase
  - Branch strategy: Single `master` branch active

**CI Pipeline:**
- None configured
- Manual validation via `/gsd:verify-work` commands
- No automated testing infrastructure

**Deployment Strategy:**
- Manual via git push
- No deployment automation
- Documentation published directly to repository

## Environment Configuration

**Required env vars:**
- None for documentation/learning project

**Secrets location:**
- No secrets present in codebase
- `.env` files: None present
- Credentials: Managed via system git configuration

## Webhooks & Callbacks

**Incoming:**
- None configured

**Outgoing:**
- Git commit hooks (potential)
  - Pre-commit: Not configured
  - Post-commit: Not configured
- GSD agent callbacks managed within Claude Code IDE

## Development Workflow Integration

**GSD Framework Integration:**
- Entry Points:
  - `/gsd:new-project` - Initialize new feature development
  - `/gsd:discuss-phase [N]` - Capture implementation decisions
  - `/gsd:plan-phase [N]` - Research and planning
  - `/gsd:execute-phase <N>` - Parallel execution with 200K token context
  - `/gsd:verify-work [N]` - User acceptance testing
  - `/gsd:complete-milestone` - Archive and release

**Context Files Managed:**
- `PROJECT.md` - Project vision (auto-loaded)
- `REQUIREMENTS.md` - v1/v2 requirements (auto-loaded)
- `ROADMAP.md` - Progress tracking
- `STATE.md` - Session memory and decisions
- `research/` - Ecosystem knowledge
- `todos/` - Future work ideas

**Spec Kit Integration:**
- Complementary to GSD
- Used for feature specification writing
- Command suite in `.claude/commands/speckit.*.md`
- Templates in `.specify/templates/`

## Permissions & Access Control

**Local Configuration:**
- File: `.claude/settings.local.json`
- Permitted bash operations:
  - `Bash(ls:*)` - File listing
  - `Bash(/Users/imheejung/Study/vibe-engineering-lab/.specify/scripts/bash/create-new-feature.sh:*)`
  - `Bash(/Users/imheejung/Study/vibe-engineering-lab/.specify/scripts/bash/setup-plan.sh:*)`
  - `Bash(/Users/imheejung/Study/vibe-engineering-lab/.specify/scripts/bash/update-agent-context.sh:*)`
  - `Bash(git checkout:*)`
  - `Bash(/Users/imheejung/Study/vibe-engineering-lab/.specify/scripts/bash/check-prerequisites.sh:*)`

**IDE Integration:**
- Obsidian for local documentation editing
- Claude Code with permission-gated bash execution

---

*Integration audit: 2026-02-08*
