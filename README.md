# Quantum Advantage with Shallow Circuits

Implementation of the quantum advantage demonstration based on the groundbreaking research paper:

**Bravyi, S., Gosset, D., & König, R. (2018). "Quantum advantage with shallow circuits." Science, 362(6412), 308-311.**  
DOI: [10.1126/science.aar3106](https://doi.org/10.1126/science.aar3106)

## Overview

This project demonstrates a rigorous proof of quantum advantage using **constant-depth quantum circuits** that can solve problems requiring **growing-depth classical circuits**. Unlike previous quantum advantage demonstrations, this work:

- ✅ Uses **shallow circuits** (constant depth, NISQ-friendly)
- ✅ Requires only **nearest-neighbor connectivity** (matches real hardware)
- ✅ Provides a **mathematically rigorous proof** of separation
- ✅ Works on **near-term quantum devices** (no error correction needed)

### Key Result

- **Quantum circuits**: O(1) constant depth (typically 4-5 layers)
- **Classical circuits**: Ω(√n) depth lower bound (grows with problem size)
- **Separation**: Exponential advantage that increases with system size

## Problem: 2D Hidden Linear Function (HLF)

The implementation solves the **2D Hidden Linear Function problem**:
- n qubits arranged in a 2D grid
- Compute a linear function f(x) with nearest-neighbor constraints
- Quantum achieves constant depth; classical requires depth proportional to √n

## Project Structure

```
qc/
├── README.md                          # This file
├── quantum_shallow_circuits.ipynb     # Main implementation notebook
├── science.aar3106 (1).pdf           # Original research paper
├── README.txt                         # Detailed setup instructions
└── COMPLETE_EXPLANATION_GUIDE.txt    # Comprehensive explanation guide
```

## Quick Start

### Option 1: Google Colab (Recommended)

1. Upload `quantum_shallow_circuits.ipynb` to Google Drive
2. Right-click → "Open with" → "Google Colaboratory"
3. Run all cells (Runtime → Run all)
4. Dependencies are automatically installed in the first cell

### Option 2: Local Jupyter Notebook

1. Install dependencies:
```bash
pip install qiskit>=0.40.0 qiskit-aer>=0.11.0 matplotlib>=3.5.0 numpy>=1.21.0 scipy>=1.7.0 pandas>=1.3.0 networkx>=2.6.0 seaborn>=0.11.0
```

2. Open the notebook:
```bash
jupyter notebook quantum_shallow_circuits.ipynb
```

3. Run all cells

## Requirements

All packages are auto-installed in the notebook, but for local setup:

- **qiskit** >= 0.40.0 - Quantum circuit framework
- **qiskit-aer** >= 0.11.0 - Quantum simulator
- **matplotlib** >= 3.5.0 - Visualization
- **numpy** >= 1.21.0 - Numerical computing
- **scipy** >= 1.7.0 - Scientific computing
- **pandas** >= 1.3.0 - Data analysis
- **networkx** >= 2.6.0 - Graph algorithms
- **seaborn** >= 0.11.0 - Statistical visualization

## Features

### Implementation

- **QuantumGrid2D**: 2D qubit grid structure with nearest-neighbor connectivity
- **ShallowQuantumCircuit**: Constant-depth quantum circuit implementation
- **Classical Circuit Simulation**: Bounded fan-in classical circuits for comparison
- **Performance Analysis**: Comprehensive comparison across multiple grid sizes

### Visualizations

- 2D qubit grid layout
- Circuit depth comparison (quantum vs classical)
- Measurement outcome distributions
- Parity analysis plots
- Quantum advantage growth charts
- Asymptotic scaling analysis
- Circuit scaling metrics

### Analysis

- Depth comparison across grid sizes (2×2 to 5×5)
- Execution time measurements
- Gate count analysis
- Efficiency metrics
- Statistical verification

## Expected Runtime

- **Complete notebook**: 5-10 minutes (depends on resources)
- **Individual sections**: 30 seconds - 2 minutes each
- **First run** (with installation): Add 1-2 minutes

## Key Concepts

### Circuit Depth
Maximum number of gate layers from input to output. Quantum circuits maintain constant depth (~4-5 layers) regardless of qubit count.

### Nearest-Neighbor Connectivity
Qubits can only interact with their immediate neighbors in the 2D grid, matching constraints of real quantum hardware.

### Quantum Advantage
The exponential separation between quantum O(1) depth and classical Ω(√n) depth, proven mathematically and demonstrated experimentally.

## Results

The implementation demonstrates:

1. **Constant Quantum Depth**: Quantum circuits maintain ~5 layers for all grid sizes
2. **Growing Classical Depth**: Classical circuits require depth proportional to √n
3. **Increasing Advantage**: Quantum advantage ratio grows from 1.5× to 5× as system size increases
4. **NISQ-Friendliness**: Shallow circuits are robust against decoherence

## Theoretical Background

This work proves a separation between complexity classes:
- **QNC⁰**: Problems solvable by constant-depth quantum circuits
- **NC⁰**: Problems solvable by constant-depth classical circuits

The paper proves: **QNC⁰ ⊋ NC⁰** (quantum strictly contains classical)

Specifically, the 2D Hidden Linear Function problem is in QNC⁰ but not in NC⁰.

## Citation

If you use this implementation in your work, please cite:

1. **Original Paper**:
   ```
   Bravyi, S., Gosset, D., & König, R. (2018). Quantum advantage with 
   shallow circuits. Science, 362(6412), 308-311.
   ```

2. **This Implementation**:
   ```
   Quantum Advantage with Shallow Circuits - Qiskit Implementation
   Available at: [Your repository URL]
   ```

## Troubleshooting

**Package installation fails**: Run the first cell again. Colab sometimes needs a retry.

**Out of memory**: Reduce grid sizes in comparison sections. Use smaller values like `[(2,2), (3,3)]` instead of larger grids.

**Plots not displaying**: Ensure you're running in Colab or have proper matplotlib backend configured.

**Slow execution**: Normal for quantum simulations. Larger grid sizes take longer. Reduce `num_trials` parameter for faster testing.

## Customization

You can modify:
- **Grid sizes**: Change `(rows, cols)` tuples in comparison sections
- **Number of shots**: Modify `shots` parameter in `execute_circuit()`
- **Number of trials**: Adjust `num_trials` in comparison functions
- **Visualization styles**: Modify matplotlib/seaborn parameters

## Hardware Compatibility

This implementation can run on:
- **IBM Quantum**: 27+ qubit superconducting chips
- **Google Sycamore**: 53 qubit processors
- **IonQ**: Trapped ion quantum computers
- **Rigetti**: Superconducting quantum processors

Circuit requirements: 9-25 qubits, depth 5, nearest-neighbor gates only.

## Additional Resources

- **Original Paper**: See `science.aar3106 (1).pdf`
- **Detailed Guide**: See `COMPLETE_EXPLANATION_GUIDE.txt`
- **Setup Instructions**: See `README.txt`
- **Qiskit Documentation**: https://qiskit.org/documentation/

## License

This implementation is for educational and research purposes. Based on publicly available research from Science journal.

## Acknowledgments

This implementation is based on the groundbreaking work by Bravyi, Gosset, and König. Special thanks to the Qiskit community for providing excellent quantum computing tools.

---

**Enjoy exploring quantum advantage with shallow circuits!** 🚀

# quantumPaper
