---
name: Docker Image Optimizer Devops
description: Audits and refactors Dockerfiles to reduce image size, improve security and speed up build times.
---

# Context
Use this skill when:
1. Creating a new `Dockerfile`
2. A user complains about "slow builds" or "large images"
3. Reviewing container security (reducing attack surface)

# Optimization Pillars

### 1. Multi-Stage Strategy (The 2026 Standard)
- **Separate Build from Runtime:** Use a heavy image (with compilers/SDKs) for building, but copy ONLY the final binary/artifacts into a minimal runtime image (Alpine or Scratch).
- **Named Stages:** Use `FROM base AS builder` for readability.

### 2. Base Image Selection
- **Prefer Minimal:** Default to `alpine` (≈5MB) or `debian-slim` (≈30MB) over `ubuntu:latest` (≈75MB).
- **Distroless:** For production, suggest `gcr.io/distroless` to remove all shells and package managers.

### 3. Layer Management & Caching
- **Order Matters:** Place instructions that change least often (like `RUN apt-get update`) at the top. Place source code `COPY` commands at the bottom.
- **Atomic RUNs:** Combine related commands using `&&` and `\` to prevent intermediate layer bloat. 
  *Example:* `RUN apt-get update && apt-get install -y --no-install-recommends pkg && rm -rf /var/lib/apt/lists/*`

### 4. Dependency Hygiene
- **No-Install-Recommends:** Always use `--no-install-recommends` with `apt`.
- **Cache Cleaning:** Remove package manager caches in the *same* layer as the installation.
- **Production Only:** Ensure `devDependencies` or build-only headers never reach the final stage.

### 5. The .dockerignore File
- **Exclusion:** Every Docker project MUST have a `.dockerignore` to prevent `.git`, `node_modules`, `tests/`, and local logs from leaking into the build context.

# Instructions for the Agent
- When a user provides a Dockerfile, perform a **Size Audit** first.
- If the image is single-stage, provide a **Refactored Multi-Stage Version**.
- Check for "Magic Versions" and suggest pinning specific tags (e.g., `node:22.1.0-alpine` instead of `node:latest`).