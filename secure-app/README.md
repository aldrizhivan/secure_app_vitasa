# Secure DevSecOps App

This repository demonstrates a mature GitHub-native DevSecOps pipeline.

## Features

- SAST (Semgrep)
- Dependency Scanning (pip-audit)
- Secret Detection (Gitleaks)
- Container Scanning (Grype)
- SBOM Generation (Syft)
- Trusted Build Promotion Logic
- Artifact Storage via GitHub Actions

## Pipeline Flow

1. **Scan Job**
   - Dependency audit
   - Static code analysis
   - Secret scanning

2. **Build Job (gated)**
   - Runs only if scans pass
   - Builds container image
   - Generates SBOM
   - Performs container vulnerability scan
   - Marks image as trusted

## Produced Artifacts

- `pip-audit-report.json`
- `gitleaks-report.json`
- `grype-report.json`
- `sbom.json`
- `image-info.txt`

## Security Posture

- No secrets in code
- Minimal container footprint
- Non-root execution
- Full audit trail via artifacts