# Numerical Simulation of Satellite Orbital Decay Under Atmospheric Drag

## Description

This project simulates the orbital motion of a satellite under the influence of Earth's gravitational force and atmospheric drag. The fourth-order Runge–Kutta (RK4) method is used to numerically solve the equations of motion in two dimensions. A simplified exponential model is used to represent atmospheric density.

## Objectives

* Simulate the two-dimensional orbital motion of a satellite under Earth's gravitational force, with and without atmospheric drag.
* Implement the RK4 method to solve the equations of motion.
* Investigate changes in satellite altitude over time.
* Analyze how atmospheric drag affects the rate of orbital decay.

## Mathematical Equations

### 1. Gravitational Acceleration

The gravitational acceleration acting on the satellite is

$$
\vec{a}_g = -\frac{\mu}{r^3}\vec{r}
$$

where:

* \(\mu\) is Earth's gravitational parameter.
* \(\vec{r}\) is the satellite's position vector.
* \(r\) is the magnitude of the position vector.

### 2. Atmospheric Density

Atmospheric density is modeled using a simplified exponential model:

$$
\rho(h) = \rho_0 e^{-\frac{h-h_{\mathrm{ref}}}{H}}
$$

where:

* \(\rho_0\) is the atmospheric density at the reference altitude.
* \(h\) is the satellite's altitude.
* \(h_{\mathrm{ref}}\) is the reference altitude.
* \(H\) is the atmospheric scale height.

### 3. Atmospheric Drag

#### A. Drag Force

The atmospheric drag force is

$$
\vec{F}_D = -\frac{1}{2}C_D A\rho v^2\hat{v}
$$

where:

* \(C_D\) is the drag coefficient.
* \(A\) is the satellite's cross-sectional area.
* \(\rho\) is the atmospheric density.
* \(v\) is the satellite's speed.
* \(\hat{v}\) is the unit vector in the direction of velocity.

The negative sign indicates that drag acts opposite to the satellite's velocity.

#### B. Drag Acceleration

The drag acceleration is obtained by dividing the drag force by the satellite's mass:

$$
\vec{a}_D = -\frac{1}{2}\frac{C_D A\rho}{m}v^2\hat{v}
$$

where \(m\) is the satellite's mass.

### 4. Equations of Motion

#### A. Total Acceleration

The total acceleration is the sum of gravitational acceleration and atmospheric drag acceleration:

$$
\vec{a} = \vec{a}_g + \vec{a}_D
$$

For the simulation without atmospheric drag, only gravitational acceleration is considered.

#### B. Initial Orbit Radius

The initial orbital radius is

$$
r_0 = R_E + h_{\mathrm{ref}}
$$

where \(R_E\) is Earth's radius.

#### C. Initial Orbital Velocity

Assuming an initially circular orbit, the initial orbital speed is

$$
v_0 = \sqrt{\frac{\mu}{r_0}}
$$

#### D. Altitude as a Function of Time

The satellite's altitude at time \(t\) is calculated from its position:

$$
h(t) = \sqrt{x(t)^2+y(t)^2}-R_E
$$

or equivalently,

$$
h(t) = r(t)-R_E
$$

where \(x(t)\) and \(y(t)\) are the satellite's position coordinates.

## Simulation Parameters

| Parameter                       | Symbol               | Value                                        |
| ------------------------------- | -------------------- | -------------------------------------------- |
| Earth's gravitational parameter | \(\mu\)              | \(3.9860044\times10^{14}\ \mathrm{m^3/s^2}\) |
| Earth's radius                  | \(R_E\)              | \(6.371\times10^6\ \mathrm{m}\)              |
| Drag coefficient                | \(C_D\)              | 2.2                                          |
| Satellite mass                  | \(m\)                | 1000 kg                                      |
| Satellite cross-sectional area  | \(A\)                | 10 m²                                        |
| Reference atmospheric density   | \(\rho_0\)           | \(5\times10^{-13}\ \mathrm{kg/m^3}\)         |
| Initial altitude                | \(h_{\mathrm{ref}}\) | \(4\times10^5\ \mathrm{m}\) (400 km)         |
| Atmospheric scale height        | \(H\)                | \(5\times10^4\ \mathrm{m}\) (50 km)          |
| Simulation duration             | \(t\)                | 86400 s (24 hours)                           |

## Results

![image alt](https://github.com/Zakwan-Star/Numerical-Simulation-of-Satellite-Orbital-Decay-Under-Atmospheric-Drag/blob/37849f023c3651df46e6825783be810dd857e57c/Decaying%20Altitude.png)

### Analysis

The two orbital trajectories almost coincide, indicating that the change caused by atmospheric drag is small compared with the overall size of the orbit. However, the altitude graph shows a clearer difference between the two conditions. Without drag, the satellite maintains a nearly constant altitude of approximately 400 km, while the drag case shows periodic altitude variations with a decreasing trend over 24 hours.

This occurs because atmospheric drag opposes the satellite's motion and removes orbital energy, causing the orbit to decay. Although atmospheric density at this altitude is very low, its effect accumulates over time and gradually changes the satellite's orbit.

## References

Carroll, B. W., & Ostlie, D. A. (2017). *An introduction to modern astrophysics* (2nd ed.). Cambridge University Press.

Curtis, H. D. (2020). *Orbital mechanics for engineering students* (4th ed.). Butterworth-Heinemann.

Newman, M. E. J. (2013). *Computational physics*. CreateSpace Independent Publishing Platform.

Wakker, K. F. (2015). *Fundamentals of astrodynamics*. Delft University of Technology.
