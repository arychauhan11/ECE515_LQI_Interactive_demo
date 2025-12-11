# Optimal Control of Inverted Pendulum: LQR and LQI

An interactive Pluto notebook demonstrating optimal feedback control design (LQR and LQI) for the inverted pendulum system.

## Quick Start

### Installation & Setup (Automatic)

#### 1. Clone or Download the Repository

```bash
git clone <https://github.com/arychauhan11/ECE515_LQI_Interactive_demo>
cd LQI_ECE515_project
```

#### 2. Restore Project Environment (Recommended)

The repository includes `Project.toml` and `Manifest.toml` which specify the exact package versions used.

From the command line, start Julia in the project directory:
```bash
julia
```

In the Julia REPL, press `]` to enter package mode:
```julia
pkg> activate .
pkg> instantiate
```

This will automatically install all dependencies with their correct versions from `Manifest.toml`. The process may take 3-5 minutes on first installation.

**Verify packages installed:**
```julia
pkg> status
```

Press backspace to exit package mode.

#### 3. Run Pluto

Still in the Julia REPL:
```julia
julia> using Pluto
julia> Pluto.run()
```

This will open a browser window with the Pluto interface.

#### 4. Open the Notebook

In the Pluto browser interface:
1. Click **"Open a notebook"**
2. Navigate to `Claude_LQI.jl` and select it
3. The notebook will load and execute

**Alternative (single command):**
```julia
julia> import Pluto; Pluto.open("path/to/Claude_LQI.jl")
```

### Manual Package Installation (Fallback)

If the automatic restoration fails, manually install packages:

```julia
pkg> add PlutoUI Symbolics ControlSystems DifferentialEquations Plots
```

Then proceed to step 3 above.

### Running the Notebook

Once the notebook loads:
- **All cells execute automatically** as you scroll
- **Use the interactive sliders** to vary control parameters:
  - $Q_{11}$: Position penalty
  - $Q_{33}$: Angle penalty  
  - $R$: Control cost
  - $\theta_0$: Initial angle
  - Position setpoint and disturbance magnitude
- **Observe real-time plots** showing system response for both linear and nonlinear dynamics

### Run on the Cloud

You can also run this notebook on cloud platforms without local installation:

- **JuliaHub** (Official): [www.juliahub.com](https://www.juliahub.com) - Upload the notebook directly
- **Google Colab**: Install Julia via [juliaup](https://github.com/JuliaLang/juliaup) and upload the notebook
- **MyBinder**: Create a binder environment using `environment.yml` with the required packages

Simply upload `Claude_LQI.jl` to any of these platforms and run it interactively in your browser with no local setup required.

## What You'll See

The notebook demonstrates:

1. **Equations of Motion**: Symbolic derivation using Lagrangian mechanics
2. **System Linearization**: Linear approximation around equilibrium
3. **LQR Control**: Optimal regulator design minimizing a quadratic cost function
4. **LQI Control**: Extended controller with integral action for tracking and disturbance rejection
5. **Interactive Visualization**: Comparison of linear vs. nonlinear responses under varying cost parameters

## Troubleshooting

**Issue: `pkg> instantiate` fails**
- Ensure you're in the correct project directory with `Project.toml` and `Manifest.toml` present
- Try: `pkg> update` then retry `instantiate`
- If still failing, use manual installation above

**Issue: Packages fail to install manually**
- Ensure you're in package mode (press `]` in Julia REPL)
- Check internet connection is active
- Try: `pkg> add PlutoUI` individually to identify problematic packages

**Issue: Pluto fails to start**
- Verify PlutoUI is installed: `using PlutoUI` in REPL
- Restart Julia and try again

**Issue: Notebook runs slowly**
- First execution is slower due to JIT compilation; subsequent runs are faster
- Cloud platforms may be slower than local machines

## Project Structure

- **Claude_LQI.jl**: Main interactive notebook
- **Project.toml**: Package dependencies specification
- **Manifest.toml**: Exact versions of all dependencies (ensures reproducibility)
- **README.md**: This file
- **Claude_LQI backup 1.jl**: Backup of the notebook (optional)
- **LQR Pendulum Demo.jl**: Related demo (optional)

## Learning Outcomes

The notebook demonstrates:

1. **Equations of Motion**: Symbolic derivation using Lagrangian mechanics
2. **System Linearization**: Linear approximation around equilibrium
3. **LQR Control**: Optimal regulator design minimizing a quadratic cost function
4. **LQI Control**: Extended controller with integral action for tracking and disturbance rejection
5. **Interactive Visualization**: Real-time comparison of linear vs. nonlinear responses under varying parameters

## Next Steps

Once running:
- Experiment with different $Q$ and $R$ values to understand control trade-offs
- Increase $\theta_0$ to see when linearization becomes inaccurate
- Compare LQR vs. LQI performance with and without disturbances
- Adjust the position setpoint to see setpoint tracking

## Questions or Issues?

Refer to the notebook's markdown sections for detailed explanations of the control theory and implementation.
