# Определитель матрицы
> 23 сентября 2020

$$
\begin{cases}
a_{11} x_1 + \dots + a_{1n} x_n = b_1 \\
\dots \\
a_{m1} x_1 + \dots + a_{mn} x_n = b_n
\end{cases}
\iff
\begin{pmatrix}
a_{11} & \dots & a_{1n} \\
\dots \\
a_{m1} & \dots & a_{mn}
\end{pmatrix}
\cdot
$$

**Определение**\
Всякое расположение числел $1,\dots , n$ в определенном порядке называют перестановкой

Запись
$$
\alpha = (\alpha_1, \alpha_2, \dots, \alpha_n) \\
\text{Перестановка } (43215)
$$

**определение**\
$\alpha_i$ и $\alpha_j$ образуют инверсию в перестановке $\alpha$ если $\alpha_j > \alpha_i, i > j$

**Определение**\
Знак перестановки $syn \space \alpha = (-1)^{\text{кол-во инверсий}}$

Прмер $\alpha = (4, 5, 1, 3, 6, 2)$
$$
4: 1, 3, 2 \to 3 \space инв\\
5: \to 3 \space инв\\
1: 0 \\
3: 1 \space инв
6: 1 \space инв
$$

**Определение**\
Транспозиция перестановки - операция, при которой в $\alpha$ меняются $\alpha_i$ и $\alpha_j$, а остальное не меняется

**Утверждение**\
Транспозиция меняет четность перестановки

**Определение**\
Подстановка
$$
\sigma = \begin{pmatrix}
1 & \dots & n \\
\sigma(1) & \dots & \sigma(n)
\end{pmatrix}_{2\cdot n}
$$
отображение числел $\boxed{1, \dots, n}$ в себя является взаимно-однозначным

Здесь\
$\sigma(1), \dots, \sigma(n)$ - перестановка

Пример
$$
\sigma = \begin{pmatrix}
1 & 2 & 3 & 4 \\
4 & 3 & 1 & 2
\end{pmatrix} \\
\sigma(3) = 1
$$

**Определение**
Умножение подстановок - это последовательное их примененеие (композиция)

Пример
$$
\sigma_1 \cdot \sigma_2 = 
\begin{pmatrix}
1 & 2 & 3 \\
3 & 1 & 2
\end{pmatrix} \cdot
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 3
\end{pmatrix} =
\begin{pmatrix}
1 & 2 & 3 \
3 & 2 & 1
\end{pmatrix}
$$

Умножеются только подстановки одинаковых длинны $n$. Всего их $n!$

**Определение**\
МНожество всех подстановок длинны $n$ с операцией умножения обозначается $S_n$

**Определение**\
Определителем (детерминатором) порядка $n$, соответствующим квадратной матрице:
$$
A = \begin{pmatrix}
a_{11} & \dots & a_{1n} \\
\dots & \ddots & \dots \\
a_{n1} & \dots & a_{nn}
\end{pmatrix}
$$

Называют число равное сумме $n!$ слагаемых

$$
detA = \sum_{\sigma \in S_n} sgn(\sigma) \cdot a_{1\sigma(1)} \cdot a_{2\sigma(2)} \cdot
\dots \cdot a_{n\sigma(n)}\\
\sigma \in S_n - \text{Множетсо всех подстоновок длинны n}
$$
т.е.е номер строк $= 1$\
а номер столбца $= \sigma(1)$

**Замечание**\
Определитель - это сумма всех возможных произведений, стоящих в разных строках и разных столбцах (с учетом знака)

Пример
$$
n = 2\\
\sigma_1 = id = 
\begin{pmatrix}
1 & 2 \\
1 & 1
\end{pmatrix} \\
\sigma_2 = 
\begin{pmatrix}
1 & 2 \\
2 & 1
\end{pmatrix} \\
\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix} = A \\
det A = sgn(\sigma_1) \cdot a_n \cdot a_{22} + sgn(\sigma_2) \cdot a_{12} \cdot_{21} =
a_{11} a_{22} - a_{12} a_{22}
$$

**Свойства определителей**\
1. $det A^T = det A$
$$
\square B = A^T \quad b_{ij} = a_{ji} \\
det B = \sum_{\sigma \in S_n} sgn(\sigma) \\
b_{1\sigma(1)} \dots b_{n\sigma(n)} = \\
\sum_{\sigma \in S_n} sgn(\sigma) b_{\sigma^{-1}(1)} \dots b_{\sigma^{-1}(n)n}
$$

$$
\sigma = \begin{pmatrix}
1 & \dots & n \\
\sigma(1) & \dots & \sigma(n)
\end{pmatrix} \to
\sigma^{-1} = \begin{pmatrix}
\sigma(1) & \dots & \sigma(n) \\
1 & \dots & n
\end{pmatrix}
$$

2. Определитель линеен по строкам (столбцам), т.е.

a)
$$
det\underbrace{(A_1, \dots, A_i + A_i, \dots, A_n)}_{\text{матрица записанная как совокупность столбцов } A_1, \dots, A_n} =\\
det(A_1, \dots, A_i', \dots, A_n) + det(A_1, \dots, A_i'', \dots, A_n)
$$
б)
$$
det(A_1, \dots, \alpha A_i, \dots, A_n) = \alpha det(A_1, \dots, A_i, \dots, A_n)
$$

Так как линейность есть по каждому из $n$ строк, то говорят о полилинейность

3. При перестановке (строк) столбцов определитель меняет знак.
Это свойство называется кососимметричность

$\square$Если произведение 
$$
a_{1\alpha(1)} \dots a_{i\alpha(i)} \dots \\
\dots a_{j\alpha(j)} \dots \\
\dots a_{n\alpha(n)}
$$
Учавствует в первом определиеле $\iff$ оно участвует во втором

$$
A_1 = 
\begin{vmatrix}
a_{11} & \dots & a_{1n} \\
\dots & & \dots \\
a_{i1} & \dots & a_{in} \\
\dots & & \dots \\
a_{j1} & \dots & a{jn} \\
\dots & & \dots \\
a_{n1} & \dots & a{nn}
\end{vmatrix},
A_2 = 
\begin{vmatrix}
a_{11} & \dots & a_{1n} \\
\dots & & \dots \\
a_{j1} & \dots & a_{jn} \\
\dots & & \dots \\
a_{i1} & \dots & a{in} \\
\dots & & \dots \\
a_{n1} & \dots & a{nn}
\end{vmatrix}
$$

Знак подстановки в $A_1$ это знак:
$$
\alpha = \begin{pmatrix}
1 & \dots & i & \dots & j & \dots & n \\
\alpha(1) & \dots & \alpha(i) & \dots & \alpha(j) & \dots & \alpha(n)
\end{pmatrix} \\

\alpha' = \begin{pmatrix}
1 & \dots & j & \dots & i & \dots & n \\
\alpha(1) & \dots & \alpha(i) & \dots & \alpha(j) & \dots & \alpha(n)
\end{pmatrix} \\
$$

Они отличаются на транспозицию $\implies sgn(\alpha) = -sgn(\alpha') \implies 
A_1 = -A_2 \blacksquare$ 

4. $det A = 0$, если\
    а) В матрице есть нулевая строка (по определению)\
    б) В матрице есть 2 одинаковые строки (по свойству 3)

5. $det A = 0$ если один из столбцов является линейней комбинацией остальных 
$$
A_i = \sum_{j=1, j\not=i}^i \alpha_jA_j \\
\square det(A_1, \dots, \sum_{j=1, j\not=i}^n \alpha_jA_j, \dots, A_n) = 
\sum_{j=1, j\not=i}^n \alpha_i \cdot det(A_1, \dots, A_j, \dots, A_n) = \\
= 0 + \dots + 0 = 0
$$

6. Определительне меняется, если к $\forall$ строке прибавить линейную комбинацию остальных\
Применим свойство 2 и свойсвтво 5

7. 
$$
det E_n = det \begin{pmatrix}
1 & & 0 \\
& \ddots & \\
0 & & 1
\end{pmatrix}_{n\cdot n} = 1 \text{ по определениею}
$$

**Замечание**\
Определителем матрицы 3*3
$$
A = \begin{pmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{23} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{pmatrix} \\
det A = a_{11} a_{22} a_{33} + \\
a_{12} a_{23} a_{31} + \\
a_{21} a_{32} a_{13} + \\
$$
> А потом мне стало лень
