# Thrust-Constrained Instantaneously Optimal Sliding-Mode Guidance  
### Fuel-Efficient Precision Soft Landing on Asteroids

---

## Overview
This repository presents a **MATLAB implementation and research extension** of the guidance framework proposed in:

*Sliding-Mode-Control–Based Instantaneously Optimal Guidance for Precision Soft Landing on Asteroids*

The original formulation derives an **instantaneously optimal sliding-mode guidance law** under the assumption of unconstrained control authority. While theoretically sound, such assumptions are difficult to satisfy in practical spacecraft landing scenarios.

This project extends the original framework by **explicitly incorporating thrust magnitude limits**, resulting in a **fuel-aware, constrained guidance strategy** that is physically realizable under realistic propulsion system limitations.

By enforcing actuator bounds, the instantaneous optimization problem becomes **non-convex**, enabling the study of trade-offs between convergence speed, robustness, and fuel efficiency in asteroid landing missions.

---

## Objectives and Contributions
The primary goal of this repository is to bridge the gap between **idealized guidance laws** and **practical spacecraft control constraints**.

Key contributions include:
- Explicit modeling of **thrust magnitude constraints**
- Formulation of a **non-convex instantaneously optimal control problem**
- Development of a **fuel-aware sliding-mode guidance law**
- Analysis of thrust saturation effects on:
  - Sliding surface convergence
  - Terminal landing accuracy
  - Control effort and fuel consumption
- Preservation of sliding-mode robustness under actuator limitations

---

## Motivation
The unconstrained control assumption in the original formulation is rarely valid for real asteroid landing missions:

- Thrusters operate under strict magnitude limits
- Saturation can degrade sliding-mode convergence
- Fuel efficiency is critical in low-gravity environments
- Excessive switching leads to inefficient control usage

Introducing thrust constraints fundamentally alters the nature of the guidance problem:
- Instantaneous optimality no longer guarantees feasibility
- Closed-form solutions may not exist
- Trade-offs emerge between robustness, convergence rate, and fuel usage

This repository explicitly explores these effects within a unified guidance framework.

---

## Extended Guidance Framework
The thrust-constrained guidance strategy follows these key steps:

### Sliding Variable Construction
A sliding variable is defined using position and velocity errors to encode terminal precision landing objectives.

### Instantaneously Optimal Control
At each time step, a local cost function related to control effort (as a proxy for fuel consumption) is minimized instantaneously, preserving computational efficiency and real-time applicability.

### Thrust Constraint Enforcement
The control input is subject to:
- Upper and lower thrust magnitude limits
- Directional constraints arising from thrust vector orientation and heading dynamics

These nonlinear constraints introduce **non-convexity** into the instantaneous optimization problem.

### Constraint-Aware Sliding Enforcement
The resulting control law:
- Respects actuator limitations
- Maintains sliding-mode convergence properties
- Avoids excessive switching and unnecessary fuel expenditure

The final guidance strategy is **physically realizable, fuel-efficient, and robust**.

---

## Repository Structure```
├── main.m # Simulation entry point with thrust-constrained guidance```
├── Optimizer.m # Non-convex instantaneous optimization under thrust limits```
├── SlidingVariable.m # Sliding surface formulation```
├── HeadingErrorDynamics.m # Thrust direction and heading error dynamics```
├── VelocityProfile.m # Fuel-aware reference velocity design```
├── GetGravity.m # Low-gravity asteroid environment model```
├── utilities.m # Shared mathematical utilities```
├── plots.m # Trajectory, control, and fuel analysis```
└── README.md # Project documentation```
