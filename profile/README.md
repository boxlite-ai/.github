<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/boxlite-ai/.github/main/profile/logo-dark.png">
    <img src="https://raw.githubusercontent.com/boxlite-ai/.github/main/profile/logo-light.png" alt="BoxLite" width="300">
  </picture>
</p>

<p align="center"><b>One micro-VM runtime — embed it, deploy it, distribute it.</b></p>

BoxLite is a micro-VM runtime in Rust. It spins up lightweight, stateful Boxes — OCI containers each running in their own Linux kernel — so AI agents get real isolation, from your laptop to serverless scale.

- **Embed** — in-process library; ship sandboxing as a feature.
- **Deploy** — standalone server for multi-tenant workloads.
- **Distribute** — cluster it for serverless-scale execution.

**Small as a library, elastic as a service — one repo, sub-50ms boot.**

---

## Getting started

**Embed it** — sandboxing as a library

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

**Deploy it** — the binary, one command, no daemon

```bash
curl -fsSL https://sh.boxlite.ai | sh
boxlite run python:slim python -c "print('Hello from BoxLite!')"
```

**Deploy it** — a standalone server

```bash
boxlite serve 
```

**Distribute it** — serverless scale

```bash
git clone https://github.com/boxlite-ai/boxlite && cd boxlite/apps/infra
npx sst deploy --stage production
```

## Highlights

- **Stateful** — environments persist across sessions; install once, resume later.
- **Reversible** — checkpoint, roll back instantly, fork for parallel exploration.
- **Isolated** — every box runs its own Linux kernel in a micro-VM (KVM / Hypervisor.framework).
- **Fast** — sub-50ms boot, not minutes.

## Links

- **Repo** — https://github.com/boxlite-ai/boxlite
- **Docs** — https://docs.boxlite.ai/

## Where to find us

[![X (Twitter)](https://img.shields.io/badge/@BoxLiteAI-%23000000.svg?style=for-the-badge&logo=x&logoColor=white)](https://x.com/BoxLiteAI)
[![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)](http://go.boxlite.ai/discord)
