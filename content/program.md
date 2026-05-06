+++
title = "Program"
draft = false
+++

The workshop will take place on **May 20** and will be chaired by Davide Gadioli. Each speaker will have 15 minutes for their presentation, followed by 5 minutes for questions and discussion.

## Timetable

<div style="max-width: 100%; overflow-x: auto;">
<table>
  <colgroup>
    <col style="width: 200px;">
    <col style="width: 300px;">
    <col style="width: 700px;">
  </colgroup>
  <thead>
    <tr>
      <th>Time</th>
      <th>Speaker</th>
      <th>Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>16:00–16:10</td>
      <td>Nitin Shukla</td>
      <td>Welcome</td>
    </tr>
    <tr>
      <td>16:10–16:50</td>
      <td>Gianluca Palermo</td>
      <td>Beyond Molecular Docking: Toward Extreme-Scale Virtual Screening on European HPC Infrastructures</td>
    </tr>
    <tr>
      <td>16:50–17:10</td>
      <td>Alessandro Romeo</td>
      <td>On the Limits of Performance Portability in Directive-Based GPU Programming</td>
    </tr>
    <tr>
      <td>17:10–17:30</td>
      <td>Dionisis-Odysseas Sotiropoulos</td>
      <td>Evaluating the benefits of Argument Fusion: Optimizing host-device communication</td>
    </tr>
    <tr>
      <td>17:30–17:50</td>
      <td>Leonardo Beltrame</td>
      <td>A Distributed Virtual Screening Miniapp for Performance Portability and Cross-Architecture Benchmarking</td>
    </tr>
    <tr>
      <td>17:50–18:10</td>
      <td>Mandana Safari</td>
      <td>Design and Implementation of a Prediction-Serving System for Runtime and Parallel Performance in Quantum ESPRESSO</td>
    </tr>
    <tr>
      <td>18:10–18:30</td>
      <td>Lorenzo Carpentieri</td>
      <td>Enabling Portable Collective Communication on Heterogeneous GPU Systems</td>
    </tr>
    <tr>
      <td>18:30–18:40</td>
      <td>Biagio Cosenza</td>
      <td>Conclusions and remarks</td>
    </tr>
  </tbody>
</table>
</div>

## Abstracts

#### Beyond Molecular Docking: Toward Extreme-Scale Virtual Screening on European HPC Infrastructures

In drug discovery, virtual screening is primarily a scaling problem: the more molecules that can be evaluated, the greater the chance of finding relevant candidates. With classical approaches, only a tiny fraction of chemical space can be explored within a useful timeframe. This talk presents our journey in rethinking virtual screening on HPC architectures, covering approximation techniques and GPU acceleration, as well as portability and full-pipeline optimizations. The pandemic scenario will also be discussed, where urgent computing requires not only high performance, but also the ability to distribute workloads across multiple European supercomputing centers.


---

#### On the Limits of Performance Portability in Directive-Based GPU Programming

The transition of scientific applications to GPU-accelerated exascale systems is constrained by trade-offs between performance, portability, and productivity. This work evaluates the performance portability of directive-based GPU programming by porting gPLUTO, a production-grade magnetohydrodynamics code for astrophysical simulations, from OpenACC to OpenMP, and analyzing its performance on NVIDIA A100 (Leonardo Booster) and AMD MI250X (LUMI-G) devices. On NVIDIA platforms, OpenACC and OpenMP achieve comparable performance due to a shared compiler backend, providing a consistent baseline for assessing algorithmic efficiency. In contrast, the same OpenMP implementation is approximately three times slower at the application level on AMD MI250X with respect to the NVIDIA A100 OpenACC baseline, with kernel-level slowdowns reaching up to an order of magnitude, driven by sensitivity to strided memory-access patterns and compiler limitations. Kernel-level profiling shows that the dominant contributors to runtime are memory-latency-bound rather than limited by peak bandwidth. In low-parallelism kernels, C++ abstraction layers increase register pressure and spilling, leading to extreme slowdowns of up to 47× in specific cases. These results indicate that portable performance across GPU architectures requires not only application-level changes but also continued advances in compiler backends and architecture-aware optimization strategies.

---

#### Evaluating the benefits of Argument Fusion: Optimizing host-device communication

Data movement remains a major bottleneck in heterogeneous systems with discrete GPUs, particularly when kernels expose many arguments that are transferred independently, leading to fragmented allocations and inefficient interconnect utilization. In this work, we evaluate Argument Fusion, a technique that merges multiple kernel arguments into a single contiguous buffer, reducing the number of allocation, transfer, and deallocation operations. We further study Argument Fusion+, which combines fusion with pinned memory and asynchronous CUDA transfers. Using both a parametric synthetic benchmark and real applications from the Polybench suite, we show that Argument Fusion achieves up to 2.1× speedup, while Argument Fusion+ reaches up to 2.6×. On real benchmarks, the combined approach improves end-to-end execution time by up to 68%.

---

#### A Distributed Virtual Screening Miniapp for Performance Portability and Cross-Architecture Benchmarking

Drug discovery is a long and costly process with a low success probability. One of the challenges is the sheer size of the chemical space of drug candidates to explore. To mitigate this problem, we make use of large-scale virtual screening campaigns running on HPC centers to suggest which molecules should be tested in-vitro. For this reason, there is a recent trend that aims to rewrite scientific applications to improve computational efficiency. In this work, we target muDock, a single node virtual screening miniapp designed to experiment and benchmark virtual screening implementations for performance portability on different architectures. In particular, we enhance muDock with the ability to distribute the computation using a static partition, enabling scale-out across the available nodes of an HPC center. Experimental results show that muDock scales well, due to the embarrassingly parallel nature of the problem.

---

#### Design and Implementation of a Prediction-Serving System for Runtime and Parallel Performance in Quantum ESPRESSO

Ab initio simulations, such as those performed with Quantum ESPRESSO (QE), play a central role in materials science but are often limited by their high computational cost. Predicting the execution time of self-consistent field (SCF) iterations is particularly challenging, as performance depends on both the physical characteristics of the simulated system and the parallelization parameters of the underlying hardware. To address this challenge, we investigate the use of machine learning techniques to predict the time required per SCF iteration directly from QE inputs, pseudopoten- tials, and computational settings. A complete workflow is designed to process raw benchmarking data into structured datasets, train a proper neural network, and integrate the trained models into a web-based prediction-serving system.

---

#### Enabling Portable Collective Communication on Heterogeneous GPU Systems

Multi-node GPU systems are the foundation of modern, high-performance computing and deep neural networks training. While vendor-specific collective communication libraries such as NVIDIA’s NCCL deliver superior performance over traditional MPI, they sacrifice portability by tightly coupling applications to a single hardware platform. The oneAPI Collective Communications Library (oneCCL), as part of the oneAPI ecosystem, aims to provide a vendor-agnostic communication API for heterogeneous GPU clusters, but its support for non-Intel hardware remains limited.
This paper presents a lightweight integration layer that bridges oneCCL’s portable API with vendor-optimized backends, mapping oneCCL collective calls to native implementations such as NCCL on NVIDIA GPUs and RCCL on AMD GPUs. This design preserves source-level portability through the SYCL programming model and the oneCCL API while delivering communication performance on par with the underlying native library.
We evaluate our approach on NVIDIA A100 GPUs and AMD MI250x GPUs, comparing vensor specific libary such as NCCL and RCCL with our oneCCL integration across allreduce and all-to-all collectives, with multiple data types and message sizes, in both intra-node and inter-node configurations. Experimental results show that oneCCL achieve near-identical performance against native backends without losing cross-platform portability.