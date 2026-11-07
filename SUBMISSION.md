# ChargeQuest — GreatUniHack 2026


Project name
ChargeQuest

Elevator pitch
Predict, experiment, understand: a shared circuit classroom where a local AI agent turns misconceptions into testable experiments.

## Inspiration
Students can remember a formula without understanding the system it describes. We wanted to make that gap visible. Our starting point is a deceptively simple question: when a charged capacitor is connected to an identical empty capacitor, why does only half the initial energy remain stored in the capacitors?

## What it does
ChargeQuest is a multiplayer circuit-learning platform. Students join a room in their browser, make independent predictions and explain their reasoning. The host reveals the class responses and runs interactive experiments with voltage, current and energy visualisations.

The research agent goes further: it proposes a hypothesis, designs controlled parameter comparisons, calls a validated simulation tool, receives the computed evidence and interprets the results. It then proposes a follow-up teaching question; an optional second round lets it refine the investigation.

Experiments cover resistance sweeps, unequal capacitors, precharged capacitors, ideal LC transfer and lossy RLC behaviour. Students finish with a new prediction, and the platform reports actual paired concept-check results.

## How we built it
We combined React and TypeScript with a Node.js/Express backend and Socket.IO for classroom synchronisation. SVG visualisations provide live waveforms, energy accounting and interactive probes.

The local-model integration uses Ollama with Qwen2.5 3B. Structured experiment plans pass through parameter validation before execution. Analytical circuit calculations supply the numerical evidence; the model provides experimental choices and explanations. Model-generated and manually selected experiments are labelled separately.

## Challenges we ran into
The main challenge was connecting experimental design to reliable physical evidence. We handled unequal capacitances, different initial voltages, and underdamped, critically damped and overdamped RLC responses. Switching is supported at valid zero-current instants rather than by forcing inductor current to disappear.

We also had to prevent stale AI suggestions, repeated tool execution and accidental disclosure of individual answers.

## Accomplishments we're proud of
We integrated a shared classroom, an inspectable experiment-design pipeline and a physics engine in one application. Fifty automated checks pass, covering circuit calculations, validation, permissions and local-model interface behaviour. Simulated model responses verified integration; actual on-device inference performance remains a final demonstration check.

## What we learned
Effective AI teaching needs observable evidence and opportunities for students to reconsider their predictions. Making agent decisions and experiment parameters visible also makes the system easier to question and trust.

## What's next
Connect each follow-up student explanation directly to the agent's next experiment, evaluate learning outcomes with real classes, and extend the verified experiment library.

## Built with
React, TypeScript, JavaScript, Node.js, Express, Socket.IO, SVG, Ollama, Qwen2.5 3B.

