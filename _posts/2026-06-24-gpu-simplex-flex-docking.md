---
layout: post
title: "GPU Simplex Minimizer for Flexible Docking"
date: 2026-06-24 08:00:00 -0700
tags: [gpu, metal, flex-docking, performance]
---

The GPU simplex minimizer has progressed through several phases and is now
functional for flexible-ligand docking with Metal on Apple Silicon.

## What's done

- **Phase 1–2**: GPU scoring kernels (`dg_internal`, `dg_grid`) running on
  Metal, verified against CPU results
- **Phase 3A**: GPU-side simplex loop — translations, rotations, and torsions
  evaluated on the GPU with batch scoring
- **Phase 3B**: Full flexible-ligand docking path using the GPU minimizer,
  including ligand parameter handling and IE (internal energy) upload

## Key fixes along the way

- Fixed step-size scaling in the GPU simplex to match the CPU behavior
- Corrected an `active_flags` bug in the scoring kernels that caused incorrect
  atom masking
- Added proper ligand parameter transfer to the GPU for torsion evaluation
- Fixed IE upload so internal energies are computed on-device

## Speculative batch evaluation

One of the more interesting optimizations: instead of scoring one simplex
vertex at a time, the GPU evaluates multiple candidate conformations in a
single batch — dramatically improving occupancy and throughput on the GPU.

This is still being tuned, but early results are promising.
