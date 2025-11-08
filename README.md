# DC Motor Dynamic Simulation – MATLAB/Simulink

This project models the dynamic behavior of a **separately excited DC motor** using its electrical and mechanical equations. The model simulates how input voltage, armature current, motor torque, load torque, and speed interact over time.

## Model Overview

The simulation contains two primary subsystems:

1. **Electrical Armature Dynamics**
   \[
   V_a = L_a \frac{dI_a}{dt} + R_a I_a + E_b
   \]

2. **Mechanical Rotor Dynamics**
   \[
   T_m = J \frac{d\omega}{dt} + B\omega + T_L
   \]

### Key Relationships
- **Motor torque:**  
  \[
  T_m = K_t I_a
  \]
- **Back EMF:**  
  \[
  E_b = K_e \omega
  \]

### Signal Flow
1. Input voltage \( V_a \) drives the armature.
2. The armature current \( I_a \) is computed considering resistance and inductance.
3. The current generates torque using the motor constant \( K_t \).
4. Load torque \( T_L \) is subtracted to get net torque.
5. Net torque determines speed \( \omega \) via inertia \( J \) and friction \( B \).
6. The resulting speed generates back EMF \( K_e \omega \), forming feedback.

## Files
| File | Description |
|------|-------------|
| `motor_model.slx` | Simulink model |
| `parameters.m` | Motor constants and run configuration |
| `images/` (optional) | Simulation plots or block diagram images |

## How to Run
1. Open MATLAB.
2. Run:
   ```matlab
   parameters
