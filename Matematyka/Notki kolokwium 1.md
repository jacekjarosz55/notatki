# Notatki na matematykę


## Liczby zespolone
$i$ - **jednostka urojona**
$$ i^2 = -1$$
$$ x^2 = -1$$
$$ x = i \lor x = -i$$
$2 + 4i$ - liczba zespolona - liczba złożona z części rzeczywistej lub/oraz części urojonej($x\cdot i$)
$Rez$ = część rzeczywista
$Imz$ = część urojona

Sprzężenie zespolone $\bar{z}$:
$$z = a + bi$$
$$ \bar{z} = a - bi$$

Postać trygonometryczna:
$a = Rez$
$b = Imz$
$$|z| = \sqrt{a^2 + b^2}$$
$$z = |z|(\cos{\alpha} + i\sin{\alpha})$$
## Potęgowanie - wzór Moirre'a

$$z^n = |z|^n(\cos{(n \cdot \alpha)} + i\sin({n \cdot \alpha}))$$

### Niektóre wartości funkcji trygonometrycznych
| $\alpha$ | $0^{\circ}$ | $30^{\circ}$ | $45^{\circ}$ | $60^{\circ}$ | $90^{\circ}$ | 
|---|---|------|------|------|--------|
| $\alpha$ | $0$ | $\frac{\pi}{6}$ | $\frac{\pi}{4}$ | $\frac{\pi}{3}$| $\frac{\pi}{2}$|
|$\sin{a}$ |$0$ | $\frac{1}{2}$ | $\frac{\sqrt{2}}{2}$ | $\frac{\sqrt{3}}{2}$ | $1$ |
|$\cos{a}$ |$1$ | $\frac{\sqrt{3}}{2}$ | $\frac{\sqrt{2}}{2}$ | $\frac{1}{2}$ | 0 |
|$\tan{a}$ |$0$ | $\frac{\sqrt{3}}{3}$ | $1$ | $\sqrt{3}$ | $-$|



## Mnożenie macierzy
### Przez skalar
### Przez inną macierz
## Wyznacznik macierzy
### Dla macierzy 2-stopnia
### Metoda Sarussa
### Rozwinięcie Laplace'a


## Macierz odwrotna
Warunek: $detA \neq 0$

$$ A \cdot A^{-1} = I$$ 
$$A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix} = \begin{bmatrix} 2 & 1 \\ 5 & 3 \end{bmatrix}$$
Na początku obliczamy wyznacznik:
$$
detA = a_{11} \cdot a_{22} - a_{12} \cdot a_{21} =  2 \cdot 3 - 1 \cdot 5 = 1
$$


Transpozycja macierzy - kolumny czytane od góry jako wiersze
$$A^T = \begin{bmatrix} 2 & 3 \\ 1 & 1 \end{bmatrix}$$
Dopełnienie algebraiczne:
$$A_{ij} = (-1)^{i+j} detB$$
Gdzie:
- $i$, $j$ = to wiersz i kolumna elementu $a_{ij}$ w macierzy $A$
- $B$ to macierz powstała z wykreślenia tych kolumn z $A$.

Dlatego macierz dopełnień algebraicznych $A_D$ jest równa:
$$A_D = \begin{bmatrix}
+|B_{11}| & -|B_{12}| & +|B_{13}| \\
-|B_{21}| & +|B_{22}| & -|B_{23}| \\
+|B_{31}| & -|B_{32}| & +|B_{33}| \\
\end{bmatrix}$$
Gdzie $B_{ij}$ to macierz powstała z wykreślenia $i$ oraz $j$ z $A$.

Tworzymy macierz dopełnień algebraicznych $A_D$:
$$A_D = \begin{bmatrix}
A_{11} &  A_{12} \\
A_{21} &  A_{22} 
\end{bmatrix}
= 
\begin{bmatrix}
3 & {-5} \\
{-1} & 2
\end{bmatrix}
$$
Oraz transponujemy ją:
$$
A^{-1} = {A_D}^T = 
\begin{bmatrix}
3 & -1 \\
-5 & 2
\end{bmatrix}

$$


## Rozwiązywanie układów równań metodą macierzową

Warunek:
- $A$ jest macierzą kwadratową
- $detA \neq 0$
 $$\left\{
\begin{array}{l}
2x + y = -5 \\
3x + y = -10
\end{array}
\right.
$$
$$A \cdot X = B$$
$$
\begin{bmatrix}
2 & 1 \\
3 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y
\end{bmatrix}
=
\begin{bmatrix}
-5 \\
-10
\end{bmatrix}
$$
$A \cdot X = B$
$A \cdot A^{-1} \cdot X = B \cdot A^{-1}$
$I \cdot X = A^{-1} \cdot B$
$$X = A^{-1} \cdot B$$



## Wzory Cramera
Warunki:
1. Liczba niewiadomych = liczba równań
2. $det A \neq 0$

Dla $AX = B$

Wzory Cramera:
$x = \frac{detA_x}{detA}$, $y = \frac{detA_y}{detA}$, $z = \frac{detA_z}{detA}$

Tworzymy macierz $A_x$  poprzez zastąpienie kolumny $x$ przez macierz wyrazów wolnych.
Przykład:
$$A = 
\begin{bmatrix}
1 & 2 & 4 \\
4 & 5 & 6 \\
8 & 8 & 8
\end{bmatrix}
\text{, }
B = \begin{bmatrix}
2\\
2 \\
2
\end{bmatrix}
\text{, }
A_x = \begin{bmatrix}
2 & 2 & 4 \\
2 & 5 & 6 \\
2 & 8 & 8
\end{bmatrix}$$

## Metoda eliminacji Gaussa-Jordana

	 Metodę tą polecam przy obliczaniu macierzy odwrotnych większych niż 3x3

### Operacje elementarne na macierzach
Można:
- dodać do jednego wiersza macierzy inny wiersz pomnożony przez liczbę,
- zamienić dwa wiersze miejscami,
- mnożyć wiersz przez liczbę różną od zera.

Metoda eliminacji Gaussa-Jordana:
$$ [A | B] \xrightarrow{\text{operacje elementarne}} [I | X]  $$

Celem jest uzyskanie macierzy jednostkowej $I$, poprzez wykonywanie operacji elementarnych na macierzy $[A | B]$
