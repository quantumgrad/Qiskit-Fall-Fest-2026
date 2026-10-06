# ⚛️ Qiskit Fall Fest 2026

Welcome to the official repository for the **Qiskit Fall Fest 2026**! 
This repo will contain material and links to the needed resources for this years QFF. 

### Install Requirements
Install the latest stable version of Qiskit, the Aer simulator, and visualization utilities.
```bash
pip install qiskit qiskit-aer matplotlib jupyterlab
```

## 📂 Repository Structure

* 📁 **`notebooks/`** — Jupyter Notebooks containing learning material.
* 📄 **`README.md`** — Project overview and setup instructions (this file).


## 🛠️ Verify Your Setup (Bell State Example)

You can check if your environment is configured correctly by running this simple snippet to create quantum entanglement (a Bell State) in your notebook:

```python
from qiskit import QuantumCircuit
from qiskit_aer import AerSimulator

# 1. Create a Quantum Circuit with 2 qubits and 2 classical bits
qc = QuantumCircuit(2, 2)

# 2. Apply a Hadamard gate to qubit 0 (putting it into superposition)
qc.h(0)

# 3. Apply a CNOT gate (control: 0, target: 1) to entangle the qubits
qc.cx(0, 1)

# 4. Measure both qubits into the classical bits
qc.measure([0, 1], [0, 1])

# 5. Initialize the Aer simulator and run the circuit
simulator = AerSimulator()
job = simulator.run(qc, shots=1024)
result = job.result()

# 6. Print the measurement counts (should output ~50% '00' and ~50% '11')
counts = result.get_counts(qc)
print("Measurement Results:", counts)
```

## 🤝 Contributing

If you want to contribute your solutions or custom notebooks to this repository:
1. Create a new branch (`git checkout -b feature-your-name`).
2. Stage and commit your changes (`git commit -m "Add quantum simulation notebook"`).
3. Push to your branch (`git push origin feature-your-name`).
4. Open a **Pull Request** on GitHub for review.
5. This will be needed for our hackathon.


## 📝 License

This project is licensed under the **MIT License** 

