---
marp: true
theme: lab
paginate: true
---

<!--
Part 2 slides — ENGLISH (final-deck language), 9 slides / 50 min (#16~22, #20 split a/b, divider first)
Copy follows the lab template's English style. Korean draft (part2-draft.md)
remains the planning/reference version; timing and demo pointers are identical.
Speaker notes stay in Korean for the presenter.
-->

<!-- _class: divider -->

# Part 2. Claude Code

**The assembled result, hands on**

<!--
표지 | 0분 (휴식 복귀 안내 겸용)
- 휴식 직전 멘트 회수: "10분 쉬고, 방금 본 조립의 결과물을 직접 봅니다."
-->

---

# Claude Code — Not an Invention, an Assembly

**The pieces of Part 1, assembled for the development workflow**

```
Piece from Part 1          What it looks like in Claude Code
Long context (#7)     →   reads the codebase whole
Tool use (#8)         →   file read/write, shell (Bash), git — executes directly
Projects instr. (#10) →   CLAUDE.md — team instructions in the repo (#19)
MCP (#13)             →   connections to internal systems (#21)
                          the frame around this loop = harness (permissions, hooks — #20)
```

- The decisive difference from chat: **reads, fixes, tests, and commits** — no human carries the results
  (#5's "manual work" fully resolved here)
- One-line history: research preview Feb 2025 → GA May 2025 → 2.x today

<!--
#16 | 4분 | Part 2의 개념 장 — #14 조립 도식의 재등장
- [도식 자리] #14 조립 도식과 같은 시각 언어 + 개발 도구 매핑.
- 중심 멘트: "If you followed Part 1, Claude Code is a combination of
  things you already know."
- 터미널에서 동작하는 이유(말로): 개발자의 도구가 다 터미널에 있다.
-->

---

# Getting Started — Four Entry Points

<style scoped>
table { font-size: 20px; }
</style>

**One terminal, five minutes**

```bash
npm install -g @anthropic-ai/claude-code
cd our-project && claude        # log in and start talking
```

| Entry point | Character |
|-------------|-----------|
| **CLI (terminal)** | The original — newest features land here first |
| **VS Code · JetBrains extensions** | Inside the IDE you know — convenient diffs |
| **Claude desktop** | Convenient GUI, chat and code — local, cloud, and SSH environments + remote control |
| **claude.ai/code (web)** | Browser, partial mobile — cloud environments only, no automatic memory |

<!--
#17 | 3분 | 사용자 원안 12장(Starting Claude Code) 기반
- 원안 문안 반영: desktop "편리한 GUI, 코드와 채팅 둘 다", VSCode "익숙한 편".
- [예시 자리] 첫 실행 화면 캡처 1장.
- ⚠️ 설치 명령·플랜은 발표 직전 재확인.
- "오늘 데모는 CLI로."
-->

---

# Live Demo (25 min)

**Planned scenarios**

1. **Understanding a repo** — explain an unfamiliar codebase
2. **Fixing a bug** — hand over one issue, tests included
3. **Adding a feature** — plan → implement → commit, small scope
4. **CLAUDE.md, before and after** — same request, with and without team instructions

<!--
#18 | 25분 | ⚠️ 시나리오·샘플 레포 확정 전 (보류 중) — 확정 시 이 장 갱신
- 백업: 녹화본 준비. 권한 프롬프트가 뜨면 #20a의 예고편으로 활용.
-->

---

# Team Setup ① CLAUDE.md — the Onboarding Document for the Agent

**The problem: Projects instructions lived inside a claude.ai account — not next to the code, versioned, shared with the whole team**

```markdown
# CLAUDE.md (repo root — loaded automatically at session start)
## Build & test
- pnpm test to run tests, pnpm lint to lint
## Conventions
- API responses use the shared error format (src/lib/errors.ts)
- Commit messages follow conventional commits
```

- With vs. without: the same request, answered with or without the team's rules (demo #4)
- **Third stop on the secondary axis**: instructions become a **version-controlled team asset** — refined through review and PRs

**Skill ⑨ — environment design**: setting up the desk so the junior works well

<!--
#19 | 3분 | Projects(#10)의 레포 버전이라는 연결
- 시작은 /init — 레포를 훑고 초안을 만들어 준다.
- 계층(말로): 홈 디렉토리(개인 전역) → 레포 루트(팀) → 하위 디렉토리(모듈별).
- "Start by porting what worked in your Projects instructions."
-->

---

# Team Setup ② Permissions and Hooks — Delegate, but Hold the Reins

**The problem: a junior who edits files and runs commands — who decides how far? (the "permissions" of the Introduction)**

```
Permissions — allow / ask / deny, per tool call
  allow: run tests, read files      ask: git push      deny: rm, deploy commands
  Settings hierarchy: organization (enforced) > project (.claude/settings.json) > personal

Hooks (Jun 2025) — scripts that run before/after tool calls (deterministic)
  e.g. run the formatter after every edit / block dangerous commands up front
```

- Permissions are **enforced by the system, not requested from the model** — the decisive difference from instructions ("don't do X")
- The confirmation prompt you saw in the demo is this system

<!--
#20a | 4분 | Introduction ② permissions 매핑의 회수 지점
- 서사: 채팅 시절엔 권한 개념이 불필요 → 행동하는 에이전트에게 필요해짐.
- 훅·권한은 코드라서 어길 수 없다(deterministic) — 지침과의 차이 강조.
- 모드(말로): 기본(매번 확인) / 편집 자동 수락 / plan 등.
- ⚠️ 설정 파일 경로·모드 명칭은 발표 직전 재확인.
-->

---

# Skills — the Final Form of Repeated Instructions

<style scoped>
h1 { font-size: 32px; }
pre { margin: 6px 0; }
</style>

**The problem: even CLAUDE.md loads whole, always — as instructions pile up, they eat the context window**

```
skills/deploy-check/SKILL.md
  ---
  name: deploy-check          ← name & description (metadata) always loaded
  description: Pre-deploy checklist. Use for deploy/release requests.
  ---
  body (detailed procedure)   ← loaded only when the task is relevant
  reference files & scripts   ← loaded only at the moment they are needed
```

**The instructions lineage, completed**: retyped every chat → system prompt (Nov 2023)
→ Projects (Jun 2024) → CLAUDE.md (2025) → **Agent Skills (Oct 2025, open standard)**

- The core shift: **"always load everything (static)" → "only what's needed, when needed (dynamic)"** — the context window is a finite resource
- One skill, everywhere: Claude apps, Claude Code, and the API
- **The instruction you keep pasting is a skill candidate**

<!--
#20b | 5분 | #6b 복선의 회수 지점 — Part 2의 하이라이트
- 계보 도식 [도식 자리]: #6b→#10→#19를 거쳐 온 부 축의 완성.
- progressive disclosure 3단계를 코드 블록 화살표로 표현.
- 표현 주의: "이 흐름의 연장선"으로 (단일 기원 단정 회피).
- 슬래시 커맨드·플러그인은 말로 한 줄씩.
-->

---

# Team Setup ④ Connecting MCP — Where the Standard Becomes Practice

**Wiring #13's standard into our team**

```bash
claude mcp add our-tracker -- npx our-tracker-mcp   # personal registration
# commit .mcp.json to the repo → the whole team shares the same servers
```

- Scenario: "find the cause of issue #123 and fix it" — tracker lookup to fix and commit, one session
- **Permissions in three layers** (recalling #15):
  ① least-privilege credentials on the server (read-only accounts)
  ② per-tool allow/deny on the client (#20a) ③ an org-managed list of connectable servers

<!--
#21 | 3분 | #13 개념 → 실전
- 도구 결과를 통한 prompt injection 위험(말로): 신뢰할 수 있는 서버만,
  쓰기 도구는 확인 프롬프트 유지.
- ⚠️ mcp add 문법·.mcp.json 공유 방식은 발표 직전 재확인.
-->

---

# Adoption — Start Small, Accumulate Team Assets

**The teams that win are the ones whose small starts leave assets behind (CLAUDE.md, skills)**

1. **Week 1** — everyone delegates one small task (a bug fix, a test)
2. **Week 2** — CLAUDE.md in the main repo (/init, then refine through team review)
3. **Month 1** — promote 2–3 repeated instructions to skills; agree on permission rules
4. **Beyond** — connect internal systems via MCP; automate team rules with hooks

- Cost & plans: to be confirmed right before the talk (figures change often)

<!--
#22 | 3분
- 도입 순서 = 오늘 발표의 목차 순서.
- 사내 플랜·계정 정책이 있으면 여기 명시.
-->
