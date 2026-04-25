# Secure Application

A minimal, highly secure Python Flask application demonstrating advanced DevSecOps pipeline practices within GitHub Actions.

## DevSecOps Pipeline Enhancements
This pipeline goes beyond simply checking for vulnerabilities; it generates auditable security artifacts for every build:

1. **Job Dependencies**: The container is only built if the source code passes SAST (`bandit`, `semgrep`) and SCA (`pip-audit`).
2. **SBOM Generation**: A comprehensive Software Bill of Materials is generated using CycloneDX formatting.
3. **Artifact Retention**: All scan results and the SBOM are saved as downloadable GitHub workflow artifacts.
4. **Trusted Promotion**: Only after the container passes a strict `trivy` scan is the image locally tagged with a `trusted-` prefix and granted a build provenance receipt.
