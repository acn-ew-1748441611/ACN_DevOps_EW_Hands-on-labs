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

## 🧠 Optional: Control CI/Pipeline Behaviour

To control pipeline hehaviour you can pass the `--fail-on [severity]` flag and the process will exit with non-zero if any [severity] or greater vulnerabilities are found, causing a pipeline to fail.

```
grype grype-demo --fail-on high # Or 'critical'

# Or you can parse the content to display key information instead of the table

grype grype-demo -o json | jq -r '.matches[] | select(.vulnerability.severity == "High" or .vulnerability.severity == "Critical") | .artifact.name + " - " + .vulnerability.id + " - " + .vulnerability.severity'
```

---

## 📎 Notes

You can also scan:
- Tarballs: `grype ./myimage.tar`
- SBOMs: `grype sbom:./sbom.json`