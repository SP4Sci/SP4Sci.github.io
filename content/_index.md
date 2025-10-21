The increasing adoption of heterogeneous computing architectures—particularly GPU-accelerated and domain-specific systems has redefined the landscape of high-performance computing (HPC).
However, this architectural heterogeneity introduces significant challenges in achieving performance portability.
Vendor-specific programming models (e.g., CUDA, HIP) often result in tightly coupled codebases, limiting cross-platform interoperability, impeding collaborative development, and undermining reproducibility.

As scientific applications scale toward exascale and beyond, the need for performance-portable solutions becomes critical. Achieving near-peak performance across diverse architectures without sacrificing maintainability or extensibility requires abstraction of layers, domain-specific languages, and compiler/runtime innovations. Simultaneously, the energy footprint of large-scale simulations is becoming a first-order concern, necessitating energy-aware optimizations and sustainable computing practices.

This convergence of performance, portability, and sustainability is not merely a technical challenge—it is a foundational requirement for the future of computational science and engineering.

## Objectives

This workshop will focus on methodologies and frameworks that enable scalable, portable, and energy-efficient scientific computing across heterogeneous platforms.
Topics will include:

- Compiler and runtime strategies for performance portability (e.g., Kokkos, SYCL, RAJA, OpenMP offloading)
- Abstractions and DSLs for architecture-agnostic optimization
- Case studies demonstrating cross-platform scalability and performance tuning
- Energy-aware scheduling, profiling, and optimization techniques
- Metrics and methodologies for evaluating sustainability in HPC
- Co-design approaches for balancing performance, portability, and power efficiency

The session aims to foster discussion on the trade-offs and synergies between these dimensions, highlighting emerging research and practical solutions that address the evolving demands of extreme-scale scientific computing.
