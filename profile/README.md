## BoxLite

**Secure, lightweight micro-VM sandboxes for AI agents.**

We build sandbox infrastructure that lets AI agents run untrusted code safely — hardware-isolated, sub-second boot, zero-daemon.

---

<h3>Architecture</h3>

```
  ┌───────────────────────────────────────────────┐
  │                                               │
  │                    BoxRun                      │
  │        Sandbox Management Platform             │
  │  · · · · · · · · · · · · · · · · · · · · · ·  │
  │      REST API Server                           │
  │      CLI & Web Dashboard                       │
  │      Python & Rust SDK                         │
  │                                               │
  └───────────────────────┬───────────────────────┘
                          │
                     powered by
                          │
  ┌───────────────────────▼───────────────────────┐
  │                                               │
  │                    BoxLite                     │
  │        Embedded micro-VM Sandbox Library       │
  │  · · · · · · · · · · · · · · · · · · · · · ·  │
  │      ┌──────┐   ┌──────┐   ┌──────┐           │
  │      │  VM  │   │  VM  │   │  VM  │   ...      │
  │      └──────┘   └──────┘   └──────┘           │
  │      KVM / HVF  ·  OCI Images  ·  Async I/O   │
  │                                               │
  └───────────────────────────────────────────────┘
```

---

<h3>Repositories</h3>

- **[BoxLite](https://github.com/boxlite-ai/boxlite)** — Embedded micro-VM sandbox runtime. Lightweight, hardware-isolated, OCI-compatible. SDKs for Python, Node.js, Rust, and C.
- **[BoxRun](https://github.com/boxlite-ai/boxrun)** — Sandbox management platform. REST API, CLI, web dashboard, single-binary deployment. Powered by BoxLite.

---

<h3>Quick Start</h3>

**BoxLite** — embed in your app:

```bash
pip install boxlite
```

```python
import asyncio
from boxlite import SimpleBox

async def main():
    async with SimpleBox("python:slim") as box:
        result = await box.run("echo 'Hello from a micro-VM!'")
        print(result.stdout)

asyncio.run(main())
```

**BoxRun** — platform:

```bash
boxrun shell ubuntu
```

---

<h3>Highlights</h3>

- **Sub-second boot** — micro-VMs start in milliseconds, not minutes
- **Hardware isolation** — each sandbox has its own kernel (KVM / Hypervisor.framework)
- **OCI compatible** — use any Docker image (`python:slim`, `node:alpine`, `ubuntu`, etc.)
- **No daemon** — BoxLite links as a library; BoxRun ships as a single binary
- **Async-first** — designed for high concurrency with streaming I/O

---

<h3>Where to Find Us</h3>

<a href="https://x.com/BoxLiteAI" target="_blank">
<img src="https://img.shields.io/badge/@BoxLiteAI-%23000000.svg?style=for-the-badge&logo=x&logoColor=white" alt="X (Twitter)" style="margin-bottom: 5px;"/></a>
<a href="http://go.boxlite.ai/discord" target="_blank">
<img src="https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" style="margin-bottom: 5px;"/></a>
