# AlbedoPolicy: Albedo-Aware Diffusion Policy for Manipulation of Reflective Objects

This repository contains the code and experimental setup for AlbedoPolicy, a visuomotor learning framework that integrates albedo-based visual representations into Diffusion Policy for real-world robotic manipulation. The goal of this project is to improve robustness and data efficiency when manipulating reflective and glossy objects, where RGB observations are often corrupted by illumination, shading, and specular highlights.

**Overview:**
Standard RGB-based visuomotor policies entangle object appearance with lighting effects, which can significantly degrade performance on reflective objects. AlbedoPolicy addresses this challenge by:
  - Converting RGB demonstrations into albedo representations offline using a photorealistic intrinsic decomposition method.
  - Training Diffusion Policies directly on albedo observations instead of raw RGB.
  - Learning a real-time RGB-to-albedo model that enables deployment without access to ground-truth intrinsic information.
    
At inference time, the robot operates fully in closed loop: RGB images from a wrist-mounted camera are converted to albedo in real time and consumed by a diffusion-based control policy to generate actions.

## Table of contents
- [Sections](#sections)
  - [Sections2](#sections2)
- [Definitions](#definitions)

## Method Summary
The pipeline consists of three main stages:
1. Demonstration Collection
   - Teleoperated demonstrations using a UR5 robot with a wrist-mounted RGB camera
   - RGB video synchronized with robot state and action trajectories
   - Objects include metallic, glossy, transparent, and diffuse materials
2. Offline Albedo Generation
   - Demonstration RGB videos are processed offline using a diffusion-based intrinsic renderer to obtain paired RGB–albedo data
3. Policy and Perception learning
   - A Vision Transformer–based model is trained to map RGB frames to albedo
   - Diffusion Policy is trained using albedo observations and original robot trajectories
   - At deployment, the learned RGB-to-albedo model provides real-time albedo estimates for closed-loop control
### Sections2



## Contributing

