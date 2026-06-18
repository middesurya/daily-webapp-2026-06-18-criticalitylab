# BUILD REPORT: CriticalityLab
**Date:** 2026-06-18
**Build Time:** ~50 minutes
**Status:** Complete & Deployed

## What Was Built
CriticalityLab — an interactive laboratory for exploring computation at the edge of chaos. 6 deep interactive modules exploring cellular automata, phase transitions, reservoir computing, continuous CA (Lenia), neural CA, and criticality metrics. Single-file HTML (~68KB).

## Idea Selection
**Score: 98/110** (Novelty 10, Feasibility 8, Wow Factor 10, Learning Value 10, Utility 9)

Selected based on:
- "Reservoir Computing with Evolved Critical Neural Cellular Automata" (arxiv May 2025) trending in ML research
- Cellular automata + reservoir computing intersection is a hot research front
- Zero overlap with 30+ existing lab projects (none cover CA computing, edge of chaos, or reservoir computing)
- Deeply scientific (complexity science, phase transitions, information theory)
- Visually spectacular (CA are inherently mesmerizing)
- Connects to Bay Area complexity science community (Santa Fe Institute influence)

## Modules Implemented
1. **Wolfram Universe** — All 256 elementary CA rules with space-time diagram visualization. Interactive 8-bit rule editor (click to toggle individual neighborhood entries). Automatic Wolfram class classification (I-IV) using entropy, run-length, and stability heuristics. Shannon entropy, compression ratio, active cell metrics.

2. **Lambda Phase Transition** — Langton's lambda parameter sweep from 0→1. Generates random CA rule tables at each lambda, evolves them, computes Shannon entropy and mutual information. Clear visualization of ORDER→CRITICAL→CHAOS phase transition. Shaded critical region (λ ≈ 0.2-0.45). Click any lambda to see corresponding CA evolution.

3. **Reservoir Automaton** — 1D CA as reservoir computer. Input signal injected at left boundary. State matrix collected, readout trained via pseudoinverse (normal equations + ridge regularization, Gaussian elimination solver). 3 tasks: 5-bit parity, temporal XOR, NARMA-5. Accuracy heatmap across sampled rules. Key insight: edge-of-chaos rules (Class IV) outperform ordered and chaotic rules.

4. **Lenia Explorer** — 2D continuous cellular automaton with configurable kernel radius, growth function (μ, σ), time step. 4 presets (Orbium glider, Geminium self-replicator, Scutium oscillator, Random). Real-time heatmap rendering (black→blue→cyan→green→yellow→red→white). Click-to-seed, play/pause/step, live mass/entropy/bounding-box statistics.

5. **Neural CA Training Lab** — Sobel-filtered state → dense ReLU hidden layer → residual update. Finite-difference gradient estimation. 4 target patterns (circle, square, star, heart). Damage button zeroes central patch to demo self-repair. Live loss curve visualization.

6. **Criticality Dashboard** — 5 unified metrics for any selected system (CA rules 0/4/30/90/110, pure random, fully ordered):
   - Lyapunov divergence trajectories
   - Shannon entropy rate
   - Mutual information vs spatial lag
   - Avalanche size distribution with power-law slope
   - DFA scaling exponent α
   - Each metric gets a gauge needle and text verdict
   - Summary verdict: ordered/critical/chaotic

## Tech Stack
- Single HTML file (67,761 bytes)
- Pure JavaScript + Canvas 2D API
- CSS custom properties for theming (dark theme with order=blue, critical=amber, chaos=red)
- No build step, no external dependencies
- Typed arrays (Uint8Array/Float32Array) for performance
- Linear algebra: manual pseudoinverse via normal equations

## Deployment
- **GitHub:** https://github.com/middesurya/daily-webapp-2026-06-18-criticalitylab
- **Vercel:** https://critlab.vercel.app
- HTTP 200, 68KB, <0.8s load time

## Scientific References
- Wolfram, S. (1984) "Universality and complexity in cellular automata"
- Langton, C. (1990) "Computation at the edge of chaos"
- Maass, W. et al. (2002) "Real-time computing without stable states" (reservoir computing)
- Chan, B.W.-C. (2019) "Lenia: Biology of Artificial Life" (continuous CA)
- Mordvintsev, A. et al. (2020) "Growing Neural Cellular Automata" (Distill)

## Lessons Learned
- Canvas-based CA rendering with typed arrays is performant even for 400×400 grids
- Langton's lambda sweep clearly shows the phase transition — very pedagogically effective
- Reservoir computing with CA is a natural fit: the linear readout training via pseudoinverse is fast and clean
- Lenia's continuous dynamics require careful parameter tuning for stable patterns
- The color scheme (blue=order, amber=critical, red=chaos) reinforces the scientific narrative throughout all modules
