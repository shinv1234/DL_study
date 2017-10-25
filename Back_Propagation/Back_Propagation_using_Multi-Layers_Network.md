# Back Propagation using Multi-Layers Network


$$ 
\frac{\partial E_n}{\partial w_{ji}^{(l)}} = \frac{\partial E_n}{\partial u_{j}^{(l)}} \frac{\partial u_{j}^{(l)}}{\partial w_{ji}^{(l)}}  
$$

$$ 
\frac{\partial E_n}{\partial u_{j}^{(l)}} = \sum_k \frac{\partial E_n}{\partial u_{k}^{(l+1)}} \frac{\partial u_{k}^{(l+1)}}{\partial u_{j}^{(l)}} 
$$

$$ 
\delta_j^{(l)} = \frac{\partial E_n}{\partial u_{j}^{(l)}} 
$$

$$ 
\delta_j^{(l)} = \sum_k \delta_{k}^{(l+1)} ( w_{kj}^{(l+1)}f^{\prime}(u_j^{(l)}) ) 
\quad (
\because \; u_{k}^{(3)} = \sum_j  w_{kj}^{(3)}z_j^{(l)} = \sum_j  w_{kj}^{(3)}f(u_j^{(2)}) 
\; , \;  \frac{\partial u_{k}^{(l+1)}}{\partial u_{j}^{(l)}} = w_{kj}^{(l+1)}f^{\prime}(u_j^{(l)}) )
$$

$$
\frac{\partial u_{j}^{(l)}}{\partial w_{ji}^{(l)}} = z_i^{(l-1)} \quad 
( \because \; u_j^{(l)} = \sum_i w_{ji}^{(l)} z_i^{(l-1)} )
$$

$$
\frac{\partial E_n}{\partial w_{ji}^{(l)}} = \delta_j^{(l)} z_i^{(l-1)} 
$$

- minibatch에서의 계산
$$
\frac{\partial E}{\partial w_{ji}^{(l)}} = \sum_n \frac{\partial E_n}{\partial w_{ji}^{(l)}} \quad
(\because \; E = \sum_n E_n)
$$



