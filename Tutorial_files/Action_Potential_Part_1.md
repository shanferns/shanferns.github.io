---
title: "Introduction to Action Potentials (Part 1)"
date: 2025-11-15
layout: archive
categories: [tutorials]
permalink: /tutorials/APPart1/
intro : "This tutorial provides an overview of action potentials and highlights how their characteristics differ across regions—for example, between cortical neurons and various excitable organ cells. It also introduces how to implement action-potential models in code and reviews several commonly used modeling frameworks."
use_math: true
author_profile: true
toc: false
toc_label: "Table of Contents"
toc_sticky: true
---

## Table of Contents

1. [Introduction to Gastric Electrophysiology](#introduction-to-gastric-electrophysiology)
2. [Compartmental Modeling of the Stomach](#compartmental-modeling-of-the-stomach)
3. [Coding the Model in Jupyter](#coding-the-model-in-jupyter)
4. [References](#references)


This tutorial provides an overview of action potentials and highlights how their characteristics differ across regions—for example, between cortical neurons and various excitable organ cells. It also introduces how to implement action-potential models in code and reviews several commonly used modeling frameworks.

# The Neuron: The Brain's Messenger
A neuron is a specialized cell that transmits information. Think of it as the wiring of your body's electrical system.

Dendrites: These are branch-like extensions that receive signals from other cells.

Cell Body (Soma): This is the main part of the cell that processes the incoming information.

Axon: A long, slender cable that carries the signal (the action potential) away from the cell body over long distances.

Axon Terminal: The end of the axon, which transmits the signal to the next cell in the chain.

<img src="Neuron_figure.png" alt="Neuron" width="400">

## The Action Potential: The "Fire" Signal
An action potential is the signal itself—a rapid, all-or-nothing electrical impulse that travels down the axon. When we say a neuron "fires," we mean it's sending an action potential.

The entire process is about the movement of charged particles (ions), mainly sodium (Na+) and potassium (K+), across the neuron's membrane.

### 1. The Resting State (Ready)
When a neuron is "at rest" and waiting for a signal, it has a stable electrical charge of about -70 millivolts (mV). This is called the resting potential.

This negative charge is maintained because there are more positive sodium ions outside the cell and more positive potassium ions inside the cell.

The sodium-potassium pump actively works to keep it this way, like a bouncer keeping the crowds separated.

### 2. The Trigger (Threshold)
The neuron receives signals from its dendrites. If these signals are strong enough to push the cell's charge from -70mV up to a trigger point called the threshold (around -55mV), the action potential begins. It's "all-or-nothing"—if it doesn't hit the threshold, it doesn't fire. If it does, it fires completely.

### 3. Depolarization (Rising Action)
Once the -55mV threshold is hit, voltage-gated sodium (Na+) channels fly open.

Positive sodium ions (Na+) rush into the cell, causing the inside to become rapidly positive (up to +30mV). This massive change in charge is the action potential spike.

### 4. Repolarization (Falling Action)
At the peak, the sodium (Na+) channels close.

Slower voltage-gated potassium (K+) channels open.

Positive potassium (K+) ions rush out of the cell, making the inside negative again and bringing the charge back down.

### 5. Hyperpolarization (Overshoot)
The potassium channels are a bit slow to close, so the charge briefly dips even more negative than the resting potential. This "downtime" is called the refractory period, which ensures the signal can only travel in one direction (down the axon).

Finally, the sodium-potassium pump restores everything to its resting state, ready to fire again. This entire electrical signal then travels down the axon to the axon terminals, where it triggers the release of neurotransmitters to the next neuron.

To understand more about action potenials, please check the below link

[Figures that show how the gated channels function](https://speechneurolab.ca/en/action-potential/)
 
[To see how action potentials fire](https://nba.uth.tmc.edu/neuroscience/m/s1/chapter01.html)




## Different types of action potential

### 🎥 [Video 1 — Neuronal Action Potential (Part 1)](https://www.youtube.com/watch?v=pBOXHJQt-LI&ab_channel=AMBOSS%3AMedicalKnowledgeDistilled)


### 🎥 [Video 2 — Neuronal Action Potential (Part 2)](https://www.youtube.com/watch?v=zc-_HpszyIY&ab_channel=AMBOSS%3AMedicalKnowledgeDistilled)

<img src="Neuron action potential.png" alt="Neuron" width="400">

### 🎥 [Video 3 — Skeletal Muscle Action Potential](https://www.youtube.com/watch?v=4VOMadMSbrc&ab_channel=AMBOSS%3AMedicalKnowledgeDistilled)

<img src="Skeletal Muscle Action Potential.png" alt="Neuron" width="400">

### 🎥 [Video 4 — Cardiac Action Potentials](https://www.youtube.com/watch?v=2yFWs-_2rcw&t=4s&ab_channel=AMBOSS%3AMedicalKnowledgeDistilled)

<img src="Cardiac action potential.png" alt="Neuron" width="400">

# Differences between spike potential and potential with plateau

<img src="Neuron types new.png" alt="Neuron" width="400">

## Spike Potential

**Seen in:** Neurons and skeletal muscle fibers  

**Description:**  
A short, sharp depolarization followed by rapid repolarization.  
Represents a brief electrical event lasting only a few milliseconds.  
The membrane potential quickly rises due to influx of Na⁺ through voltage-gated sodium channels, and then falls as K⁺ efflux occurs.

**Key Features:**  
- **Duration:** ~1–2 ms  
- **Phases:** Rapid depolarization → rapid repolarization  
- **Function:** Triggers nerve impulses or muscle contraction  
- **Shape:** Narrow and sharp “spike”  

**Examples:**  
- Neuronal action potential  
- Skeletal muscle action potential  

---

## Potential with Plateau

**Seen in:**  
- Cardiac muscle (especially ventricular myocytes)  
- Gastric smooth muscle cells (SMC) during strong contractions  

**Description:**  
After initial depolarization, the membrane remains depolarized for an extended period before repolarizing — this is the plateau phase.  
In cardiac muscle, this plateau prolongs contraction to allow efficient blood ejection and prevent tetanus.  
In gastric SMC, a similar plateau may be observed during intense contractions, contributing to coordinated peristaltic movement.  
The plateau occurs due to a balance between inward Ca²⁺ current (via L-type calcium channels) and outward K⁺ current.

**Key Features:**  
- **Duration:** upto 1 sec; shorter in gastric SMC (~ 20 sec)  
- **Phases:** Depolarization → Plateau → Repolarization  
- **Function:**  
  - Cardiac: Sustains contraction for effective pumping  
  - Gastric SMC: Supports stronger, coordinated contractions for peristalsis  
- **Shape:** Broad, flat-topped waveform  

**Examples:**  
- Cardiac ventricular action potential  
- Cardiac muscle cells responsible for contraction  
- Gastric smooth muscle cells during strong phasic contractions

# The Hodgkin–Huxley Model and Neuronal Excitability  

The **Hodgkin–Huxley (HH) model** mathematically describes how neurons generate and propagate **action potentials** based on ionic currents through voltage-gated channels.  
It combines biophysical principles (ion gradients, membrane permeability) into a **system of coupled ODEs**.

---

## 1. Nernst Equation & Electrochemical Gradient  
🎥 [Science with Tal – Nernst Equation](https://www.youtube.com/watch?v=rJSJWosBJg0&ab_channel=ScienceWithTal)

### Concept:
The **Nernst equation** gives the **equilibrium potential** for a specific ion — the membrane voltage at which **no net ionic current** flows because the electrical and chemical gradients are balanced.

### Equation:
\begin{equation}
E_{ion} = \frac{RT}{zF} \ln\left(\frac{[ion]_{out}}{[ion]_{in}}\right)
\end{equation}

- $E_{ion}$: equilibrium (Nernst) potential for the ion (in volts)  
- $R$: gas constant (8.314 J/mol·K)  
- $T$: absolute temperature (Kelvin)  
- $z$: charge of the ion (e.g., +1 for K⁺, Na⁺)  
- $F$: Faraday’s constant (96485 C/mol)  
- $[ion]_{out}$, $[ion]_{in}$: extracellular and intracellular ion concentrations  

 **Interpretation:**  
If the membrane potential $V_m = E_{ion}$, that ion is in electrochemical equilibrium.  
Otherwise, the ion will flow in or out to move toward $E_{ion}$.

---

## 2. Goldman Equation & Resting Membrane Potential  
🎥 [Science with Tal – Goldman Equation](https://www.youtube.com/watch?v=YOFXkZu-r8M&t=498s&ab_channel=ScienceWithTal)

### Concept:
The **Goldman–Hodgkin–Katz (GHK) equation** extends the Nernst equation to include **multiple ions** with different permeabilities.  
It determines the **resting membrane potential (RMP)** of a neuron.

### Equation:
\begin{equation}
V_m = \frac{RT}{F} \ln \left( 
\frac{P_K [K^+]_{out} + P_{Na} [Na^+]_{out} + P_{Cl} [Cl^-]_{in}}
     {P_K [K^+]_{in} + P_{Na} [Na^+]_{in} + P_{Cl} [Cl^-]_{out}}
\right)
\end{equation}

- $V_m$: resting membrane potential  
- $P_{ion}$: permeability of the membrane to that ion  
- Note that for anions (like Cl⁻), the inside/outside terms are flipped.  

 **Typical neuron RMP:** ≈ **−70 mV**, mainly determined by **K⁺ permeability**.

---

## 3. Equivalent Circuit Model of a Neuron  
🎥 [Science with Tal – Equivalent Circuit](https://www.youtube.com/watch?v=LdumhvDBpzQ&ab_channel=ScienceWithTal)

### Concept:
A neuron can be represented electrically as an **RC circuit**:
- **Capacitor (Cₘ)** → lipid bilayer (stores charge)  
- **Resistors (1/gₖ, 1/gNa)** → ion channels (control ion flow)  
- **Batteries (Eₖ, ENa)** → Nernst potentials for each ion  

### Membrane Current Equation:
\begin{equation}
I_{ext} = C_m \frac{dV_m}{dt} + \sum I_{ion}
\end{equation}

and each ionic current:
\begin{equation}
I_{ion} = g_{ion}(V_m - E_{ion})
\end{equation}

- $I_{ext}$: external (stimulating) current  
- $C_m$: membrane capacitance  
- $g_{ion}$: conductance (1/resistance) of the ion channel  
- $E_{ion}$: equilibrium potential for that ion  

**Analogy:**  
Charging/discharging of the membrane is like charging a capacitor through resistors.

---

## 4. Hodgkin–Huxley Model of Voltage-Gated Channels  
🎥 [Science with Tal – Hodgkin-Huxley Model](https://www.youtube.com/watch?v=no_1cElnSIQ&ab_channel=ScienceWithTal)

### Concept:
The HH model describes how **voltage-gated Na⁺ and K⁺ channels** generate the **action potential** through dynamic changes in conductance.

### Core HH Equation:
\begin{equation}
C_m \frac{dV_m}{dt} = I_{ext} - (I_{Na} + I_{K} + I_{L})
\end{equation}

where:

\begin{aligned}
I_{Na} &= \bar{g}_{Na} m^3 h (V_m - E_{Na}) \\
I_{K} &= \bar{g}_{K} n^4 (V_m - E_{K}) \\
I_{L} &= \bar{g}_{L} (V_m - E_{L})
\end{aligned}


- $\bar{g}_{ion}$: maximal conductance  
- $m, h, n$: gating variables (probabilities of activation/inactivation)  
- $E_{ion}$: equilibrium potentials for each ion  

### Gating Variable Dynamics:
Each gating variable follows a **first-order ODE**:

\begin{equation}
\frac{dx}{dt} = \alpha_x(V)(1 - x) - \beta_x(V)x, \quad x \in \{m, h, n\}
\end{equation}

where $\alpha_x(V)$ and $\beta_x(V)$ are **voltage-dependent rate constants**.

### Action Potential Mechanism:
1. **Depolarization:** Na⁺ channels open rapidly → Na⁺ influx  
2. **Repolarization:** K⁺ channels open, Na⁺ channels inactivate → K⁺ efflux  
3. **Hyperpolarization:** Excess K⁺ outflow → membrane potential dips below rest  
4. **Return to RMP:** Gradually restored by leak currents

---

## 🧾 Summary Table

| Concept | Equation | Key Idea | Related Video |
|----------|-----------|-----------|---------------|
| **Nernst Equation** | $E_{ion} = \frac{RT}{zF}\ln\frac{[ion]_{out}}{[ion]_{in}}$ | Single ion equilibrium | [🔗](https://www.youtube.com/watch?v=rJSJWosBJg0&ab_channel=ScienceWithTal) |
| **Goldman Equation** | $V_m = \frac{RT}{F}\ln\frac{P_K[K^+]_{out}+P_{Na}[Na^+]_{out}+P_{Cl}[Cl^-]_{in}}{P_K[K^+]_{in}+P_{Na}[Na^+]_{in}+P_{Cl}[Cl^-]_{out}}$ | Multi-ion resting potential | [🔗](https://www.youtube.com/watch?v=YOFXkZu-r8M&t=498s&ab_channel=ScienceWithTal) |
| **Equivalent Circuit** | $I_{ext} = C_m \frac{dV_m}{dt} + \sum I_{ion}$ | Neuron as RC circuit | [🔗](https://www.youtube.com/watch?v=LdumhvDBpzQ&ab_channel=ScienceWithTal) |
| **Hodgkin–Huxley Model** | $C_m\frac{dV_m}{dt}=I_{ext}-(I_{Na}+I_{K}+I_{L})$ | Dynamic voltage-gated channels | [🔗](https://www.youtube.com/watch?v=no_1cElnSIQ&ab_channel=ScienceWithTal) |

---


# References

1. Wallisch, P., Lusignan, M. E., Benayoun, M. D., Baker, T. I., Dickey, A. S., & Hatsopoulos, N. G. (2014). MATLAB for neuroscientists: an introduction to scientific computing in MATLAB. Academic Press.
2. Cooper, D. C. (2011). Introduction to Neuroscience. Donald C. Cooper Ph. D..
3. HODGKIN AL, HUXLEY AF. A quantitative description of membrane current and its application to conduction and excitation in nerve. J Physiol. 1952 Aug;117(4):500-44. doi: 10.1113/jphysiol.1952.sp004764. PMID: 12991237; PMCID: PMC1392413.
4. https://www.youtube.com/@sciencewithtal
5. https://www.youtube.com/@ambossmedical
