# Hi, I'm Jiayan Wen

Electrical & Computer Engineering graduate working across **digital design, design verification, silicon validation, and computer architecture**.

I am interested in understanding how design intent becomes real system behavior — from RTL and cycle-level correctness to timing, physical implementation, performance, and hardware measurement.

My engineering work increasingly follows a common loop:

```text
Problem / Design Intent
        ↓
Architecture & Contracts
        ↓
Implementation
        ↓
Verification & Measurement
        ↓
Controlled Experiments
        ↓
Evidence
        ↓
Engineering Decision
```

Rather than accumulating implementations, I try to use projects to answer specific engineering questions and make the boundary between **measured evidence, assumptions, and unresolved questions** explicit.

---

## Featured Projects

### Fixed-Point Radix-2 Butterfly

**SystemVerilog | Fixed-Point RTL | Verification | Synthesis | Timing & PPA**

A signed Q1.15 complex butterfly used to study the complete path from numerical specification to physical implementation.

Highlights:

* Defined an explicit fixed-point numerical contract covering width propagation, round-to-nearest ties-to-even, saturation, and component-level flags
* Implemented combinational and pipelined RTL microarchitectures
* Built an integer-only Python reference model and self-checking verification flow
* Matched **1,071 directed, twiddle-factor, and reproducible-random vectors bit-for-bit**
* Verified fixed latency, one-input-per-cycle operation, bubbles, and reset behavior
* Ran matched Nangate45/OpenROAD RTL-to-route experiments
* Increased the highest fully passing tested frequency from **425 MHz to 640 MHz**, with **16.4% more area at 400 MHz**
* Used routed critical-path evidence to identify the multiplier stage as the ASIC bottleneck
* Turned FPGA/ASIC mapping differences into a separate experimental question rather than assuming ASIC conclusions transfer directly to FPGA DSP architectures

Repository:
[radix2-butterfly](https://github.com/jwen2003/radix2-butterfly)

---

### Adaptive V.35 Sampling Monitor

**SystemVerilog | CPLD | CDC | Hardware/Software Interface | Verification**

A reconstruction and redesign of a legacy CPLD subsystem for adaptive receive-edge sampling.

The project started from a real engineering failure mechanism rather than a predefined RTL exercise: asynchronous RCLK/DATA timing could create sampling-margin problems, requiring both hardware observation and CPU-side decision logic.

Highlights:

* Translated legacy engineering documents and engineer clarifications into explicit behavioral contracts
* Designed matched two-stage synchronizers, event detectors, clock-origin tracking, phase measurement, and CPU-visible register/control semantics
* Defined deterministic behavior for same-cycle and adjacent-cycle events, busy commands, result validity, read-clear, reset, and restart
* Built **four unit testbenches and one end-to-end self-checking testbench**, with the integrated test passing **29 checks**
* Treated phase wraparound as a falsifiable algorithm question rather than an RTL patch
* Compared ordinary linear averaging against circular decision rules using **33 boundary-focused Python tests**
* Showed that circular averaging removed the observed wraparound failures while keeping low-confidence and threshold-stability cases explicit

Repository:
[adaptive-sampling-monitor](https://github.com/jwen2003/adaptive-sampling-monitor)

---

### Output-Stationary Systolic Array — Ongoing

**SystemVerilog | Spatial Dataflow | Parameterized RTL | Verification**

A parameterized output-stationary systolic array being developed to study spatial dataflow, PE-level concurrency, operand scheduling, utilization, and architectural scaling.

Current milestone:

* Implemented a parameterized **N×N PE fabric**
* Uses signed 8-bit operands and 18-bit local accumulators
* Propagates A and B independently through registered horizontal and vertical links
* Accumulates only when corresponding A/B valids coincide
* Defined cycle-level invariants for data movement, valid propagation, accumulation, hold, and clear behavior
* Built self-checking PE and bare-array tests covering signed/extreme products, consecutive MACs, one-sided traffic, clear with the first MAC, and 2×2 cycle-by-cycle connectivity

Current project boundary:

```text
Completed:
PE → Bare Array → Cycle-Level Verification

Next:
Input Feeder → Wavefront Scheduling → Controller
→ End-to-End Matmul → Utilization Analysis → PPA
```

The project intentionally separates completed RTL/verification evidence from feeder, control, utilization, and PPA claims that have not yet been established.

Repository:
https://github.com/jwen2003/systolic-array

---

### Matrix Multiplication & CPU Performance Study — Ongoing

**C++17 | CPU Architecture | Cache | SIMD | Performance Analysis**

A performance study using FP32 matrix multiplication as a controlled workload for understanding how numerical semantics, memory access, compiler optimization, and hardware architecture interact.

The goal is not to accumulate optimized kernels or report a single speedup. Instead, the project follows:

```text
Correctness Contract
        ↓
Reproducible Baseline
        ↓
Performance Anomaly
        ↓
Hypothesis
        ↓
Controlled Intervention
        ↓
Compiler / Hardware Evidence
        ↓
Engineering Decision
```

Current work includes:

* Built an independent double-accumulating correctness oracle and corner-case/randomized test suite
* Implemented and compared multiple CPU memory-access patterns
* Identified a reproducible **N=256 performance trough** in the i-j-k implementation
* Used adjacent-size controls and hardware performance counters to measure an L1D miss-rate increase from about **7% to 82%**
* Connected the anomaly to stride and cache-set mapping rather than attributing it only to benchmark timing
* Used memory-layout interventions, compiler vectorization reports, hardware counters, and assembly inspection to distinguish cache behavior from reduction semantics
* Maintains explicit strict versus relaxed numerical policies when compiler transformations change floating-point behavior

The longer-term project connects the same Matmul contract to CPU optimization, GPU kernels, memory hierarchy, and minimal runtime dispatch.

Repository:
[mini-gpu-runtime-playground](https://github.com/jwen2003/mini-gpu-runtime-playground)

---

### PCB Defect Detection and Review Pipeline

**Python | OpenCV | Classical ML | Industrial Inspection**

An explainable two-stage PCB inspection pipeline combining high-recall candidate generation with lightweight classification.

Highlights:

* Built ECC registration, difference-based candidate extraction, morphological processing, connected-component analysis, and Random Forest filtering
* Evaluated the pipeline on **500 DeepPCB test images**
* Reduced false-positive candidates by **70.52%**
* Maintained **99.59% recall** while improving precision from **31.77% to 61.19%**
* Performed stage-by-stage failure analysis on the remaining 13 false negatives, localizing **8 to candidate generation and 5 to classification**
* Documented threshold tradeoffs, data-split boundaries, and domain limitations rather than treating aggregate accuracy as sufficient evidence

Repository:
[pcb-defect-detection](https://github.com/jwen2003/pcb-defect-detection)

---

## Industry Experience

### Board Design Intern — MetaX Integrated Circuits

Currently working on GPU board validation and post-silicon characterization.

My work includes:

* High-speed interconnect and S-parameter analysis
* Automated processing of Touchstone measurement datasets
* Measurement repeatability and anomaly analysis
* Hardware BOM revision comparison
* GPU power, temperature, and voltage characterization-log processing
* Connecting hardware revisions and measurement definitions to observed system behavior

This experience has pushed me to think beyond whether a design is logically correct and toward how hardware behavior can actually be **observed, measured, isolated, and explained**.

---

## Current Engineering Questions

My current projects are centered around several related questions:

**Digital Design**

* How should numerical and interface semantics be specified before RTL implementation?
* Which microarchitectural changes actually improve timing or throughput?
* How do implementation targets such as ASIC standard cells and FPGA DSP resources change design decisions?

**Verification**

* What constitutes an executable correctness contract?
* Which corner cases expose incorrect assumptions rather than simple coding bugs?
* How should reference models, self-checking tests, and cycle-level invariants divide verification responsibility?

**Computer Architecture & Performance**

* How do dataflow, scheduling, memory hierarchy, and numerical semantics interact?
* When is a performance anomaly caused by the algorithm, memory layout, compiler, or underlying hardware?
* How can controlled experiments distinguish competing explanations?

**Silicon & System Debug**

* What can actually be observed at board and silicon level?
* How can measurements be turned into falsifiable hypotheses?
* How should failure isolation proceed when multiple hardware layers can produce similar symptoms?

---

## Engineering Approach

I care less about the number of tools or implementations in a project than about whether the reasoning chain can survive scrutiny.

A useful engineering result should make clear:

```text
What was observed?
        ↓
What do we know?
        ↓
What are we assuming?
        ↓
What competing explanations exist?
        ↓
What experiment separates them?
        ↓
What does the evidence support?
        ↓
What should change in the design?
```

This is the common thread connecting my work in RTL design, verification, hardware characterization, and performance analysis.

---

## Current Focus

Currently working on:

* Output-stationary systolic-array architecture and verification
* FPGA vs. ASIC implementation behavior of arithmetic datapaths
* CPU/GPU Matmul performance and memory hierarchy
* RTL microarchitecture and fixed-point computation
* Design verification methodology
* Post-silicon characterization and failure isolation
* Hardware/software boundaries in accelerator systems

---

## Background

* **B.S. Electrical and Computer Engineering — Santa Clara University**
* **Incoming M.S.E. Electrical and Computer Engineering — University of Pennsylvania, Fall 2027**
* **Board Design Intern — MetaX Integrated Circuits**

---

## Contact

LinkedIn:
https://www.linkedin.com/in/j-wen/

GitHub:
https://github.com/jwen2003

Email:
[jiayanwen2003@gmail.com](mailto:jiayanwen2003@gmail.com)
[13621074266@163.com](mailto:13621074266@163.com)
