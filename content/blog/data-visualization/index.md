---
title: Dataset for multi-degree-of-freedom robotic 
summary: Create a dataset containing multiple robotic arm MJCF files.
date: 2024-10-25
authors:
  - admin
tags:
  - Hugo
  - Hugo Blox
  - Markdown
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
---


## Overview

1. We plan to build a dataset for multi-degree-of-freedom robotic arms, with the goal of training a model that takes videos of robotic arm movements as input and outputs the corresponding URDF file.
2. I generated the link in Fusion 360, using DH parameters to determine the link's shape. A spine curve was used as the baseline, and the link was created with the loft function, then saved as an STL file.
3. Since the loft function failed to generate the link for certain DH parameters, I switched to using dual quaternions. This method produced smoother curves and was capable of handling any DH parameter.
4. I modified the DH parameter generation range to reduce the occurrence of oddly shaped links. Additionally, I optimized the link generation process to minimize excessive twisting caused by large theta values.
5. I wrote a program that automatically selects appropriate links to assemble into a robotic arm and generates the corresponding MJCF files for visualization in MuJoCo.


