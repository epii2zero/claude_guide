# 인트로 근거 자료 — AI의 수학 난제 해결 (2026-08-30 검증)

> 인트로 훅 슬라이드(#0.2)의 사실관계와 출처. 발표에서 써도 되는 표현과
> 쓰면 안 되는 표현을 구분해둔다. 발표 직전 최신 상태(특히 GPT-5.6 검증 진행)
> 재확인 필요.

## 1. Claude Fable 5 — 야코비안 추측 반증 (확정)

- **무엇**: 야코비안 추측 (Keller, 1939 — 87년 미해결, Smale의 주요 미해결 문제
  목록에 포함)에 대한 **반례** 발견 → 추측이 거짓임을 증명 (반증).
- **누가/언제**: 2026.07.19~20, 수학자 Levent Alpöge(Anthropic 소속)가
  **Claude Fable 5와 함께** 작업한 결과로 발표. C³→C³ 다항식 사상,
  야코비안 행렬식은 상수(−2)인데 단사가 아님(세 점이 한 점으로).
- **검증**: 손으로("고교 대수 수준") 검증 가능. 약 하루 만에 Lean으로 기계 검증.
  Terence Tao가 2026.07.21 해설 글 발표 및 약 15,000줄 Lean 형식화.
  차원 ≥3 일반화 후속 논문도 나옴.
- **주의(캐비앳)**:
  - "AI 단독 발견"이 아님 — 수학자의 지휘 아래 AI가 반례를 생성.
  - "증명"이 아니라 **반례를 통한 반증** (다만 87년 문제를 매듭지은 것은 맞음).
  - 고전적 2차원 케이스는 여전히 미해결.
  - 발표자가 Anthropic 소속(이해관계 소지)이나 독립 검증 완료로 문제없음.
- **출처**:
  - Terence Tao 해설: https://terrytao.wordpress.com/2026/07/21/a-digestion-of-the-jacobian-conjecture-counterexample/
  - 일반화 논문: https://arxiv.org/abs/2608.00222
  - 보도: https://www.stanfordtechreview.com/articles/jacobian-conjecture-disproved-ai-counterexample

**슬라이드 안전 표현**: "수학자가 Claude Fable 5와 함께 87년 된 야코비안 추측을
반례로 반증 — 하루 만에 Lean 기계 검증 완료 (2차원 케이스는 미해결)"
**금지 표현**: "Fable 5가 (단독으로) 야코비안 추측을 증명/해결했다"

## 2. GPT-5.6 — 사이클 이중 덮개 추측 증명 발표 (검토 진행 중)

- **무엇**: 사이클 이중 덮개 추측 (Szekeres 1973 / Seymour ~1979, 약 50년 미해결,
  그래프 이론)의 증명 발표.
- **누가/언제**: 2026.07.10, OpenAI가 **GPT-5.6 Sol** ("Ultra" 모드)이 증명을
  생성했다고 발표 (GPT-5.6 자체는 2026.07.09 출시). 증명 PDF와 사용 프롬프트 공개.
- **검증 상태 (2026.08 말 기준)**: **미완료.** 자연어 증명, 동료 검토 없음,
  TheoremDB 기준 "Lean 미검증". 다만 전문가 반응은 긍정적 — Thomas Bloom:
  "매우 좋은 증명, 짧고 초등적" (인용 누락은 비판). 독립 해설 논문 존재.
- **주의(캐비앗)**:
  - "해결 확정"으로 말하면 안 됨 — "증명 발표 + 전문가 호평 + 검증 진행 중"까지.
  - "64개 서브에이전트로 1시간 내" 프레이밍은 OpenAI 마케팅 — 의문 제기 있음. 인용 비권장.
- **출처**:
  - OpenAI 발표: https://openai.com/index/gpt-5-6/
  - 증명 PDF: https://cdn.openai.com/pdf/04d1d1e4-bc75-476a-97cf-49055cd98d31/cdc_proof.pdf
  - 검증 상태: https://www.theoremdb.org/statements/cycle-double-cover-conjecture/
  - 전문가 반응: https://the-decoder.com/openais-gpt-5-6-sol-ultra-reportedly-solves-a-50-year-old-math-problem-in-under-an-hour/
  - 독립 해설: https://arxiv.org/abs/2607.16356

**슬라이드 안전 표현**: "GPT-5.6이 ~50년 된 사이클 이중 덮개 추측의 증명을 발표 —
수학자들의 호평, 동료 검토는 진행 중"
**금지 표현**: "GPT-5.6이 난제를 해결했다(확정)" / "1시간 만에 풀었다"

## 3. 보조 근거 (한 줄씩)

- **2025.07** — Gemini Deep Think(공식 채점)와 OpenAI 실험 모델이 IMO 2025에서
  **금메달 수준**(35/42) 달성 — 자연어, 표준 시간 제한.
  https://deepmind.google/blog/advanced-version-of-gemini-with-deep-think-officially-achieves-gold-medal-standard-at-the-international-mathematical-olympiad/
- **2026.01** — 에르되시 미해결 문제들의 **진짜 새 해결**: GPT-5.2가 #397 해결
  (Terence Tao 검증), #728/#729는 Lean 검증 증명. https://arxiv.org/pdf/2601.07421
- **2024.07** — (참고) AlphaProof/AlphaGeometry 2, IMO 2024 은메달 수준.

## 4. ⚠️ 인용하면 안 되는 것

- **2025.10 "GPT-5가 에르되시 문제 10개 해결" 바이럴** — 실제로는 문헌에 이미
  있던 해법을 재발견한 것으로 판명(유용하지만 새 수학 아님). 인용 금지.

## 5. 채택된 인트로(발표자 구성 버전)의 이정표와 캡처

인트로가 발표자의 "IQ 150+ 후배" 버전으로 교체되면서 이정표가 아래 4개로 확정.
캡처 원본은 `slides/assets/intro/`에 보관 (발표자 업로드 PPTX에서 추출).

| 이정표 (슬라이드 표기) | 캡처 파일 | 비고 |
|------------------------|-----------|------|
| IMO 금메달 – 25.07 | news-imo-gemini.png | 제미나이, AI 최초 공식 인정 (기사 2025.07.23) — 2절의 IMO 항목과 일치 ✓ |
| 수능 만점 – 26.02 | news-csat-gemini.png | 제미나이 3.1 프로 (기사 2026.02.20) — 별도 검증 안 함, 캡처가 근거 |
| 최초의 수학 증명 – 26.05 | news-erdos-openai.png | 오픈AI, 에르되시 평면 단위 거리 (기사 2026.05.22) — ⚠️ "최초" 표현은 발표 전 확인 권장 |
| 리만가설 진전 – 26.08 | paper-riemann-claude.png | Claude(Anthropic) 논문 1페이지, Lean 4 형식 검증 명시. 링크: anthropic.com/research/riemann-zeta — ⚠️ 발표 전 상태 재확인 |

기존 1~2절(야코비안·GPT-5.6)은 인트로에서 빠졌지만 Q&A 대비 자료로 유지.

## 6. 전체 프레이밍 가이드

- "AI는 이미 우리보다 높은 지능을 가졌다"는 **단정은 근거가 지탱하지 못함**
  (Tao 등도 "알려진 기법을 쓴 AI-보조 결과"로 프레이밍). 안전하고 여전히 강한 표현:
  - "AI가 수십 년 된 수학 미해결 문제들을 매듭짓기 시작했다 — 하나는 완전 검증,
    하나는 검토 중"
  - "적어도 이런 영역에서, 지능은 이미 인간 최고 수준을 넘나든다"
- 이 정직한 프레이밍 자체가 발표 후반부 "검증 습관"(#15) 메시지와 일관됨 —
  발표자가 시범을 보이는 셈.
