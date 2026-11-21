# Vision & Need

## What the Tool Is

**Financial Toolkit** is a browser-based, single-page application that provides six essential financial calculators for investment analysis, loan calculations, and portfolio management. Built as a static web application (vanilla HTML/CSS/JavaScript with Chart.js via CDN), it runs instantly in any modern browser and deploys freely to GitHub Pages with zero backend infrastructure.

The toolkit includes six core calculators:

| Module | Purpose |
|--------|---------|
| **Compound Interest** | Calculate future value of investments with multiple compounding frequencies, regular contributions (beginning/end of period), and effective annual rate (EAR) computation. |
| **Loan Amortization** | Generate full amortization schedules for mortgages and loans with monthly/bi-weekly/weekly payments, total interest breakdown, and bi-weekly payment savings analysis. |
| **Investment Returns** | Three analysis modes: CAGR calculator, annualized return conversion, and side-by-side investment comparison. |
| **Retirement Planner** | Two planning modes: savings goal calculator (required monthly contributions for target income) and withdrawal strategy tester (portfolio longevity with inflation-adjusted withdrawals, 4% rule benchmark). |
| **Bond Calculator** | Fixed income analysis: price from yield (clean price, current yield, premium/discount), YTM from price (Newton-Raphson), and duration/convexity metrics (Macaulay, modified, convexity, DV01). |
| **NPV / IRR Analysis** | Capital budgeting evaluation: NPV at specified discount rate, IRR (numerical approximation), Profitability Index, Payback Period, and cash flow summary table. |

All calculators share a unified, responsive UI with dark/light theme support, keyboard shortcuts, and export capabilities.

---

## Target User

| Persona | Why They Need This |
|---------|-------------------|
| **Finance Students (BUS 201, FIN 445, MSF, MBA)** | Interactive learning aid for time-value-of-money, bond math, capital budgeting, and retirement planning concepts. Verify homework, explore "what-if" scenarios instantly. |
| **Investment Banking / PE Analysts** | Quick back-of-envelope calculations for CAGR, NPV/IRR, bond duration, and loan amortization without opening Excel. |
| **Real Estate / Credit Analysts** | Loan amortization schedules with bi-weekly payment analysis; bond analytics for credit spread work. |
| **Financial Advisors / Wealth Managers** | Retirement planning conversations with clients: show savings gaps, withdrawal sustainability, and inflation impact in real time. |
| **Career Switchers / Self-Learners** | Portfolio piece demonstrating both domain fluency (financial mathematics) and technical execution (full-stack web development, GitHub Pages deployment). |

---

## Problem It Solves

| Pain Point | How the Toolkit Addresses It |
|------------|-------------------------------|
| **Scattered calculators** — different websites for TVM, bonds, loans, NPV; inconsistent UX. | Single unified interface: six calculators, consistent design, instant switching. |
| **Excel dependency** — templates require Office, version conflicts, no mobile access. | Zero-install, runs anywhere with a browser (laptop, tablet, phone). |
| **Black-box formulas** — online calculators hide the math; users memorize buttons instead of understanding drivers. | Every formula displayed in documentation; tooltips explain each input's economic meaning. |
| **No scenario comparison** — most calculators solve for one variable at a time. | Investment Returns module enables side-by-side comparison; Retirement Planner tests multiple withdrawal strategies. |
| **Static outputs** — can't export cleanly for reports or presentations. | Copy-ready results, print-friendly layout, CSV export capability. |
| **Steep learning curve for students** — financial calculators (HP 12C, TI BA II+) have opaque key sequences. | Clean UI separates *inputs* from *calculations* from *outputs*; pedagogical by design. |

---

## Key Features & Career Relevance

| Feature | Career Value |
|---------|--------------|
| **Six calculators in one app** | Shows breadth across corporate finance (NPV/IRR), investments (CAGR, bonds), personal finance (retirement, loans), and real estate credit (amortization). |
| **Multiple modes per calculator** | Investment Returns: CAGR + annualized + comparison. Retirement: savings goal + withdrawal strategy. Bond: price→yield + yield→price + duration. Demonstrates product thinking. |
| **Numerical methods implemented** | IRR via binary search, YTM via Newton-Raphson, duration/convexity via closed-form sums — proves you understand the math behind the buttons. |
| **Bi-weekly mortgage analysis** | Real-world feature: shows interest savings from accelerated payments — exactly the kind of client-facing analysis advisors do daily. |
| **Inflation-adjusted retirement modeling** | Real rate of return calculations, 4% rule benchmark — shows you understand purchasing power erosion, not just nominal math. |
| **Chart.js visualizations** | Interactive charts for amortization schedules, retirement projections, and cash flow timelines — walk an interviewer through the visual live. |
| **GitHub Pages deployment** | A live, public URL you put on your resume: "Built a financial calculator toolkit used by classmates—try it at username.github.io/financial-toolkit." |
| **Vanilla JS, no framework lock-in** | Proves you understand fundamentals (DOM, event loop, ES6 modules, CSS custom properties) not just React/Vue boilerplate. |
| **Dark/light theme, responsive, accessible** | Production-quality polish: WCAG-friendly contrast, keyboard navigation, mobile-first layout. |
| **Open source, extensible** | Add modules (Black-Scholes, CAPM, WACC, mortgage refinance) and showcase continuous improvement on your GitHub profile. |

---

## How It Enhances Your Resume

> **Financial Toolkit** — *Full-stack web application (Vanilla JS, Chart.js, GitHub Pages)*
> - Architected and built a browser-based financial calculator platform spanning six modules: TVM, loan amortization, investment returns, retirement planning, bond analytics, and capital budgeting
> - Implemented numerical methods: Newton-Raphson for YTM, binary search for IRR, closed-form duration/convexity
> - Deployed as a static site (zero backend) enabling instant access via GitHub Pages with automated CI/CD
> - **Tech stack**: ES6 modules, Chart.js (CDN), CSS Grid/Flexbox/Custom Properties, GitHub Actions
> - **Finance references**: Brealey/Myers/Allen (Corporate Finance), Bodie/Kane/Marcus (Investments), Fabozzi (Fixed Income)
>
> **Why this stands out**: Most candidates list "financial modeling" as a skill with Excel screenshots. You ship a *product* that proves you understand both the finance *and* the engineering—and you can hand a hiring manager a working URL during the interview.