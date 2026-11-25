# Hi, I'm Jiayan Wen

Electrical & Computer Engineering graduate and incoming graduate student at the University of Pennsylvania.

My primary interests are **computer architecture, RTL microarchitecture, and hardware/software co-design**, supported by work in verification, low-level systems software, performance analysis, and hardware validation.

## Featured Projects

### [Systolic Array — Software-Accessible Accelerator](https://github.com/jwen2003/systolic-array)
**SystemVerilog · AXI · C++ · Architecture Modeling · Physical Design**

- Parameterized output-stationary INT8/INT18 compute fabric with deterministic wavefront scheduling.
- AXI-Lite control, on-chip input storage, restricted AXI4 burst writes, command/status semantics, and C++ host-side invocation.
- Cycle-level modeling and controlled experiments on transaction overhead, packing, buffering, and scheduling.
- Packed writes reduced end-to-end latency from 115 to 57 cycles in a controlled N=2, K=17 experiment.
- Nangate45/OpenROAD RTL-to-GDS comparisons at a common 2.5 ns clock target.

### [Fixed-Point Radix-2 Butterfly](https://github.com/jwen2003/radix2-butterfly)
**SystemVerilog · Arithmetic Datapaths · UVM · Timing & PPA**

- Combinational and pipelined Q1.15 complex datapaths with explicit rounding and saturation contracts.
- Bit-exact Python reference model, 1,071 common test vectors, and directed/constrained-random UVM verification.
- Highest fully passing tested clock target increased from 425 to 640 MHz in matched Nangate45/OpenROAD experiments, with 16.4% more area at 400 MHz.
- Post-route critical-path reconstruction and FPGA/ASIC mapping investigation.

Physical results are open-PDK comparative experiments, not silicon measurements or commercial-process signoff.

### [Mini GPU Runtime Playground](https://github.com/jwen2003/mini-gpu-runtime-playground)
**C++17 · CPU Architecture · Memory Hierarchy · SIMD · Performance Analysis**

- Investigated cache-set conflicts, compiler vectorization, and floating-point reduction dependencies using performance counters and assembly.
- Compared cache blocking, register blocking, SIMD microtiles, and numerical policies.
- Register blocking achieved 1.466× speedup over strict i-k-j for a 1024-square workload on Ryzen 7 7730U.
- CPU experiments are implemented; CUDA and runtime dispatch remain future work.

### [Adaptive V.35 Sampling Monitor](https://github.com/jwen2003/adaptive-sampling-monitor)
**SystemVerilog · CDC · CPLD · Hardware/Software Interfaces**

- Reconstructed a legacy receive-edge phase measurement subsystem from engineering specifications.
- Implemented synchronizers, event detection, phase measurement, and CPU-facing register contracts.
- Self-checking unit and integration tests, including 29 integrated checks.
- Separate CPU reference-model experiments on circular averaging, phase wraparound, and decision confidence.

## Open-Source Contributions

**[IREE](https://github.com/iree-org/iree) — Runtime / Python Bindings**

Contributing exception-safety fixes at the HAL C/C++ and Python boundary, focusing on resource lifetime and RAII.

- [#25301 — HalDriver::Query](https://github.com/iree-org/iree/pull/25301)
- [#25314 — HalDriver.dump_device_info](https://github.com/iree-org/iree/pull/25314)
- [#25315 — HalAllocator::FormattedStatistics](https://github.com/iree-org/iree/pull/25315)
- [#25323 — HalDriver::QueryAvailableDevices](https://github.com/iree-org/iree/pull/25323)

## Industry Experience

**FPGA Engineering Intern — Current**

- RTL integration, simulation, board bring-up, and hardware debugging.
- High-speed digital interfaces, packet-level diagnostics, and PLL control/sequencing.

**Board Design Intern — MetaX Integrated Circuits**

- GPU board validation and post-silicon characterization support.
- Automated S-parameter analysis, measurement repeatability analysis, BOM comparison, and characterization-log processing.

## Additional Projects

- [Mobile WebGPU GEMM](https://github.com/jwen2003/mobile-webgpu-gemm) — Partial mobile GPU performance evaluation on Mali; Adreno not yet tested.
- [PCB Defect Detection](https://github.com/jwen2003/pcb-defect-detection) — Explainable inspection pipeline; 99.59% recall and 61.19% precision on 500 DeepPCB test images.
- [Hardware Engineering Playbook](https://github.com/jwen2003/hardware-engineering-playbook) — Hardware engineering notes and investigation methods.

## Engineering Approach

Design intent → Architecture & contracts → Implementation → Verification & measurement → Controlled experiments → Evidence → Engineering decision.

I aim to distinguish demonstrated results from assumptions and future work, and explain why a design decision is justified rather than simply report an implementation or speedup.

## Background & Contact

- B.S. Electrical and Computer Engineering — Santa Clara University
- Incoming M.S.E. — University of Pennsylvania, Fall 2027

[LinkedIn](https://www.linkedin.com/in/j-wen/) · [GitHub](https://github.com/jwen2003)

[jiayanwen2003@gmail.com](mailto:jiayanwen2003@gmail.com) · [13621074266@163.com](mailto:13621074266@163.com)
