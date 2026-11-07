---
layout: post
title: "Building NRL Tackle in VR"
author: "UQ Reality Labs"
date: 2026-11-07 09:00:00 +1000
categories: projects
tags: nrl tackle unity xr vr
---

NRL Tackle is an early Unity XR remake of the NRL Tackle game, aimed at VR
headsets and camera-tracked square play spaces. The goal is to rebuild the
rugby league tackling experience as an immersive prototype, replacing the
remaining Unity VR template and sample content with project-specific gameplay,
environments, and assets.

The project targets Unity `6000.5.2f1` with the Universal Render Pipeline
(`17.5.0`), OpenXR, the XR Interaction Toolkit, and XR Hands. Meta OpenXR and
Android XR headsets are the current targets, with Git LFS tracking the large
art and media files.

## What is in the project

- A playable OpenXR scene with project-owned gameplay scripts and settings.
- A stadium built in Blender, with source files kept outside Unity's import
  tree and exported to FBX for the build.
- VR-friendly import defaults applied automatically by `AutoQuality.cs`,
  including foveation and dynamic resolution selected from the available
  headset hardware.

The build is still a prototype, and the Unity template and package sample
content remain in place while the team replaces them piece by piece.

## Running it

1. Install Git LFS and Unity `6000.5.2f1`, including the Android Build Support
   module for standalone headsets.
2. Clone the repository and run `git lfs pull`.
3. Open the project in Unity Hub and let Package Manager restore the packages.
4. Open `Assets/Scenes/BasicScene.unity` and test with a compatible OpenXR
   runtime.

The repository is at
[github.com/uqrealitylabs/NRL-tackle](https://github.com/uqrealitylabs/NRL-tackle).
