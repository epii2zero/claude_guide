---
marp: true
theme: lab
paginate: true
---

<!--
Part 1 slides — ENGLISH (final-deck language), 12 slides / 40 min.
Copy follows the lab template's English style. Korean draft (part1-draft.md)
remains the planning/reference version; timing and demo pointers are identical.
Speaker notes stay in Korean for the presenter.
-->

# One Direction of Evolution

**Every feature gave the junior more context and more ability to act**

```
2023          2024                    2025~                     2026
 Chat   →   Context / multimodal →  Birth of agents        →  Agents everywhere
            Tools / artifacts /     (Claude Code)             (Skills, SDK, Cowork,
            standards                                          Claude 5 generation)
            (Tool use, Artifacts,
             Projects, MCP)
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

# Fundamentals — Briefing the Junior Well

**Bad question**
> "My code doesn't work. Please fix it."

**Good question**
> [Situation] Adding pagination to the orders API / [Materials] error log + function attached
> [Constraint] DB schema is fixed / [Request] two likely causes, each with a fix as a diff

**Formula: context + materials + constraints + output format** — the same briefing you would give a human junior

<!--
#6 | 6분 (시연 3분 포함)
- [시연 자리] 두 질문을 실제로 던져 응답 차이 (part1-demos.md 시연 1).
- 시연 후: "The difference is not the model — it is the quality of the briefing."
- 역량 ① Asking well. 시스템 프롬프트(2023.11, Claude 2.1) 소개 —
  반복하던 지시를 대화에서 분리한 첫걸음 = Introduction ②의 **instructions**의
  출발점. 복선: "이 흐름이 스킬까지 이어집니다."
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

# June 2024: The Junior Reports with Deliverables — Artifacts

**Receive work products, not conversation**

- Code, documents, **runnable HTML prototypes** in a separate pane — iterate and share
- "Explain it" ✗ → "Build it" ✓ (Skill ⑤)

[캡처 자리: API spec → working mockup page, 1 screenshot]

<!--
#9 | 2분 | 간단히 언급
- 사전 녹화 30초 또는 캡처 2장 (시연 4 축소판).
- "수동 전달(manual relay)의 벽(#5)이 절반 열린 지점" 한 줄로 연결.
-->

---

# June 2024: Projects — Giving the Junior Domain Knowledge

**The Introduction asked what we are still better at — domain knowledge and know-how. This is the first feature for handing it over.**

| Component | Role |
|-----------|------|
| **Custom instructions** | Rules applied to every conversation in the project |
| **Knowledge** | Uploaded documents every conversation can reference |
| **Conversations** | One home for all chats on the same work |

**Why it still matters**: design discussions, writing, and reviews still happen in chat —
Projects lays the team's context underneath them

<!--
#10 | 5분 | Part 1의 두 번째 하이라이트 시작
- "잠깐 쓰고 지나간 기능이 아니다" — 10분을 쓰는 이유 명시.
- 부 축 상기: 시스템 프롬프트(개발자 API 기능)가 일반 사용자 기능이 된 두 번째 정거장.
- Introduction ② 매핑 회수: custom instructions = **instructions**,
  knowledge + 이후의 Memory = **memory**.
- 이후 Memory로 확장 한 줄.
-->

---

# Projects in Practice — Three Patterns

**① Team convention guide** — API design and review rules as instructions
→ every design consultation reflects team rules automatically

**② Onboarding and domain knowledge** — design docs, glossary, architecture notes
→ "how does X work here?" answered even for newcomers

**③ Recurring work templates** — postmortems, release notes, weekly reports
→ same format and tone, every time

**Tips**: keep instructions short and imperative / curate documents / one project per job

<!--
#11 | 5분 (시연 3분 포함)
- [시연 자리] 시연 5 확대판: 지침 안/밖 비교 + 용어집 질의 (part1-demos.md).
- 시연 후: "같은 질문, 다른 답. 차이는 담아둔 지침과 문서뿐."
- 역량 ⑥ 지식의 문서화. Part 2 복선: "이 지침이 레포로 들어간 것이 CLAUDE.md."
-->

---

# Oct 2024: Delegate and Watch — Computer Use

**From step-by-step instruction to delegate-and-watch — the first experiment in handing the junior a whole task**

- The model views the screen, decides, and moves the cursor like a person (beta)
- Not a mature product — a preview of the direction

**Skill ⑦ — judging what to delegate and what to keep**

<!--
#12 | 2분
- 데모 영상 캡처 1장. 짧게 치고 넘어가는 장.
- 도구를 '골라 쓰는' 것을 넘어 '연속으로, 스스로' 쓰는 모델 — #14 두 번째 복선.
-->

---

# Nov 2024: MCP — A Standard Key to Internal Systems

**Granting the junior access to servers and internal systems becomes one open protocol — the "MCP" of the Introduction**

```
[Internal wiki]  [Issue tracker]  [Internal DB]
       └──────────  MCP server  ──────────┘
                        │  (standard protocol)
       ┌────────────────┼────────────────┐
  [Claude.ai]     [Claude Code]     [Other clients]
```

- Build one MCP server; use it from every MCP client
- Adopted industry-wide as an open standard

**Skill ⑧ — integration design and access boundaries** (limiting permissions remains our job)

<!--
#13 | 3분
- [도식 자리] 위 텍스트 도식을 그래픽으로.
- 개념까지만. "실제 연결은 Part 2에서 Claude Code와 함께."
- 보안 경계 언급 — #15와 연결.
-->

---

# 2025: Convergence — A Junior You Can Hand Whole Tasks To

**All the pieces assemble into a model that runs its own loop — an agent**

```
Long context ─┐
Vision        ─┤
Tool use      ─┼─→  A model that plans, uses tools,     =  an agent
Artifacts     ─┤    checks results, and loops on its own    (the frame around
Knowledge     ─┤    (extended thinking, Feb 2025)            this loop is the
MCP           ─┘                                             harness)
```

**Feb 2025 — the assembled result arrives: Claude Code**

<!--
#14 | 4분 | Part 1의 클라이맥스
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
