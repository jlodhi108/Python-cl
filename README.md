# DevOps with GitHub Actions — Python CI Demo

[![CI – Python Tests](https://github.com/<YOUR_USERNAME>/<YOUR_REPO>/actions/workflows/ci.yml/badge.svg)](https://github.com/<YOUR_USERNAME>/<YOUR_REPO>/actions/workflows/ci.yml)

A minimal Python project that demonstrates a **real-world Continuous Integration (CI) pipeline** using **GitHub Actions**.

---

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions CI pipeline
├── app/
│   ├── __init__.py
│   └── calculator.py       # Python source code
├── tests/
│   ├── __init__.py
│   └── test_calculator.py  # pytest test suite
├── requirements.txt        # Project dependencies
└── README.md
```

---

## ⚙️ How the CI Pipeline Works

Every time you **push to `main`** or **open a Pull Request targeting `main`**, GitHub Actions automatically:

| Step | What happens |
|------|-------------|
| 1 | **Checkout** — downloads the latest code |
| 2 | **Setup Python** — installs Python 3.10, 3.11, and 3.12 in parallel |
| 3 | **Install deps** — runs `pip install -r requirements.txt` |
| 4 | **Run tests** — executes `pytest tests/ -v --tb=short` |
| 5 | **Upload report** — saves a JUnit XML report as a workflow artifact |

If **all tests pass** ✅ → the branch is safe to merge.  
If **any test fails** ❌ → the team is alerted via the failed check on GitHub.

---

## 🚀 Running Locally

```bash
# 1. Clone the repo
git clone https://github.com/<YOUR_USERNAME>/<YOUR_REPO>.git
cd <YOUR_REPO>

# 2. Create and activate a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the tests
pytest tests/ -v
```

---

## 📦 Dependencies

| Package | Purpose |
|---------|---------|
| `pytest` | Test runner |

---

## 🧪 Test Coverage

| Module | Tests |
|--------|-------|
| `add()` | 5 test cases |
| `subtract()` | 4 test cases |
| `multiply()` | 5 test cases |
| `divide()` | 5 test cases (incl. divide-by-zero) |

---

## 📌 Submission Checklist

- [x] `.github/workflows/ci.yml` — CI pipeline
- [x] `requirements.txt` — dependencies
- [x] `app/calculator.py` — source code
- [x] `tests/test_calculator.py` — automated tests
- [ ] Push to GitHub and confirm the Actions workflow turns **green**
- [ ] Take a screenshot of the successful workflow run

---

> **Replace `<YOUR_USERNAME>/<YOUR_REPO>`** with your actual GitHub username and repository name before pushing.
