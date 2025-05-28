# 🧪 Lab 1: Trivy - Docker Image Scanning

## 🛠️ What You'll Learn
- Scan Docker images for OS and application vulnerabilities using Trivy.

---

## 🚀 Getting Started

1. Install Trivy:

   ```
   brew install aquasecurity/trivy/trivy  # macOS
   sudo apt install trivy                 # Ubuntu/Debian
   ```

2. Go into the lab:
   ```
   cd lab1-trivy
   ```

3. Build the image:
   ```
   docker build -t vulnerable-app .
   ```

4. Run the Trivy scan:
   ```
   trivy image vulnerable-app
   ```

---

## 🧠 Challenge

Try scanning a public image:

```
trivy image nginx:latest
```

> Can you spot the vulnerabilities in `nginx` or `python:3.6`?

---

## 📎 Notes

Trivy supports scanning:
- Docker images
- Filesystems
- Repos
- SBOMs