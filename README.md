# Optimal Control of Inverted Pendulum: LQR and LQI

An interactive Pluto notebook demonstrating optimal feedback control design (LQR and LQI) for the inverted pendulum system.

## Quick Start

### Prerequisites

- **Julia 1.7+** installed on your system

### Installation & Setup

#### 1. Install Julia

Download and install Julia from [julialang.org](https://julialang.org/downloads/).

**Verify installation:**
```bash
julia --version
```

#### 2. Clone or Download the Repository

```bash
# If using git
git clone <repository-url>
cd LQI_ECE515_project

# Or manually download the files and navigate to the folder
```

#### 3. Open Julia and Install Required Packages

From the command line, start Julia:
```bash
julia
```

In the Julia REPL, press `]` to enter package mode, then:
```julia
pkg> add PlutoUI Symbolics ControlSystems DifferentialEquations LinearAlgebra Plots
```

This will install all required dependencies. The process may take 2-5 minutes on first installation.

**Verify packages installed:**
```julia
pkg> status
```

Press backspace to exit package mode.

#### 4. Install and Run Pluto

Still in the Julia REPL:
```julia
julia> using Pluto
julia> Pluto.run()
```

This will open a browser window with the Pluto interface.

#### 5. Open the Notebook

In the Pluto browser interface:
1. Click **"Open a notebook"**
2. Navigate to `Claude_LQI.jl` and select it
3. The notebook will load and execute

**Alternative (single command):**
```julia
julia> import Pluto; Pluto.open("path/to/Claude_LQI.jl")
```

### Running the Notebook

Once the notebook loads:
- **All cells execute automatically** as you scroll
- **Use the interactive sliders** to vary control parameters:
  - $Q_{11}$: Position penalty
  - $Q_{33}$: Angle penalty  
  - $R$: Control cost
  - $\theta_0$: Initial angle
- **Observe real-time plots** showing system response for both linear and nonlinear dynamics

## What You'll See

The notebook demonstrates:

1. **Equations of Motion**: Symbolic derivation using Lagrangian mechanics
2. **System Linearization**: Linear approximation around equilibrium
3. **LQR Control**: Optimal regulator design minimizing a quadratic cost function
4. **LQI Control**: Extended controller with integral action for tracking and disturbance rejection
5. **Interactive Visualization**: Comparison of linear vs. nonlinear responses under varying cost parameters

## Troubleshooting

**Issue: Packages fail to install**
- Ensure you're in package mode (press `]` in Julia REPL)
- Try: `pkg> update` then retry installation

**Issue: Pluto fails to start**
- Verify PlutoUI is installed: `using PlutoUI` in REPL
- Update all packages: `pkg> update`

**Issue: Notebook runs slowly**
- First execution is slower (JIT compilation); subsequent runs are faster
- Ensure sufficient RAM (2+ GB recommended)

**Issue: Permission denied when running Julia**
- On macOS/Linux: Make sure Julia is in your PATH
  ```bash
  export PATH="/Applications/Julia-1.x.app/Contents/Resources/julia/bin:$PATH"
  ```

## System Requirements

- **RAM**: 2+ GB
- **Disk Space**: ~1 GB (for Julia + packages)
- **Internet**: Required for initial package download
- **Operating System**: macOS, Linux, or Windows

## Package Descriptions

- **Pluto.jl**: Reactive notebook environment
- **PlutoUI.jl**: Interactive sliders and widgets
- **Symbolics.jl**: Symbolic mathematics and equation solving
- **ControlSystems.jl**: Control theory algorithms (LQR, Riccati)
- **DifferentialEquations.jl**: Numerical ODE solving
- **LinearAlgebra.jl**: Matrix operations
- **Plots.jl**: Visualization and plotting

## Next Steps

Once running:
- Experiment with different $Q$ and $R$ values to understand control trade-offs
- Increase $\theta_0$ to see when linearization becomes inaccurate
- Compare LQR vs. LQI performance with and without disturbances

## Questions or Issues?

Refer to the notebook's markdown sections for detailed explanations of the control theory and implementation.
