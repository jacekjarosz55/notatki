# Sprowadzenie postaci kwadratowej  do postaci kanonicznej

$$x = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$$
Forma kwadratowa
$$Q(x) = a_{11}x_1^2 + 2a_{12}x_1x_2 + a_{22}x_2^2$$
$$ M = \begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
\end{bmatrix}$$
$$ \text{zał. }  a_{12} = a_{21} $$
Obliczamy $detM$:
- jeżeli $detM>0$  typ eliptyczny
- jeżeli $detM=0$  typ paraboliczny
- jeżeli $detM<0$  typ hiperboliczny


Obliczamy wartości własne $M$:
$$ \begin{vmatrix}
a_{11} - \lambda & a_{12} \\
a_{21} & a_{22} - \lambda \\
\end{vmatrix} = 0$$
dla każdej lambdy:
$$ V_1 = \begin{bmatrix} v_{11} \\ v_{12} \end{bmatrix}$$
$$ \begin{bmatrix}
a_{11} - \lambda & a_{12} \\
a_{21} & a_{22} - \lambda \\
\end{bmatrix}
\cdot 
\begin{bmatrix}
v_{11} \\
v_{12}
\end{bmatrix}
=
\begin{bmatrix}
0\\
0
\end{bmatrix}
$$

Macierz przejścia
$$ A = 
\begin{bmatrix} 
\cos\alpha & -\sin\alpha \\
\sin\alpha & \cos\alpha
\end{bmatrix} $$






