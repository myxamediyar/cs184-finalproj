---
title: CS 184 Project Milestone Writeup
layout: default
---

# CrushFX: Soft body compression for crumple zone simulation

**Team members:** Rishi Khare, Mukhamediyar Kudaikulov, Aniketh Prasad, Alson Chan


Unlike we initially proposed in the proposal, we decided to implement mesh deformation in Unity. When writing the proposal, we had initially imagined using OpenGL/C++; however, we found that Unity offers a variety of mesh customization options which would be very helpful for our project. We implemented procedural mesh generation based on vertices and triangles in order to customize both the number of triangles and the shape of triangles which compose a 3D shape. From this custom mesh object, we implemented deformation by modifying the positions of the vertices of the mesh. For this milestone, we decided to trigger timesteps in deformation using user feedback with mouse clicks in our script, which can be applied to any 3D object in Unity and applies a top-down crushing effect on a mesh. Notably, the effect seems to work well with the default Capsule shape in Unity, and we theorize that this is because the Capsule shape includes many more triangles, vertices, and faces than simpler objects, such as cylinders, which allows for more vertices to move over the course of the deformation.

### Approach 1: Adjusted Spring Mass System
The approach we first envisioned was an adjusted spring mass system, built partially off the idea first introduced in HW4. 

Here, we imagined that taking a spring-mass system and modifying it to prevent “spring back” to its normal configuration would also result in deformation. Specifically, the springs could only be compressed and not return to their original length after compression. Thus, we created a mesh with enough geometry to be represented as a 3D spring-mass system, and binded a point mass to each vertex and a spring between each adjacent point mass. The biggest challenge with this approach was modeling realistic self-collisions, and finding the right parameters to make the deformation appear more realistic. These are the things we will try to fix moving forward.


### Approach 2: Direct Polygon Mesh Deformation
An approach that we are considering is manipulating the vertices of the mesh directly, with random noise vectors to account for random perturbations in deformation. 
The algorithm that we came up with computed the centroid of the vertices of a given shape, offset in the y-value to match the highest vertex and an additional optional constant. This centroid will act as the point from which the force originates. For every point within a certain radius of the centroid, we apply the deformation function to compute the vertex’s deformed version offset by a noise vector. This will shift the centroid’s neighboring vertices down, in turn lowering the centroid too. This deformation is applied continuously until the ground point is reached. 
Albeit a few rendering errors similar to those in the first approach, our idea is to expand on this implementation, and apply it onto a broader class of meshes (rather than Unity’s defaults).
Unity offers a Mesh class which allows for scripting for custom mesh definitions. Through procedural meshes representing cubes and spheres, we were able to make meshes with far more vertices and triangles than the built-in Sphere and Cube GameObjects in Unity. In this way, with more vertices and triangles, we theorized that the meshes would be able to have more agility in deformation because there would be more edges to collapse and “crumple zones” to exploit movement from.  
