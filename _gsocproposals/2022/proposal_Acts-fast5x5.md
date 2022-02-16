---
title: Vectorized linear algebra implementation in Acts
layout: gsoc_proposal
project: Acts
year: 2022
organization: CERN
---

## Description

Data taking and analyses in high energy physics critically rely on a precise reconstruction of particle trajectories through a detector geometry. Given the amount of data to be processed and the rising combinatorics in future experiments, track finding and fitting tasks need to be implemented as efficient as possible, making use of state of the art computing hardware. The ACTS project (A Common Tracking Software) provides highly optimized implementations of tracking algorithms written in C++ that are designed to be integrated into the reconstruction software of high energy physics experiments.

A key role in optimizing performance of tracking software is the deployment of hardware based parallelization, which requires an adaptation of the existing code base to the specific technology in certain places. Making heavy use of linear algebra routines throughout the algorithmic code, and given the inherent parallel nature of such computations, it is expected that ACTS will benefit from the integration of a dedicated parallelized implementation in this area.

## Task ideas
We propose the deployment of the fast5x5 library for the ACTS linear algebra implementation, which makes use of xsimd for CPU vectorization in common matrix operations. The student is expected to make the existing library implementation available to ACTS as a compute backend and to perform a subsequent performance study to validate the approach.

## Expected results
Working prototype

## Requirements
C++

## Mentors
  * **[Joana Niermann](mailto:joana.niermann@cern.ch)** (CERN)
  * [Hadrien Grasland](mailto:)

## Links
  * [Acts](https://github.com/acts-project/acts)
  * [fast5x5](https://gitlab.in2p3.fr/CodeursIntensifs/Fast5x5/)
  * [xsimd](https://github.com/xtensor-stack/xsimd)