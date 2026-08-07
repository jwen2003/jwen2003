# Hi, I'm Jiayan Wen

Electrical & Computer Engineering student focusing on **computer systems, digital hardware, and silicon-level debugging**.

My interests lie at the boundary between:

- Digital Design & RTL Architecture
- Computer Architecture
- Silicon Validation & Hardware Debug
- AI Accelerator Systems

I enjoy understanding systems from first principles:

> Why does a system work?  
> Where does it fail?  
> What evidence can prove the root cause?

---

## Featured Projects

### Adaptive V.35 Sampling Monitor

**SystemVerilog | RTL Design | Verification**

A reconstruction of a legacy CPLD subsystem for adaptive receive-edge sampling.

Highlights:

- Recovered system behavior from legacy engineering documents and discussions
- Designed a synthesizable SystemVerilog implementation
- Built modular RTL architecture:
  - Input synchronization
  - Event detection
  - Phase measurement
  - Register interface
- Developed unit tests and end-to-end simulation flow with Verilator

Repository:
[adaptive-sampling-monitor](https://github.com/jwen2003/adaptive-sampling-monitor)

---

### DeepPCB Two-Stage Defect Detection

**Computer Vision | Classical ML | Industrial Inspection**

A reproducible PCB defect detection pipeline combining:

- ECC-based image registration
- Difference-based candidate extraction
- Morphological processing
- Connected-component analysis
- Random Forest candidate filtering

Key idea:

Use a high-recall detector first, then reduce false positives with lightweight classification.

Results on the official DeepPCB test split:

- False positives reduced by 70.52%
- Precision improved from 31.77% to 61.19%
- F1 improved from 48.19% to 75.81%

Repository:
[DeepPCB-defect-detection](https://github.com/jwen2003/DeepPCB-defect-detection)

---

### The Hardware Engineering Playbook

**System Hardware Notes | Engineering Methodology**

A personal engineering knowledge framework exploring:

- AI accelerator boards
- Power delivery
- High-speed interconnect
- Firmware and validation
- Hardware debugging methodology

The goal is not memorizing components, but building a reusable approach:

- Understand system architecture
- Map interfaces and dependencies
- Analyze failure paths
- Connect physical behavior with software-visible symptoms

Repository:
[The-Hardware-Engineering-Playbook](https://github.com/jwen2003/The-Hardware-Engineering-Playbook)

---

## Current Focus

Currently exploring:

- RTL microarchitecture optimization
- Fixed-point hardware computation
- FPGA-based accelerators
- Post-silicon validation methodology
- Hardware/software boundaries in AI systems

---

## Engineering Philosophy

I believe strong engineers are not defined by the number of tools they know, but by their ability to build correct mental models.

A system should be understood through:

```
Architecture
     ↓
Interfaces
     ↓
Implementation
     ↓
Measurement
     ↓
Failure Analysis
```

---

## Contact

LinkedIn:
https://www.linkedin.com/in/j-wen/

Email:
jiayanwen2003@gmail.com
13621074266@163.com
