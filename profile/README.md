# BoxLite

### A micro-VM runtime in Rust for AI agents — embed it in your app, run it as a server, or cluster it at serverless scale.

BoxLite spins up lightweight, stateful micro-VMs ("Boxes") and runs OCI
containers inside them, each with its own Linux kernel. It's **designed to
span the full range of agent deployments**:

- **Library** — embed it in-process, ship sandboxing as a feature.
- **Server** — run it standalone for multi-tenant workloads.
- **Distributed service** — cluster it for serverless-scale execution.

**One repo. Warm start 100ms. From sandbox to serverless, from security to scale.**

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

**Get the binary** — one-shot CLI

```bash
curl -fsSL https://sh.boxlite.ai | sh
boxlite run python:slim python -c "print('Hello from BoxLite!')"
```

**Deploy locally** — standalone server

```bash
boxlite serve                       # REST API on :8100
```

**Go distributed** — serverless scale

```bash
git clone https://github.com/boxlite-ai/boxlite && cd boxlite/apps/infra
npx sst deploy --stage production
```

## Highlights

The all-terrain runtime of the micro-VM domain — **embeddable** in your app,
**deployable** as a single binary, **distributable** at serverless scale.

- **Stateful** — environments persist across sessions; install once, resume later.
- **Snapshotable** — checkpoint, roll back instantly, fork for parallel exploration.
- **Isolated** — every box runs its own Linux kernel in a micro-VM (KVM / Hypervisor.framework).
- **Fast** — warm start 100ms.

## Links

- **Repo** — https://github.com/boxlite-ai/boxlite
- **Docs** — https://docs.boxlite.ai/

## Where to find us

[![X (Twitter)](https://img.shields.io/badge/@BoxLiteAI-%23000000.svg?style=for-the-badge&logo=x&logoColor=white)](https://x.com/BoxLiteAI)
[![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)](http://go.boxlite.ai/discord)
