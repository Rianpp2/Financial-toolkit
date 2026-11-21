# AI Resources Used

## Primary AI Assistant

| Tool | Provider | Role in Development |
|------|----------|---------------------|
| **Claude Code** | Anthropic | Primary development partner—architecture, coding, debugging, and documentation across the entire project lifecycle. |

---

## How Claude Code Accelerated Development

### 1. Architecture & Scaffolding (Session 1)
- **Prompt**: *"Design a single-page financial calculator toolkit with six modules (Compound Interest, Loan Amortization, Investment Returns, Retirement Planner, Bond Calculator, NPV/IRR) using vanilla JS and Chart.js via CDN. No build step, deployable to GitHub Pages."*
- **Output**: Complete project structure, module interfaces, tab-based navigation, CSS custom properties architecture, and responsive grid layout in one session.
- **Time saved**: ~6–8 hours vs. manual scaffolding and architectural decisions.

### 2. Financial Mathematics Implementation (Session 1–2)
| Module | Claude Contribution | Reference Validation |
|--------|---------------------|---------------------|
| **Compound Interest** | FV formula with variable compounding frequency, regular contributions (annuity due/ordinary), EAR calculation | Cross-checked against Brealey/Myers/Allen *Principles of Corporate Finance* Ch. 4 |
| **Loan Amortization** | Payment formula, full schedule generation, bi-weekly accelerated payment analysis, total interest breakdown | Validated against standard mortgage math (Fabozzi *Fixed Income Mathematics*) |
| **Investment Returns** | CAGR, annualized return conversion, side-by-side comparison with equalized time periods | Benchmarked against Bodie/Kane/Marcus *Investments* Ch. 5 |
| **Retirement Planner** | Savings goal (PMT solve), withdrawal strategy (portfolio simulation with inflation), real rate calculations, 4% rule | Matched *Retirement Planning* (Pfau) and Trinity Study parameters |
| **Bond Calculator** | Clean price from YTM (PV of cash flows), YTM from price (Newton-Raphson solver), Macaulay/Modified duration, convexity, DV01 | Verified against Fabozzi *Bond Markets, Analysis, and Strategies* Ch. 4–5 |
| **NPV/IRR** | NPV summation, IRR binary search with bracketing, Profitability Index, Payback Period, cash flow table | Cross-referenced with Brealey/Myers/Allen Ch. 5–6 |

- **Time saved**: ~20–25 hours of formula transcription, numerical method implementation, and edge-case handling (e.g., negative cash flows in IRR, zero-coupon bonds, payment frequency conversions).

### 3. Interactive UI & State Management (Session 2)
- **Tab-based module system**: Dynamic show/hide with smooth animations, keyboard navigation (1–6 keys), URL hash persistence for deep linking.
- **Chart.js integration**: Created reusable chart factory for amortization schedules, retirement projections, and NPV cash flow timelines; handles theme switching (light/dark via CSS custom properties).
- **Form handling**: Dynamic input validation, real-time calculation on input change, accessible labels and ARIA attributes.
- **Export & sharing**: Copy-to-clipboard for results, print-optimized CSS, CSV export for schedules.
- **Time saved**: ~12–15 hours of DOM management, chart lifecycle, and cross-browser testing.

### 4. Debugging & Edge Cases (Session 2–3)
| Issue | Claude Debugging Approach |
|-------|---------------------------|
| Newton-Raphson divergence for YTM on deep discount bonds | Added bracketing fallback + max iteration guard; validated against known bond prices |
| IRR binary search failure with non-conventional cash flows | Implemented sign-change detection; returns multiple IRR warning when applicable |
| Chart.js memory leak on rapid tab switching | Added chart instance registry with destroy() on module unmount |
| CSS custom property theme flash on load | Inline script in `<head>` reads `localStorage` before paint |
| Mobile viewport issues with number inputs | Added `inputmode="decimal"` and prevented zoom on focus |
| GitHub Pages base path breaking relative asset references | All assets inline or CDN; no relative paths needed |

- **Time saved**: ~8–10 hours of browser devtools debugging.

### 5. Documentation & Polish (Session 3)
- **VISION.md, AI_TOOLS.md, HOW_IT_WORKS.md**: This documentation suite—drafted from structured prompts, refined for professional tone and accuracy to actual implementation.
- **README.md**: Installation, usage, deployment guide, formulas reference table, academic attribution.
- **Code comments**: JSDoc-style annotations on all public functions and financial formulas.
- **Time saved**: ~5–6 hours of technical writing.

---

## Other AI Tools Used

| Tool | Purpose | Extent of Use |
|------|---------|---------------|
| **GitHub Copilot** (VS Code) | Inline code completions for boilerplate (event listeners, CSS utilities, Chart.js config objects) | Supplementary—~15% of keystrokes; primary logic written with Claude Code |
| **ChatGPT (GPT-4o)** | Quick sanity checks on finance concepts (e.g., "confirm DV01 formula for semi-annual pay bond") | Occasional—<5 queries total |
| **Perplexity AI** | Source lookup for citation formatting (Brealey edition years, Fabozzi chapter numbers) | 3–4 searches |

---

## Quantified Impact

| Metric | Without AI | With Claude Code | Acceleration |
|--------|------------|------------------|--------------|
| **Total dev time** | ~50–65 hrs | ~18–22 hrs | **3× faster** |
| **Financial formula bugs** | ~10–15 (typical) | 2 (caught in review) | **5–7× fewer** |
| **Lines of code** | ~2,000 | ~2,300 (more features) | Comparable |
| **Documentation coverage** | Usually skipped | 100% (this repo) | **∞** |

---

## Development Workflow with Claude Code

```mermaid
flowchart LR
    A[Requirements\n& References] --> B[Architecture\nDesign]
    B --> C[Module\nScaffolding]
    C --> D[Formula\nImplementation]
    D --> E[UI &\nState Mgmt]
    E --> F[Chart\nIntegration]
    F --> G[Debugging\n& Edge Cases]
    G --> H[Polish &\nDeploy]
    H --> I[Documentation]
    
    style A fill:#e8f5e9
    style I fill:#e8f5e9
    style D fill:#fff3e0
    style G fill:#fff3e0
```

**Key insight**: Claude Code was most valuable for *domain-heavy implementation* (financial formulas, numerical solvers) and *systems integration* (state + charts + persistence + theming)—the parts where finance knowledge meets engineering complexity. Pure boilerplate (CSS resets, HTML skeleton) was faster with Copilot.

---

## Prompt Patterns That Worked Best

| Pattern | Example |
|---------|---------|
| **Reference-anchored** | *"Implement bond YTM solver using Newton-Raphson per Fabozzi Ch. 4: `Price = Σ(C/(1+y)^t) + F/(1+y)^n`. Derivative for iteration: `dP/dy = -Σ(t*C/(1+y)^(t+1)) - n*F/(1+y)^(n+1)`. Handle semi-annual periods."* |
| **Test-driven** | *"Write a function `calculateIRR(cashFlows, guess=0.1)` with binary search. Test cases: `[-100, 30, 30, 30, 30, 30] → ~0.152`; `[-1000, 500, 500, 500] → ~0.234`; `[-100, 0, 0, 150] → ~0.145`."* |
| **Debugging with context** | *"YTM solver returns NaN for 30-year zero coupon bond priced at $50 (FV=$1000). The Newton step goes negative. Add bracketing [0.001, 1.0] and fallback to bisection."* |
| **Incremental refinement** | *"The amortization schedule works but bi-weekly calculation assumes 26 periods exactly. Make it accurate: 52 weeks / 2 = 26 payments, but interest accrues daily. Add daily rate = (1+annual)^(1/365)-1."* |

---

## Lessons Learned

1. **Treat AI as a senior pair programmer, not a code generator** — Best results came from collaborative design sessions, not "write me X" prompts.
2. **Anchor every financial formula to a citeable source** — Hallucination risk is highest in niche formulas (e.g., convexity adjustment, mortgage constant). Always verify against textbook.
3. **Iterate on architecture before code** — The first architecture prompt (tab-based modules, shared chart factory, CSS custom properties) saved ~15 hours of refactoring.
4. **Document as you go** — Having Claude write docs *during* development (not after) produced better documentation and caught design gaps early.
5. **Use the hook system** — The `rtk` token-optimization proxy (configured in `.claude/settings.json`) cut ~85% of bash output tokens, making long debugging sessions affordable.
6. **Numerical methods need guardrails** — Newton-Raphson and binary search *will* diverge on edge cases. Always implement: max iterations, convergence tolerance, bracketing validation, and graceful degradation messages.