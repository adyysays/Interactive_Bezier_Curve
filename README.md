# Interactive Bézier Rope Simulation

An interactive real-time simulation of a **cubic Bézier curve behaving like a springy rope**, built from scratch using **HTML Canvas and JavaScript**.

This project demonstrates mathematical modeling, real-time rendering, and physics-based animation without using any external libraries.

---

## 🎯 Objective

To implement an interactive cubic Bézier curve that:
- Responds smoothly to user input (mouse / touch)
- Visualizes tangents along the curve
- Behaves like a rope using spring-damping physics

---

## 🧮 Bézier Curve Mathematics

The cubic Bézier curve is defined using four control points:

\[
B(t) = (1-t)^3 P_0 + 3(1-t)^2 t P_1 + 3(1-t)t^2 P_2 + t^3 P_3
\]

- \( P_0 \) and \( P_3 \) are **fixed endpoints**
- \( P_1 \) and \( P_2 \) are **dynamic control points**

The curve is sampled in small increments of `t = 0.01` for smooth rendering.

---

## ➰ Tangent Computation

Tangents are computed using the derivative of the Bézier equation:

\[
B'(t) = 3(1-t)^2 (P_1 - P_0) + 6(1-t)t (P_2 - P_1) + 3t^2 (P_3 - P_2)
\]

- Tangents are normalized
- Short tangent lines are drawn at regular intervals along the curve

---

## ⚙️ Physics Model (Spring-Damping)

Each dynamic control point follows a spring-damping system:

\[
a = -k(x - x_{target}) - d \cdot v
\]

Where:
- `k` = stiffness constant
- `d` = damping factor
- `v` = velocity

Integration is done using **semi-implicit Euler integration** for improved numerical stability.

This produces smooth, rope-like motion.

---

## 🖱️ Interaction

- Move mouse / touch → influences rope motion
- Click & drag **P1** or **P2** → manually control rope
- UI sliders:
  - Spring stiffness
  - Damping
  - Tangent density

---

## 🚀 How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/interactive-bezier-rope.git

