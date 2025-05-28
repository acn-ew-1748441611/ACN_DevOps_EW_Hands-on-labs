# 🔐 Lab 2: Gitleaks - Secret Scanning

## 🛠️ What You'll Learn
- Detect secrets committed to your git repository using Gitleaks.

---

## 🚀 Getting Started

1. Install Gitleaks:

   ```
   brew install gitleaks        # macOS
   scoop install gitleaks       # Windows
   ```

2. Go to the secrets demo directory:
   ```
   cd lab2-gitleaks/secrets-demo
   ```

3. Run the scan:
   ```
   gitleaks detect --source . --report-format sarif --report-path report.sarif
   ```

4. Review results:
   ```
   cat report.sarif | less
   ```

---

## 🧠 Bonus: Git History Scan

```
gitleaks detect --source . --log-level debug --no-git
```

Or scan your entire commit history:
```
gitleaks detect --source . --log-level debug
```

---

## 🔒 Pro Tip

Prevent secrets from being committed in the first place by using pre-commit hooks:
```
pre-commit install
```