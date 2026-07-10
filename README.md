# Mathematical Modelling and Numerical Simulation Projects

This repository is a collection of Jupyter notebooks exploring mathematical modelling, numerical methods, and scientific visualization. Each project develops a physical or mathematical problem from its governing equations to a numerical implementation and graphical output.

## Projects

### Fourier Epicycles

[`Fourier/epicycles.ipynb`](Fourier/epicycles.ipynb) reconstructs the outline of *Castel del Monte* using a discrete Fourier transform and visualizes the result as a chain of rotating epicycles.

The notebook covers:

- loading a planar curve from [`Fourier/castel_del_monte.csv`](Fourier/castel_del_monte.csv);
- uniform arc-length resampling;
- computation and verification of the discrete Fourier representation;
- selection of the largest Fourier coefficients;
- generation and optional MP4 export of the epicycle animation.

### Sliding Ball in a Bowl

[`Ball_in_a_bowl/sliding_ball_in_a_bowl.ipynb`](Ball_in_a_bowl/sliding_ball_in_a_bowl.ipynb) studies a finite-radius ball sliding without rolling inside an axisymmetric parabolic bowl.

The notebook develops:

- the bowl geometry and the normal-offset surface followed by the ball's center;
- a cylindrical-coordinate formulation;
- undamped and damped equations of motion;
- a four-dimensional state-space model;
- numerical integration with explicit Euler and classical RK4;
- contact constraints and admissible initial conditions;
- static and interactive trajectory visualizations.

Detailed mathematical derivations are included in the notebook appendices.

### Two Tanks Draining Problem

The tank study is divided into two notebooks:

- [`Tanks_problem/tanks.ipynb`](Tanks_problem/tanks.ipynb) derives the draining model from Torricelli's law and volume conservation, determines consistent tank dimensions and initial water levels, and compares the emptying of oppositely oriented conical-frustum tanks.
- [`Tanks_problem/tanks_part_2.ipynb`](Tanks_problem/tanks_part_2.ipynb) investigates whether the initial center of mass determines which tank empties first. It models tanks assembled from stacked conical frustums and searches for counterintuitive geometries using Differential Evolution.

The notebooks combine analytical derivations, root finding, numerical integration, optimization, and animations of the draining process.

## Repository Structure

```text
.
├── Ball_in_a_bowl/
│   └── sliding_ball_in_a_bowl.ipynb
├── Fourier/
│   ├── castel_del_monte.csv
│   └── epicycles.ipynb
├── Tanks_problem/
│   ├── images/
│   ├── tanks.ipynb
│   └── tanks_part_2.ipynb
└── README.md
```

## Requirements

The notebooks use Python 3 and the following packages:

```text
numpy
matplotlib
pandas
plotly
jupyter
```

Install them with:

```bash
python -m pip install numpy matplotlib pandas plotly jupyter
```

[FFmpeg](https://ffmpeg.org/) is optional and is only required when exporting Matplotlib animations as MP4 files.

## Running the Notebooks

Clone the repository, move into its root directory, and start Jupyter:

```bash
git clone <repository-url>
cd Projects
jupyter notebook
```

Open the notebook of interest and run its cells in order. Keeping the repository structure unchanged is recommended because some notebooks load data or images through relative paths.

The animations can be computationally and memory intensive. If a JavaScript animation exceeds Matplotlib's default notebook embedding limit, increase it before rendering:

```python
import matplotlib as mpl

mpl.rcParams["animation.embed_limit"] = 50  # MB
```

Alternatively, reduce the number of frames, frame rate, figure size, or export the animation as a video.

## Notes

- All physical quantities are expressed in SI units unless stated otherwise in a notebook.
- The notebooks are intended to be both computational experiments and self-contained mathematical explanations.
- Numerical results depend on the chosen discretization, integration step, and model parameters.
