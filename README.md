# Wan 2.2 Fast API Examples for PoYo

[![Model page](https://img.shields.io/badge/Model%20page-wan--2--2--fast-84cc16)](https://poyo.ai/models/wan-2-2-fast)
[![API docs](https://img.shields.io/badge/API%20docs-docs.poyo.ai-22d3ee)](https://docs.poyo.ai/api-manual/video-series/wan2.2-text-to-video-fast)
[![License: MIT](https://img.shields.io/badge/License-MIT-111827)](LICENSE)
[![Main examples](https://img.shields.io/badge/Main%20examples-PoyoAPI%2Fpoyo--examples-0f172a?logo=github)](https://github.com/PoyoAPI/poyo-examples)

Focused server-side examples for building Wan 2.2 Fast text-to-video and image-to-video workflows on PoYo.

Wan 2.2 Fast is useful for low-cost video draft loops, one-frame or two-frame guided motion tests, and quick creative direction checks before moving to heavier models.

[Model Page](https://poyo.ai/models/wan-2-2-fast) | [Docs](https://docs.poyo.ai/api-manual/video-series/wan2.2-text-to-video-fast) | [Get API Key](https://poyo.ai/dashboard/api-key) | [Pricing](https://poyo.ai/pricing) | [Main Examples](https://github.com/PoyoAPI/poyo-examples)

## What This Repo Covers

- Text-to-video with `wan2.2-text-to-video-fast`
- Image-to-video with `wan2.2-image-to-video-fast`
- One-image and two-image guide frame patterns
- 480p and 720p draft tiers
- cURL and Node.js backend examples

## Quick Start

```bash
cp .env.example .env
export POYO_API_KEY="your-api-key"
```

Run the Node.js example:

```bash
cd node
npm start
```

Keep `POYO_API_KEY` on the server. Do not expose it in browser code, mobile apps, screenshots, or public logs.

## Production Pattern

- Keep `POYO_API_KEY` on the server
- Submit a generation task
- Store `data.task_id`
- Poll status while testing
- Use `callback_url` webhooks in production

## Models

This repo uses `wan2.2-text-to-video-fast` and `wan2.2-image-to-video-fast`.

## Examples

| Path | What it covers |
| --- | --- |
| [`curl/generate.md`](curl/generate.md) | Copy-paste async submit request. |
| [`node/`](node/) | Native Node.js backend example with polling. |
| [`docs/prompt-examples.md`](docs/prompt-examples.md) | Practical prompts for product workflows and creative tests. |
| [`docs/production-notes.md`](docs/production-notes.md) | Security and reliability notes before launch. |
| [`webhooks/express-webhook/`](webhooks/express-webhook/) | Minimal Express receiver for PoYo callbacks. |

## Run Checks

```bash
make check
```

On Windows:

```powershell
./scripts/check.ps1
```

## License

MIT
