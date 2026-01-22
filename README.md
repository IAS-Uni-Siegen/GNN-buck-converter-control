# Graph Neural Network Control of Buck Converters — Proof of Concept

This repository contains a minimal, self-contained JAX implementation accompanying the paper:

**A Power Electronic Converter Control Framework Based on Graph Neural Networks - An Early Proof-of-Concept**  
Darius Jakobeit, Oliver Wallscheid  
arXiv: https://arxiv.org/abs/2601.06686

---

## Overview

The main notebook implements a complete evaluation pipeline for topology-aware control of power converters using graph neural networks.

Key elements include:

- Random sampling of physically consistent buck-converter parameters  
- Averaged continuous-time dynamics with forward Euler discretization  
- Stability filtering of sampled models  
- Graph-based representation of the buck topology  
- A lightweight GNN policy producing duty-cycle commands  
- End-to-end training via differentiable closed-loop rollouts  
- Quantitative comparison against an offline optimal-control baseline

This code is meant as a **proof-of-concept**, demonstrating the feasibility of using GNNs for control across heterogeneous converter instances.

---

## Repository structure

- `gnn_buck_notebook.ipynb`  
  Main notebook with sampling, training, evaluation, and plots.

- `ckpt_gnn_final/`  
  Saved checkpoint including trained GNN parameters and optimizer state.

---

## Notes

- The converter model is an **averaged buck converter** with fixed topology.
- Discretization uses **forward Euler** at a fixed switching frequency.
- The optimal-control baseline is computed **offline** via direct optimization of the duty-cycle sequence and is **not suitable for real-time control**.
- All computations are vectorized with **JAX** for efficiency.

---

## Citation

If you use this code, please cite:


@article{jakobeit2026gnnpec,<br/>
title = {A Power Electronic Converter Control Framework Based on Graph Neural Networks}, <br/>
author = {Jakobeit, Darius and Wallscheid, Oliver},<br/>
journal = {arXiv preprint arXiv:2601.06686},<br/>
year = {2026},<br/>
url = { https://arxiv.org/abs/2601.06686 }<br/>
}


