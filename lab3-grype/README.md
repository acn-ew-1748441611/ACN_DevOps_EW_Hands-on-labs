# 🧬 Lab 3: Grype - Vulnerability Scanner for Dependencies

## 🛠️ What You'll Learn
- Use Grype to find known vulnerabilities in container images and SBOMs.

---

## 🚀 Getting Started

1. Install Grype:

   ```
   brew install anchore/grype/grype
   ```

2. Go to the lab:
   ```
   cd lab3-grype
   ```

3. Build the image:
   ```
   docker build -t grype-demo .
   ```

4. Scan it:
   ```
   grype grype-demo
   ```

---

## 🧠 Optional: JSON Output

```
grype grype-demo -o json > results.json
```

Review using `jq` or your favorite viewer.

---

## 📎 Notes

You can also scan:
- Tarballs: `grype ./myimage.tar`
- SBOMs: `grype sbom:./sbom.json`