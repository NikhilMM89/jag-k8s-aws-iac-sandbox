# Versioning & Commit Guidelines

This repository follows **Semantic Versioning (SemVer)**.

Version format:

MAJOR.MINOR.PATCH

Example:

v1.4.2

---

# What Each Version Means

## PATCH (v1.0.1 → v1.0.2)

Use PATCH when making safe, backward-compatible fixes or small improvements.

Typical changes:
- Bug fixes
- Internal refactoring (no behavior change)
- Documentation updates
- CI/CD pipeline updates
- Dependency updates (non-breaking)
- Formatting or lint fixes

### Commit Examples

fix: correct IAM role permissions  
fix: resolve null pointer in service layer  
docs: update deployment instructions  
chore: update GitHub workflow  
refactor: clean up logging logic  

PATCH increases the third number only.

---

## MINOR (v1.0.2 → v1.1.0)

Use MINOR when adding new functionality that does not break existing behavior.

Typical changes:
- New features
- New modules
- New endpoints (backward compatible)
- Enhancements
- Performance improvements that do not change APIs

### Commit Examples

feat: add Kafka health check endpoint  
feat: introduce Terraform module for Databricks  
feat: support multi-region deployment  

MINOR increases the second number and resets PATCH to 0.

---

## MAJOR (v1.1.0 → v2.0.0)

Use MAJOR when making breaking changes.

Typical changes:
- Removing functionality
- Changing API contracts
- Renaming or restructuring interfaces
- Non-backward-compatible schema changes
- Changing required configuration inputs

### Commit Examples

feat!: migrate authentication to OAuth2  
feat!: restructure Terraform module variables  

Or include this in the commit body:

BREAKING CHANGE: removed legacy REST endpoints  

MAJOR increases the first number and resets MINOR and PATCH to 0.

---

# Commit Message Format

We follow a structured commit format:

type: short description

Examples:

fix: correct database connection timeout  
feat: add Azure Key Vault integration  
docs: improve README clarity  

If the change is breaking:

type!: short description

Example:

feat!: remove deprecated configuration flags  

Or:

type: short description

BREAKING CHANGE: explanation of breaking change  

---

# Supported Commit Types

feat      → Minor  
fix       → Patch  
docs      → Patch  
chore     → Patch  
refactor  → Patch  
test      → Patch  
perf      → Minor (if meaningful improvement)  
feat!     → Major  
BREAKING CHANGE → Major  

If no clear type is detected, the system defaults to PATCH.

---

# How Versioning Works

- Version tags are automatically generated when changes are merged into the main branch.
- Tags follow this format:

vX.Y.Z

- If no tags exist yet, versioning starts at:

v0.0.1

---

# Good vs Bad Commit Messages

Good:

fix: prevent race condition in Kafka consumer  
feat: add Helm chart for service deployment  
refactor: simplify Terraform module structure  

Bad:

update  
changes  
fix stuff  
misc  

Commit messages should clearly describe what changed and why.

---

# Quick Summary

Bug fix → PATCH  
New feature → MINOR  
Breaking change → MAJOR  
Use feat! or BREAKING CHANGE to trigger a major bump  

---

Keeping commits clean and descriptive ensures automated versioning works correctly and keeps releases predictable.
