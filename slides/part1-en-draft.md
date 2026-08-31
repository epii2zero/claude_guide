---
marp: true
theme: lab
paginate: true
---

<!--
Part 1 slides — ENGLISH (final-deck language), 12 slides / 40 min
(original numbering #4~15; #9 Artifacts and #12 Computer use removed; #6 and #10 each split into a/b).
Copy follows the lab template's English style. Korean draft (part1-draft.md)
remains the planning/reference version; timing and demo pointers are identical.
Speaker notes stay in Korean for the presenter.
-->

# One Direction of Evolution

**Every feature gave the junior more context and more ability to act**

```
2023          2024                    2025~                     2026
 Chat   →   Context / multimodal →  Birth of agents        →  Agents everywhere
            Tools / knowledge /     (Claude Code)             (Skills, SDK, Cowork,
            standards                                          Claude 5 generation)
            (Tool use, Projects,
             MCP)
```

[도식 자리: timeline graphic — year axis + feature icons + direction arrow]

<!--
#4 | 2분
- "지금부터 40분간 이 타임라인을 왼쪽에서 오른쪽으로 걷습니다."
- 인트로 연결 멘트: "This timeline is the industry's three-year answer to the
  Introduction's two questions — what to give the junior, and how to delegate."
- 기능이 "왜 나왔는지"를 보면 언제 써야 하는지도 보인다는 프레임.
-->

---

# Chatbot (2023)

<style scoped>
p:has(img) { text-align: center; margin: 2px 0; }
p:has(img) img { margin: 0 8px; vertical-align: top; }
em { display: block; text-align: center; font-size: 17px; margin: 2px 0 14px; }
</style>

![h:195](assets/part1/chat-claude.png) ![h:195](assets/part1/chat-gpt.png)

*< Chat screens of Claude and GPT >*

- A chatbot that answers questions
- Limitations
  - **Frozen knowledge** - only what it was trained on; unaware of recent information
  - **Manual relay** - every piece of context delivered by hand, every result carried back by hand
  - **Hallucination** - plausible wrong answers, spoken with confidence
  - These limitations motivate every feature that follows

<!--
#5 | 3분 | 사용자 구성 기반, 영어 문안
- "수동 전달"은 "Manual relay"로 — 사람이 중계기 역할을 한다는 뉘앙스.
  ("Copy-paste workflow"보다 원안의 표현 의도에 가까움)
- 후배 은유 연결 멘트: "Like a junior's first day — knows a great deal,
  but nothing about our work."
- 2023.03 첫 Claude(API), 2023.07 claude.ai 공개.
- 마지막 줄이 Part 1 전체의 예고편.
-->

---

# Chatbot-Era Usage ① — Briefing Well

**Bad question**
> "My code doesn't work. Please fix it."

**Good question**
> [Situation] Adding pagination to the orders API / [Materials] error log + function attached
> [Constraint] DB schema is fixed / [Request] two likely causes, each with a fix as a diff

**Formula: context + materials + constraints + output format** — the same briefing you would give a human junior

<!--
#6a | 4분 (시연 3분 포함)
- [시연 자리] 두 질문을 실제로 던져 응답 차이 (part1-demos.md 시연 1).
- 시연 후: "The difference is not the model — it is the quality of the briefing."
- 역량 ① Asking well.
-->

---

# Chatbot-Era Usage ② — Instructions

<style scoped>
p:has(img) { text-align: center; margin: 2px 0; }
p:has(img) img { margin: 0 10px; vertical-align: top; }
em { display: block; text-align: center; font-size: 17px; margin: 2px 0 12px; }
</style>

![h:205](assets/part1/profile-instructions.png) ![h:230](assets/part1/custom-instructions-gpt.jpg)

*< Custom instructions in Claude and ChatGPT >*

- **The age of prompt engineering** — context, rules, and the desired output format typed in with every chat request
  - **"You are a backend engineer with ten years of experience"** — assigning a persona
- **Global instruction** — context once retyped into every conversation, now managed separately and applied to every chat automatically
- **An early way of handing know-how to the AI** — the lineage runs on to Projects instructions → CLAUDE.md → skills

<!--
#6b | 3분 | 사용자 원안 기반 (전체본 v2 문안) | 지시의 계보 부 축의 출발 정거장
- 캡처 2장: 왼쪽 Claude 프로필 개인 지침, 오른쪽 ChatGPT 맞춤 설정 (원안 보존본).
- 변화의 서사가 핵심: 매번 채팅에 붙여넣던 역할·규칙 → 설정에 한 번
  통째로(global instruction).
- 담는 곳의 계보(스피커용 연표): system prompt(2023.11, API) →
  profile instructions(계정 전역) → Projects custom instructions(2024.06,
  프로젝트 단위) → CLAUDE.md → skills. 담는 곳이 곧 적용 범위.
- 후배 은유: 페르소나 = 후배에게 역할과 기준을 정해주는 것.
- Introduction ② 매핑 회수: **instructions**의 출발점.
-->

---

# 2023–24: Handing Over the Onboarding Binder, Whole

**Long context** — 100K → 200K → now 1M tokens
Paste logs, documents, and code whole; beyond "summarize this" to "find the root cause in this log"

**Vision** (Mar 2024, Claude 3) — show, don't transcribe
Error screenshots, architecture diagrams, UI mockups as-is

**Skills ②③** — curating what goes in; choosing words vs. pictures

<!--
#7 | 3분 | 간단히 훑는 장
- 백업 캡처 2장으로 시연 대체 (시간 여유 시에만 로그 라이브 — 시연 2).
- 오해 교정: more is not better — 무관한 자료는 초점을 흐린다.
-->

---

# May 2024: Handing the Junior Tools — Tool Use

**The model starts acting on the world beyond its training data — the "tools" of the Introduction begin here**

```
Request → model selects a tool → executes → observes result → decides next step
          (search, compute, look up, ...)
```

- Web search, code execution — the frozen-knowledge wall opens
- **First step toward agents**: a model that chooses its tools

**Skill ④ — knowing what the model can and cannot do**

<!--
#8 | 3분
- [도식 자리] 루프 도식 — #14에서 "스스로 도는 루프"로 확장. 시각 언어 유지.
- 개발자 한 줄: 좋은 도구 설명 = 좋은 API 문서.
-->

---

# June 2024: Projects — Giving the Junior Domain Knowledge

<style scoped>
h1 { font-size: 37px; }
p:has(img) { text-align: center; margin: 0; }
em { display: block; text-align: center; font-size: 17px; margin: 2px 0 8px; }
table { font-size: 20px; }
</style>

![h:225](assets/part1/project-screen.png)

*< A real project screen — Instructions · Memory · Context >*

**A workspace where instructions, knowledge, and memory are stored once and shared by every conversation** — work context separated and managed by topic

| Component | Role |
|-----------|------|
| **Instructions** | Rules applied to every conversation in the project |
| **Context** | Shared reference knowledge for the project (design docs, guides, glossaries) |
| **Conversations** | Chats in the project can reference one another — history in one place |
| **Project memory** | Project-scoped memory, managed automatically |

<!--
#10a | 3분 | 사용자 원안 기반 (실제 프로젝트 화면 캡처) | Projects 3장의 시작
- 도입 멘트(인트로 회수): "The Introduction asked what we are still better at —
  domain knowledge and know-how. This is the first feature for handing it over."
- 요소 명칭은 실제 UI 라벨을 따름: Instructions / Context(구 Knowledge) /
  Project memory — 캡처 화면의 패널명과 1:1 대응.
- 캡처 포인트: Context 패널의 "6% of project capacity used · Search mode"
  → 다음 장(#10b) 동작 원리의 예고.
- 왜 지금도 중요한가(말로): design discussions, writing, reviews still happen
  in chat — Projects lays the team's context underneath them.
- 부 축 상기: #6b의 다음 정거장 (계정 전역 → 프로젝트 단위).
- Introduction ② 매핑 회수: Instructions = **instructions**, Context +
  Project memory = **memory**.
- ⚠️ 수치(지침 약 8천 자)는 발표 전 헬프센터 재확인.
-->

---

# Projects — How Knowledge Actually Works

**Small enough, read whole; too large, retrieved**

```
knowledge ≤ context window   →  loaded whole (every chat sees everything)
knowledge > context window   →  RAG retrieval kicks in (paid plans)
                                only the parts relevant to the question are loaded
```

- Developer takeaway: **curation still matters** — noisy documents lower answer quality even in retrieval mode

**Availability** (as of Aug 2026 — re-verify before the talk)

- Free: 5 projects (since Feb 2026) / **Pro·Max·Team·Enterprise**: unlimited + RAG mode
- **Team sharing**: Team·Enterprise — role-based (private/view/edit), co-managed instructions and knowledge

<!--
#10b | 3분 | 동작 원리와 제공 범위
- "Small enough, read whole; too large, retrieved" 한 줄이 핵심.
  #20의 정적/동적 로딩 이야기의 복선.
- 실전 경로: start personal, promote the good ones to team projects.
- ⚠️ 수치·플랜 조건 발표 직전 재확인.
-->

---

# Projects in Practice — Three Patterns

**① Team convention guide** — API design and review rules as instructions
→ every design consultation reflects team rules automatically

**② Onboarding and domain knowledge** — design docs, glossary, architecture notes
→ "how does X work here?" answered even for newcomers

**③ Recurring work templates** — postmortems, release notes, weekly reports
→ same format and tone, every time

**Tips**: keep instructions short and imperative (short rules are followed best)
/ curate documents — noise lowers quality even in retrieval mode / one project per job
/ promote a well-built personal project to a team project

<!--
#11 | 6분 (시연 3분 포함)
- [시연 자리] 시연 5 확대판: 지침 안/밖 비교 + 용어집 질의 (part1-demos.md).
- 시연 후: "같은 질문, 다른 답. 차이는 담아둔 지침과 문서뿐."
- 역량 ⑥ 지식의 문서화. Part 2 복선: "이 지침이 레포로 들어간 것이 CLAUDE.md."
-->

---

# Nov 2024: MCP — Standardizing the Connection

**The problem: models could use tools, but every connection was hand-built — M apps × N tools = M×N custom integrations**

```
Before (M×N) — a dedicated connector per app-tool pair
  [Claude]═[wiki]  [Claude]═[DB]  [IDE]═[wiki]  [IDE]═[DB]  [bot]═[wiki] ...

After (M+N) — one connection standard: MCP
  [Internal wiki]  [Issue tracker]  [Internal DB]
        └──────────  MCP server  ──────────┘
                         │  (standard protocol)
        ┌────────────────┼────────────────┐
   [Claude.ai]     [Claude Code]     [Other clients]
```

- One **MCP server** per tool, one **MCP client** per app — the explosion disappears
- "USB-C for AI" — one port instead of a different cable per device
- An open standard (Anthropic, Nov 2024), adopted industry-wide — the shared key to internal systems

**Skill ⑧ — integration design** (deciding what to open, with which boundaries — limiting permissions remains our job)

<!--
#13 | 3분 | 서사: 무슨 문제를 풀려고 나왔나
- 서사 순서: ① 도구 사용이 열림(#8) → ② 연결마다 다른 API·인증·형식을
  앱별로 따로 구현 (M×N 조합 폭발) → ③ 연결 "규격"을 공개 표준으로 (M+N).
- Introduction ② 매핑 회수: 후배에게 서버·사내 시스템 접근을 주는 방법 =
  **MCP**. "서버 할당"의 표준화.
- 채택 언급(스피커): OpenAI(2025.03)·Google 등도 채택 ⚠️ 발표 전 재확인.
- [도식 자리] Before/After 텍스트 도식을 그래픽으로.
- 개념까지만. "실제 연결은 Part 2에서 Claude Code와 함께."
- 보안 경계 언급 — #15와 연결.
-->

---

# 2025: Convergence — A Junior You Can Hand Whole Tasks To

**All the pieces assemble into a model that runs its own loop — an agent**

```
Long context ─┐
Vision        ─┤    A model that plans, uses tools,
Tool use      ─┼─→  checks results, and loops on its own  =  an agent
Knowledge     ─┤    (extended thinking, Feb 2025)             (the frame around
MCP           ─┘                                              this loop is the harness)
```

**Feb 2025 — the assembled result arrives: Claude Code**

<!--
#14 | 5분 | Part 1의 클라이맥스
- [도식 자리] 조립 도식 — #8 루프 도식의 확장형. Part 2 #16에서 재등장.
- 중심 문장: "새 발명품이 아니라 방금 본 기능들의 조립입니다." 호흡 길게.
- Introduction ② 매핑 완성: 루프를 감싸는 틀 = **harness** — 이로써
  tools·MCP·harness 줄이 모두 채워짐. instructions·memory·skills 줄은
  Projects~Part 2(CLAUDE.md·skills)에서 완성된다고 언급.
-->

---

# However Brilliant the Junior, Verification Is Ours

**Two safety rules before Part 2 — the Introduction's "permissions, verifying the work"**

1. **Hallucination has not gone away** → always verify
   (run tests, review code, check sources — capability up, verification up)
2. **Respect security boundaries** → follow internal rules on code and data
   (⚠️ 사내 정책 확인 후 이 장 문안 확정)

> The tools grew stronger; the responsibility is still ours

<!--
#15 | 2분
- 사내 보안 정책 확인 후 문안 확정.
- 휴식 직전: "10분 쉬고, 방금 본 조립의 결과물을 직접 봅니다."
-->
