# Time dependent Advection-Diffusion-Reaction Equation Solver in FreeFEM

This project provides a FreeFEM implementation for solving the time dependent Advection-Diffusion-Reaction equation over a user-defined mesh. It is designed for flexibility and clarity, with modular configuration and automatic result generation for multiple refinement levels.

---

## 📁 Project Structure
```
.
├── README.md
└── src
    ├── TimeDependentADREquation.edp
    ├── config
    │   ├── functions.edp
    │   └── parameters.edp
    └── meshes
        ├── circle_mesh.edp
        └── square_mesh.edp
```
---

## 🧩 Description

The solver numerically solves the time dependent ADR equation using finite element discretization in space and the theta method in time on a mesh defined in the `meshes/` directory. Stabilization for advection dominated problems is performed via SUPG (Streamline-Upwind Petrov Galerkin) method. The script supports multiple levels of refinement, controlled via configuration files.

### ✅ Features

- Customizable meshes
- Modular parameter and function definitions
- Exact solution support (for error estimation)
- Automated refinement and error analysis
- Per-step solution output in the `Results/` folder

## ⚙️ How to Use

1. **Choose or modify a mesh** in the `meshes/` folder by modifying accordingly the first lines of the script.
2. **Configure parameters** in:
   - `config/parameters.edp` – e.g., list of `mesh refinements`, `timestep`, `theta` and more
   - `config/functions.edp` – e.g., `forcing term`, `Dirichlet data`, `exact solution` and more
3. **Run the solver**:
   ```bash
   FreeFem++ TimeDependentADREquation.edp
    ```
4. **Inspect Results**:
A `Results/` folder is created with solution plots for each refinement step.

---
### 📂 Example Mesh Files
1. `circle_mesh.edp`: Defines a mesh over the unit circle.
2. `square_mesh.edp`: Defines a mesh over the unit square.

Feel free to add or modify mesh files while maintaining the same .edp script format.

---

### 📈 Output
The code reports the error with respect to mesh refinement levels. This allows you to analyze convergence behavior.

---

Feel free to adapt or extend this code. Contributions are welcome.
For any questions, suggestions, or to report a bug, feel free to contact me at mattia.murachelli@mail.polimi.it

09/05/2025 — Mattia Murachelli

---