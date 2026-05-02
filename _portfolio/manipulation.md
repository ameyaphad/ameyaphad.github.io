---
title: "A Novel Vision-guided Manipulation Pipeline for Effective Grasping"
collection: portfolio
permalink: /projects/manipulation/
# ↓ Replace with your actual GitHub repo URL
# external_link: "https://github.com/ameyaphad/vision-guided-manipulation"
teaser_image: manipulation.jpg
image_width: 180
order: 1
short_description: >
  Vision-guided manipulation pipeline for effective grasping of handle objects using purely point cloud data by leveraging an Octree compression algorithm.
---

This project proposes a **novel vision-guided manipulation pipeline** used for grasping objects, especially common household objects with handles, using purely point clouds. There are 2 contributions to this project- a **novel vision pipeline** which uses an algorithm that performs an adaptive Octree partitioning of the object point cloud, and a **grasping algorithm** which leverages the features generated from this Octree generation to perform effective grasping.

The pipeline was tested on a **cooking pan** as can be seen in the gif below. Point cloud data was merged from 2 **Intel Realsense Depth Cameras**, and robotic grasping was performed using the **Franka Emika Panda Arm**.

<figure>
  <img src="{{ '/images/grasping_panda.gif' | relative_url }}" alt="grasping demo" style="max-width: 500px; width: 100%;">
  <figcaption>Handle Object Grasping Demo using Panda Robotic Arm</figcaption>
</figure>



## Vision Pipeline

The image below gives an overview of the vision pipeline. It takes in the object point cloud, performs outlier removal, and then performs an adaptive Octree spatial partitioning by using a robust density packing metric to result in a lighter Octree representation.

<figure>
  <img src="{{ '/images/vision.png' | relative_url }}" alt="vision pipeline" style="max-width: 720px; width: 100%;">
  <figcaption>Vision Pipeline Flow</figcaption>
</figure>


## Grasping Pipeline

The image below shows the flow of the grasping algorithm. It takes in the compressed Octree representation of the object, determines if the object requires simple grasping or not, and then based on that performs a handle region search and generates appropriate grasp poses.

<figure>
  <img src="{{ '/images/grasping.png' | relative_url }}" alt="grasping pipeline" style="max-width: 720px; width: 100%;">
  <figcaption>Grasping Pipeline Flow</figcaption>
</figure>


## System Integration

The vision and grasping pipeline were integrated with a robotic arm system with Intel Realsense Depth cameras for obtaining the point cloud. The system integration was done using **ROS2** and the robot motion was executed with a **MoveIt2** integrated motion planner.

<figure>
  <img src="{{ '/images/system.png' | relative_url }}" alt="system pipeline" style="max-width: 720px; width: 100%;">
  <figcaption>System Integration</figcaption>
</figure>