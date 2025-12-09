# In control theory, the solution to the state at every point in time is given by the variation-of-constants formula. For linear-time-invariant (LTI) systems, it involves the matrix exponential as follows: 
$x(t)=e^{At}x_0+\int^{t}_{t_0}e^{A(t-s)}Bu(s)ds$
# However, for Linear-Time-Variant (LTV) systems, it involves the state transition matrix (STM), denoted as $\phi$:
$x(t)=\phi(t,t_0)x_0+\int^{t}_{t_0}\phi(t,s)B(s)u(s)ds$
# The primary way to determine it is by computing the Peano-Baker series: a series of nested integrals of A(t) as follows:
$\phi(t, t_0)=I+\int^{t}_{t_0}A(s)ds+\int^{t}_{t_0}A(s_1) \int^{s_1}_{t_0}A(s_2)ds_2ds_1$
