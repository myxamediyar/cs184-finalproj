---
title: CS 184 Project Proposal
layout: default
---

# CrushFX: Soft body compression for crumple zone simulation

**Team members:** Rishi Khare, Mukhamediyar Kudaikulov, Aniketh Prasad, Alson Chan

## Problem Description

We aim to develop a soft body polygon mesh deformation simulator with the ability to customize the amount of force and force directions which can be applied. The upshot of this project is to analyze the crumple zones of everyday objects, which become incredibly important in regards to consumer safety, particularly in car design in crash simulations. Additionally, the “hydraulic press” style animations will help show the deformation of the mesh over the course of several time steps of constant pressure.

## Goals and Deliverables

### Baseline Deliverable:
Key parts of our deliverable: Our goal is to explore finite element deformation techniques to achieve a high level of realism in our deformation and crushing simulations. Using finite element analysis, we can accurately model the behavior of complex structures under various loading conditions while accounting for different material behavioral and structural differences. To accomplish this, we will utilize the Deal.II library which provides a robust framework for finite element analysis. In the end, we are aiming to provide an interface for users to add mesh elements and visualize an animation of a force being applied.


### Outcomes:
- Be able to probabilistically model soft body compression via pressure mathematically (Not hard-coded)
- Demo: Animate crushing over a series of time steps
- Display crumple zones of the polygon mesh


### Measuring accuracy:
We can measure the accuracy of our deformation model by comparing against realistic simulations of hydraulic press crushes. If we are able to achieve a visually similar and physically reasonable effect. Accuracy measurement is a qualitative analysis for this project.


### Important questions:
In conducting analysis with our simulation framework for can crumpling, we aim to answer several key questions to gain insights into the behavior of materials during deformation events. Some of these questions include:
- **Structural Integrity:** How does the structure of the can deform under different loading conditions, and how does this affect its structural integrity? We seek to understand how the can's geometry changes, where stress concentrations occur, and how these factors influence its ability to withstand external forces.
- **Energy Absorption:** How effective are different designs or materials at absorbing energy during the crumpling process? We aim to evaluate the energy absorption capacity of the can and how it varies with factors such as material properties, geometry, and crumple zone design.
- **Deformation Patterns:** What are the characteristic deformation patterns exhibited by the can during crumpling? We seek to analyze the distribution of strain and displacement throughout the can's structure and identify any recurring deformation modes or failure mechanisms.


### Customizations features:
- **Amount of force:** the user should be able to modify the amount of pressure exerted on the mesh
Directions of force: the user can customize the direction of force applied to the object (not just from top-down in the hydraulic press manner)
- **Material of Object:** Different material properties should have different responses to forces
Objects included: Our “teapot” example will be a soda can, however, we will also include meshes of a car and other objects
- **Speed of animation:** edit the speed of video playback (frames/second)


### Extensions of the project:
- Stylistic backgrounds for video renders (i.e. generate cool backgrounds to make videos more aesthetically pleasing)
- Generate a heatmap of which areas of the object will be more prone to deformation: visualize crumple zones
- 3D simulation via NeRF: render a 3D scene from 2D snapshots of the compression animation


### Schedule:
- **Week 1:** Go through the deal.ii library and learn the prerequisite knowledge and library features we will need to accomplish our goals. Create our codebase and finish mesh creation.
- **Week 2:** Create our finite element deformation model, implement self-collision, and be able to simulate a force over a series of time steps. 
- **Week 3:** Finish GUI layout for customization for different force vectors/force amounts and material properties.
- **Week 4:** Finish video generations of crushing and refine by testing with other polygon meshes. If time permits, we can tackle the extensions of the project including: backgrounds for video renders, heatmaps of deformation, and 3D animation from 2D snapshots using NeRF.


## Resources

- Deal II framework: https://www.dealii.org/current/doxygen/deal.II/step_18.html
  Here is how the Deal.II library can be used:
  - Mesh Generation: Deal.II offers robust mesh generation capabilities, allowing for the creation of     complex geometries suitable for simulating the deformation of objects like cans. It supports mesh refinement strategies that can focus computational resources on areas of interest, such as the regions undergoing crushing.
  - Finite Element Solvers: Deal.II provides a suite of finite element solvers for solving a variety of partial differential equations, including those governing the mechanical behavior of deformable bodies. These solvers can be adapted to model the deformation of materials under external forces, such as those experienced during crushing.
  - Material Models: Deal.II provides a framework for implementing custom material models.
- OpenGL: https://www.opengl.org/
  - We will need to export meshes from Deal.II to OpenGL to create a GUI, textures, and animations.


