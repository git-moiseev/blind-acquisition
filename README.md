# Hierarchical Signal Discovery

## Motivation

Classical communication theory assumes that the receiver already knows how the transmitted waveform is organized.

Carrier frequency, modulation, coding, synchronization, and packet structure are typically agreed upon before communication begins. Under these assumptions, waveform design is naturally optimized for bandwidth efficiency, power efficiency, channel capacity, or bit error rate.

Blind detection is a fundamentally different problem.

When the receiver possesses little or no prior knowledge of the transmitted waveform, the dominant challenge is no longer decoding the information. The primary challenge becomes discovering the signal itself.

This project investigates a different optimization criterion:

> **How should a waveform be designed to minimize the computational effort required for blind detection?**

---

## Central Idea

Instead of treating synchronization as a prerequisite for communication, this work considers synchronization itself as part of the information conveyed by the waveform.

The proposed approach separates the information contained in a transmitted signal into three categories.

1. **Existence information**

   Is there an artificial transmission?

2. **Structural information**

   How should the waveform be interpreted?

3. **Payload information**

   What message is being transmitted?

These categories need not become observable simultaneously.

Instead, an efficient waveform should reveal them progressively, allowing the receiver to reduce uncertainty one stage at a time.

---

## Hierarchical Signal Discovery

The receiver gradually discovers increasingly detailed properties of the waveform.

```text
Signal present
        │
        ▼
Continuous narrowband energy
        │
        ▼
Frequency geometry
        │
        ▼
Doppler estimation
        │
        ▼
Temporal geometry
        │
        ▼
Packet synchronization
        │
        ▼
Payload recovery
```

At each stage, newly observable signal properties reduce the uncertainty of the next stage.

The receiver is never required to solve the complete blind detection problem at once.

---

## Reference Waveform

This repository currently investigates one possible waveform architecture implementing these principles.

Its principal characteristics are

- continuous transmission;
- constant transmitted power;
- extremely narrow occupied bandwidth;
- two deterministic frequency states;
- complemented packet repetition.

The waveform is intended as a **reference architecture**, not as a definitive or mathematically optimal solution.

---

## Research Goals

This project explores several open research questions.

- Can waveform design be optimized for blind detection rather than communication efficiency?

- What is the minimum structural information required for computationally efficient signal discovery?

- Can waveform complexity be deliberately organized so that receiver uncertainty decreases monotonically during observation?

- Can the resulting optimization problem be formulated mathematically?

The present work represents an initial exploration of these questions.

---

## Current Status

The repository currently contains

- a conceptual waveform architecture;
- receiver-side discovery strategy;
- engineering trade-off analysis;
- discussion of open theoretical questions.

Future work will include

- mathematical formulation of blind detection cost;
- receiver algorithms;
- simulation results;
- performance evaluation;
- comparison with alternative waveform architectures.
