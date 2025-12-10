# The Peano-Baker Series: Introduction

In control theory, the solution to the state of a dynamical system with control input $u$ is given by the **variation-of-constants formula**.



For linear-time-invariant (LTI) systems, the solution involves the **matrix exponential**:

$$
x(t) = e^{A(t-t_0)} x_0 + \int_{t_0}^{t} e^{A(t-s)} B u(s) ds
$$



For linear-time-variant (LTV) systems, the solution involves the **state transition matrix (STM)**, denoted by $\phi$:

$$
x(t) = \phi(t, t_0) x_0 + \int_{t_0}^{t} \phi(t, s) B(s) u(s) ds
$$



The STM for an LTV system is computed using the **Peano–Baker series**, which consists of nested integrals of A(t):

$$
\phi(t, t_0)=I+\int_{t_0}^{t}A(s_1)ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)ds_2ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)\int_{t_0}^{s_2}A(s_3)ds_3ds_2ds_1+\cdots
$$


The position of each argument in $\phi$ dictates the integral bounds. In compact form, we can write the following:


$$
k=0, \quad M_0(t,t_0)=I
$$

$$
k \geq 1, \quad M_k(t,t_0)=I+\int^{t}_{t_0}A(s)M_{k-1}(s,t_0)ds
$$

$$
\phi(t,t_0)=\lim_{k\rightarrow \infty} M_k(t,t_0)
$$

This limit exists and the series is guaranteed to converge to a unique solution as long as A(t) is element-wise continuous. Note that if one inputs a time-invariant A into the series, the solution will converge to $\phi(t,t_0)=e^{A(t-t_0)}$, thereby recovering the LTI variation-of-constants formula. Other relevant properties of the STM include $\phi(t,t)=I$, $\phi(t,t_0)=\phi(t,t_1)\phi(t_1,t_0)$ for some intermediate time $t_1$, and that $\phi$ is invertible for all time where $\phi(t,t_0)^{-1}=\phi(t_0,t)$. 

# Summary of Content/Results

This repository contains a Jupyter Notebook in Python that takes a system matrix A and number of terms as inputs to compute the state-transition matrix via the Peano-Baker series. The program will allow LTI and LTV inputs, print partial sums to show convergence as terms are added, and plot each element of $\phi$ over time to show behavior (the user can also change the plotting interval and resolution if desired). The instructions and documentation are presented in the form of comments throughout the code so that the user is able to follow along with each section; "Example" contains an instance of the code using the 2-dimensional identity matrix as an illustrative example, and "User Code" contains what the user should download (an LTV example appears by default so that the user immediately knows how the inputs should look). 
