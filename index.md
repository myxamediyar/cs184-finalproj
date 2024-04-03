---
title: CS 184 Project Proposal
layout: default
---

# CrushFX: Soft body compression for crumple zone simulation

**Team members:** Aniketh Prasad, Rishi Khare, Mukhamediyar Kudaikulov, Alson Chan

## Problem Description

We aim to develop a soft body polygon mesh deformation simulator capable of customizing the force amount and direction applied. This project is intended to analyze crumple zones of everyday objects, crucial for consumer safety, particularly in car crash simulations. The simulations will also provide "hydraulic press" style animations to demonstrate mesh deformation over time under constant pressure.

## Goals and Deliverables

### Baseline Deliverable:
Our key deliverables include:
- Probabilistically modeling soft body compression via mathematical pressure (not hard-coded).
- Animating compression over a series of time steps.
- Displaying crumple zones of the polygon mesh.

### Customizations:
- **Amount of Force:** Users can modify the pressure exerted on the mesh.
- **Directions of Force:** Users can customize the force direction applied to the object.
- **Objects Included:** We will use a soda can as our "teapot" example, including car meshes and other objects.
- **Speed of Animation:** Users can adjust the playback speed of the video (frames/second).

### Extensions of the project:
- Stylistic backgrounds for video renders.
- Generating a heatmap to visualize crumple zones prone to deformation.
- 3D simulation via NeRF from 2D snapshots of the compression animation.

## Schedule

- **Week 1:** Complete mesh transformation.
- **Week 2:** Add support for custom force amounts and animation rendering.
- **Week 3:** Finalize GUI layout for customizing force vectors/amounts.
- **Week 4:** Complete video generations and add other polygon meshes for compression.

## Resources

- [Deal II framework](https://www.dealii.org/current/doxygen/deal.II/step_18.html)

