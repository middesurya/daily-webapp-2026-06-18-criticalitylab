# CriticalityLab — Computation at the Edge of Chaos

An interactive laboratory exploring one of the deepest ideas in complexity science: complex computation emerges at phase transitions between order and chaos.

## Live Demo
[criticalitylab.vercel.app](https://criticalitylab.vercel.app)

## Modules

1. **Wolfram Universe** — All 256 elementary cellular automata. Space-time diagrams, Wolfram class classification, Shannon entropy & compression metrics. Interactive rule editor.
2. **Lambda Phase Transition** — Langton's lambda parameter sweep showing the order→critical→chaos phase transition. Entropy & mutual information vs λ.
3. **Reservoir Automaton** — 1D CA as reservoir computer. Parity, temporal XOR, NARMA tasks. Proves edge-of-chaos rules compute best.
4. **Lenia Explorer** — 2D continuous cellular automaton. Orbium, Geminium, Scutium presets. Real-time dynamics with configurable kernel/growth parameters.
5. **Neural CA** — Train update rules via backprop to grow target patterns. Self-repair demo.
6. **Criticality Dashboard** — Lyapunov exponents, Shannon entropy, mutual information, avalanche distributions, DFA scaling. Unified verdict: ordered/critical/chaotic.

## Built With
Single HTML file (~68KB), pure JavaScript + Canvas 2D. No build step, no dependencies.

## License
MIT
