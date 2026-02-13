# Structure and Stratigraphy Oriented Smoothing (SOS)

## Overview
This repository implements **Structure- and Stratigraphy-Oriented Smoothing (SOS)** for 3D seismic images. The core algorithm is based on **Fast Explicit Diffusion (FED)**, which provides an efficient way to perform anisotropic diffusion, enhancing seismic reflectors while preserving and even sharpening structural features like faults and stratigraphic features like channels.

Original Author: **Xinming Wu**  
Original Repository: [xinwucwp/sos](https://github.com/xinwucwp/sos)  
Reference Paper: [Detecting faults and channels while enhancing seismic structural and stratigraphic features](https://library.seg.org/doi/abs/10.1190/int-2017-0174.1).

## Implementation Details
The project is originally written in Java, leveraging the **Mines Java Toolkit (JTK)** for high-performance digital signal processing and visualization.

### Key Components:
- **Fast Explicit Diffusion (FED)**: A cyclic scheme for PDE-based image analysis that allows for larger time steps than standard explicit schemes.
- **Anisotropic Diffusion**: Smoothing is directed along seismic structures (reflectors) using structure tensors.
- **Nonlinear Diffusion**: Diffusivity is reduced near faults and channels to avoid smoothing across these features.

## Usage (Original Java/JTK version)
1. **Compilation**: Use Gradle to build the project.
   ```bash
   ./gradlew build
   ```
2. **Execution**: Run the provided Jython scripts in the `src/sos` directory. These scripts require a JTK-enabled environment.
   - `fed2.py`: 2D FED smoothing examples.
   - `fed3.py`: 3D FED smoothing examples.

## Python (PyTorch) Version Requirements
To run a modern Python version of this code with GPU acceleration (specifically for NVIDIA GPUs like the A5000), the following libraries are required:
- `torch`: For tensor operations and GPU acceleration (CUDA).
- `numpy`: For fundamental array handling.
- `scipy`: For advanced filtering and signal processing.
- `matplotlib`: For visualization.
- `segyio`: For handling SEG-Y seismic data formats.

Refer to the `pyproject.toml` or the `uv` environment setup for a complete list of dependencies.

## Citation
If you find this work helpful in your research, please cite:
```bibtex
@article{wu2019detect,
    author = {Xinming Wu and Zhenwei Guo},
    title = {Detecting faults and channels while enhancing seismic structural and stratigraphic features},
    journal = {INTERPRETATION},
    volume = {7},
    number = {1},
    pages = {T155-T166},
    year = {2019},
    doi = {10.1190/INT-2017-0174.1},
    URL = {https://library.seg.org/doi/abs/10.1190/int-2017-0174.1},
}
```
