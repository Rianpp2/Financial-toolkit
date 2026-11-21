# Financial Toolkit

A collection of professional financial calculators for investment analysis, loan calculations, and portfolio management. Built for educational coursework (BUS 201 Professional Development, FIN 445 Investments).

## 🌐 Live Demo

**[View Live Demo →](https://rianpatel.github.io/financial-toolkit/)**

*(Replace `rianpatel` with your GitHub username after deployment)*

---

## 🚀 Quick Start

### Option 1: Run Locally (No Setup Required)

Simply open `index.html` in your browser:

```bash
# Clone the repository
git clone https://github.com/rianpatel/financial-toolkit.git
cd financial-toolkit

# Open in default browser
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

Or drag and drop `index.html` directly into any modern browser.

### Option 2: Local Development Server

For a better development experience with live reload:

```bash
# Using Python 3
python3 -m http.server 8000

# Using Node.js (if installed)
npx serve .

# Using PHP
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

---

## ✨ Features

### 📈 Compound Interest Calculator
Calculate future value with support for:
- Multiple compounding frequencies (annual, quarterly, monthly, daily)
- Regular contributions (beginning or end of period)
- Effective annual rate calculation

![Compound Interest Calculator](docs/screenshots/compound-interest.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

### 🏠 Loan Amortization
Mortgage and loan analysis with:
- Monthly, bi-weekly, or weekly payments
- Full amortization schedule (first 24 periods + final payment)
- Total interest cost breakdown
- Bi-weekly payment savings tip

![Loan Amortization](docs/screenshots/loan-amortization.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

### 📊 Investment Returns
Three analysis modes:
- **CAGR Calculator** — Compound Annual Growth Rate from beginning/ending values
- **Annualized Return** — Convert total return to annualized rate
- **Investment Comparison** — Side-by-side CAGR comparison of two investments

![Investment Returns](docs/screenshots/investment-returns.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

### 🏖️ Retirement Planner
Two planning modes:
- **Savings Goal** — Calculate required monthly contributions for target retirement income
- **Withdrawal Strategy** — Test portfolio longevity with inflation-adjusted withdrawals
- Real rate of return calculations (nominal return adjusted for inflation)
- 4% rule benchmark reference

![Retirement Planner](docs/screenshots/retirement-planner.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

### 📜 Bond Calculator
Fixed income analysis tools:
- **Price from Yield** — Clean price, current yield, premium/discount
- **YTM from Price** — Yield to maturity via Newton-Raphson approximation
- **Duration & Convexity** — Macaulay duration, modified duration, convexity, DV01

![Bond Calculator](docs/screenshots/bond-calculator.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

### 💰 NPV / IRR Analysis
Capital budgeting evaluation:
- Net Present Value at specified discount rate
- Internal Rate of Return (numerical approximation)
- Profitability Index
- Payback Period
- Full cash flow summary table

![NPV IRR](docs/screenshots/npv-irr.png)
*[Screenshot placeholder — add actual screenshot to `docs/screenshots/`]*

---

## 🛠️ Tech Stack

- **HTML5** — Semantic markup, accessible forms
- **CSS3** — Custom properties (CSS variables), CSS Grid, Flexbox
- **Vanilla JavaScript (ES6+)** — No dependencies, no build step
- **GitHub Actions** — Automated deployment to GitHub Pages

### Browser Support
| Browser | Version |
|---------|---------|
| Chrome  | 80+     |
| Firefox | 75+     |
| Safari  | 13+     |
| Edge    | 80+     |

---

## 📦 Deployment

### Automatic Deployment (Recommended)

This repository includes a GitHub Actions workflow (`.github/workflows/pages.yml`) that automatically deploys to GitHub Pages on every push to `main`.

**Setup steps:**

1. **Push to GitHub:**
   ```bash
   git add .
   git commit -m "Initial commit: Financial Toolkit"
   git branch -M main
   git remote add origin https://github.com/rianpatel/financial-toolkit.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - Go to **Settings → Pages** in your GitHub repository
   - Under **Build and deployment**, select **GitHub Actions** as the source
   - The workflow will run automatically on push

3. **Access your site:**
   - URL: `https://<your-username>.github.io/financial-toolkit/`
   - First deployment takes 1-2 minutes

### Manual Deployment

If you prefer manual control:

```bash
# Build not required — static files only
# Just push to a gh-pages branch or use GitHub Pages UI
```

### Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file to the repository root:
   ```
   financial-toolkit.yourdomain.com
   ```

2. Configure DNS:
   - **A records** pointing to GitHub Pages IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Or **CNAME** pointing to `<username>.github.io`

3. Enable **Enforce HTTPS** in Settings → Pages after DNS propagates

---

## 📁 Project Structure

```
financial-toolkit/
├── index.html              # Main application (GitHub Pages entry point)
├── README.md               # This file
├── .github/
│   └── workflows/
│       └── pages.yml       # GitHub Actions deployment workflow
└── docs/
    └── screenshots/        # Screenshot assets for README (add your own)
```

---

## 🎓 Attribution & Academic Use

This project was developed as part of coursework for:

- **BUS 201 — Professional Development** (University of Illinois)
- **FIN 445 — Investments** (University of Illinois)

### Academic Integrity Notice

> This toolkit is intended as a **learning aid and reference implementation** for financial mathematics concepts. If you are a student using this for assignments:
> - **Understand the formulas** before using the calculators
> - **Verify results** independently (spreadsheet, financial calculator)
> - **Cite this tool** if used in submitted work
> - **Do not submit** this code as your own original work

### Formulas Reference

| Calculator | Key Formulas |
|------------|--------------|
| Compound Interest | `FV = P(1 + r/n)^(nt) + PMT × [((1 + r/n)^(nt) - 1) / (r/n)]` |
| Loan Payment | `PMT = P × [r(1+r)^n / ((1+r)^n - 1)]` |
| CAGR | `(Ending / Beginning)^(1/n) - 1` |
| Bond Price | `Σ(C/(1+y)^t) + F/(1+y)^n` |
| NPV | `Σ(CF_t / (1+r)^t) - Initial` |
| IRR | Rate where `NPV = 0` |
| Macaulay Duration | `Σ(t × PV_t) / Price` |

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

> **Note:** Educational coursework attribution requirements may apply. Check your course syllabus for specific guidelines on code reuse and citation.

---

## 🤝 Contributing

This is an educational project, but improvements are welcome:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-calculator`)
3. Commit your changes (`git commit -m 'Add amazing calculator'`)
4. Push to the branch (`git push origin feature/amazing-calculator`)
5. Open a Pull Request

### Ideas for Contributions
- [ ] Add more financial calculators (Black-Scholes, CAPM, WACC)
- [ ] Export results to CSV/PDF
- [ ] Dark/light theme toggle persistence
- [ ] Keyboard shortcuts for power users
- [ ] Unit tests for financial formulas
- [ ] Localization (i18n) support

---

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/rianpatel/financial-toolkit/issues)
- **Discussions:** [GitHub Discussions](https://github.com/rianpatel/financial-toolkit/discussions)

---

## 🙏 Acknowledgments

- Financial formulas based on standard corporate finance textbooks (Brealey, Myers, Allen; Bodie, Kane, Marcus)
- UI inspiration from modern financial platforms
- Built with ❤️ for BUS 201 / FIN 445 coursework at the University of Illinois

---

**Made with vanilla HTML/CSS/JS — No frameworks, no build step, no dependencies.**