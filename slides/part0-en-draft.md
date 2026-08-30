---
marp: true
theme: lab
paginate: true
---

<!--
Part 0 intro slides — ENGLISH (final-deck language).
Based on the presenter's own refined Introduction (IQ 150+ junior-colleague
frame), carried over as faithfully as possible; screenshots preserved in
slides/assets/intro/. Copy follows the lab template's English style.
Korean draft (part0-draft.md) remains the planning/reference version.
Speaker notes stay in Korean for the presenter.
-->

<!-- _class: title -->
<!-- _paginate: false -->

# How to Get the Most out of Claude

## From Chat to Agents

DSP&AI Lab., Yonsei University
발표자 이름
2026.MM.DD

<!--
#0.1 | 30초
- 제목이 곧 주제(질문), 부제가 방법론(발전 과정을 따라간다).
- 템플릿 타이틀 형식: 제목 30pt #003876 / 소속 / 발표자 / 날짜.
-->

---

# Introduction

![bg vertical right:38% fit](assets/intro/news-imo-gemini.png)
![bg fit](assets/intro/news-csat-gemini.png)
![bg fit](assets/intro/news-erdos-openai.png)
![bg fit](assets/intro/paper-riemann-claude.png)

**AI may have already surpassed us in intelligence**

- IMO gold medal – Jul 2025
- Perfect score on the Suneung (Korean CSAT) – Feb 2026
- First original mathematical proof – May 2026
- Progress on the Riemann hypothesis – Aug 2026
  <span class="cite">anthropic.com/research/riemann-zeta</span>

**How I think about AI when I use it**

- Treat AI as a **junior colleague with an IQ of 150+**
- What am I still better at than this brilliant junior?
- How, and how far, should I delegate work to them?

*< News on AI's achievements · Claude's Riemann paper >*

<!--
#0.2 | 3분 | Introduction ① (사용자 구성 기반, 영어 문안)
- "may have already surpassed us" — 단정("has surpassed")이 아닌 신중한 표현으로
  원문의 "능가했을지 모른다"를 살림.
- "junior colleague with an IQ of 150+" — 후배는 junior colleague가 자연스럽고,
  IQ 150+를 형용사구로. 이후 슬라이드에서 "the junior"로 짧게 받는다.
- 이정표·캡처 대응과 발표 전 확인 사항은 KO 버전(part0-draft.md) 노트 참고.
-->

---

# Introduction

**What I am still better at than the junior**

- Domain knowledge, know-how

**How, and how far, to put the junior to work**

- Training on our tools, allocating servers, limiting permissions, verifying the work

**Everyone shares the same questions**

- How to give AI domain knowledge and know-how → **instructions, memory, skills**
- Allocating servers, limiting permissions, verifying the work → **tools, MCP, permissions, harness**

<!--
#0.3 | 2분 | Introduction ② (사용자 구성 기반, 영어 문안)
- "프로그램 사용법 교육"은 "training on our tools"로 — 신입 온보딩 뉘앙스 유지.
- 기능명(instructions/memory/skills/tools/MCP/harness)은 소문자 일반명사로 두어
  "사람 후배에게 하던 일의 AI 버전"이라는 대응이 자연스럽게 읽히게.
- 전환 멘트: "Today we will walk through these answers one by one."
-->

---

# Today's Journey

**Not a feature list — the path features took**

```
2023          2024                    2025~
 Chat   →   Accumulating         →   Agents (Claude Code)
            capabilities
            Knowing why a feature emerged tells you when to use it
```

- **Part 1** (40 min) — From chat to agents: evolution of features and skills
- **Part 2** (50 min) — The agent in full: Claude Code + live demo
- Out of scope: API integration development

<!--
#0.5 | 1.5분 | 지도
- 휴식·Q&A 안내 한 줄.
- "여정의 끝에서 오늘의 질문에 대한 각자의 답이 생기기를"로 인트로 마감.
-->
