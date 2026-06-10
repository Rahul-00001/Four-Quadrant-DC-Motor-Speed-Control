# Four-Quadrant DC Motor Speed Control using Cascaded PI Control

## Project Overview

This project presents the modeling, analysis, control design, and implementation of a DC motor drive system using MATLAB/Simulink.

The work began with mathematical modeling of a separately excited DC motor and frequency-domain controller design using loop-shaping techniques. Practical implementation challenges such as controller saturation were investigated and resolved through anti-windup compensation.

To improve dynamic performance, a cascaded speed-current control architecture was developed. Additional enhancements including current limiting, back-EMF feedforward compensation, current filtering, PWM-based voltage control, and dead-time implementation were incorporated.

The final system was extended from a one-quadrant drive to a four-quadrant H-bridge drive capable of regenerative braking and bidirectional operation.

---

## Key Results

* Settling Time Reduced: 5.37 s → 0.27 s
* Overshoot Reduced: 19.4 % → 1.55 %
* Anti-Windup Compensation Implemented
* Cascaded Speed-Current Control Architecture
* Four-Quadrant Operation Achieved
* Regenerative Braking Demonstrated

---

## Key Features

* Mathematical modeling of a separately excited DC motor
* Frequency-domain controller design using loop shaping
* PI controller implementation
* Anti-windup compensation
* Cascaded speed-current control architecture
* Current limiting and actuator protection
* Back-EMF feedforward compensation
* Current feedback filtering
* PWM-based armature voltage control
* One-quadrant DC motor drive implementation
* Four-quadrant H-bridge drive implementation
* Regenerative braking capability
* Bidirectional speed operation
* Disturbance rejection analysis
* Speed reference tracking validation

---

## Control Architecture

The final controller uses a cascaded speed-current control architecture. The outer speed loop generates the current reference, while the inner current loop provides fast torque regulation. Additional enhancements including current limiting, anti-windup compensation, back-EMF feedforward, PWM voltage control, and four-quadrant operation were incorporated into the final implementation.

<img width="672" height="225" alt="High-Level Cascaded Control Architecture" src="https://github.com/user-attachments/assets/0b570e7c-4f86-4e3d-9ada-d1615e94a796" />

---

## Performance Improvements

| Performance Metric         | Frequency-Domain Controller | PI Controller | Anti-Windup + Duty-Ratio | Final Cascaded Controller |
| -------------------------- | --------------------------- | ------------- | ------------------------ | ------------------------- |
| Peak Speed (rad/s)         | 358.1783                    | 358.2332      | 334.1434                 | 304.6646                  |
| Overshoot (%)              | 19.3928                     | 19.4111       | 11.3811                  | 1.5549                    |
| Steady-State Speed (rad/s) | 299.9821                    | 299.9980      | 300.0039                 | 299.9953                  |
| Steady-State Error (%)     | 0.005973                    | 0.000674      | 0.001309                 | 0.001583                  |
| Settling Time (s)          | 5.3661                      | 5.3701        | 3.2392                   | 0.2706                    |

The final controller achieved a significant reduction in settling time and overshoot while maintaining excellent steady-state accuracy.

---

## Validation Tests

The following tests were performed:

### Speed Reference Tracking

* 50 rad/s → 400 rad/s
* 400 rad/s → 50 rad/s

### Load Disturbance Rejection

* Positive load torque disturbance
* Reduced load torque condition

### Four-Quadrant Operation

* Regenerative braking
* Reverse motoring operation
* Speed reversal (+400 rad/s → -400 rad/s)

---

## Regenerative Braking

The four-quadrant implementation enables regenerative braking.

During a commanded speed reversal from +400 rad/s to -400 rad/s, the controller generates negative armature current, producing negative electromagnetic torque. The drive initially operates in Quadrant II (forward regenerative braking) before transitioning into Quadrant III (reverse motoring).

This demonstrates successful bidirectional current control and regenerative operation.

The figure below demonstrates regenerative braking and reverse motoring operation. The controller initially applies negative current to decelerate the motor (Quadrant II) before accelerating it in the reverse direction (Quadrant III).

<img width="2210" height="1262" alt="Speed_Test_FourQuad_2" src="https://github.com/user-attachments/assets/5e2cbae5-d134-4636-9f92-651657c228e1" />

---

## Tools and Technologies

* MATLAB
* Simulink
* Frequency-Domain Loop Shaping
* PI Control
* PWM Motor Drive Control

---

## Repository Structure

```text
Four-Quadrant-DC-Motor-Speed-Control
│
├── README.md
├── Project_Report.pdf
│
└── Simulink_Models
    ├── 01_First_Quadrant_NonPI.slx
    ├── 02_First_Quadrant_PI.slx
    ├── 03_First_Quadrant_Cascaded_Control.slx
    └── 04_Four_Quadrant_Final.slx
```

---

## Project Report

The complete technical report describing the modeling, controller design, implementation, validation, and four-quadrant extension is available in this repository.

📄 [Project Report](Project_Report.pdf)

---

## Author

Rahul Kumar Pandey

B.Tech Electrical Engineering

Areas of Interest:

* Control Systems
* Power Electronics
* Electric Drives
