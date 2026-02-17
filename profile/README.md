## BoxLite

**The SQLite of sandboxing — embeddable, stateful micro-VMs with snapshots and hardware isolation.**

Embeddable, stateful micro-VMs with hardware isolation and snapshots. Boot in milliseconds. Just import and run.

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

- **[BoxLite](https://github.com/boxlite-ai/boxlite)** — Embeddable, stateful micro-VM sandbox with snapshots and hardware isolation. SDKs for Rust, Python, Node.js, and C (Go coming soon).
- **[BoxRun](https://github.com/boxlite-ai/boxrun)** — Sandbox management platform. REST API, CLI, web dashboard, single-binary deployment. Powered by BoxLite.

---

<h3>Quick Start</h3>

**BoxLite** — embed in your app:

```bash
pip install boxlite
```

```python
import asyncio
import boxlite

async def main():
    async with boxlite.SimpleBox(image="python:slim") as box:
        result = await box.exec("python", "-c", "print('Hello from BoxLite!')")
        print(result.stdout)

asyncio.run(main())
```

**BoxRun** — platform:

```bash
boxrun shell ubuntu
```

---

<h3>Highlights</h3>

- **Embeddable** — a single importable library — no cloud accounts, no daemons, no root. Just import and run
- **Stateful** — environments persist across sessions. Install packages, configure once — come back later and everything is still there
- **Snapshots** — checkpoint before risky operations, rollback instantly. Fork environments for parallel exploration
- **Hardware isolation** — each sandbox runs in its own micro-VM with a dedicated Linux kernel (KVM / Hypervisor.framework)
- **Sub-50ms boot** — micro-VMs start in milliseconds, not minutes

---

<h3>Where to Find Us</h3>

<a href="https://x.com/BoxLiteAI" target="_blank">
<img src="https://img.shields.io/badge/@BoxLiteAI-%23000000.svg?style=for-the-badge&logo=x&logoColor=white" alt="X (Twitter)" style="margin-bottom: 5px;"/></a>
<a href="http://go.boxlite.ai/discord" target="_blank">
<img src="https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" style="margin-bottom: 5px;"/></a>
