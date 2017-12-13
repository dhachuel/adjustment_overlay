## Overview
$$
For \left\{\begin{matrix}
B_n : \textrm{remaining balance at time n}, \forall n \in \mathbb{N}
\\ 
D_n : \textrm{% defaults at time n}, \forall n \in \mathbb{N}
\end{matrix}\right. \ \ \textrm{we have the following }
$$

$$
B_{n} = B_{n-1} \cdot (1-D_n) \Rightarrow B_{n} = B_0 \cdot \prod_{i=1}^{n}(1-D_i) 
$$


## Analysis
Our aim is to find an additional constant default rate $$ \alpha $$ so that the remaining balance after $$n$$ periods i lower by an arbitrary amount $$ A $$. This can be summarized by the following proposition:

$$
\begin{Bmatrix}
\left.\begin{matrix}
\alpha
\end{matrix}\right|
B_0 \cdot \prod_{i=1}^{n}\begin{bmatrix} (1-D_i) \cdot (1-\alpha)  \end{bmatrix} = B_{n}-A
\end{Bmatrix} 
$$

Let's solve for $$ \alpha $$:

$$
B_0 \cdot \prod_{i=1}^{n}\begin{bmatrix} (1-D_i) \cdot (1-\alpha)  \end{bmatrix} = B_{n}-A 
$$

Since $$ B_{n} = B_0 \cdot \prod_{i=1}^{n}(1-D_i)  $$, we have


$$
B_0 \cdot \prod_{i=1}^{n}\begin{bmatrix} (1-D_i) \cdot (1-\alpha)  \end{bmatrix} = B_0 \cdot \prod_{i=1}^{n}(1-D_i)-A \\
\Leftrightarrow 

A = B_0 \cdot 

\begin{bmatrix}   

\prod{i=1}^{n}\begin{bmatrix} (1-D_i) \end{bmatrix} - \prod{i=1}^{n}\begin{bmatrix} (1-D_i) \cdot (1-\alpha)  \end{bmatrix}

\end{bmatrix}\\

\Leftrightarrow 
A = B_0 \cdot 
\begin{bmatrix}   
\prod_{i=1}^{n}\begin{bmatrix} (1-D_i) \end{bmatrix} - (1-\alpha)^{n} \cdot\prod_{i=1}^{n}\begin{bmatrix} (1-D_i)  \end{bmatrix}
\end{bmatrix} \\

\Leftrightarrow 

A = 

B_0 \cdot 

\prod_{i=1}^{n}(1-D_i) \cdot [1 - (1-\alpha)^{n}] \\

\Leftrightarrow 

(1-\alpha)^{n} = 
1 - \frac{A}{B_0 \cdot \prod_{i=1}^{n}(1-D_i)} \\

\Leftrightarrow 

\alpha = 

1 - \sqrt[n]{1 - \frac{A}{B_0 \cdot \prod_{i=1}^{n}(1-D_i)}}
$$





## Application
For any period $$n$$ in the forecast, the new/adjusted PD rates will be:

$$
(1-PD_{new}) = (1-PD_{old}) \cdot (1-\alpha) \\

\Leftrightarrow 

PD_{new} = PD_{old} + \alpha - PD_{old} \cdot \alpha \\
$$
