---
title: Vectorized linear algebra implementation for Acts
layout: gsoc_proposal
project: Acts
year: 2022
organization: CERN
difficulty: medium
duration: 350h
mentor_avail: June-August
---

## Description

Data taking and analyses in high energy physics critically rely on a precise reconstruction of particle trajectories through a detector geometry. Given the amount of data to be processed and the rising combinatorics in future experiments, track finding and fitting tasks need to be implemented as efficient as possible, making use of state of the art computing hardware. The ACTS project (A Common Tracking Software) provides highly optimized implementations of tracking algorithms written in C++ that are designed to be integrated into the reconstruction software of high energy physics experiments.

A key role in optimizing performance of tracking software is the deployment of hardware based parallelization, which requires an adaptation of the existing code base to the specific technology in certain places. Making heavy use of linear algebra routines throughout the algorithmic code, and given the inherent parallel nature of such computations, it is expected that ACTS will benefit from the integration of a dedicated parallelized implementation in this area.

CPUs are equipped with inbuilt data vectorization capabilities that allow to apply a single instruction to multiple data (SIMD). In order to make use of vectorization, special instructions need to be used and further requirements regarding memory layout need to be observed. Multiple library implementations exist which expose a C++ style API and provide a portable solution to deploy explicitely vectorized code for larger projects.

## Task ideas
We propose the development of a linear algebra plugin for ACTS, which makes use of the Vc vectorization library.

* Port a similar existing library implementation (fast5x5/xsimd) to the Vc backend 
* Adapt the implemenatation to the 6x6, 6x8, 8x6, 8x8 linear algebra operations needed in the ACTS Kalman filter
* Find a way to make the implementation available to ACTS as a compute backend
* Validate the approach and its performance and possibly optimize the performance further

## Expected results
Working prototype to run in ACTS examples and performance statement

## Requirements
C++, experience with code optimization/performance tools, such as perf or vtune, and vectorization would be an asset

## Mentors
  * **[Joana Niermann](mailto:joana.niermann@cern.ch)** (CERN)
  * [Hadrien Grasland](mailto:hadrien.grasland@ijclab.in2p3.fr)
  * [Paul Gessinger](mailto:paul.gessinger@cern.ch)

## Links
  * [Acts](https://github.com/acts-project/acts)
  * [Vc](https://vcdevel.github.io/Vc-1.4.2/)
  * [fast5x5](https://gitlab.in2p3.fr/CodeursIntensifs/Fast5x5/)
  * [xsimd](https://github.com/xtensor-stack/xsimd)