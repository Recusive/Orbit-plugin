# Audit Suite

A Claude Code plugin with 10 expert audit lenses + a full spectrum orchestrator. Review implementation plans or actual code through the eyes of specialized engineers.

## Skills

### Individual Lenses

Each lens reviews through a specific expert's perspective:

| Skill | Expert | What It Catches |
|-------|--------|----------------|
| `/audit-as-design-eng` | Design Engineer | Visual hierarchy, design tokens, dark mode, states, animation quality |
| `/audit-as-ux-eng` | UX Engineer | User journeys, mental models, discoverability, error recovery |
| `/audit-as-frontend-eng` | Frontend Engineer | React patterns, Zustand, type safety, re-renders, bundle impact |
| `/audit-as-backend-eng` | Backend Engineer | Rust/error handling, concurrency, resource lifecycle, IPC |
| `/audit-as-structural-eng` | Structural Architect | Coupling, dependencies, layer violations, abstraction levels |
| `/audit-as-repo-maintainer` | Repo Maintainer | Conventions, barrel exports, naming, code reuse, lint compliance |
| `/audit-as-prod-readiness` | Production Engineer | E2E flow, env parity, error recovery, data integrity, rollback |
| `/audit-as-dx-eng` | DX Engineer | Error messages, CLI ergonomics, defaults, keyboard, config |
| `/audit-as-perf-eng` | Performance Engineer | Memory over long sessions, IPC latency, streaming, resource lifecycle |
| `/audit-as-a11y-eng` | Accessibility Engineer | Screen readers, keyboard nav, ARIA, focus management, contrast |

### Orchestrator

| Skill | What It Does |
|-------|-------------|
| `/full-audit` | Runs all relevant lenses sequentially, writes ONE document with master verdict + cross-cutting concerns |

## Modes

### Plan Mode
```
/full-audit docs/plans/my-plan.md
```
Audits an implementation plan before you write code.

### Repo Mode
```
/full-audit
```
Asks what to audit:
1. **Uncommitted changes** — working tree diff
2. **Branch vs main** — PR-level review
3. **General repo health** — broad codebase check

## Output

Everything goes into one file: `reviews/audit-plan-full.md`

```
Master Summary (verdict, cross-cutting concerns, all critical issues)
─────────────────────────────────────────────────────────────────────
## 1. Design Engineer        ← full output
## 2. UX Engineer            ← full output
## 3. Frontend Engineer      ← full output
...
## 10. Accessibility Engineer ← full output
```

## Install

```bash
# Direct from GitHub
/plugin install Recusive/Orbit-plugin
```

## Cross-References

Six lenses reference existing skills for deeper guidance when issues are found:

- Design → `/emil-design-engineering`, `/make-interfaces-feel-better`, `/web-animation-design`
- UX → `/web-design-guidelines`, `/emil-design-engineering`
- Frontend → `/vercel-react-best-practices`
- Structural → `/vercel-react-best-practices`
- Performance → `/vercel-react-best-practices`, `/web-animation-design`
- Accessibility → `/emil-design-engineering`, `/web-design-guidelines`, `/web-animation-design`

These are optional — the audit skills work standalone, but produce richer recommendations when the referenced skills are also installed.

## License

MIT
