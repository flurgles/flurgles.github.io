---
layout: post
title: "WL Graph Symmetry Detection & Hungarian RMSD"
date: 2026-06-24 07:00:00 -0700
tags: [clustering, rmsd, hungarian, wl-graph]
---

Added Weisfeiler-Lehman (WL) graph symmetry detection with Hungarian algorithm
min-cost matching for RMSD calculations. This improves clustering quality by
finding the optimal atom mapping when symmetric atoms are present.

## What changed

- **`compute_hungarian_rmsd()`** — new function that finds the minimum RMSD
  over all valid permutations of symmetric atoms using the Hungarian algorithm
- **Short-circuit optimization** — for the common case where there are no
  symmetries, a fast path avoids the full Hungarian overhead
- **Verbose print** — optional diagnostic output showing the permutation matrix
  and cost breakdown

## Cluster RMSD split

The single `cluster_rmsd_type` parameter has been split into two:

| Parameter | Purpose |
|---|---|
| `pruning_cluster_rmsd_type` | Used during pruning (internal clustering) |
| `final_pose_cluster_rmsd_type` | Used for final pose output clustering |

This gives independent control over the clustering behavior at each stage.

## Hungarian RMSD fix

Also fixed a fencepost error in the Hungarian RMSD implementation and removed
an unnecessary `NUM` member that was causing off-by-one indexing in the cost
matrix.
