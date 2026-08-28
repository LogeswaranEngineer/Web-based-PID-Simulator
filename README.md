# 🚗 PID Cruise Control Lab

An interactive browser-based simulator for understanding **PID control through vehicle cruise control**.

Instead of learning PID only from equations, this project lets you **change Kp, Ki, and Kd in real time** and immediately observe how the vehicle responds.

> **Learn PID by experimenting with it.**

## 🌐 Live Demo

🚀 [**Open the PID Cruise Control Lab**](https://logeswaranengineer.github.io/Web-based-PID-Simulator/)

## 🎥 Demo

Watch the PID controller respond to different gains, target speeds, road disturbances, and actuator saturation.

## 🖥️ Simulator

The simulator displays:

* 🚗 Vehicle motion
* 🎯 Target speed
* 📈 Actual speed
* ⚠️ Speed error
* 💪 Net control force
* P / I / D force contribution
* Speed response over time
* PID force contribution over time
* Actuator saturation status

---

## 🎛️ Interactive Controls

### Controller Gains

The simulator provides real-time adjustment of:

| Parameter | Meaning           |
| --------- | ----------------- |
| `Kp`      | Proportional gain |
| `Ki`      | Integral gain     |
| `Kd`      | Derivative gain   |

You can change the gains while observing the vehicle response.

---

## 🔴 Proportional Control

The proportional term reacts to the **current error**.

```text
P = Kp × error
```

Try the **P only** preset and observe how the vehicle approaches the target.

---

## 🟡 Integral Control

The integral term accumulates error over time.

```text
I = Ki × ∫ error dt
```

Try the **PI** preset and compare it with P-only control, especially on an uphill road.

---

## 🔵 Derivative Control

The derivative term reacts to how quickly the error is changing.

```text
D = Kd × d(error)/dt
```

Try the **PD** preset and compare the response with P-only control.

---

## 🧠 Full PID

The complete controller combines all three terms:

```text
PID = P + I + D
```

```text
Error
   ↓
P ─┐
I ─┼──→ Control Force ──→ Vehicle
D ─┘
```

Try the **PID tuned** preset and observe how the three terms work together.

---

## ⛰️ Disturbance Experiments

The simulator includes:

* **Flat road**
* **Uphill**
* **Downhill**

Try P-only control on an uphill road, then compare it with PID control.

Observe how the controller responds to external disturbances.

---

## ⚠️ Actuator Saturation

The simulated actuator has a maximum available force.

When the requested control force exceeds this limit, the controller output is clamped.

```text
Requested force
      ↓
   [ PID ]
      ↓
Maximum actuator force
      ↓
 Actual force
```

The simulator displays an **Actuator saturated** indicator when saturation occurs.

---

## 🛑 Anti-Windup

The simulator includes an **anti-windup** option.

When the actuator is saturated, the integral term can continue accumulating error if it is not handled properly.

Try:

**Anti-windup ON**

and then:

**Anti-windup OFF**

Compare the resulting behavior.

---

## 📊 What You Can Observe

### Speed Response

The speed graph shows:

* Target speed
* Actual speed
* Rise toward target
* Overshoot
* Settling behavior
* Steady-state error

### PID Force Contribution

The simulator shows the contribution of:

* Proportional control
* Integral control
* Derivative control
* Total controller output

---

## 🧪 Suggested Experiments

### Experiment 1 — P Only

Select **P only**.

Observe:

* How quickly speed increases
* Whether the target is reached
* Steady-state error

### Experiment 2 — Add Integral

Select **PI**.

Compare it with P-only control.

**Question:** What changed when the integral term was introduced?

### Experiment 3 — Add Derivative

Select **PD**.

Compare it with P-only control.

**Question:** Does derivative control reduce overshoot or oscillation?

### Experiment 4 — Uphill

Set:

```text
Road → Uphill
```

Compare:

```text
P only
```

with:

```text
PID tuned
```

Observe how the controller compensates for the disturbance.

### Experiment 5 — Too Aggressive

Select **Too aggressive**.

Look for:

* Overshoot
* Saturation
* Oscillation
* Slow recovery

### Experiment 6 — Anti-Windup

Compare:

```text
Anti-windup ON
```

with:

```text
Anti-windup OFF
```

Observe the difference in controller behavior.

---

## ⚙️ Simulation Model

The simulator uses a simplified vehicle dynamic model:

```text
Fnet = Fcontroller - Fdrag - Frolling - Fslope
```

Then:

```text
acceleration = Fnet / mass
```

and:

```text
velocity = velocity + acceleration × dt
```

Simulation parameters:

```text
Vehicle mass      = 1100 kg
Drag coefficient  = 0.42
Rolling force     = 140 N
Maximum force     = 4000 N
Simulation dt     = 0.05 s
History           = 24 s
```

---

## 🚀 Running the Project

No ROS 2 installation or additional dependencies are required.

Simply open:

```text
index.html
```

in a modern web browser.

---

## 📚 What This Project Helps You Understand

* PID control
* Proportional control
* Integral control
* Derivative control
* Steady-state error
* Overshoot
* Oscillation
* Controller tuning
* Actuator saturation
* Integral windup
* Anti-windup
* Disturbance rejection
* Vehicle dynamics
* Feedback control

---

## 💡 Learning Philosophy

Instead of starting with:

> "Memorize the PID equation."

Start with:

> **Change something → observe the response → ask why → understand the equation.**

The simulator is designed around this approach.

---

## 🔮 Future Improvements

* [ ] Adjustable vehicle mass
* [ ] Adjustable drag
* [ ] Adjustable actuator limits
* [ ] Noise injection
* [ ] Sensor delay
* [ ] Low-pass filtering for derivative control
* [ ] Different vehicle models
* [ ] Automatic PID tuning
* [ ] Step-response metrics
* [ ] Rise-time calculation
* [ ] Settling-time calculation
* [ ] Overshoot percentage
* [ ] Steady-state error calculation
* [ ] Export simulation data as CSV
* [ ] Mobile-friendly improvements

---

## 👨‍💻 Author

**Logeswaran**

Built as a practical control-systems learning project.

The objective is simple:

> **Make control theory something you can experiment with, not just read about.**

---

## ⭐ If This Helps You

If you find this simulator useful for learning PID control, consider giving the repository a ⭐.
