---
geometry:
- margin=1.25in
mainfont: Palatino
header-includes: 
- \usepackage[document]{ragged2e}
---

# Assignment 7

### Instructions
- PHY411: Do problems 1–3.
- PHY 506: Do all four problems.

Accept the assignment from github classroom: https://classroom.github.com/a/pkol8Ur-. This will create a new repository for you on github, titled something like `compphys-assignment7-username`.
You should submit your code through github classroom, and your writeup through UBLearns. If you prefer, you can do your writeup "in-line" in your notebooks (using Markdown cells), convert the notebook to HTML/PDF/etc., and upload the converted notebooks.


\newpage


## Problem 1: diffusion
*20 points*

Start from the `RandomNumbers/random_walkers.ipynb` notebook in the CompPhys repository (the relevant parts have been copied to the notebook `Problem1/Problem1.ipynb` here).

Do your work in `Problem1/Problem1.ipynb`.


### Problem 1a: more dimensions
*10 points*

In class, we covered a 1D random walk. In this notebook, simulate and plot the random walk in 1, 2, and 3 dimensions. For 1D, the walker steps either left or right; in the program, the step is sample randomly from the set `[-1, 1]`. For this problem, in more than 1 dimension, the walker should take a step of length 1 along a single axis (i.e. you should *not* have the walker move in more than one dimension for a given step). 

For plotting:

- In 1D, plot the walker's position versus the step number.
- In 2D and 3D, just plot the spatial coordinates (no need to plot step number).
- For a 3D plot, you might consider using the following example: [scatter3d](https://matplotlib.org/stable/gallery/mplot3d/scatter3d.html) . Feel free to use what you like. 

### Problem 1b: diffusion
For $N_{dim}=1$, $2$, and $3$ dimensions, plot the quantity $\langle | x_n^2 | \rangle$ versus $N_{dim}$. For each $N_{dim}$, calculate the diffusion constant from your simulation, and compare with theoretical expectations. 

\newpage


## Problem 2: Ising model
*30 points*

Start from the `RandomNumbers/ising.ipynb` notebook in the CompPhys repository (the notebook has been copied here). Do your work in `Problem2/Problem2.ipynb`.

### Problem 2a
*10 points*

First, let's explore the effect of various parameters in the simulation. Recall that sudden reversals of the magnetization occur occasionally in systems of finite size. What is a reasonable value of `L` (number of spins per axis) to be chosen to maintain one single domain, versus flipping throughout? What value of `Nskip` (the number of spins flipped between each sample, aka the number of Metropolis-Hastings steps in between recorded samples) do you need to ensure an appropriate MC simulation? Show a plot of the average magnetization per spin at temperature T = 2.0 for various values of `L` and `Nskip`, and describe the result in your writeup.


### Problem 2b
*10 points*

Recall from the lectures that the analytical solution of the 2D Ising model predicts the following behavior of the average magnetization per spin: 

$$m\sim(T_C-T)^{\beta}$$. 

Starting from your simulation after part (a) (i.e. with a reasonable value of `L` and `Nskip`), re-run the simulation as a function of the temperature, $T$, and fit the resulting $\langle m \rangle$ versus $T$ for the the critical temperature, $T_C$, and the exponent, $\beta$. 


### Problem 2c
*10 points*

Similarly to part (b), use your simulation to compute the energy per spin as a function of $T$. Plot the result, and determine the heat capacity, $C=\frac{\partial E}{\partial T}$. 


\newpage

## Problem 3: computational fluid dynamics
*25 points*

Start from the `AdvDiffEq/16_Step_12.ipynb` notebook (it has been copied here). Repeat the calculation, but add a small rectangular obstruction in the center of the pipe of length $1/20$ and width $1/40$. What boundary conditions are needed? Plot the resulting vector field. 

You will have to modify your grid (space and time) to accommodate this new feature. Keep in mind the CFL condition!


\newpage

## Problem 4: cosmic inflation
*25 points*

**PHY506 students only**

There is no code for you to start from explicitly. But, you can use `planetary.ipynb`, for example,
as an inspiration.

Assume space is completely flat ($k=0$), and set $R(t) = 1$ at the present time. You may work in
scaled units of the density and pressure, as we did in class. The Friedmann equations are written:

$$
\begin{aligned}
H^2 &= \left(\frac{\dot{R}}{R}\right)^2 = \frac{8\pi G}{3}\rho \\
\dot{H} + H^2 &= \left(\frac{\ddot{R}}{R}\right) = -\frac{4\pi G}{3} (1+3w) \rho \\
\textrm{with } \dot{\rho} &= -3 H (1+w) \rho
\end{aligned}
$$

### Problem 4a
*10 points*

Solve this analytically for $w=0$, $1$, and $-1/3$. 


### Problem 4b
*15 points*

Solve this numerically with an adaptive RK4 scheme for $w=0$, $1$, and $-1/3$. Compare your results to the analytical solution. 


