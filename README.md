# Fast Alignment of AR Headset from Local to Geodetic Coordinate Frame for Navigation and Mixed Reality Applications
Code from the paper:
E. Sangenis and A. M. Shkel, "Fast-Alignment of AR Headset from Local to Geodetic Coordinate Frame for Navigation and Mixed Reality Applications," in IEEE Sensors Letters. You can find the paper [here](https://ieeexplore.ieee.org/document/10830499).

## Abstract:
The integration of Virtual Reality (VR) and Augmented Reality (AR) technologies into location-based services and applications necessitates precise navigation within an absolute geodetic reference frame, utilizing latitude, longitude, and altitude (LLA) coordinates. Typically, VR/AR headsets establish a local Cartesian (XYZ) world coordinate (WC) frame with an arbitrary initial origin and orientation. For accurate geodetic navigation, it is essential to align these devices to the true North (TN). This letter introduces an AR-based method for achieving the initial alignment of the WC frame relative to the geodetic frame. We developed an AR user interface to visually guide users to a known target with LLA coordinates, indirectly aligning the system to TN. Using a Magic Leap 2 AR headset, we evaluated our approach against traditional magnetometer-based methods. Our experimental results demonstrated that our method reduces the mean angular error by a factor of 4× and the standard deviation (σ) by 5× compared to traditional magnetometer methods. This improvement can eliminate the need for initial magnetometer calibration, offering a more efficient and robust solution for TN alignment in AR/VR applications.

## 📌 Overview
AR/VR systems typically operate in a WC frame with arbitrary origin and orientation. However, many navigation and location-based services require alignment with a global frame (LLA coordinates) and, critically, with TN.

This repository provides code and examples for a visual AR-based fast-alignment method that:

* Aligns the AR headset WC frame to the geodetic frame
* Indirectly aligns the system to True North using a known geographic target
* Reduces heading error compared to magnetometer-based methods
* Eliminates the need for magnetometer calibration

See the paper for full theory, derivations, and validation results.

## 🧠 Key Idea
Instead of relying on magnetometers for North finding:
* The user starts at a location with known LLA.
* A target in the environment with known LLA is selected in a GPS satellite app.
* The AR interface displays a virtual line to the target position.
* The user visually aligns this AR line with the real target with the AR/VR device.
* A heading offset ψ is computed and applied to the WC frame.
This yields a fast and practical initialization to the geodetic frame.

## Hardware
Example hardware used in the experiments:

* **AR Headset**
  + Magic Leap 2
* **IMU**
  + ICM-20948 (9DoF)
* **Position Reference**
  + GPS-RTK (for ground-truth surveying)

Your own setup may vary.

## How to Cite
If you use this work, please cite the following paper:
> **Fast-Alignment of AR Headset From Local to Geodetic Coordinate Frame for Navigation and Mixed Reality Applications**<br>
> E. Sangenis, and A. M. Shkel<br>
> *IEEE Sensors Letters*, vol. 9, no. 2, pp. 1-4, 2025.

**BibTeX:**

```bibtex
@ARTICLE{11314840,
  author={Sangenis, Eudald and Jao, Chi-Shih and Wang, Danmeng and Shkel, Andrei M.},
  journal={IEEE Sensors Letters},
  title={Foot Velocity in Stance Phase Is Not Zero: Revisiting Velocity Updates for Foot-Mounted Inertial Navigation Systems},
  year={2025},
  volume={9},
  number={2},
  pages={1-4},
  doi={10.1109/LSENS.2025.3526597}
}
```

## Authorship
Eudald (esangeni@uci.edu)
