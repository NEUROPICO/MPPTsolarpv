This repository contains a MATLAB implementation of a Maximum Power Point Tracking (MPPT) algorithm and its integration within a photovoltaic (PV) system simulated in Simulink. The project demonstrates how to optimize power output from a PV array using MPPT techniques and control components such as a DC-DC boost converter.

Files in the Repository
1. `MPPTalgorithm.m`
   This MATLAB script implements an MPPT algorithm to dynamically adjust the reference voltage (`Vref`) of a PV array. The algorithm tracks the maximum power point by observing changes in voltage (`dV`) and power (`dP`) to optimize system performance. Key features include:
   - Dynamic adjustment of reference voltage.
   - Boundary constraints for safe operation (`Vrefmax = 450`, `Vrefmin = 0`).
   - Persistent storage for previous voltage and power states.

2. `testPV.slx`  
   A Simulink model that simulates a complete PV system with:
   - A PV array block.
   - DC-DC boost converter controlled by the MPPT algorithm.
   - PWM generation to regulate the MOSFET switch.
   - Real-time performance monitoring of PV voltage, current, and power.

## How to Use

### 1. Prerequisites
- MATLAB (R2021b or later recommended).
- Simulink toolbox.
- Simscape Electrical toolbox for modeling the PV array and power electronics.

### 2. Running the MPPT Algorithm
- Open the `MPPTalgorithm.m` file in MATLAB.
- The script requires two inputs:
  - `V`: Voltage from the PV array.
  - `I`: Current from the PV array.
- The function outputs the optimized reference voltage (`Vref`) to regulate the system.

### 3. Running the Simulink Model
1. Open the `testPV.slx` file in Simulink.
2. Connect the `MPPTalgorithm.m` function as the controller for the boost converter.
3. Simulate the model:
   - Observe the performance of the PV system under varying irradiance and temperature.
   - Verify the output voltage regulation and power optimization.

## Features
- MPPT Algorithm: Implements a Perturb & Observe strategy to track the maximum power point efficiently.
- Simulink Integration: Demonstrates real-world PV system behavior with adjustable parameters.
- Dynamic Control: Uses a PI controller and PWM signal to regulate the boost converter.

## Future Improvements
- Extend the simulation to handle partial shading scenarios.
- Integrate a battery management system for energy storage.
- Experiment with alternative MPPT algorithms, such as Incremental Conductance or Artificial Neural Networks.

## References
- MATLAB documentation: [MATLAB & Simulink](https://www.mathworks.com/help/)
- Maximum Power Point Tracking (MPPT) principles.
- 
## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute it
