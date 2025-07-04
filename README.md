# PennyLane Quantum Computing Solutions

This repository contains my implementations and explorations of a series of quantum computing tasks using **[PennyLane](https://pennylane.ai/)**. The projects cover key concepts in quantum information processing such as quantum state preparation, entanglement, measurement methods, parameterized quantum gates, and variational optimization.

---

## 1. Bell State Circuit

I implemented a 2-qubit quantum circuit to generate a **Bell state**, which is a maximally entangled state.

- Used `qml.probs()` to extract and display the probability distribution of measurement outcomes.
- Additionally visualized the quantum statevector and sampled measurement results using `qml.sample()`.

The resulting probability distribution confirms equal likelihood of states `|00⟩` and `|11⟩`, demonstrating successful entanglement.

---

## 2. GHZ State for 4 Qubits

I built a quantum circuit to prepare the **GHZ state** 4 qubits:

- Applied Hadamard and chained CNOT gates for entanglement.
- Measured final states with `qml.probs(wires=[0, 1, 2, 3])`.

The results show probability concentrated on `|0000⟩` and `|1111⟩`, confirming creation of the 4-qubit GHZ state.

---

## 3. Rotation and Measurement Circuit

I designed a single-qubit rotation circuit using parameterized rotation gates (`qml.RX()`, `qml.RY()`, or `qml.RZ()`):

- Returned the expectation value of `PauliZ` via `qml.expval(qml.PauliZ(0))`.
- Varied the rotation angle across \([0, 2\pi]\) and plotted how the expectation value changes.

The expectation value follows sinusoidal behavior consistent with quantum rotation theory.

---

## 4. Variational Optimization

I implemented a variational quantum circuit with a trainable rotation parameter:

- Defined a cost function as the expectation value of `PauliZ`.
- Used PennyLane's `GradientDescentOptimizer` to minimize the cost function.
- Logged and plotted cost convergence over optimization steps.

The optimization successfully found the angle minimizing the cost, demonstrating variational algorithm principles.

---

## 5. Measurement Comparison

I constructed a 2-qubit circuit to compare three measurement methods:

- `qml.probs()` for exact probability distributions (deterministic).
- `qml.sample()` for shot-based measurement samples (stochastic).
- `qml.expval()` for expectation values of observables.

I analyzed and documented how their outputs differ, typical use cases, and why `qml.probs()` yields deterministic results whereas `qml.sample()` produces random outcomes, reflecting physical quantum measurement behavior.

---

## Author

**Tamrat Demse**  
ML and Quantum computing enthusiast .

---

## Feedback and Contributions

I welcome suggestions, improvements
