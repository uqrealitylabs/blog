---
layout: post
title: "Face-controlled ball tracking for referee training"
author: "UQ Reality Labs"
date: 2026-11-07 12:00:00 +1000
categories: projects
tags: referee tracking webcam unity python
---

The referee project is a face-controlled ball tracking setup: a webcam tracker
reads where you are looking and a Unity stadium scene uses that aim to measure
how well you keep the ball in view.

It is a camera-aim trainer, not a test of eye gaze or refereeing ability. The
panel compares time aimed at the visible ball with time aimed elsewhere, and
occlusion counts as elsewhere. Pauses are excluded from the measurement.

## How it works

A small Python tracker reads the webcam feed, then a Unity `6000.5.2f1` scene
(`Assets/Scenes/Stadium.unity`) receives the face and hand landmarks over shared
memory.

- Move your head to aim the crosshair.
- Press **C** to centre, then **Space** to start or pause.
- Press **R** for the next guest, which pauses, clears stats, recentres, and
  resets sensitivity to 2x.
- Adjust sensitivity with the right-hand slider or by moving a closed fist
  up and down. Open the hand to stop adjusting.
- Press **Q** in the webcam window, or `Ctrl+C` in the terminal, to stop
  tracking.

Losing face tracking for half a second pauses play; press **Space** to resume.
The tracking side is checked with `uv run check` in `tracking/`, and the Unity
side has a batch-mode check that logs `Ball tracking checks passed`.

The positioning guidance the project follows is the
[IFAB guidance on positioning, movement, and teamwork](https://www.theifab.com/laws/latest/guidelines/positioning-movement-and-teamwork/).

The repository is at
[github.com/uqrealitylabs/referee-project](https://github.com/uqrealitylabs/referee-project).
