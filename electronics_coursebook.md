# Electronics Coursebook for Computer Science Students

> **Who this is for:** A CS student with MPC background, catching up from Topic 1 through Topic 4 (RLC circuits and resonance) and beyond. Every section is built to be scannable for quick review and deep enough to actually learn from.

---

## Table of Contents

- [Chapter 1 — Basic Concepts: Current, Voltage, Power, Units](#chapter-1)
  - [Electric Charge and Current](#electric-charge-and-current)
  - [Voltage](#voltage)
  - [Power and Energy](#power-and-energy)
  - [SI Units Table](#si-units-table)
  - [DC vs. AC](#dc-vs-ac)
  - [Measuring Instruments](#measuring-instruments)
  - [Ohm's Law](#ohms-law)
- [Chapter 2 — DC Circuits: Kirchhoff's Laws, Capacitors, Inductors, Resistors](#chapter-2)
  - [Resistors in Series and Parallel](#resistors-in-series-and-parallel)
  - [Kirchhoff's Current Law (KCL)](#kirchhoffs-current-law)
  - [Kirchhoff's Voltage Law (KVL)](#kirchhoffs-voltage-law)
  - [Worked Two-Loop Example](#worked-two-loop-example)
  - [Capacitor in DC](#capacitor-in-dc)
  - [Inductor in DC](#inductor-in-dc)
  - [Resistor in DC](#resistor-in-dc)
- [Chapter 3 — AC Circuits: Superposition, Mesh Method, Impedance, Symbolic Method](#chapter-3)
  - [Superposition Principle](#superposition-principle)
  - [Mesh Current Analysis](#mesh-current-analysis)
  - [AC Signals](#ac-signals)
  - [RMS and Average Values](#rms-and-average-values)
  - [Phasors](#phasors)
  - [Symbolic / Complex Method](#symbolic--complex-method)
  - [Ohm's Law in AC](#ohms-law-in-ac)
- [Chapter 4 — RLC Circuits: Frequency Response, Resonance, AC Power](#chapter-4)
  - [Frequency Response](#frequency-response)
  - [Filter Types](#filter-types)
  - [Bode Plots](#bode-plots)
  - [Series RLC Resonance](#series-rlc-resonance)
  - [Parallel RLC Resonance](#parallel-rlc-resonance)
  - [Q-Factor and Bandwidth](#q-factor-and-bandwidth)
  - [Voltage and Current Resonance](#voltage-and-current-resonance)
  - [AC Power](#ac-power)
- [Chapter 5 — Semiconductors and Diodes](#chapter-5)
  - [Band Model](#band-model)
  - [Intrinsic Semiconductors](#intrinsic-semiconductors)
  - [Doping](#doping)
  - [The P-N Junction](#the-p-n-junction)
  - [Diode I–V Characteristic](#diode-iv-characteristic)
  - [Diode Circuit Models](#diode-circuit-models)
  - [Diode Applications](#diode-applications)
- [Chapter 6 — Transistors: Amplifiers, Switches, Multivibrators](#chapter-6)
  - [BJT Structure and Operation](#bjt-structure-and-operation)
  - [BJT Operating Modes](#bjt-operating-modes)
  - [Common-Emitter Amplifier](#common-emitter-amplifier)
  - [MOSFET](#mosfet)
  - [Transistor as Digital Switch](#transistor-as-digital-switch)
  - [Multivibrators](#multivibrators)
  - [Binary Counter](#binary-counter)
- [Chapter 7 — Operational Amplifiers and Feedback](#chapter-7)
  - [Ideal Op-Amp Properties](#ideal-op-amp-properties)
  - [Real Op-Amp Limitations](#real-op-amp-limitations)
  - [Negative Feedback and the Golden Rules](#negative-feedback-and-the-golden-rules)
  - [Op-Amp Circuits](#op-amp-circuits)
- [Chapter 8 — Digital Logic: Gates, Flip-Flops, Registers, Counters, Adders](#chapter-8)
  - [Boolean Algebra and Gates](#boolean-algebra-and-gates)
  - [De Morgan's Theorems](#de-morgans-theorems)
  - [NAND Universality](#nand-universality)
  - [Flip-Flops](#flip-flops)
  - [Registers](#registers)
  - [Counters](#counters)
  - [Adders](#adders)
- [Section A — Calculus in Electronics: A Compact Guide](#section-a)
- [Section B — Falstad Quick-Start Reference](#section-b)
- [Section C — Self-Assessment Questions](#section-c)
- [Formula Index](#formula-index)

---

<a name="chapter-1"></a>
## Chapter 1 — Basic Concepts: Current, Voltage, Power, Units

### The Real-World Hook

Every time you charge your phone, a current of roughly 2–3 amperes flows from the charger into the battery. But what *is* that current, physically? And why does your charger specify 5 V, 9 V, or 20 V? This chapter gives you the language to answer those questions precisely.

---

<a name="electric-charge-and-current"></a>
### Electric Charge and Current

**Electric charge** is a fundamental property of matter. The elementary charge — the charge carried by a single proton or electron — is:

$$
e = 1.602 \times 10^{-19} \text{ C}
$$

The **Coulomb (C)** is the SI unit of charge. One coulomb is approximately $6.24 \times 10^{18}$ elementary charges — an enormous number.

**Electric current** is defined as the rate at which charge flows past a cross-section of a conductor:

$$
i(t) = \frac{dq}{dt}
$$

The derivative here measures how many coulombs pass per second. If $6.24 \times 10^{18}$ electrons drift past a point in a wire every second, that is exactly 1 ampere.

#### Conventional vs. Electron Flow

Here is something that trips up almost every student:

- **Electron flow**: electrons (negative charge) move from the negative terminal of a battery toward the positive terminal.
- **Conventional current**: by historical convention (thanks to Benjamin Franklin's educated guess in the 1700s), we define current direction as flowing from + to −, i.e., opposite to electron motion.

> ⚠️ Warning: In all circuit analysis — KVL, KCL, Ohm's Law — you must use **conventional current direction** consistently. Mixing conventions mid-calculation is a guaranteed error.

Why do we keep this seemingly backwards convention? Because it was established before electrons were discovered (1897), and changing it globally would break hundreds of years of engineering notation. In practice, it makes no difference to circuit calculations — we just pick one convention and stick with it.

---

<a name="voltage"></a>
### Voltage

**Voltage** (also called *electric potential difference*) is the energy required to move one coulomb of charge between two points:

$$
V_{AB} = \frac{W_{AB}}{Q}
$$

where $W_{AB}$ is the work done (in joules) moving charge $Q$ (in coulombs) from point B to point A.

**The water pressure analogy:** Think of a circuit as a plumbing system. Voltage is like pressure difference — it's what *pushes* current through the pipe (wire). A battery is like a pump that maintains a constant pressure difference between its terminals. A higher voltage means more "pressure" pushing charges through the circuit.

> 💡 Insight: Voltage is always measured *between two points*. Saying "the voltage at point A" only makes sense if you've also defined a reference point (usually called "ground" or 0 V). In the water analogy: water height only means something relative to some ground level.

The unit of voltage is the **Volt (V)**. 1 V = 1 J/C.

---

<a name="power-and-energy"></a>
### Power and Energy

**Power** is the rate at which energy is transferred or consumed:

$$
P = \frac{dW}{dt}
$$

In electrical terms, combining $P = dW/dt$ with $V = W/Q$ and $i = dq/dt$:

$$
P = V \cdot I
$$

This is one of the most important equations in electronics. The units work out: $[V] \cdot [A] = [J/C] \cdot [C/s] = [J/s] = [W]$.

**Energy** is power multiplied by time. For constant power:

$$
W = P \cdot t = V \cdot I \cdot t
$$

> 💡 Insight: Your electricity bill is measured in kilowatt-hours (kWh). 1 kWh = $3.6 \times 10^6$ J. A 60 W light bulb running for 1 hour consumes 0.06 kWh.

---

<a name="si-units-table"></a>
### SI Units Table

| Symbol | Name | Unit | Unit Symbol | Physical Role |
|--------|------|------|-------------|---------------|
| $Q$ | Charge | Coulomb | C | Amount of electric charge |
| $I$ | Current | Ampere | A | Rate of charge flow (C/s) |
| $V$ | Voltage / Potential difference | Volt | V | Energy per unit charge (J/C) |
| $R$ | Resistance | Ohm | Ω | Opposition to current flow |
| $C$ | Capacitance | Farad | F | Charge stored per volt (C/V) |
| $L$ | Inductance | Henry | H | Voltage induced per A/s of change |
| $P$ | Power | Watt | W | Energy per second (J/s) |
| $W$ | Energy | Joule | J | Capacity to do work |
| $f$ | Frequency | Hertz | Hz | Cycles per second (1/s) |
| $\omega$ | Angular frequency | Radian/second | rad/s | $\omega = 2\pi f$ |

**Useful prefixes:**

| Prefix | Symbol | Multiplier |
|--------|--------|------------|
| Mega | M | $10^6$ |
| Kilo | k | $10^3$ |
| Milli | m | $10^{-3}$ |
| Micro | μ | $10^{-6}$ |
| Nano | n | $10^{-9}$ |
| Pico | p | $10^{-12}$ |

---

<a name="dc-vs-ac"></a>
### Types of Current: DC vs. AC

**Direct Current (DC):** Current flows in one direction only, and typically at a constant magnitude. A battery produces DC. Your USB charger converts AC from the wall to DC for your phone.

$$
v(t) = V_0 \quad \text{(constant)}
$$

**Alternating Current (AC):** Current changes direction periodically. The mains electricity in your home is AC at 50 Hz (Europe/Poland) or 60 Hz (USA).

$$
v(t) = V_m \sin(\omega t + \phi)
$$

> 💡 Insight: The 50 Hz hum you sometimes hear from audio equipment or transformers is the sound of the AC mains frequency making metal components (transformer cores, speaker cones) vibrate at 50 times per second. It is a purely physical consequence of the frequency of alternating current.

**Why do we use AC for power transmission?** AC voltages can be stepped up and down easily using transformers (Chapter 3 physics). High voltage = low current = low resistive losses in cables. DC is better for electronics; AC is better for long-distance transmission. Modern high-voltage DC (HVDC) lines are now changing this, but AC still dominates.

---

<a name="measuring-instruments"></a>
### Measuring Instruments

#### Voltmeter

A voltmeter measures the **voltage difference between two nodes**. It must be connected **in parallel** with the component being measured.

**Why parallel?** A voltmeter must not disturb the circuit. To avoid drawing significant current, its internal resistance must be very high (ideally infinite). When you place a very high resistance in parallel with a component, almost no current flows through the meter — the original circuit is barely affected.

> ⚠️ Warning: Never connect a voltmeter in series. A near-infinite resistance in series would block almost all current and break the circuit's normal operation. Your reading would be the full supply voltage, which tells you nothing useful about the component.

#### Ammeter

An ammeter measures the **current flowing through a branch**. It must be connected **in series** in that branch.

**Why series?** The meter must be in the path of the current you want to measure. Its internal resistance must be very low (ideally zero) so that inserting it doesn't significantly change the resistance (and therefore current) in the branch.

> ⚠️ Warning: Never connect an ammeter directly across a voltage source (in parallel). The near-zero resistance would create a short circuit, drawing enormous current. In real labs this blows fuses or destroys the meter.

---

<a name="ohms-law"></a>
### Ohm's Law

**Resistance** is defined as the ratio of voltage across a component to the current flowing through it:

$$
R = \frac{V}{I} \quad \Longrightarrow \quad V = IR
$$

This is Ohm's Law. It holds for **ohmic (linear) resistors** — materials where resistance is constant regardless of voltage or current. The I–V graph for a resistor is a straight line through the origin, with slope $1/R$.

**Derivation from physics:** In a conductor, free electrons drift in response to an electric field. Their average drift velocity is proportional to the field (at the microscopic level, collisions with the lattice create a proportionality constant). This macroscopic proportionality between field and current density gives rise to Ohm's Law.

**Parameter intuition:** ↑R → ↓I (for fixed V). ↑V → ↑I (for fixed R).

> 💡 Insight: Not everything obeys Ohm's Law. Diodes (Chapter 5), LEDs, and thermistors are all non-ohmic — their I–V graphs are curves, not straight lines. The concept of resistance still applies, but it changes with operating point.

> 💻 CS Link: ADC (Analog-to-Digital Converters) inside microcontrollers measure voltages. When your Arduino reads a temperature sensor, it's measuring a voltage produced by a resistor divider. Understanding Ohm's Law is the foundation for understanding every sensor interface in embedded systems.

---

### Quick Recap

- **Current** is charge flow per second ($i = dq/dt$). Conventional current flows from + to −, opposite to electrons.
- **Voltage** is energy per unit charge — it's the "pressure" that drives current. Always measured between two points.
- **Power** = Voltage × Current ($P = VI$). Energy = Power × Time ($W = Pt$).
- **Voltmeter** goes in parallel (high internal R); **ammeter** goes in series (low internal R). Getting this wrong can destroy equipment.
- **Ohm's Law** ($V = IR$) holds for linear resistors; the I–V graph is a straight line.

### Falstad Lab Prep

1. Open Falstad. Place a DC voltage source (battery), a resistor (try 1 kΩ), and connect them in a loop.
2. Add a voltmeter across the resistor (in parallel). Add an ammeter in series in the loop.
3. Read both values. Verify $V = IR$ with your chosen values.
4. Now try connecting the voltmeter in series — observe what happens to the readings.
5. Try connecting the ammeter in parallel — observe (carefully in simulation) the short-circuit current.

### Exam Traps

1. **Conventional vs. electron current:** If a question says "current flows from A to B," it means conventional current. Don't reverse it.
2. **Voltage is relative:** "Voltage at node X" = 0 V unless a reference is defined. Always check what ground is.
3. **Ammeter in parallel / voltmeter in series:** This is a very common exam trick. Know *why* each connection is wrong.
4. **Units of power:** Watts = Volts × Amperes. Don't confuse energy (J) with power (W).

---

<a name="chapter-2"></a>
## Chapter 2 — DC Circuits: Kirchhoff's Laws, Capacitors, Inductors, Resistors in DC

### The Real-World Hook

Consider the wiring in a car: the battery supplies 12 V, but dozens of devices — headlights, radio, windscreen wipers — all run simultaneously. How does the current split? Why doesn't running the headlights lower the voltage to the radio? The answer is Kirchhoff's Laws, and they govern every circuit you will ever analyse.

---

<a name="resistors-in-series-and-parallel"></a>
### Resistors in Series and Parallel

#### Series

When resistors are placed end-to-end (the same current flows through all of them), the total resistance is simply the sum:

**Derivation:** By KVL (next section), the total voltage across the chain equals the sum of individual voltages:

$$
V = V_1 + V_2 + \ldots + V_n = IR_1 + IR_2 + \ldots + IR_n = I(R_1 + R_2 + \ldots + R_n)
$$

$$
\boxed{R_{series} = R_1 + R_2 + \cdots + R_n}
$$

Parameter intuition: Adding more resistors in series **always increases** total resistance.

#### Parallel

When resistors share the same two nodes (the same voltage across all of them), the total conductance adds:

**Derivation:** By KCL, total current = sum of branch currents:

$$
I = I_1 + I_2 + \ldots = \frac{V}{R_1} + \frac{V}{R_2} + \ldots = V\left(\frac{1}{R_1} + \frac{1}{R_2} + \ldots\right)
$$

$$
\frac{1}{R_{parallel}} = \frac{1}{R_1} + \frac{1}{R_2} + \cdots + \frac{1}{R_n}
$$

For two resistors specifically:

$$
R_{parallel} = \frac{R_1 R_2}{R_1 + R_2}
$$

Parameter intuition: Adding more resistors in parallel **always decreases** total resistance (more paths for current = less total opposition).

> 💡 Insight: Parallel resistance is always less than the smallest individual resistor. If you see a parallel combination giving a result larger than any of the individual resistors, you've made an arithmetic error.

---

<a name="kirchhoffs-current-law"></a>
### Kirchhoff's Current Law (KCL)

**Physical basis:** Conservation of charge. Charge cannot accumulate at a node (a junction point) in steady state — whatever flows in must flow out.

**Statement:** The algebraic sum of all currents entering a node is zero:

$$
\sum_{k} i_k = 0 \quad \text{(at any node)}
$$

**Convention:** Currents entering the node are positive; currents leaving are negative (or vice versa — pick one convention per problem and stick to it).

**Example:** At a node with three branches: $I_1 + I_2 - I_3 = 0$, meaning $I_3 = I_1 + I_2$. The current leaving equals the sum of currents arriving. This is exactly like water flowing: what enters a pipe junction must exit through other pipes.

---

<a name="kirchhoffs-voltage-law"></a>
### Kirchhoff's Voltage Law (KVL)

**Physical basis:** Conservation of energy. If you walk around a closed loop in a circuit and return to your starting point, your net change in potential energy must be zero.

**Statement:** The algebraic sum of all voltages around any closed loop is zero:

$$
\sum_{k} v_k = 0 \quad \text{(around any closed loop)}
$$

**Convention:** Choose a direction (clockwise or counterclockwise). Voltage rises (when you go through a source from − to +, or through a resistor against the current) are positive; voltage drops (source + to −, resistor in current direction) are negative.

> ⚠️ Warning: KVL requires you to be consistent about sign convention throughout the whole problem. Mixing sign conventions mid-loop is the single most common cause of wrong answers in circuit analysis.

---

<a name="worked-two-loop-example"></a>
### Worked Two-Loop Example

**Circuit:** Two voltage sources and three resistors in a two-loop network.

- Loop 1: $V_{s1} = 10$ V, $R_1 = 2\,\Omega$, $R_2 = 4\,\Omega$ (shared branch)
- Loop 2: $V_{s2} = 6$ V, $R_2 = 4\,\Omega$ (shared), $R_3 = 3\,\Omega$
- $I_1$ flows clockwise in Loop 1; $I_2$ flows clockwise in Loop 2

**Apply KVL to Loop 1** (clockwise, starting from left):

$$
-V_{s1} + I_1 R_1 + (I_1 - I_2)R_2 = 0
$$

$$
-10 + 2I_1 + 4(I_1 - I_2) = 0
$$

$$
6I_1 - 4I_2 = 10 \quad \cdots (1)
$$

**Apply KVL to Loop 2** (clockwise):

$$
-V_{s2} + (I_2 - I_1)R_2 + I_2 R_3 = 0
$$

$$
-6 + 4(I_2 - I_1) + 3I_2 = 0
$$

$$
-4I_1 + 7I_2 = 6 \quad \cdots (2)
$$

**Solve the system.** From (1): $I_1 = \frac{10 + 4I_2}{6}$. Substitute into (2):

$$
-4\cdot\frac{10 + 4I_2}{6} + 7I_2 = 6
$$

$$
\frac{-40 - 16I_2}{6} + 7I_2 = 6
$$

$$
-40 - 16I_2 + 42I_2 = 36
$$

$$
26I_2 = 76 \quad \Rightarrow \quad I_2 = \frac{76}{26} \approx 2.92\,\text{A}
$$

$$
I_1 = \frac{10 + 4(2.92)}{6} = \frac{10 + 11.69}{6} \approx 3.61\,\text{A}
$$

The current in the shared branch $R_2$ is $I_1 - I_2 \approx 0.69\,\text{A}$.

---

<a name="capacitor-in-dc"></a>
### Capacitor in DC

**Physical picture:** A capacitor is two conducting plates separated by an insulator (dielectric). When connected to a voltage source, charge builds up on the plates — positive on one, negative on the other — creating an electric field in the gap.

**Fundamental relation:**

$$
Q = CV
$$

where $C$ is capacitance in Farads, $V$ is voltage across the capacitor, and $Q$ is charge stored.

**Capacitor in DC steady state:** Once fully charged to the supply voltage $V_s$, current stops flowing (no charge can cross the insulating gap). A capacitor **blocks DC in steady state**.

**Charging transient:** When you first connect a discharged capacitor in series with a resistor to a DC source, current flows and the capacitor voltage rises exponentially:

$$
v_C(t) = V_s\left(1 - e^{-t/\tau}\right)
$$

where the **time constant** is:

$$
\tau = RC
$$

**Geometric interpretation of $\tau$:** At $t = \tau$, the capacitor has charged to $1 - e^{-1} \approx 63.2\%$ of the final voltage. At $t = 5\tau$, it is considered "fully charged" (99.3%). The time constant is the time it would take to reach full charge *if charging continued at its initial rate*.

**Discharging:** If a charged capacitor discharges through $R$:

$$
v_C(t) = V_0 e^{-t/\tau}
$$

**Energy stored in a capacitor:**

$$
W_C = \frac{1}{2}CV^2 = \frac{Q^2}{2C}
$$

Parameter intuition: ↑C → longer $\tau$ (slower charge/discharge). ↑R → longer $\tau$.

> 💻 CS Link: RC circuits are the basis of debounce filters in button inputs. When you press a physical button, it "bounces" (makes and breaks contact) many times in a few milliseconds. An RC filter with $\tau$ around 10 ms smooths this out before the microcontroller reads the input. They also form simple low-pass audio filters.

---

<a name="inductor-in-dc"></a>
### Inductor in DC

**Physical picture:** An inductor is a coil of wire. Current through it creates a magnetic field. By Faraday's law, if that magnetic field changes, it induces a voltage that opposes the change (Lenz's Law). An inductor therefore resists *changes* in current.

**Fundamental relation:**

$$
v_L = L\frac{di}{dt}
$$

**Geometric interpretation:** The derivative $di/dt$ is the slope of the current vs. time graph. A steep slope (rapidly changing current) produces a large inductor voltage. A constant current produces zero voltage — so in DC steady state, an inductor is just a wire (zero voltage, allows current freely).

**DC transient:** When you first apply DC through an RL circuit, current rises exponentially with time constant $\tau = L/R$.

**Energy stored in an inductor:**

$$
W_L = \frac{1}{2}LI^2
$$

This energy is stored in the magnetic field.

> ⚠️ Warning: Never suddenly open-circuit an inductor carrying current. The energy $\frac{1}{2}LI^2$ must go somewhere — it produces a large voltage spike (potentially thousands of volts) as $di/dt$ becomes very large. This is how flyback converters work, and also how inductive loads can destroy transistors if not properly protected.

Parameter intuition: ↑L → slower current change (more "inertia"). ↑R → faster decay (more energy dissipated per second).

---

<a name="resistor-in-dc"></a>
### Resistor in DC

A resistor is purely **dissipative** — it converts electrical energy to heat immediately, with no storage. There is no transient: voltage and current are in proportion at all times via Ohm's Law.

**Energy dissipated:**

$$
W = I^2 R t = \frac{V^2}{R} t = VIt
$$

---

### Quick Recap

- **Series resistors** add directly; **parallel resistors** add as reciprocals. Parallel combination is always less than the smallest.
- **KCL** (current law): currents into a node sum to zero — charge conservation.
- **KVL** (voltage law): voltages around a loop sum to zero — energy conservation.
- **Capacitor in DC**: charges exponentially with $\tau = RC$, then blocks current. Stores energy as $\frac{1}{2}CV^2$.
- **Inductor in DC**: opposes current change with $v_L = L\,di/dt$. Stores energy as $\frac{1}{2}LI^2$. Never open-circuit a live inductor.

### Falstad Lab Prep

1. Build a series RC circuit: 9 V source, 10 kΩ resistor, 100 μF capacitor.
2. Use a switch to connect/disconnect. Observe the capacitor voltage rising toward 9 V.
3. Measure the time constant: how long until voltage reaches ~5.7 V (~63% of 9 V)? Verify against $\tau = RC = 10000 \times 100\times10^{-6} = 1$ second.
4. Disconnect the source and let the capacitor discharge through the resistor. Observe exponential decay.

### Exam Traps

1. **Forgetting the $e^{-t/\tau}$ form:** The charge and discharge equations look different — always check which one you need and whether the capacitor starts from zero or from $V_0$.
2. **KVL sign convention:** Pick a loop direction, label voltage polarities on each element, and be consistent. Every sign error here leads to wrong currents.
3. **Inductor in steady state DC:** In steady state, $di/dt = 0$, so $v_L = 0$ — the inductor behaves like a short circuit (a wire). Students often forget this and treat it as an open circuit.
4. **Parallel resistance can't exceed the smallest resistor:** If your calculated $R_{parallel}$ is larger than any individual resistor, recheck your arithmetic.

---

<a name="chapter-3"></a>
## Chapter 3 — AC Circuits: Superposition, Mesh Method, Impedance, Symbolic Method

### The Real-World Hook

Your home has one AC source (the mains) feeding many devices simultaneously. But an RF engineer designing a radio front-end might have a signal source, a noise source, and an interference source all entering the circuit at once. How do you analyse a circuit with multiple independent sources? The superposition principle is the answer — and it's the conceptual foundation for everything from audio mixing boards to wireless communications.

---

<a name="superposition-principle"></a>
### Superposition Principle

**Statement:** In a **linear** circuit with multiple independent sources, the response (voltage or current) at any point due to all sources acting simultaneously equals the **sum** of the responses due to each source acting alone.

**Procedure:**
1. For each independent source, deactivate all others:
   - Voltage source → replace with a **short circuit** (wire, 0 Ω)
   - Current source → replace with an **open circuit** (gap, ∞ Ω)
2. Analyse the simplified circuit (with only one source active) using Ohm's Law and KVL/KCL.
3. Sum the individual results algebraically.

> ⚠️ Warning: Superposition applies only to **voltage and current** responses, not to power. Power is $P = I^2 R$, which is nonlinear in $I$. You cannot add powers from individual sources to get total power.

**Worked Example:** Two voltage sources $V_1 = 10$ V and $V_2 = 6$ V, resistors $R_1 = 2\,\Omega$, $R_2 = 3\,\Omega$, $R_3 = 6\,\Omega$, in a T-network.

- **Step 1:** Deactivate $V_2$ (replace with wire). Solve for voltage across $R_3$ due to $V_1$ alone: call it $V_{R3}^{(1)}$.
- **Step 2:** Deactivate $V_1$ (replace with wire). Solve for voltage across $R_3$ due to $V_2$ alone: call it $V_{R3}^{(2)}$.
- **Step 3:** Total: $V_{R3} = V_{R3}^{(1)} + V_{R3}^{(2)}$.

The specific arithmetic depends on the topology; the principle is always these three steps.

---

<a name="mesh-current-analysis"></a>
### Mesh Current Analysis

**What it is:** A systematic method to write KVL equations for planar circuits by assigning one imaginary current per mesh (a loop with no smaller loops inside it).

**Procedure:**
1. Identify all meshes. Assign a mesh current to each (e.g., $I_1, I_2, \ldots$) — typically all clockwise for consistency.
2. For each mesh, write a KVL equation. In shared branches between mesh $m$ and mesh $n$, the current is $(I_m - I_n)$.
3. Solve the system of linear equations.

**Example (2-mesh circuit):**

Mesh 1: $V_s - R_1 I_1 - R_2(I_1 - I_2) = 0$

Mesh 2: $-R_2(I_2 - I_1) - R_3 I_2 = 0$

Rearranging:

$$
(R_1 + R_2)I_1 - R_2 I_2 = V_s
$$

$$
-R_2 I_1 + (R_2 + R_3)I_2 = 0
$$

This is a $2\times2$ linear system, solved by substitution or Cramer's rule.

> 💡 Insight: Mesh analysis is especially efficient for circuits with few meshes but many nodes. Node voltage analysis (not covered here) is the dual method — choose based on circuit topology.

---

<a name="ac-signals"></a>
### AC Signals

A sinusoidal AC voltage source produces:

$$
v(t) = V_m \sin(\omega t + \phi)
$$

| Symbol | Name | Definition |
|--------|------|------------|
| $V_m$ | Peak/Amplitude | Maximum voltage value |
| $\omega$ | Angular frequency | $\omega = 2\pi f$ [rad/s] |
| $f$ | Frequency | Cycles per second [Hz] |
| $T$ | Period | $T = 1/f$ [s] |
| $\phi$ | Phase | Initial angle at $t=0$ [rad or °] |

**Phase shift:** If $v_1(t) = V_m \sin(\omega t)$ and $v_2(t) = V_m \sin(\omega t + 90°)$, then $v_2$ leads $v_1$ by 90°. "Leads" means $v_2$ reaches its peak earlier in time.

> 💡 Insight: A cosine is just a sine shifted by 90°: $\cos(\theta) = \sin(\theta + 90°)$. When working with phasors, engineers often use cosine as the reference — just be consistent within a problem.

---

<a name="rms-and-average-values"></a>
### RMS and Average Values

**Why RMS?** A DC voltage of $V_{DC}$ delivers power $P = V_{DC}^2 / R$ to a resistor. We want to know what AC amplitude delivers the same average power. The answer is the **Root Mean Square** value.

For a sinusoid:

$$
V_{rms} = \frac{V_m}{\sqrt{2}} \approx 0.707\, V_m
$$

**Derivation sketch:** $P_{avg} = \frac{1}{T}\int_0^T \frac{v^2(t)}{R}dt = \frac{V_m^2}{2R}$. Setting this equal to $V_{rms}^2/R$ gives $V_{rms} = V_m/\sqrt{2}$.

> 💡 Insight: The "230 V" on a European wall socket is the RMS value. The actual peak voltage is $230\sqrt{2} \approx 325$ V. This matters when selecting component voltage ratings.

**Average of a half-wave (rectified sinusoid):**

$$
V_{avg} = \frac{2V_m}{\pi} \approx 0.637\, V_m
$$

This is relevant for rectifier circuits (Chapter 5).

---

<a name="phasors"></a>
### Phasors

**The problem:** Adding two sinusoids $A\sin(\omega t + \phi_1) + B\sin(\omega t + \phi_2)$ by direct trigonometry is painful. Phasors make it as easy as adding vectors.

**The idea:** Represent a sinusoid as a rotating vector in the complex plane. At $t = 0$, the vector has:
- Magnitude = amplitude ($V_m$)
- Angle = phase ($\phi$)

The **phasor** (time-independent) is:

$$
\mathbf{V} = V_m \angle \phi = V_m e^{j\phi} = V_m(\cos\phi + j\sin\phi)
$$

To find the sum of two sinusoids at the same frequency, add their phasors as complex numbers. The result gives you the amplitude and phase of the combined sinusoid directly.

> ⚠️ Warning: Phasors only work for signals at the **same frequency**. You cannot add phasors for signals at 100 Hz and 200 Hz — they must be at the same $\omega$.

---

<a name="symbolic--complex-method"></a>
### Symbolic / Complex Method

This is the most powerful technique for AC circuit analysis. The core idea: instead of solving differential equations directly, represent everything in the **frequency domain** using complex numbers.

**The transformation:** Replace $v(t) = V_m \cos(\omega t + \phi)$ with the complex representation:

$$
\mathbf{V} = V_m e^{j\phi}
$$

**Complex impedances:** Each element gets a complex impedance $\mathbf{Z}$ that captures both its amplitude and phase response:

| Component | Time-domain relation | Complex Impedance |
|-----------|---------------------|-------------------|
| Resistor | $v = Ri$ | $Z_R = R$ |
| Inductor | $v = L\,di/dt$ | $Z_L = j\omega L$ |
| Capacitor | $i = C\,dv/dt$ | $Z_C = \frac{1}{j\omega C} = \frac{-j}{\omega C}$ |

**Why $j\omega$ for the inductor?** In the time domain, $v_L = L\,di/dt$. For a phasor current $\mathbf{I}e^{j\omega t}$, taking the derivative brings down a factor of $j\omega$. So $\mathbf{V}_L = j\omega L \cdot \mathbf{I}$.

**Reactance vs. Impedance:**
- **Reactance** $X$ is the imaginary part of impedance: $X_L = \omega L$, $X_C = -1/(\omega C)$
- **Impedance** $Z = R + jX$ is the full complex opposition to current (both resistive and reactive parts)

**Total impedance** follows the same rules as resistance:
- Series: $Z_{total} = Z_1 + Z_2 + \cdots$
- Parallel: $\frac{1}{Z_{total}} = \frac{1}{Z_1} + \frac{1}{Z_2} + \cdots$

---

<a name="ohms-law-in-ac"></a>
### Ohm's Law in AC

In phasor form, Ohm's Law becomes:

$$
\mathbf{V} = \mathbf{I} \cdot \mathbf{Z}
$$

where $\mathbf{V}$, $\mathbf{I}$, and $\mathbf{Z}$ are all complex numbers. This means:

$$
|\mathbf{V}| = |\mathbf{I}| \cdot |\mathbf{Z}| \quad \text{(magnitudes multiply)}
$$

$$
\angle\mathbf{V} = \angle\mathbf{I} + \angle\mathbf{Z} \quad \text{(phases add)}
$$

This is the key: with complex impedances, all the DC analysis techniques (KVL, KCL, voltage divider, mesh analysis) work identically — just with complex numbers instead of real ones.

> 💻 CS Link: FIR (Finite Impulse Response) and IIR (Infinite Impulse Response) digital filters are the software equivalent of impedance networks. The frequency response $H(j\omega)$ of a filter is computed from its coefficients exactly as we compute impedance ratios here. DSP is applied AC circuit theory in discrete time.

---

### Quick Recap

- **Superposition:** One source at a time, others deactivated (V-sources → short, I-sources → open). Sum results. **Not** applicable to power directly.
- **Mesh analysis:** Assign loop currents, write KVL per mesh, solve linear system.
- **AC signals** are characterised by amplitude $V_m$, frequency $\omega$, and phase $\phi$. RMS = $V_m/\sqrt{2}$.
- **Phasors** convert sinusoidal addition into complex vector addition — only valid at the same frequency.
- **Complex impedances**: $Z_R = R$, $Z_L = j\omega L$, $Z_C = 1/(j\omega C)$. Ohm's Law works in phasor form: $\mathbf{V} = \mathbf{I}\mathbf{Z}$.

### Falstad Lab Prep

1. Build a series RL circuit: AC source (10 V, 1 kHz), $R = 1\,\text{k}\Omega$, $L = 100\,\text{mH}$.
2. Use the oscilloscope to display both source voltage and current. Observe the phase shift — current **lags** voltage for an inductor.
3. Replace the inductor with a capacitor ($C = 100\,\text{nF}$). Now current **leads** voltage.
4. Calculate the theoretical phase angle: $\phi = \arctan(X/R)$ where $X = \omega L$ or $X = 1/(\omega C)$. Compare to simulation.

### Exam Traps

1. **Superposition and power:** Never add powers from superposition. Calculate total currents/voltages first, then compute power from those.
2. **Phase of capacitor impedance:** $Z_C = 1/(j\omega C) = -j/(\omega C)$. The negative sign is important — capacitor current leads voltage by 90°, inductor current lags by 90°.
3. **RMS vs. peak:** Exam problems may give you peak voltage or RMS voltage. Always check, and convert before plugging into power formulas (which use RMS).
4. **Mesh current vs. branch current:** The mesh current $I_m$ flows around the loop. The actual current in a shared branch between meshes $m$ and $n$ is $I_m - I_n$, not just $I_m$.

---

<a name="chapter-4"></a>
## Chapter 4 — RLC Circuits: Frequency Response, Resonance, AC Power

### The Real-World Hook

When you tune a radio to 100.5 FM, a circuit inside the receiver selects 100.5 MHz and rejects 100.7 MHz. That selectivity — the ability to "peak" sharply at one frequency and suppress everything else — is resonance. The same principle governs 5G antenna design, crystal oscillators in your CPU, and the bass/treble controls in a speaker system. This chapter explains how and why.

---

<a name="frequency-response"></a>
### Frequency Response

**The key insight:** Impedance depends on frequency.

- Capacitor: $|Z_C| = \frac{1}{\omega C}$ → as frequency **increases**, $|Z_C|$ **decreases** (capacitor becomes a better conductor at high frequencies)
- Inductor: $|Z_L| = \omega L$ → as frequency **increases**, $|Z_L|$ **increases** (inductor blocks high frequencies more strongly)

Parameter intuition:
- ↑$\omega$ → ↓$|Z_C|$ (capacitor passes more current)
- ↑$\omega$ → ↑$|Z_L|$ (inductor blocks more current)
- At $\omega = 0$ (DC): $|Z_C| \to \infty$ (capacitor blocks DC); $|Z_L| = 0$ (inductor is a wire)
- At $\omega \to \infty$: $|Z_C| \to 0$ (capacitor is a wire); $|Z_L| \to \infty$ (inductor blocks)

This frequency dependence is what allows circuits to **filter** signals — passing some frequencies and rejecting others.

---

<a name="filter-types"></a>
### Filter Types

The **transfer function** $H(j\omega) = \mathbf{V}_{out}/\mathbf{V}_{in}$ describes how a circuit transforms an input signal at each frequency.

#### Low-Pass Filter (RC)

Uses the capacitor voltage as output. At low frequencies, $Z_C$ is large → most voltage drops across $C$ → signal passes. At high frequencies, $Z_C \to 0$ → capacitor voltage drops to zero → signal blocked.

$$
H(j\omega) = \frac{Z_C}{R + Z_C} = \frac{1}{1 + j\omega RC}
$$

**Cutoff frequency:**

$$
\omega_c = \frac{1}{RC} \quad \text{or} \quad f_c = \frac{1}{2\pi RC}
$$

At $\omega = \omega_c$: $|H| = 1/\sqrt{2} \approx 0.707$ (the "half-power" point, or −3 dB point).

#### High-Pass Filter (RC)

Uses the resistor voltage as output. At high frequencies, $Z_C \to 0$ → all voltage drops across $R$ → signal passes. At low frequencies, $Z_C$ is large → nearly all voltage drops across $C$ → signal blocked.

$$
H(j\omega) = \frac{j\omega RC}{1 + j\omega RC}
$$

Cutoff frequency is the same: $\omega_c = 1/(RC)$.

#### Band-Pass Filter (RLC)

A series RLC circuit with output taken across $R$. Passes a band of frequencies centred on the resonant frequency $\omega_0$. At resonance, $Z_L$ and $Z_C$ cancel, only $R$ remains.

#### Band-Stop (Notch) Filter (RLC)

Output taken across the LC series combination. At resonance, $Z_L + Z_C = 0$ → zero output → notch. Used in audio equipment to reject 50/60 Hz power line hum.

> 💡 Insight: A guitar amplifier's "tone" control is simply a variable RC low-pass filter. A wah pedal sweeps the resonant frequency of an RLC-based band-pass filter across the audio spectrum.

---

<a name="bode-plots"></a>
### Bode Plots

A **Bode plot** displays $|H(j\omega)|$ in decibels (dB) vs. frequency on a logarithmic axis:

$$
|H|_{dB} = 20\log_{10}|H(j\omega)|
$$

**Asymptotic sketch for a low-pass filter:**

- For $\omega \ll \omega_c$: $|H| \approx 1$, so $|H|_{dB} \approx 0$ dB. The response is flat.
- For $\omega \gg \omega_c$: $|H| \approx \omega_c/\omega$, which decreases at −20 dB/decade (a first-order roll-off).
- At $\omega = \omega_c$: $|H|_{dB} = -3$ dB. This is the corner/break frequency.

**Why log scale?** Because human hearing is logarithmic, and because filters often span many orders of magnitude in frequency. A log scale makes the important features visible across the whole range.

---

<a name="series-rlc-resonance"></a>
### Series RLC Resonance

**Circuit:** Voltage source $V_s$, resistor $R$, inductor $L$, capacitor $C$ — all in series.

**Total impedance:**

$$
Z = R + j\omega L + \frac{1}{j\omega C} = R + j\left(\omega L - \frac{1}{\omega C}\right)
$$

**Resonance condition:** The imaginary part of $Z$ equals zero:

$$
\omega_0 L - \frac{1}{\omega_0 C} = 0 \quad \Rightarrow \quad \omega_0 = \frac{1}{\sqrt{LC}}
$$

At resonance:
- $Z = R$ (purely resistive — minimum impedance)
- Current is maximum: $I_{max} = V_s / R$
- The circuit "looks like" a pure resistor — source voltage and current are in phase

Parameter intuition: ↑L → ↓$\omega_0$. ↑C → ↓$\omega_0$. $R$ does not affect $\omega_0$.

---

<a name="parallel-rlc-resonance"></a>
### Parallel RLC Resonance

**Circuit:** Current source $I_s$ in parallel with $R$, $L$, and $C$.

**Total admittance** $Y = 1/Z$:

$$
Y = \frac{1}{R} + j\omega C + \frac{1}{j\omega L} = \frac{1}{R} + j\left(\omega C - \frac{1}{\omega L}\right)
$$

**Resonance condition:** Imaginary part of $Y$ equals zero — same frequency $\omega_0 = 1/\sqrt{LC}$.

At resonance:
- $Y = 1/R$ → $Z$ is maximum (purely resistive)
- Source current is minimum (tank circuit recirculates energy between L and C)
- Large currents can circulate between $L$ and $C$, but the source only supplies losses

> 💡 Insight: Think of the parallel LC "tank" at resonance as a pendulum swinging back and forth — energy transfers between kinetic (inductor = magnetic energy) and potential (capacitor = electric energy) with only friction ($R$) draining it. The source just tops up the losses.

---

<a name="q-factor-and-bandwidth"></a>
### Q-Factor and Bandwidth

**Q-factor (Quality Factor):** Measures the "sharpness" of the resonance peak. Physically, it is the ratio of energy stored to energy dissipated per radian of oscillation:

$$
Q = \frac{\text{energy stored}}{\text{energy lost per cycle}} \times 2\pi
$$

For a series RLC circuit:

$$
Q = \frac{\omega_0 L}{R} = \frac{1}{\omega_0 R C} = \frac{1}{R}\sqrt{\frac{L}{C}}
$$

Parameter intuition: ↑R → ↓Q (more damping, broader peak). ↑L → ↑Q (for fixed R). ↓R → ↑Q (sharper resonance).

**Bandwidth:**

$$
BW = \frac{\omega_0}{Q} \quad \text{[rad/s]}
$$

The bandwidth is the frequency range between the two half-power points ($-3\,\text{dB}$ points):

$$
\omega_{1,2} = \omega_0 \pm \frac{BW}{2} \quad \text{(valid for high Q)}
$$

> 💡 Insight: A crystal oscillator in your computer has $Q \approx 10^4$ to $10^6$ — extremely sharp resonance, giving extremely stable frequency. An LC circuit built from real components typically has $Q$ from 10 to a few hundred.

> 💻 CS Link: In radio receivers, the Q-factor of the tuning circuit determines **selectivity** — how well you receive one station without interference from neighbouring frequencies. Wi-Fi channels are 20 MHz wide; a receiver must select one and reject others 5 MHz away. High Q = better selectivity.

---

<a name="voltage-and-current-resonance"></a>
### Voltage and Current Resonance

**Series RLC — Voltage Resonance:**

At resonance, the voltages across $L$ and $C$ individually can greatly exceed the source voltage:

$$
V_L = V_C = Q \cdot V_s \quad \text{(at resonance)}
$$

**Why?** At resonance, $I = V_s/R$. The voltage across $L$ is $V_L = I \cdot |Z_L| = (V_s/R)\cdot\omega_0 L = Q \cdot V_s$.

> ⚠️ Warning: This is not a violation of KVL. The voltages across $L$ and $C$ are equal in magnitude but opposite in phase (180° apart). They cancel each other, so the net reactive voltage is zero, and only $V_R = V_s$ appears across the resistor. But the individual component voltages can still be 10×, 50×, or 100× the source voltage — which can destroy capacitors or inductors if not rated correctly.

**Parallel RLC — Current Resonance:**

Similarly, the currents circulating through $L$ and $C$ branches can be $Q$ times the source current:

$$
I_L = I_C = Q \cdot I_s \quad \text{(at resonance)}
$$

---

<a name="ac-power"></a>
### AC Power

In a purely resistive circuit, current and voltage are in phase. In reactive circuits (with $L$ or $C$), there is a phase difference $\phi$ between $v(t)$ and $i(t)$.

**Instantaneous power:**

$$
p(t) = v(t) \cdot i(t) = V_m \sin(\omega t) \cdot I_m \sin(\omega t - \phi)
$$

This fluctuates rapidly. What matters in practice is the **average** power.

**Active Power (Real Power):** the power actually consumed (converted to heat or mechanical work):

$$
P = V_{rms} I_{rms} \cos\phi \quad [W]
$$

**Reactive Power:** power that oscillates back and forth between source and reactive elements (no net energy consumption):

$$
Q_{power} = V_{rms} I_{rms} \sin\phi \quad [VAR]
$$

*(Note: $Q_{power}$ for reactive power — not to be confused with the Q-factor for quality factor. Context distinguishes them.)*

**Apparent Power:** the total power the source must supply:

$$
S = V_{rms} I_{rms} \quad [VA]
$$

**Power Factor:**

$$
\cos\phi = \frac{P}{S}
$$

**Power Triangle:** These three quantities form a right triangle:

$$
S^2 = P^2 + Q_{power}^2
$$

**Why power factor matters:** A motor with $\cos\phi = 0.6$ drawing 10 kVA from the grid only does 6 kW of useful work. The grid still transmits 10 kVA, heating the cables for nothing. This is why industrial facilities with large inductive loads (motors) are required to install **capacitor banks** to correct the power factor toward 1.0 — it saves energy and reduces cable heating.

> 💡 Insight: A purely resistive load has $\phi = 0$, $\cos\phi = 1$ (perfect power factor). A purely reactive load has $\phi = 90°$, $\cos\phi = 0$ (zero real power — energy sloshes back and forth but no work is done).

---

### Quick Recap

- **Frequency response:** $|Z_C|$ decreases with frequency; $|Z_L|$ increases. This creates filter behaviour.
- **Four filter types:** low-pass, high-pass (RC); band-pass, band-stop (RLC). Cutoff/resonant frequency is the key parameter.
- **Series resonance** at $\omega_0 = 1/\sqrt{LC}$: impedance is minimum ($= R$), current is maximum.
- **Q-factor** measures resonance sharpness: $Q = \omega_0 L/R$. Higher Q = narrower bandwidth. At resonance, $V_L = V_C = QV_s$ (can exceed source voltage!).
- **AC power** splits into active (real, in Watts), reactive (in VAR), and apparent (in VA). $\cos\phi$ = power factor.

### Falstad Lab Prep

1. Build a series RLC circuit: AC source (1 V, variable frequency), $R = 100\,\Omega$, $L = 10\,\text{mH}$, $C = 10\,\text{nF}$.
2. Calculate the resonant frequency: $f_0 = 1/(2\pi\sqrt{LC}) \approx 15.9\,\text{kHz}$.
3. Sweep the source frequency and observe the current (or voltage across $R$). Confirm maximum current at $f_0$.
4. Measure voltages across $L$ and $C$ at resonance. Calculate $Q = \omega_0 L/R$ and verify $V_L \approx QV_s$.
5. Detune slightly above and below $f_0$ to observe how quickly the current drops — compare high-Q vs. low-Q (change $R$).

### Exam Traps

1. **Q-factor units:** Q is dimensionless. $BW = \omega_0/Q$ is in rad/s (not Hz). Divide by $2\pi$ to get Hz.
2. **Voltages exceeding source voltage:** Students are surprised by $V_L = QV_s$. This is real, measurable, and not a KVL violation. Know why (L and C voltages are 180° out of phase and cancel in KVL).
3. **Power factor cos φ vs. phase angle φ:** Exam questions often give you $\phi$ and ask for $P$ — don't forget the $\cos$.
4. **$Q_{power}$ vs. $Q$-factor:** Both use the letter Q. Context is everything. Reactive power is in VAR; Q-factor is dimensionless.

---

<a name="chapter-5"></a>
## Chapter 5 — Semiconductors and Diodes

### The Real-World Hook

The LED in your keyboard indicator, the solar panel on a rooftop, and the rectifier in every phone charger all rely on the same fundamental structure: a P-N junction. Understanding it is understanding the atomic mechanism behind essentially all modern electronics. The transistor — and thus every computer — is built from multiple P-N junctions.

---

<a name="band-model"></a>
### Band Model

In a crystalline solid, electrons can only occupy certain ranges ("bands") of energy. The two most important bands are:

- **Valence band:** The highest fully (or nearly) filled band at low temperature. Electrons here are bound to atoms.
- **Conduction band:** The next higher band. Electrons here are free to move and conduct electricity.
- **Band gap $E_g$:** The forbidden energy range between valence and conduction band.

**Classification:**
- **Conductors (metals):** Bands overlap or the valence band is partially filled. Electrons can move freely. $E_g \approx 0$.
- **Insulators:** Large band gap ($E_g > 5\,\text{eV}$, e.g. diamond at 5.5 eV). Thermal energy at room temperature can't bridge the gap.
- **Semiconductors:** Small band gap ($E_g \approx 1\,\text{eV}$). Silicon: 1.12 eV. Germanium: 0.67 eV. Thermal energy can bridge the gap, creating a temperature-dependent conductivity.

---

<a name="intrinsic-semiconductors"></a>
### Intrinsic Semiconductors

A **pure** semiconductor (no impurities) is called **intrinsic**. At room temperature, thermal energy excites a small fraction of valence electrons into the conduction band.

When an electron leaves the valence band, it leaves behind an empty state called a **hole**. A hole behaves like a positive charge carrier — neighbouring electrons can hop into it, making the hole appear to move in the opposite direction to the electrons.

In an intrinsic semiconductor: number of free electrons = number of holes (they're generated in pairs).

Both electrons and holes contribute to current, but they move in opposite directions — both contributing to current in the same conventional direction.

---

<a name="doping"></a>
### Doping

**Doping** is the deliberate introduction of impurity atoms to control conductivity.

**N-type doping:** Add atoms with 5 valence electrons (e.g., phosphorus, arsenic) into a silicon lattice (silicon has 4 valence electrons). The 5th electron is not needed for bonding and is loosely held — easily promoted to the conduction band. This creates extra free electrons (majority carriers: electrons; minority carriers: holes).

**P-type doping:** Add atoms with 3 valence electrons (e.g., boron, aluminium). This creates an empty bond site — a hole — readily accepting electrons. Majority carriers: holes; minority carriers: electrons.

> 💡 Insight: Doping doesn't make the material charged — the crystal remains electrically neutral overall (the impurity atoms are neutral). Doping just creates regions with more movable electrons (N-type) or more movable holes (P-type).

---

<a name="the-p-n-junction"></a>
### The P-N Junction

When P-type and N-type semiconductors are brought together (in the same crystal), several things happen immediately:

1. **Diffusion:** Electrons from the N-side diffuse toward the P-side (high concentration to low), and holes diffuse the other way.
2. **Depletion region:** Where electrons and holes meet, they recombine and annihilate. This leaves behind ionised donor atoms (positive, fixed) on the N-side and ionised acceptor atoms (negative, fixed) on the P-side — a region depleted of mobile carriers.
3. **Built-in electric field:** The fixed ions create an electric field pointing from N to P across the depletion region. This field opposes further diffusion, reaching equilibrium.
4. **Built-in potential:** There is a contact potential difference across the junction (≈ 0.7 V for Si, ≈ 0.3 V for Ge) — but you cannot use this to drive a current in an external circuit without applying an external bias.

**Forward bias** (connect + to P-side, − to N-side):
- External voltage opposes the built-in field, reducing the depletion region width.
- When external voltage exceeds the built-in potential (~0.7 V for Si), the barrier collapses and significant current flows.
- Current increases exponentially with voltage.

**Reverse bias** (connect + to N-side, − to P-side):
- External voltage adds to the built-in field, widening the depletion region.
- Very little current flows (only tiny leakage current from minority carriers).
- At sufficiently high reverse voltage, **breakdown** occurs (avalanche or Zener mechanism) — very large current flows in reverse.

---

<a name="diode-iv-characteristic"></a>
### Diode I–V Characteristic

The full equation relating diode current to voltage is the **Shockley equation**:

$$
I = I_s\left(e^{V/(nV_T)} - 1\right)
$$

| Symbol | Meaning |
|--------|---------|
| $I_s$ | Reverse saturation current (≈ pA for Si at room temp) |
| $n$ | Ideality factor (1 for ideal, 1–2 for real diodes) |
| $V_T$ | Thermal voltage: $V_T = kT/q \approx 26\,\text{mV}$ at 25°C |
| $k$ | Boltzmann constant |
| $T$ | Temperature in Kelvin |

For $V \gg V_T$ (forward bias): $I \approx I_s e^{V/nV_T}$ — exponential growth.

For $V \ll 0$ (reverse bias): $I \approx -I_s$ — tiny constant leakage.

---

<a name="diode-circuit-models"></a>
### Diode Circuit Models for Analysis

Full Shockley equation is used in SPICE/Falstad. For hand analysis:

**Ideal diode model:**
- Forward biased: short circuit (0 V drop)
- Reverse biased: open circuit (0 current)

**0.7 V model** (better for silicon):
- Forward biased (when $V > 0.7\,\text{V}$): voltage source of 0.7 V
- Reverse biased: open circuit

> 💡 Insight: For a quick check of whether a diode conducts or not, the ideal model is sufficient. For calculating currents and voltages accurately, use the 0.7 V model. For precision simulation, use the Shockley model.

---

<a name="diode-applications"></a>
### Diode Applications

#### Half-Wave Rectifier

One diode in series with a load resistor. During the positive half-cycle of AC, the diode conducts; during negative half-cycle, it blocks. Output is pulsating DC with frequency equal to the input frequency.

**Limitation:** Only uses half the AC cycle; output has large ripple.

#### Full-Wave Bridge Rectifier

Four diodes arranged in a bridge. During positive half-cycle, two diodes conduct; during negative half-cycle, the other two conduct. Both half-cycles contribute to output, same polarity.

**Advantage:** Both halves used; output ripple frequency is double the input frequency; requires less filter capacitance.

**Smoothing capacitor:** Add a large capacitor in parallel with the load. The capacitor charges during each diode conduction phase and discharges slowly into the load between pulses, reducing ripple voltage.

$$
V_{ripple} \approx \frac{I_{load}}{2fC} \quad \text{(full-wave)}
$$

#### Zener Diode as Voltage Regulator

A Zener diode is designed to operate reliably in reverse breakdown at a specific **Zener voltage** $V_Z$. Once the reverse voltage reaches $V_Z$, the Zener maintains that voltage nearly constant even as current varies widely.

**Application:** Simple voltage regulator. Pair a Zener with a series resistor. Regardless of load current (within limits), the voltage across the Zener stays at $V_Z$.

> 💻 CS Link: Diodes are the fundamental building block of all digital ICs. The PN junction is the core of every BJT, MOSFET, LED, photodiode, and solar cell. The gate oxide in a MOSFET acts as a dielectric — essentially a capacitor. Modern CPUs contain billions of these transistors, all derived from the PN junction physics described here.

---

### Quick Recap

- **Band gap** determines whether a material is a conductor, semiconductor, or insulator. Si has $E_g = 1.12\,\text{eV}$.
- **Doping:** N-type adds electrons (donor atoms), P-type adds holes (acceptor atoms). Both remain electrically neutral overall.
- **P-N junction** creates a depletion region and built-in field. Forward bias reduces this barrier; reverse bias increases it.
- **Diode conducts** (forward) above ~0.7 V (Si); blocks (reverse) until breakdown.
- **Rectifiers** convert AC to pulsating DC. Smoothing capacitors reduce ripple. Zener diodes regulate voltage.

### Falstad Lab Prep

1. Build a half-wave rectifier: AC source (10 V, 50 Hz), one diode, $1\,\text{k}\Omega$ load.
2. View the output on the oscilloscope — observe the half-wave shape.
3. Add a full-wave bridge (four diodes). Compare the output waveform.
4. Add a 100 μF capacitor in parallel with the load. Observe ripple reduction.
5. Try a Zener circuit: reverse-biased Zener (5.1 V) in parallel with the load, with a 1 kΩ series resistor. Vary the load and verify the output stays near 5.1 V.

### Exam Traps

1. **Diode polarity:** Conventional current flows from anode (+, P-side) to cathode (−, N-side) when forward biased. Drawing it backwards blocks everything.
2. **0.7 V in forward bias:** This is a voltage drop, not a voltage source that adds energy. It reduces the available voltage to the rest of the circuit.
3. **Zener breakdown is reverse bias:** Zeners are operated in reverse. Don't forward-bias a Zener and call it a regulator.
4. **Ripple frequency:** For a half-wave rectifier, ripple is at line frequency $f$. For a full-wave rectifier, ripple is at $2f$. This affects capacitor sizing.

---

<a name="chapter-6"></a>
## Chapter 6 — Transistors: Amplifiers, Switches, Multivibrators

### The Real-World Hook

In 1947, three physicists at Bell Labs invented the transistor in a device the size of your palm. Today, your phone's processor contains approximately 15 billion transistors in an area smaller than a fingernail. Understanding the transistor — as both an amplifier and a switch — is understanding the physical mechanism behind every modern computation.

---

<a name="bjt-structure-and-operation"></a>
### BJT Structure and Operation

A **Bipolar Junction Transistor (BJT)** consists of three semiconductor layers in a sandwich: either N-P-N or P-N-P.

**Three terminals:**
- **Emitter (E):** Heavily doped; emits carriers into the base.
- **Base (B):** Very thin and lightly doped; controls carrier flow.
- **Collector (C):** Collects carriers that make it through the base.

The transistor is essentially two P-N junctions back-to-back. For an NPN transistor in active mode:
- Base-Emitter junction: forward biased (~0.7 V)
- Base-Collector junction: reverse biased

A small current injected into the base ($I_B$) controls a much larger current flowing from collector to emitter ($I_C$).

---

<a name="bjt-operating-modes"></a>
### BJT Operating Modes

| Mode | B-E Junction | B-C Junction | Behaviour |
|------|-------------|-------------|-----------|
| Cutoff | Reverse | Reverse | Both junctions off — transistor is OFF, $I_C \approx 0$ |
| Active | Forward | Reverse | Amplifying region: $I_C = \beta I_B$ |
| Saturation | Forward | Forward | Transistor fully ON; $V_{CE} \approx 0.2\,\text{V}$ regardless of $I_B$ |

**Current gain:**

$$
I_C = \beta I_B \quad \text{(active region)}
$$

$\beta$ (also written $h_{FE}$) typically ranges from 50 to 500 depending on the transistor. A base current of 10 μA with $\beta = 100$ produces $I_C = 1\,\text{mA}$.

**Why does a tiny base current control a large collector current?** The base is extremely thin. Electrons injected from the emitter must cross it. Most don't recombine with holes in the base (because it's so thin and lightly doped) — they diffuse across and get swept into the collector by the reverse-biased B-C junction. Only a tiny fraction recombine in the base, constituting $I_B$. The ratio gives $\beta$.

---

<a name="common-emitter-amplifier"></a>
### Common-Emitter Amplifier

The **common-emitter (CE) configuration** is the most widely used BJT amplifier topology.

**Circuit:** Voltage divider ($R_1$, $R_2$) biases the base. Collector resistor $R_C$ converts collector current to voltage. Emitter resistor $R_E$ provides stability. Coupling capacitors block DC while passing AC signals.

**Voltage gain** (small-signal, with bypass capacitor across $R_E$):

$$
A_v = -\frac{R_C}{r_e} \approx -\frac{R_C}{R_E}
$$

where $r_e = V_T/I_C \approx 26\,\text{mV}/I_C$ is the small-signal emitter resistance.

The negative sign indicates **phase inversion**: when the input goes up, the output goes down. This is because a larger $v_{in}$ → larger $I_B$ → larger $I_C$ → larger drop across $R_C$ → lower $v_{out} = V_{CC} - I_C R_C$.

**DC biasing:** The voltage divider sets $V_B \approx V_{CC}\cdot R_2/(R_1 + R_2)$. Then $V_E = V_B - 0.7\,\text{V}$, $I_E = V_E/R_E$, and since $I_E \approx I_C$ (for large $\beta$), the operating point is set.

---

<a name="mosfet"></a>
### MOSFET

A **MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor)** controls current flow using an electric field rather than a base current. This has a crucial advantage: the gate draws essentially no DC current.

**N-channel enhancement MOSFET:**
- Gate, Source, Drain terminals
- Gate is insulated from the semiconductor by a thin oxide layer (capacitor structure)
- When gate voltage $V_{GS} < V_{th}$ (threshold): no channel, transistor OFF
- When $V_{GS} > V_{th}$: an inversion layer (channel) of electrons forms between drain and source, transistor ON

**Key difference from BJT:**
- BJT: current-controlled (base current controls collector current)
- MOSFET: voltage-controlled (gate voltage controls drain current)
- MOSFET gate current ≈ 0 in DC — no power wasted in control
- MOSFETs switch faster and are easier to integrate — why CPUs use MOSFETs, not BJTs

---

<a name="transistor-as-digital-switch"></a>
### Transistor as Digital Switch

For digital logic, the transistor operates between two states only:

**OFF (Logic 0 = Cutoff):** $V_{in}$ below threshold. $I_C \approx 0$. $V_{out} \approx V_{CC}$ (pulled up through $R_C$).

**ON (Logic 1 = Saturation):** $V_{in}$ high enough to saturate the transistor. $I_C$ is limited by $R_C$: $I_C = (V_{CC} - V_{CE,sat})/R_C$. $V_{out} \approx V_{CE,sat} \approx 0.2\,\text{V}$ ≈ 0 V (logic low at output).

This is an **inverter**: high input → low output, low input → high output. The NOT gate.

> 💡 Insight: A 3 GHz processor means its transistors switch between cutoff and saturation approximately 3 billion times per second. The speed is limited by how fast the transistor can be pushed in and out of saturation — which is why MOSFET technology (avoiding saturation through careful design) dominates in CPUs.

---

<a name="multivibrators"></a>
### Multivibrators

**Multivibrators** are circuits with two transistors cross-coupled, producing oscillating or switching behaviour. All three types use positive feedback (output reinforces itself).

#### Astable Multivibrator (Free-Running Oscillator)

Two transistors alternately switch on and off, driven by RC timing networks. Neither state is stable — the circuit oscillates continuously, producing a square wave.

**Period** (approximately, for equal components):

$$
T \approx 1.4\, R C \quad \text{(for each half-cycle: } t \approx 0.7\,RC\text{)}
$$

**Application:** Generating clock signals, LED blinkers, tone generators. This is the circuit inside a simple 555 timer in astable mode.

#### Monostable Multivibrator (One-Shot)

One stable state. An external trigger causes a transition to the unstable state, which lasts for a time determined by $RC$, then returns automatically.

**Application:** Producing a single pulse of defined duration from a short trigger (e.g., debouncing a button — produces one clean pulse regardless of contact bouncing).

#### Bistable Multivibrator (Flip-Flop / Latch)

Two stable states. Stays in one state until externally commanded to switch. This is the basic **SR flip-flop** (Set-Reset). External pulses toggle between the two states.

**Application:** Memory — each flip-flop stores one bit. Basis of registers, counters, and SRAM.

---

<a name="binary-counter"></a>
### Binary Counter

A **binary counter** is a chain of T flip-flops (Toggle flip-flops), each dividing the clock frequency by 2.

- Stage 0: toggles every clock cycle → frequency = $f_{CLK}/2^1$
- Stage 1: toggles every 2nd clock cycle → frequency = $f_{CLK}/2^2$
- Stage $n$: frequency = $f_{CLK}/2^{n+1}$

A 4-stage counter divides by 16 and outputs the binary representation of a 4-bit count from 0000 to 1111 (0 to 15), then wraps.

> 💻 CS Link: Every logic gate in your CPU is a transistor switch. A 3 GHz processor switches its transistors 3 billion times per second. MOSFETs in a modern CPU are around 3–5 nm wide — smaller than a strand of DNA. Each one is a switch operating on the same principle as the simple circuit you can simulate in Falstad.

---

### Quick Recap

- **BJT** has three regions: cutoff (OFF), active (amplifier with $I_C = \beta I_B$), saturation (fully ON). NPN most common.
- **Common-emitter amplifier** provides voltage gain $A_v \approx -R_C/R_E$ with phase inversion.
- **MOSFET** is voltage-controlled, draws no gate current — standard device for digital ICs and power electronics.
- **As a switch:** cutoff = logic 0 (output high), saturation = logic 1 (output low). This is the inverter.
- **Multivibrators:** astable (oscillates), monostable (one pulse), bistable (flip-flop, 1-bit memory).

### Falstad Lab Prep

1. Build a common-emitter NPN amplifier: $V_{CC} = 12\,\text{V}$, $R_C = 4.7\,\text{k}\Omega$, $R_E = 1\,\text{k}\Omega$, voltage divider bias, 1 kHz AC input.
2. Observe that the output is amplified and inverted relative to the input.
3. Now configure the transistor as a switch: apply 0 V or 5 V to the base through $R_B$. Observe LED turning on/off.
4. Build an astable multivibrator with two NPN transistors and RC networks. Observe the two outputs toggling alternately.

### Exam Traps

1. **Active vs. saturation for a switch:** In saturation, $I_C \neq \beta I_B$ — the transistor is fully ON and $V_{CE}$ is fixed at ~0.2 V. Don't apply $\beta$ in saturation mode.
2. **Phase inversion in CE amplifier:** The voltage gain is negative. Students often write $|A_v|$ without noting the phase flip — which matters for feedback analysis.
3. **MOSFET gate current:** Gate current is essentially zero in DC. Don't try to calculate gate current using transistor current gain — MOSFETs don't have one.
4. **Bistable vs. monostable:** A bistable stays in its new state after a trigger. A monostable returns to its stable state after time $\tau = RC$.

---

<a name="chapter-7"></a>
## Chapter 7 — Operational Amplifiers and Feedback

### The Real-World Hook

Before digital computers, engineers built entire computers from op-amps — these circuits could solve differential equations, integrate signals, and multiply values all in real time. Today, op-amps are inside every audio device (microphone preamplifiers), every sensor interface (strain gauge amplifiers), and every power supply feedback loop. The op-amp is the Swiss Army knife of analog electronics.

---

<a name="ideal-op-amp-properties"></a>
### Ideal Op-Amp Properties

An **operational amplifier** is a high-gain differential amplifier with two inputs and one output:
- **Inverting input (−):** signal at this input is amplified with negative sign
- **Non-inverting input (+):** signal amplified with positive sign
- **Output:** $V_{out} = A_{OL}(V_+ - V_-)$

For an **ideal op-amp**, assume:

| Property | Ideal Value | Physical Meaning |
|----------|-------------|-----------------|
| Open-loop gain $A_{OL}$ | $\to \infty$ | Amplifies even tiny differential inputs |
| Input impedance $Z_{in}$ | $\to \infty$ | No current flows into the inputs |
| Output impedance $Z_{out}$ | $\to 0$ | Can drive any load without voltage drop |
| Bandwidth | $\to \infty$ | Works at all frequencies |
| Offset voltage | $= 0$ | Zero output for zero differential input |

---

<a name="real-op-amp-limitations"></a>
### Real Op-Amp Limitations

Real op-amps (e.g., LM741, TL071, LM358) deviate from ideal:

- **Finite gain:** $A_{OL}$ is typically $10^5$ to $10^6$ at DC, but drops with frequency.
- **Gain-bandwidth product (GBW):** For a typical op-amp, $GBW = A_{OL} \times f$ is constant. A 1 MHz GBW op-amp has gain of 100 only up to 10 kHz.
- **Slew rate:** The output voltage cannot change faster than the slew rate (e.g., 0.5 V/μs for LM741). High-frequency large-amplitude signals get distorted.
- **Input offset voltage:** A small internal mismatch means the output isn't exactly zero when inputs are equal — can cause DC errors.

---

<a name="negative-feedback-and-the-golden-rules"></a>
### Negative Feedback and the Golden Rules

**Negative feedback** connects the output back to the inverting input. The result is a dramatic improvement in stability, bandwidth, and linearity — at the cost of reduced gain.

**How it works:** If $V_{out}$ rises too high, the feedback voltage at $V_-$ rises, reducing $(V_+ - V_-)$, which reduces $V_{out}$. This self-correcting mechanism stabilises the output precisely.

With $A_{OL} \to \infty$ and negative feedback, two **Golden Rules** hold exactly for ideal op-amps:

> **Golden Rule 1:** The voltage at the inverting input equals the voltage at the non-inverting input: $V_- = V_+$ (virtual short)

> **Golden Rule 2:** No current flows into either input terminal.

These two rules alone let you analyse any op-amp circuit without knowing $A_{OL}$. The op-amp does whatever it takes with its output to make $V_- = V_+$.

> ⚠️ Warning: The Golden Rules only apply when **negative feedback is present** and the op-amp is **not in saturation** (output not clipped at the supply rails). If the output is stuck at +$V_{supply}$ or −$V_{supply}$, the rules don't apply.

---

<a name="op-amp-circuits"></a>
### Op-Amp Circuits

#### Inverting Amplifier

**Topology:** $V_{in}$ through $R_1$ to $V_-$ (inverting input). Feedback resistor $R_f$ from output to $V_-$. Non-inverting input at ground.

**Derivation using Golden Rules:**
- By Rule 1: $V_- = V_+ = 0$ (virtual ground)
- By Rule 2: no current into input, so $I_{R_1} = I_{R_f}$
- $I_{R_1} = (V_{in} - 0)/R_1$; $I_{R_f} = (0 - V_{out})/R_f$
- Equating: $V_{in}/R_1 = -V_{out}/R_f$

$$
\frac{V_{out}}{V_{in}} = -\frac{R_f}{R_1}
$$

Gain is set by the ratio of resistors, not by $A_{OL}$. Phase is inverted.

#### Non-Inverting Amplifier

**Topology:** $V_{in}$ directly to $V_+$. Voltage divider ($R_f$, $R_1$) from output to $V_-$.

**Derivation:**
- $V_+ = V_{in}$; by Golden Rule 1: $V_- = V_{in}$
- $V_-$ is set by voltage divider: $V_- = V_{out} \cdot R_1/(R_1 + R_f)$
- So: $V_{in} = V_{out} \cdot R_1/(R_1 + R_f)$

$$
\frac{V_{out}}{V_{in}} = 1 + \frac{R_f}{R_1}
$$

Gain is always $\geq 1$. No phase inversion.

#### Voltage Follower (Unity Gain Buffer)

Output connected directly to $V_-$ (i.e., $R_f = 0$, $R_1 = \infty$). From the non-inverting formula with $R_f = 0$:

$$
V_{out} = V_{in}
$$

**Why is this useful?** It has very high input impedance and very low output impedance. It isolates (buffers) a weak source from a demanding load — like an adapter between a microphone and a power amplifier. The source "sees" infinity; the load "sees" zero.

#### Summing Amplifier (Adder)

Multiple inputs, each through its own resistor, to the inverting input. Feedback $R_f$.

$$
V_{out} = -R_f\left(\frac{V_1}{R_1} + \frac{V_2}{R_2} + \cdots\right)
$$

**Application:** Audio mixing board — multiple microphone signals summed into one output.

#### Integrator

Capacitor $C$ in the feedback path (instead of $R_f$). Resistor $R$ at input.

$$
V_{out}(t) = -\frac{1}{RC}\int_0^t V_{in}(\tau)\,d\tau
$$

**Physical meaning:** The output voltage is proportional to the accumulated charge on $C$, which is the time integral of the input. A constant input produces a linearly ramping output. A square wave input produces a triangular wave output.

**Application:** Analog computing (integrating velocity to get position), integrating ADC designs, PID controllers in industrial systems.

#### Differentiator

Capacitor $C$ at the input (instead of $R$ for $R_1$). Resistor $R$ in feedback.

$$
V_{out}(t) = -RC\frac{dV_{in}}{dt}
$$

**Physical meaning:** The output is proportional to the rate of change of the input. A rising input produces a positive output spike; a falling input produces a negative spike. A triangle wave input produces a square wave output.

> ⚠️ Warning: Differentiators amplify high-frequency noise (noise has large $dv/dt$). In practice, a small resistor in series with the input capacitor limits the bandwidth and tames noise. Pure differentiators are rarely used without this modification.

#### Schmitt Trigger

Uses **positive feedback** (output connected to $V_+$, the non-inverting input). This creates **hysteresis** — two different threshold voltages for switching high and low.

- If $V_{in}$ rises above the upper threshold $V_{TH}$: output switches to $+V_{sat}$
- If $V_{in}$ falls below the lower threshold $V_{TL}$: output switches to $-V_{sat}$
- The gap $V_{TH} - V_{TL}$ is the hysteresis band

**Why hysteresis?** A noisy signal crossing a single threshold would cause rapid, chaotic switching. With hysteresis, the signal must cleanly cross to the other side of the band before switching occurs — noise is rejected.

> 💻 CS Link: Op-amp integrators and differentiators are analog computers — building blocks of the first electronic computers in the 1940s. Schmitt triggers are inside every UART, SPI, and I²C receiver chip, cleaning up degraded digital signals before they reach the logic core. Every time you plug in a USB device, a Schmitt trigger processes the incoming signal.

---

### Quick Recap

- **Ideal op-amp:** infinite gain, infinite input impedance, zero output impedance.
- **Golden Rules** (with negative feedback): $V_+ = V_-$ (virtual short); zero input current.
- **Inverting amplifier:** gain = $-R_f/R_1$; non-inverting: gain = $1 + R_f/R_1$.
- **Integrator/Differentiator:** capacitor in feedback (integrator) or at input (differentiator). Square waves become triangles and vice versa.
- **Schmitt trigger:** positive feedback creates hysteresis — converts noisy analog signals to clean digital.

### Falstad Lab Prep

1. Build an inverting amplifier ($R_1 = 1\,\text{k}\Omega$, $R_f = 10\,\text{k}\Omega$). Apply 0.5 V DC input. Verify $V_{out} = -5\,\text{V}$.
2. Switch to non-inverting. Verify gain = $1 + R_f/R_1 = 11$.
3. Build an integrator. Apply a 1 kHz square wave. Observe the triangular output.
4. Build a Schmitt trigger (inverting type with positive feedback to $V_+$). Apply a slow sine wave. Observe sharp square wave output. Then add noise to the input and observe that the Schmitt trigger ignores it.

### Exam Traps

1. **Applying Golden Rules when output is saturated:** If the output hits the supply rail, $V_+ \neq V_-$ and the rules don't apply. Check for saturation first.
2. **Positive vs. negative feedback:** Inverting amplifier uses negative feedback (stable, controlled gain). Schmitt trigger uses positive feedback (bistable, switching). Using positive feedback "accidentally" in an amplifier circuit creates an oscillator, not an amplifier.
3. **Integrator DC drift:** A real integrator with DC offset at input will slowly ramp until output saturates. Real circuits use a large resistor in parallel with $C$ to limit DC gain.
4. **Virtual short vs. actual short:** The virtual short ($V_- = V_+$) means the voltage difference is zero — but no physical wire connects them. You cannot bypass this by drawing a short circuit on paper.

---

<a name="chapter-8"></a>
## Chapter 8 — Digital Logic: Gates, Flip-Flops, Registers, Counters, Adders

### The Real-World Hook

When you type a key on your keyboard, a sequence of electrons causes billions of transistors in your CPU to switch states in fractions of a nanosecond, ultimately producing a character on your screen. Every step of that process — from keypress detection to character encoding to pixel rendering — is implemented in digital logic. This chapter is the bridge between the transistor switches of Chapter 6 and the computer architecture you may already study in your CS programme.

---

<a name="boolean-algebra-and-gates"></a>
### Boolean Algebra and Gates

Digital logic operates with two voltage levels: HIGH (logic 1, typically ~3.3 V or ~5 V) and LOW (logic 0, ~0 V). All operations are described by **Boolean algebra**.

**Basic Gates:**

| Gate | Symbol (text) | Boolean expression | Truth table (2 inputs) |
|------|--------------|-------------------|----------------------|
| AND | A · B | $Y = A \cdot B$ | 1 only if both A=1 and B=1 |
| OR | A + B | $Y = A + B$ | 1 if either A=1 or B=1 |
| NOT | $\bar{A}$ | $Y = \bar{A}$ | Inverts: 0→1, 1→0 |
| NAND | $\overline{A \cdot B}$ | $Y = \overline{AB}$ | Opposite of AND |
| NOR | $\overline{A + B}$ | $Y = \overline{A+B}$ | Opposite of OR |
| XOR | A ⊕ B | $Y = A\bar{B} + \bar{A}B$ | 1 if inputs differ |
| XNOR | $\overline{A \oplus B}$ | $Y = AB + \bar{A}\bar{B}$ | 1 if inputs are the same |

**Key Boolean identities:**

$$
A \cdot 0 = 0 \quad A \cdot 1 = A \quad A \cdot A = A \quad A \cdot \bar{A} = 0
$$

$$
A + 0 = A \quad A + 1 = 1 \quad A + A = A \quad A + \bar{A} = 1
$$

---

<a name="de-morgans-theorems"></a>
### De Morgan's Theorems

These are the most important simplification identities in Boolean algebra:

$$
\overline{A \cdot B} = \bar{A} + \bar{B}
$$

$$
\overline{A + B} = \bar{A} \cdot \bar{B}
$$

**In words:**
- The complement of a product is the sum of the complements.
- The complement of a sum is the product of the complements.

**How to apply:** To find the complement of a complex expression: invert the whole expression, swap AND↔OR, and invert each variable.

**Example:** $\overline{A \cdot B + C} = (\bar{A} + \bar{B}) \cdot \bar{C}$

> 💡 Insight: De Morgan's laws are how a NAND gate becomes equivalent to an OR gate with inverted inputs, and vice versa. This equivalence is used constantly in circuit optimisation.

---

<a name="nand-universality"></a>
### NAND is Universal

A **universal gate** can implement any Boolean function on its own. NAND (and NOR) are universal:

- **NOT from NAND:** Connect both inputs together: $\overline{A \cdot A} = \bar{A}$
- **AND from NAND:** NOT after NAND: $\overline{\overline{AB}} = AB$
- **OR from NAND:** Apply De Morgan: $A + B = \overline{\bar{A} \cdot \bar{B}}$ — use a NAND with inverted inputs (each input inverted by its own NAND-as-NOT)

**Why does this matter?** Chip manufacturers can build entire logic families using only one type of gate — simplifying fabrication. The original TTL (Transistor-Transistor Logic) 7400 series NAND chip powered early microcomputers.

---

<a name="flip-flops"></a>
### Flip-Flops

A **flip-flop** is a bistable memory element that stores one bit. Unlike combinational logic (output depends only on current inputs), flip-flops are **sequential** — output depends on current inputs AND past state.

#### SR Flip-Flop (Set-Reset)

| S | R | Q (next) | Q̄ | Notes |
|---|---|---------|---|-------|
| 0 | 0 | Q (hold) | Q̄ | Memory |
| 0 | 1 | 0 | 1 | Reset |
| 1 | 0 | 1 | 0 | Set |
| 1 | 1 | Forbidden | — | Invalid state |

> ⚠️ Warning: The S=1, R=1 state is forbidden in an SR flip-flop — both outputs would try to be 1 simultaneously, violating the Q and Q̄ complementary relationship. Real circuits behave unpredictably in this state.

#### D Flip-Flop (Data)

Captures and stores the value of $D$ on the rising edge of a clock:

| D | Q (after clock edge) |
|---|---------------------|
| 0 | 0 |
| 1 | 1 |

The D flip-flop eliminates the forbidden state of SR. It is the most common flip-flop in digital design. A register is simply $N$ D flip-flops sharing a clock.

#### JK Flip-Flop

The universal flip-flop — fixes the SR forbidden state by making J=K=1 cause the output to **toggle**:

| J | K | Q (next) | Operation |
|---|---|---------|-----------|
| 0 | 0 | Q | Hold |
| 0 | 1 | 0 | Reset |
| 1 | 0 | 1 | Set |
| 1 | 1 | $\bar{Q}$ | Toggle |

#### T Flip-Flop (Toggle)

A JK flip-flop with J and K tied together:

- T=0: hold
- T=1: toggle (output inverts on each clock edge)

Used in **frequency dividers** and **counters**.

---

<a name="registers"></a>
### Registers

A **register** is a group of $N$ D flip-flops sharing a common clock signal, storing $N$ bits simultaneously.

**Parallel load:** All $N$ bits are loaded in one clock cycle.

**Serial load (shift register):** Bits are shifted in one at a time, one per clock cycle. Useful for converting serial data (one wire, many clock cycles) to parallel data (many wires, one clock cycle) — this is how UART serial communication works.

---

<a name="counters"></a>
### Counters

#### 4-Bit Ripple Counter (Asynchronous)

Chain of 4 T flip-flops (or JK with J=K=1). The clock drives the first flip-flop; each subsequent flip-flop is clocked by the output of the previous.

- FF0 toggles every clock edge → output at $f_{CLK}/2$
- FF1 toggles at every FF0 toggle → output at $f_{CLK}/4$
- FF2 → $f_{CLK}/8$; FF3 → $f_{CLK}/16$

Output is a 4-bit binary count: 0000, 0001, 0010, ..., 1111, 0000, ...

**Limitation:** Each flip-flop propagates its output to the next with a delay. For high-speed circuits, this ripple delay accumulates, causing **glitches** — brief incorrect outputs during transitions.

#### Synchronous Counter

All flip-flops share the same clock. Logic gates determine when each flip-flop should toggle based on the current count. No ripple delay — all bits update simultaneously. Preferred for high-speed designs.

---

<a name="adders"></a>
### Adders

#### Half Adder

Adds two 1-bit numbers $A$ and $B$. Produces a Sum bit $S$ and Carry-out $C_{out}$:

$$
S = A \oplus B \quad \text{(XOR)}
$$

$$
C_{out} = A \cdot B \quad \text{(AND)}
$$

| A | B | S | $C_{out}$ |
|---|---|---|-----------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

#### Full Adder

Adds three 1-bit inputs: $A$, $B$, and Carry-in $C_{in}$:

$$
S = A \oplus B \oplus C_{in}
$$

$$
C_{out} = A \cdot B + C_{in}(A \oplus B)
$$

A full adder can be built from two half adders plus an OR gate.

#### Ripple Carry Adder

Chain $N$ full adders to add $N$-bit numbers. The carry-out of each stage feeds the carry-in of the next:

**Limitation:** The carry must "ripple" through all $N$ stages before the final result is valid. For a 32-bit adder, this is 32 full-adder delays. Modern CPUs use **carry lookahead adders** that predict carries in advance, dramatically reducing delay.

> 💻 CS Link: This chapter IS computer architecture at the gate level. Your CPU's Arithmetic Logic Unit (ALU) performs ADD, SUB, AND, OR, XOR operations using exactly these structures — full adder chains, XOR trees, and D flip-flop registers. Clock registers are why CPUs have a "clock speed." Every tick of that clock, data shifts through one stage of logic and is captured by registers. Understanding adder delay is why pipeline stages and branch prediction matter.

---

### Quick Recap

- **Boolean gates:** AND, OR, NOT, NAND, NOR, XOR. NAND is universal — can implement any logic function alone.
- **De Morgan's laws:** complement swaps AND↔OR and inverts each variable. Essential for simplification.
- **Flip-flops:** bistable memory elements. SR, D, JK, T — each stores one bit. D flip-flop is most common in design.
- **Registers** are banks of D flip-flops; **counters** chain T/JK flip-flops; ripple counters have glitch risk; synchronous counters are faster.
- **Half adder** adds 2 bits (Sum=XOR, Carry=AND). **Full adder** adds 3 bits (includes carry-in). Chain them for multi-bit addition.

### Falstad Lab Prep

1. Build a JK flip-flop in Falstad using NAND gates. Apply clock and verify toggle behaviour.
2. Chain 4 T flip-flops to make a 4-bit ripple counter. Clock manually or at 1 Hz. Observe each output toggling at half the frequency of the previous.
3. Build a half adder with an XOR gate and an AND gate. Verify the truth table manually.
4. Add a second half adder and an OR gate to make a full adder. Test all 8 input combinations.

### Exam Traps

1. **SR flip-flop forbidden state:** S=R=1 is forbidden — know this and know why. The JK flip-flop resolves this with the toggle state.
2. **Ripple counter glitches:** During transitions (e.g., 0111 → 1000), the outputs change at different times due to propagation delay, causing brief incorrect values. Synchronous counters avoid this.
3. **XOR vs. XNOR:** XOR is 1 when inputs differ; XNOR is 1 when inputs are the same. The extra N is easy to forget under exam pressure.
4. **Half adder can't handle carry-in:** Only a full adder has a carry-in. Chaining half adders doesn't give you a multi-bit adder — you need full adders from position 1 onward.

---

<a name="section-a"></a>
## Section A — Calculus in Electronics: A Compact Guide

You do not need to be a calculus expert to succeed in electronics. You need to recognise three patterns — derivatives, integrals, and exponentials — and understand what they mean physically.

---

### Derivatives: Rate of Change

A derivative $\frac{df}{dt}$ measures how fast a quantity changes with time. Geometrically, it is the slope of the $f$ vs. $t$ graph at a point.

**Where derivatives appear in electronics:**

**1. Current is the derivative of charge:**

$$
i(t) = \frac{dq}{dt}
$$

If charge increases steeply, current is large. If charge is constant, current is zero.

**2. Inductor voltage is the derivative of current:**

$$
v_L = L\frac{di}{dt}
$$

A large $di/dt$ (rapidly changing current, steep slope) produces a large inductor voltage. Constant current → zero voltage. This is why inductors oppose sudden changes.

**3. Capacitor current is the derivative of voltage:**

$$
i_C = C\frac{dv_C}{dt}
$$

A rapidly changing capacitor voltage drives a large current. Constant voltage → zero current. This is why capacitors block DC.

**Pattern to recognise:** When you see $L\,di/dt$ or $C\,dv/dt$, ask "how fast is this quantity changing?" A steep graph = large derivative = large response.

---

### Integrals: Accumulation

An integral $\int f\,dt$ measures the total accumulated quantity over time. Geometrically, it is the area under the $f$ vs. $t$ curve.

**Where integrals appear in electronics:**

**1. Charge is the integral of current:**

$$
q(t) = \int_0^t i(\tau)\,d\tau
$$

Total charge = area under the current-time curve. Even a small current flowing for a long time can accumulate significant charge (and energy).

**2. Energy stored in a capacitor:**

$$
W_C = \int_0^{V} qV\,dV = \frac{1}{2}CV^2
$$

The capacitor voltage builds up as charge accumulates — the energy is the integral of $V\,dq$.

**3. Op-amp integrator output:**

$$
V_{out} = -\frac{1}{RC}\int V_{in}\,dt
$$

The output is the running total of the input — the area under the input waveform grows over time.

**Pattern to recognise:** When you see an integral, ask "what has accumulated so far?" A large area under the curve = large accumulated quantity.

---

### Exponential Functions

The exponential $e^{-t/\tau}$ appears whenever a system decays toward equilibrium at a rate proportional to how far it currently is from equilibrium. This is the mathematical description of RC charge/discharge, RL transients, and first-order filter step responses.

**Key values to remember:**

| Time | $e^{-t/\tau}$ | $(1 - e^{-t/\tau})$ | Percentage of final |
|------|--------------|--------------------|--------------------|
| $\tau$ | 0.368 | 0.632 | 63.2% |
| $2\tau$ | 0.135 | 0.865 | 86.5% |
| $3\tau$ | 0.050 | 0.950 | 95.0% |
| $5\tau$ | 0.007 | 0.993 | ≈ 100% |

**Pattern for charging:** $v(t) = V_f(1 - e^{-t/\tau})$ — starts at 0, approaches $V_f$ asymptotically.

**Pattern for discharging:** $v(t) = V_0 e^{-t/\tau}$ — starts at $V_0$, decays to 0.

**The key property of exponentials you must know:**

$$
\frac{d}{dt}(e^{-t/\tau}) = -\frac{1}{\tau}e^{-t/\tau}
$$

The derivative of an exponential is itself times a constant. This is why exponentials are natural solutions to $v_L = L\,di/dt$ and $i_C = C\,dv/dt$.

**You do not need to solve differential equations from scratch.** You need to:
1. Recognise the pattern (RC, RL, first-order system)
2. Identify $\tau$ from the circuit
3. Write the appropriate exponential form
4. Evaluate at the time or percentage asked

---

<a name="section-b"></a>
## Section B — Falstad Circuit Simulator Quick-Start Reference

**Access:** [falstad.com/circuit](https://falstad.com/circuit) — runs entirely in a web browser, no installation needed.

---

### Adding Components

**Method 1 — Right-click menu:** Right-click anywhere on the canvas. A menu appears with all components. Select a component, then click-and-drag to place it.

**Method 2 — Draw menu:** Use the top menu bar: Draw → select component category → place.

**Commonly needed components and where to find them:**

| Component | Menu Path |
|-----------|-----------|
| Resistor | Draw → Passive Components → Resistor |
| Capacitor | Draw → Passive Components → Capacitor |
| Inductor | Draw → Passive Components → Inductor |
| Diode | Draw → Output Components → Diode |
| NPN Transistor | Draw → Transistors → NPN Transistor |
| Op-Amp | Draw → Active Components → Op-Amp (real) |
| DC Voltage Source | Draw → Sources → Voltage Source |
| AC Voltage Source | Draw → Sources → AC Voltage Source |
| Ground | Draw → Wiring → Ground |
| Wire | Draw → Wiring → Wire (or just drag from a node) |
| Oscilloscope | Draw → Outputs → Scope |

---

### Setting Component Values

Double-click any component to open its properties dialog. You can set:
- Resistance (Ω), Capacitance (F), Inductance (H)
- Source voltage (V) and frequency (Hz) for AC sources
- Transistor model parameters

**Entering values:** Use standard SI prefixes: `1k` = 1000 Ω, `100u` = 100 μF, `10m` = 10 mH, `470n` = 470 nF.

---

### Adding Probes and Oscilloscope

**Voltage probe:** Right-click on any wire or node → "Add Voltage to Scope." This adds that node's voltage to the built-in oscilloscope.

**Current probe:** Right-click on any component → "Add Current to Scope."

**Oscilloscope controls:** The scope appears at the bottom. Right-click on the scope panel to adjust the time scale and voltage scale. You can add multiple traces and distinguish them by colour.

---

### Simulation Controls

- **Play/Pause:** The simulation runs automatically when you open the simulator.
- **Speed slider:** Top right — slow down or speed up the simulation.
- **Reset:** Available in the Simulate menu.

---

### Exporting a Screenshot

- Right-click the canvas → "Copy as Image" (in some browsers)
- Or use your operating system's screenshot tool (Windows: Win+Shift+S; macOS: Cmd+Shift+4)
- For sharing circuits: File → "Export as Text" — saves the circuit as a text string you can paste and reload later.

---

### Common Simulation Mistakes and Fixes

| Problem | Likely Cause | Fix |
|---------|-------------|-----|
| Component shows as "not connected" (orange) | Wire not properly joined to component terminal | Zoom in; make sure the wire endpoint exactly meets the component terminal (green dot appears when connected) |
| All voltages are zero / simulation broken | Missing ground node | Every circuit needs at least one Ground node — add it and connect it to the negative terminal of your source |
| Short circuit warning / very large current | Voltage source directly across a wire with no resistance | Add a series resistor or check for unintended wire connections |
| Oscilloscope shows nothing | Probe added but component not in circuit, or time scale wrong | Right-click scope → adjust scale; verify probe connection |
| AC simulation looks wrong | Frequency too high or low for time scale | Adjust simulation speed and scope time scale to see several complete cycles |
| Transistor not switching | Base resistor too large (not enough base current) | Reduce $R_B$ or increase input voltage to exceed 0.7 V threshold |
| Op-amp output stuck at supply rail | Output saturated (input voltage too high, or wrong feedback) | Check feedback connection; verify input is within the linear range |

---

<a name="section-c"></a>
## Section C — Self-Assessment Questions

*These are exam-style questions for self-testing. No answers are provided — work through them independently, then verify using the coursebook, your notes, or Falstad.*

---

### Chapter 1 — Basic Concepts

1. **(Conceptual)** Explain why conventional current and electron flow are in opposite directions. Why do we use conventional current rather than electron flow in circuit analysis?

2. **(Conceptual)** A voltmeter has internal resistance of 10 MΩ. An ammeter has internal resistance of 0.01 Ω. Explain what would happen in each case if the connections were accidentally swapped (voltmeter put in series, ammeter put in parallel with a 1 kΩ resistor and a 9 V source).

3. **(Calculation)** A resistor has 15 V across it and 30 mA flowing through it. Calculate: (a) the resistance, (b) the power dissipated, (c) the energy consumed in 5 minutes.

4. **(Calculation)** A 240 V, 60 W light bulb: (a) calculate the operating current, (b) calculate the resistance at operating temperature, (c) calculate the energy consumed in one hour in both joules and kilowatt-hours.

5. **(Application)** Design a simple circuit to measure both the voltage across and the current through a 470 Ω resistor connected to a 5 V source. Draw the schematic, label instrument connections, and explain why you chose each meter's position.

---

### Chapter 2 — DC Circuits

1. **(Conceptual)** A capacitor is connected in series with a resistor and a DC source. Describe what happens to the current through the circuit and the voltage across the capacitor from the moment the switch is closed to steady state. What determines how long the transient lasts?

2. **(Conceptual)** An inductor is connected to a DC source and the current reaches steady state. The switch is suddenly opened. Describe what happens and why this can be dangerous.

3. **(Calculation)** In a circuit with two voltage sources ($V_1 = 12\,\text{V}$, $V_2 = 8\,\text{V}$) and three resistors ($R_1 = 4\,\Omega$, $R_2 = 6\,\Omega$, $R_3 = 3\,\Omega$) in a two-mesh configuration, use KVL mesh analysis to find the current in each mesh and the power dissipated in $R_2$.

4. **(Calculation)** An RC circuit has $R = 22\,\text{k}\Omega$ and $C = 47\,\mu\text{F}$. The capacitor is initially uncharged and connected to a 10 V source at $t = 0$. (a) Calculate $\tau$. (b) Find $v_C$ at $t = \tau$, $t = 2\tau$, $t = 5\tau$. (c) What is the energy stored in the capacitor at $t = 5\tau$?

5. **(Application)** You need to design an RC circuit that takes 2 seconds to charge to 63% of its final voltage. You have a 100 μF capacitor available. What resistor value do you need? Sketch the circuit and the charging curve.

---

### Chapter 3 — AC Circuits

1. **(Conceptual)** Explain, using the concept of impedance, why a capacitor passes high-frequency signals easily but blocks low-frequency and DC signals. Why is the opposite true for an inductor?

2. **(Conceptual)** What is the RMS value and why is it defined the way it is? Why would using the peak voltage for power calculations give an incorrect result?

3. **(Calculation)** A series RL circuit has $R = 1\,\text{k}\Omega$, $L = 50\,\text{mH}$, driven by $V = 10\sin(2000\pi t)$ V. (a) Calculate $\omega$. (b) Calculate $Z_L$ and the total impedance $|Z|$. (c) Calculate the amplitude and phase of the current.

4. **(Calculation)** Using the superposition principle, find the voltage across the 6 Ω resistor in a circuit with: $V_{s1} = 20\,\text{V}$ DC, $V_{s2} = 15\,\text{V}$ DC, $R_1 = 4\,\Omega$, $R_2 = 6\,\Omega$, $R_3 = 12\,\Omega$ arranged in a pi-network (draw your own topology and apply the method).

5. **(Application)** An audio engineer wants to block the 50 Hz power line frequency from a signal path while passing audio frequencies above 200 Hz. Describe what type of filter is needed, give an RC circuit that achieves this, and calculate the required component values.

---

### Chapter 4 — RLC Circuits and Resonance

1. **(Conceptual)** A series RLC circuit is tuned to resonance. The voltage measured across the capacitor is 50 times larger than the source voltage. Is this a violation of Kirchhoff's Voltage Law? Explain fully why this can happen.

2. **(Conceptual)** Explain the physical meaning of the Q-factor. If you have two resonant circuits — one with $Q = 5$ and one with $Q = 100$ — which would be more useful for selecting a radio station, and why?

3. **(Calculation)** A series RLC circuit has $R = 10\,\Omega$, $L = 100\,\text{mH}$, $C = 100\,\text{nF}$. (a) Find the resonant frequency $f_0$ in Hz. (b) Calculate the Q-factor. (c) Calculate the bandwidth $BW$ in Hz. (d) Find the approximate half-power frequencies.

4. **(Calculation)** A load draws 5 kW at a power factor of 0.6 lagging from a 230 V RMS supply. (a) Calculate the apparent power. (b) Calculate the reactive power. (c) Calculate the supply current. (d) What value of capacitor (connected in parallel with the load) would correct the power factor to 1.0? (Hint: the capacitor must supply the reactive power the load consumes.)

5. **(Application)** Design a band-pass filter centred on 10 kHz with a bandwidth of 1 kHz using a series RLC circuit with $R = 50\,\Omega$. Find the required $L$ and $C$ values.

---

### Chapter 5 — Semiconductors and Diodes

1. **(Conceptual)** Explain the formation of a depletion region at a P-N junction. What prevents the depletion region from growing without limit? How does forward biasing change the situation?

2. **(Conceptual)** Why does a silicon diode require approximately 0.7 V to begin conducting, while a germanium diode requires only about 0.3 V? What property of the material determines this threshold?

3. **(Calculation)** A half-wave rectifier uses a silicon diode (0.7 V drop) and has a load resistor of $R_L = 1\,\text{k}\Omega$. The AC input is $v_{in} = 12\sin(\omega t)$ V. (a) Find the peak output voltage. (b) Find the average output voltage (use $V_{avg} = V_{peak}/\pi$ for half-wave). (c) If a 1000 μF smoothing capacitor is added, estimate the ripple voltage at 50 Hz.

4. **(Calculation)** A Zener regulator circuit has a 9 V DC input, a series resistor $R_s = 100\,\Omega$, and a 5.1 V Zener diode. (a) Calculate the current through the Zener when no load is connected. (b) What is the maximum load current the circuit can supply while keeping the Zener in regulation (minimum Zener current ≈ 5 mA)?

5. **(Application)** Design a full-wave bridge rectifier for a DC power supply that must deliver 9 V DC at up to 500 mA to a load. Specify: the required AC input voltage (accounting for diode drops), the minimum capacitor value for a ripple of less than 0.5 V, and the minimum current rating for each diode.

---

### Chapter 6 — Transistors

1. **(Conceptual)** Explain why a small base current in an NPN BJT can control a much larger collector current. What physical property of the base region makes this possible?

2. **(Conceptual)** Compare the BJT and MOSFET as digital switches. What is the key advantage of the MOSFET that makes it dominant in modern CPUs? What happens at the gate in a MOSFET that does not happen at the base in a BJT?

3. **(Calculation)** An NPN transistor with $\beta = 150$ is used as a switch with $V_{CC} = 5\,\text{V}$ and $R_C = 1\,\text{k}\Omega$. (a) To saturate the transistor, what minimum $I_B$ is needed if $I_C(sat) = V_{CC}/R_C = 5\,\text{mA}$? (Use $I_B > I_C/\beta$.) (b) If $R_B = 10\,\text{k}\Omega$ and $V_{in} = 5\,\text{V}$, what is the actual $I_B$? (Assume $V_{BE} = 0.7\,\text{V}$.) (c) Is the transistor in saturation?

4. **(Calculation)** A common-emitter amplifier has $R_C = 4.7\,\text{k}\Omega$, $R_E = 470\,\Omega$, $V_{CC} = 12\,\text{V}$, and the voltage divider sets $V_B = 2.4\,\text{V}$. (a) Find $I_C$ (assume $V_{BE} = 0.7\,\text{V}$ and $I_E \approx I_C$). (b) Find $V_{CE}$. (c) Calculate the small-signal voltage gain magnitude.

5. **(Application)** You need to drive a 12 V, 200 mA relay coil from a 3.3 V microcontroller GPIO pin that can supply maximum 10 mA. Describe the transistor switching circuit needed (component types, approximate values), including any protection diode and its purpose.

---

### Chapter 7 — Operational Amplifiers

1. **(Conceptual)** State the two Golden Rules of op-amp analysis and explain the physical assumption that makes each rule valid. Under what condition do the rules break down?

2. **(Conceptual)** Explain the difference between positive feedback and negative feedback in op-amp circuits. What type of behaviour does each produce, and give one circuit example of each.

3. **(Calculation)** An inverting amplifier has $R_1 = 2.2\,\text{k}\Omega$ and $R_f = 47\,\text{k}\Omega$. (a) Calculate the closed-loop voltage gain. (b) If $V_{in} = 0.1\sin(1000t)$ V, write the expression for $V_{out}$. (c) If the op-amp supply is ±15 V, what is the maximum input voltage before clipping?

4. **(Calculation)** An op-amp integrator has $R = 10\,\text{k}\Omega$ and $C = 100\,\text{nF}$. A constant input of $V_{in} = 1\,\text{V}$ is applied. (a) How long does it take for the output to reach −5 V? (b) If $V_{in}$ is instead a 1 kHz square wave alternating between +1 V and −1 V, describe the output waveform and calculate its peak-to-peak amplitude.

5. **(Application)** A sensor produces a noisy 0–1 V signal that you need to convert to a clean digital signal (0 V or 5 V) compatible with a microcontroller. Describe the circuit topology, the op-amp configuration needed, and how to set the switching thresholds to give a hysteresis band of ±0.2 V centred on 0.5 V.

---

### Chapter 8 — Digital Logic

1. **(Conceptual)** Explain why a NAND gate is called a universal logic gate. Demonstrate, with Boolean algebra, how to implement an OR gate using only NAND gates.

2. **(Conceptual)** Compare a ripple counter and a synchronous counter. What is a glitch in the context of a ripple counter, and why doesn't it occur in a synchronous counter?

3. **(Calculation)** Using De Morgan's theorems, simplify the following Boolean expression: $\overline{(\bar{A} + B) \cdot (A + \bar{B})}$.

4. **(Calculation)** A 4-bit synchronous counter is clocked at 16 MHz. (a) What is the output frequency at the MSB (most significant bit)? (b) How many unique states does the counter cycle through? (c) Write out the binary sequence for the first 5 clock cycles.

5. **(Application)** Design a 4-bit ripple carry adder using full adder blocks. Show the connection between stages (how carry propagates). If each full adder has a propagation delay of 5 ns, what is the worst-case total delay for a 4-bit addition, and what does this mean for the maximum clock frequency of a circuit using this adder?

---

<a name="formula-index"></a>
## Formula Index

An alphabetically organised reference of every named formula in this coursebook, with the chapter where it is introduced.

---

| Formula Name | Expression | Chapter |
|-------------|-----------|---------|
| Active Power (AC) | $P = V_{rms} I_{rms} \cos\phi$ | Ch. 4 |
| Admittance | $Y = 1/Z$ | Ch. 4 |
| Apparent Power | $S = V_{rms} I_{rms}$ | Ch. 4 |
| Average value (half-wave) | $V_{avg} = 2V_m/\pi$ | Ch. 3 |
| Bandwidth (RLC) | $BW = \omega_0 / Q$ | Ch. 4 |
| BJT Current Gain | $I_C = \beta I_B$ | Ch. 6 |
| Boolean AND | $Y = A \cdot B$ | Ch. 8 |
| Boolean NAND | $Y = \overline{A \cdot B}$ | Ch. 8 |
| Boolean NOR | $Y = \overline{A + B}$ | Ch. 8 |
| Boolean NOT | $Y = \bar{A}$ | Ch. 8 |
| Boolean OR | $Y = A + B$ | Ch. 8 |
| Boolean XOR | $Y = A \oplus B = A\bar{B} + \bar{A}B$ | Ch. 8 |
| Capacitor charge/discharge | $v_C(t) = V_s(1-e^{-t/\tau})$; $v_C(t) = V_0 e^{-t/\tau}$ | Ch. 2 |
| Capacitor current | $i_C = C\,dv/dt$ | Ch. 2 |
| Capacitor energy | $W_C = \frac{1}{2}CV^2$ | Ch. 2 |
| Charge | $Q = CV$ | Ch. 2 |
| Charge-current relation | $i(t) = dq/dt$ | Ch. 1 |
| Common-emitter voltage gain | $A_v \approx -R_C/R_E$ | Ch. 6 |
| Complex impedance (capacitor) | $Z_C = 1/(j\omega C)$ | Ch. 3 |
| Complex impedance (inductor) | $Z_L = j\omega L$ | Ch. 3 |
| Complex impedance (resistor) | $Z_R = R$ | Ch. 3 |
| Current (definition) | $i = dq/dt$ | Ch. 1 |
| Cutoff frequency (RC filter) | $\omega_c = 1/(RC)$; $f_c = 1/(2\pi RC)$ | Ch. 4 |
| De Morgan's Law 1 | $\overline{A \cdot B} = \bar{A} + \bar{B}$ | Ch. 8 |
| De Morgan's Law 2 | $\overline{A + B} = \bar{A} \cdot \bar{B}$ | Ch. 8 |
| Diode Shockley Equation | $I = I_s(e^{V/nV_T} - 1)$ | Ch. 5 |
| Energy (general) | $W = Pt = VIt$ | Ch. 1 |
| Full adder carry-out | $C_{out} = AB + C_{in}(A \oplus B)$ | Ch. 8 |
| Full adder sum | $S = A \oplus B \oplus C_{in}$ | Ch. 8 |
| Half adder carry-out | $C_{out} = A \cdot B$ | Ch. 8 |
| Half adder sum | $S = A \oplus B$ | Ch. 8 |
| High-pass transfer function (RC) | $H(j\omega) = j\omega RC/(1+j\omega RC)$ | Ch. 4 |
| Inductor energy | $W_L = \frac{1}{2}LI^2$ | Ch. 2 |
| Inductor voltage | $v_L = L\,di/dt$ | Ch. 2 |
| Inverting amplifier gain | $V_{out}/V_{in} = -R_f/R_1$ | Ch. 7 |
| KCL (Kirchhoff's Current Law) | $\sum i_k = 0$ at any node | Ch. 2 |
| KVL (Kirchhoff's Voltage Law) | $\sum v_k = 0$ around any loop | Ch. 2 |
| Low-pass transfer function (RC) | $H(j\omega) = 1/(1+j\omega RC)$ | Ch. 4 |
| Non-inverting amplifier gain | $V_{out}/V_{in} = 1 + R_f/R_1$ | Ch. 7 |
| Ohm's Law | $V = IR$ | Ch. 1 |
| Ohm's Law (phasor form) | $\mathbf{V} = \mathbf{I}\mathbf{Z}$ | Ch. 3 |
| Op-amp integrator | $V_{out} = -\frac{1}{RC}\int V_{in}\,dt$ | Ch. 7 |
| Op-amp differentiator | $V_{out} = -RC\,dV_{in}/dt$ | Ch. 7 |
| Parallel resistance | $1/R_p = 1/R_1 + 1/R_2 + \cdots$ | Ch. 2 |
| Parallel resistance (two) | $R_p = R_1 R_2/(R_1+R_2)$ | Ch. 2 |
| Phasor representation | $\mathbf{V} = V_m\angle\phi = V_m e^{j\phi}$ | Ch. 3 |
| Power (DC) | $P = VI = I^2R = V^2/R$ | Ch. 1 |
| Power factor | $\cos\phi = P/S$ | Ch. 4 |
| Power triangle | $S^2 = P^2 + Q^2$ | Ch. 4 |
| Q-factor (series RLC) | $Q = \omega_0 L/R = (1/R)\sqrt{L/C}$ | Ch. 4 |
| Reactive power | $Q_{power} = V_{rms}I_{rms}\sin\phi$ | Ch. 4 |
| Resistor energy (DC) | $W = I^2Rt$ | Ch. 2 |
| Resonant frequency | $\omega_0 = 1/\sqrt{LC}$ | Ch. 4 |
| RMS value (sinusoid) | $V_{rms} = V_m/\sqrt{2}$ | Ch. 3 |
| Series resistance | $R_s = R_1 + R_2 + \cdots$ | Ch. 2 |
| Sinusoidal AC signal | $v(t) = V_m\sin(\omega t + \phi)$ | Ch. 3 |
| Summing amplifier | $V_{out} = -R_f(V_1/R_1 + V_2/R_2 + \cdots)$ | Ch. 7 |
| Thermal voltage | $V_T = kT/q \approx 26\,\text{mV}$ at 25°C | Ch. 5 |
| Time constant (RC) | $\tau = RC$ | Ch. 2 |
| Time constant (RL) | $\tau = L/R$ | Ch. 2 |
| Voltage (definition) | $V = W/Q$ | Ch. 1 |
| Voltage follower | $V_{out} = V_{in}$ | Ch. 7 |
| Voltage resonance | $V_L = V_C = Q \cdot V_s$ at resonance | Ch. 4 |

---

*End of Electronics Coursebook for Computer Science Students*

*Generated for study towards ≥ 80% written exam and ≥ 90% practical lab grades. Good luck — you've got this.*

