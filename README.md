# ChargeQuest

Predict, experiment, understand: a multiplayer circuit classroom with a local experiment-design agent.

Built for GreatUniHack 2026 / Reply Challenge.

## Run from source

Install Node.js 24 and Ollama from their official websites, then run:

```powershell
npm.cmd ci --include=dev
npm.cmd run build
node START.cjs
```

The launcher downloads `qwen2.5:3b` if necessary (approximately 1.9 GB), warms it and starts the classroom on a free port from 3001–3010. Keep the terminal open. Students connect to the classroom server, not directly to Ollama. The application creates rooms in memory; a restart clears them.

For local configuration, copy `.env.example` to `.env`. There is no paid cloud-model credential requirement. `AI_API_KEY=ollama` is a local compatibility placeholder.

For remote phones, run `node SHARE.cjs` in a second terminal. The temporary Cloudflare tunnel requires the computer, server and tunnel to remain running. Install cloudflared from its official source if the helper requests it. No permanent hosted URL is claimed.

## What it does

- Browser rooms with independent predictions, reasoning and confidence.
- Shared RC and ideal LC demonstrations, voltage/current waveforms, hover probes and energy accounting.
- Research agent: hypothesis, structured parameter comparisons, validation, simulation evidence, interpretation and teaching follow-up; optional second round.
- Verified tools for unequal or precharged capacitors and ideal/lossy RLC transfer.
- Real paired concept-check results. Manual templates are labelled separately from model-designed experiments.

## Validation and scope

```powershell
node scripts/test-local.cjs
```

50 automated checks passed in the development environment, covering physics, validation, permissions and mocked local-model integration. These checks do not establish actual model inference quality or speed, live-phone connectivity, or classroom learning gains. The demonstration video visualises computed experiments and architecture; it does not depict a live model inference session.

The source build and actual local model should be checked on the presenting computer. Model weights are not included. See `SUBMISSION.md` for the implementation boundaries.

## Stack

React, TypeScript, Node.js, Express, Socket.IO, SVG, Ollama and Qwen2.5 3B.

## Source archive

Download `ChargeQuest_Source.zip` from this repository and extract it. Enter the extracted ChargeQuest directory and use the source instructions above. The archive contains the application source and lockfile; internal team handoff files, credentials, dependencies, build outputs and model weights are excluded.

Demo video: `ChargeQuest_Demo.mp4` in this repository (1 minute 45 seconds, English narration). A YouTube upload is still required for the Devpost form.
