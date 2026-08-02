# Yggdrasil AAR Builder

**Automated Cross-Compilation & Packaging Utility for Yggdrasil Android Infrastructure**

`yggdrasil-aar-builder` is a specialized build tool and dependency pipeline designed to compile the core Yggdrasil end-to-end encrypted IPv6 mesh networking protocol into standard Android Archive (`.aar`) libraries using `gomobile`. 

It bridges low-level Go-based decentralized routing daemons with mobile-first edge environments, enabling mobile nodes to operate seamlessly within distributed peer-to-peer and mesh networks.

## Architectural Purpose

Deploying decentralized networking stacks onto resource-constrained mobile hardware requires precise cross-compilation pipelines. This repository solves that engineering challenge by:
* Managing pinned `yggdrasil-go` library submodules and version synchronization.
* Executing automated Go-to-Android mobile bindings via POSIX-compliant build scripts.
* Packaging native networking routines, packet handlers, and cryptographic routing layers for direct embedding into Android applications and mobile-driven node environments.

---

## Core Components & Structure

1. **Submodule Orchestration:** Integrates the upstream Yggdrasil core cleanly via tracked git submodules (`libs/yggdrasil-go`).
2. **Mobile Build Scripts (`contrib/mobile/build`):** Automated configuration wrappers handling target architectures (ARM, ARM64, x86, x86_64) and Java Native Interface (JNI) bindings.
3. **Artifact Output Pipeline:** Outputs production-ready `.aar` packages designed to inject secure IPv6 routing directly into mobile client apps.

---

## Prerequisites & Requirements

* POSIX-compliant environment (Linux / Termux / macOS)
* Go runtime with `gomobile` toolchain installed:
  ```bash
  go install golang.org/x/mobile/cmd/gomobile@latest
  gomobile init
