---
title: "Navigation Stack for an Autonomous Formula SAE Vehicle"
collection: portfolio
permalink: /projects/fsaedv/
teaser_image: fsaedv.jpeg
image_width: 180
order: 5
short_description: >
  Developed the navigation stack for a Formula Student vehicle, which involved custom YOLO-based object detection, depth estimation and the implementation of an Adaptive EKF.
---

Led a team of undergraduate students as part of the Student Project/Club [Formula Manipal](https://www.formulamanipal.com/) to design the autonomy stack from scratch for a Fomula SAE vehicle.

Designed the navigation stack for the vehicle, which involved building the perception and SLAM pipeline. The modules were developed in **Python and ROS**, with active testing done in **Gazebo** with simulated sensors.

## Perception

Since the main obstacles in the Formula Student events were cones, the perception pipline's main job was depth estimation of these objects. A **custom object detector** was built using YOLOv3 and the [FSCOCO](https://github.com/fsoco/fsoco-dataset/) dataset, and monocular camera-based depth estimation was done using perspective projection and known size of the cone.

<figure>
  <img src="{{ '/images/perception_demo.gif' | relative_url }}" alt="YOLO demo" style="max-width: 720px; width: 100%;">
  <figcaption>YOLO object detector demo using a laptop RGB camera</figcaption>
</figure>


## Localization and SLAM

A robust sensor-fusion based Localization and SLAM pipeline was built which fused data from various sensors like **IMU, GNSS, and Wheel Speed Sensors**. The sensor inputs were fused using an **Adaptive** Extended Kalman Filter (EKF). An adaptive version of the EKF was chosen to dynamically adjust covariances during instances when the vehicle's dynamics were highly non-linear, for instance, during sharp turns on the track.
Additionally, a robust data association module was constructed for the track cones by leveraging K-Means clustering.

<figure>
  <img src="{{ '/images/SLAM-demo.gif' | relative_url }}" alt="SLAM demo" style="max-width: 720px; width: 100%;">
  <figcaption>EKF Localization running integrated with the Planner in Simulation</figcaption>
</figure>