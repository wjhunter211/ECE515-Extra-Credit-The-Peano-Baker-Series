# The Peano-Baker Series: Introduction

In control theory, the solution to the state at every point in time is given by the **variation-of-constants formula**.



For LTI systems, the solution involves the **matrix exponential**:

$$
x(t) = e^{A(t-t_0)} x_0 + \int_{t_0}^{t} e^{A(t-s)} B u(s) ds
$$



For LTV systems, the solution involves the **state transition matrix (STM)**, denoted by $\phi$:

$$
x(t) = \phi(t, t_0) x_0 + \int_{t_0}^{t} \phi(t, s) B(s) u(s) ds
$$



The STM for an LTV system is computed using the **Peano–Baker series**, a nested sequence of integrals of A(t):

$$
\phi(t, t_0)=I+\int_{t_0}^{t}A(s_1)ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)ds_2ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)\int_{t_0}^{s_2}A(s_3)ds_3ds_2ds_1+\cdots
$$


In compact form, we can write the following:


$$
k=0, \quad M_0(t,t_0)=I
$$

$$
k \geq 1, \quad M_k(t,t_0)=I+\int^{t}_{t_0}A(s)M_{k-1}(s,t_0)ds
$$

$$
\phi(t,t_0)=\lim_{k\rightarrow \infty} M_k(t,t_0)
$$

This limit exists and the series is guaranteed to converge to a solution as long as A(t) is element-wise continuous. Note that if one plugs in a time-invariant A into the Peano-Baker Series, the solution will converge to $\phi(t,t_0)=e^{A(t-t_0)}$, therefore recovering the LTI variation-of-constants formula. 

# Summary of Content/Results

This repository contains a Jupyter Notebook in Python that takes a system matrix A, a desired number of terms, and integration bounds as inputs to compute the state-transition matrix via the Peano-Baker Series. The program will allow LTI and LTV inputs, print partial sums to show convergence as terms are added, and plot each element of $\phi$ over time to show behavior. The instructions and documentation will be presented in the form of comments throughout the code so that the user is able to follow along with each section. 
