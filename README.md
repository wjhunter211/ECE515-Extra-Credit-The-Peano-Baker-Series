# The Peano-Baker Series

In control theory, the solution to the state at every point in time is given by the **variation-of-constants formula**.



For LTI systems, the solution involves the **matrix exponential**:

$$
x(t) = e^{At} x_0 + \int_{t_0}^{t} e^{A(t-s)} B u(s) ds
$$



For LTV systems, the solution involves the **state transition matrix (STM)**, denoted by $\phi$:

$$
x(t) = \phi(t, t_0) x_0 + \int_{t_0}^{t} \phi(t, s) B(s) u(s) ds
$$



The STM for an LTV system is computed using the **Peano–Baker series**, a nested sequence of integrals of A(t):
$$\phi(t, t_0)=I+\int_{t_0}^{t}A(s_1)ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)ds_2ds_1+\int_{t_0}^{t}A(s_1)\int_{t_0}^{s_1}A(s_2)\int_{t_0}^{s_2}A(s_3)ds_3ds_2ds_1+\cdots$$
This limit exists and the series is guaranteed to converge to a solution as long as A(t) is element-wise continuous. 
##
