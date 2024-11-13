# **Robot Localization and Control Using MPC and EKF**

<div align="center">
  <img src="https://github.com/user-attachments/assets/117da2ed-f335-4a1b-abb7-3360b0f08347" alt="robot_localization" width="500px">
</div>

## Overview
This project implements a robust localization and control system for a differential drive robot using:
- **Model Predictive Control (MPC)** for real-time trajectory tracking and stabilization.
- **Extended Kalman Filter (EKF)** for accurate state estimation under noisy sensor conditions.

The combination of MPC with EKF enables the robot to reliably navigate to target positions while filtering out sensor noise, making it suitable for real-world applications.

## Project Design and Methodology

### Problem Setup
The robot is tasked with reaching and stabilizing around a predefined target position. The two main components of this setup are:
1. **MPC Controller**: Determines optimal control actions to minimize trajectory deviation while avoiding constraints.
2. **EKF**: Estimates the robot’s position and orientation by filtering noisy sensor data, which is then fed into the MPC for improved control accuracy.

A **Differential Drive Kinematic Model** is used to simulate the robot’s movement based on wheel velocities and helps predict its position over time.

### How It Works

1. **Estimation with EKF**: The EKF updates the robot's state (position and orientation) based on noisy range-bearing measurements. It predicts the state in each time step, corrects it with incoming sensor data, and provides this estimated state to the MPC.
2. **Trajectory Control with MPC**: Given the EKF’s estimated state, the MPC calculates the optimal control inputs (e.g., linear and angular velocities) to guide the robot towards the target position. The MPC minimizes deviation from the target while adjusting for the robot’s constraints and avoiding overshoot.
3. **Real-Time Feedback Loop**: The estimated state from the EKF continuously updates the MPC, creating a feedback loop that allows the robot to adapt to changing conditions and noisy data.

### Prerequisites

- **Python 3.11+**
- **Dependencies**:
  - `numpy`
  - `scipy`
  - `matplotlib`
  - `pybullet` (for simulation)


## License

This project is licensed under the GNU v3.0 License. See the `LICENSE` file for more details.

## Acknowledgments

- This project is done....
