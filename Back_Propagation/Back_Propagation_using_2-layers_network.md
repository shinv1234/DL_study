# Back Propagation using 2-Layers Network


### Forward Propagation

$$ u_j^{l} = \sum_{i=1}^n w_{ji}^{(l)} z_i^{(l-1)} +b_j^{(l)} = \sum_{i=0}^n w_{ji}^{(l)} z_i^{(l-1)}   \quad (w_{j0}^{(l)} = b_j^{(l)}, \;z_0^{l-1} = 1) $$

$$ x_i =  z_i^{(1)}$$

$$ z_j^{(2)} = f(u_j^{(2)}) = \sum_i f(w_{ji}^{(2)} z_i^{(1)}) $$

$$ y_j(x) = z_j^{3} = u_j^{3} = \sum_i w_{ji}^{(3)} z_i^{(2)} $$

$$E_n = \frac{1}{2}||y(x) - d||^2 = \frac{1}{2} \sum_i (y_j(x) - d_j)^2$$


### Back Propagation

- 출력층의 가중치 미분

$$ \frac{\partial E_n}{\partial w_{ji}^{(3)}}  = \frac{\partial E_n}{\partial y} \frac{\partial y}{\partial w_{ji}^{(3)}} = (y(x) - d)^T \frac{\partial y}{\partial w_{ji}^{(3)}} $$

$$ \frac{\partial y}{\partial w_{ji}^{(3)}} = [0\, ... 0 \,\, z_i^{2} \,\, 0\, . . . 0]^T $$

$$ \frac{\partial E_n}{\partial w_{ji}^{(3)}} =  (y_j(x) - d_j) z_i^{(2)} $$

- 중간층의 기울기 미분

$$ \frac{\partial E_n}{\partial w_{ji}^{(2)}} = \frac{\partial E_n}{\partial u_{j}^{(2)}} \frac{\partial u_{j}^{(2)}}{\partial w_{ji}^{(2)}}  $$

$$ \frac{\partial u_{j}^{(2)}}{\partial w_{ji}^{(2)}} = z_i^{(1)} \quad ( \because \; u_j^{(2)} = \sum_i w_{ji}^{(2)} z_i^{(1)} ) $$

$$ \frac{\partial E_n}{\partial w_{ji}^{(2)}} = \frac{\partial E_n}{\partial u_{j}^{(2)}} z_i^{(1)}  $$

$$ \frac{\partial E_n}{\partial u_{j}^{(2)}} = \sum_k \frac{\partial E_n}{\partial u_{k}^{(3)}} \frac{\partial u_{k}^{(3)}}{\partial u_{j}^{(2)}} $$

$$ E_n = \frac{1}{2}||y(x) - d||^2 = \frac{1}{2} \sum_i (y_j(x) - d_j)^2 = \frac{1}{2} \sum_i (u_k^{(3)} - d_k)^2 $$

$$ \frac{\partial E_n}{\partial u_{k}^{(3)}} = u_k^{(3)} - d_k $$

$$ \frac{\partial u_{k}^{(3)}}{\partial u_{j}^{(2)}} = w_{kj}^{(3)}f^{\prime}(u_j^{(2)}) \quad (  \because \; u_{k}^{(3)} = \sum_j  w_{kj}^{(3)}f(u_j^{(2)}))$$

$$ \frac{\partial E_n}{\partial w_{ji}^{(2)}}  = f^{\prime}(u_j^{(2)})\sum_j  w_{kj}^{(3)}(u_k^{(3)} - d_k)z_i^{(1)}  $$




