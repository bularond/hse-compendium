# Свойства определителей и обратная матрица
> 30 сентября 2020

определение\
в матрице $a_{n*n}$ вычекнули $i$-ную строку и $j$-й столбецю определитель получившейся матрицы называется дополняющим минором элемента $a_{ij}$

обозначение $m_{ij}$

алгебраическим дополнением элемента $a_{ij}$ называется число $a_{ij}=(-i)^{i+j}m_{ij}$

---

**свойсвтово 8** (из теормемы лапласа)

разложение определителя по строке или столбцу
$$
det a = \sum_{j=1}^n a_{ij}a_{ij} = \sum_{i=1}^n a_{ij}a_{ij} (*)
$$

замечание.\
свойство 8 позволяет определить детерменант индукцией по порядку матрицы.
при $n=1 \quad det' a_{11} = a_{11}$.
если уже определен $det'$ для матрицы порядка $n-1$ (и меньше), то зададим его для матрицы порядка $n$ по формуле: (*).
остается показать, что $det'a = deta$

**свойство 9** фальшивое разложение (часть теоремы лапласа)

$$
\sum_{j=1}^n a_{ij}a_{kj} = 0, j \not= k
\sum_{i=1}^n a_{ij}a_{ik} = 0, k \not= j
$$
это свойсво (8) и (4б)

**свойство 10**

$$
\text{верхнетреугольная матрица:} \\
det\begin{vmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
0 & a_22 & & \dots \\
\dots & & \ddots & \vdots \\
0 & 0 & \dots & a_{nn}
\end{vmatrix} = a_{11} \cdot a_{22} \cdot \dots \cdot a_{nn}
$$

**свойство 11** определитель блочной матрицы
$$
det
\left(
\begin{array}{c|c}
a & c \\
\hline \\
0 & b
\end{array}
\right) = det a \cdot det b
$$

**свойство 12**
$$
\forall a,b \in m_n(\r) \\
det(a\cdot b) = det a \cdot det b
$$
утверждение $\forall$ функция от столбцов матрицы удовлетворяет свойствам (2), (4b), (7) является определителем. то есть $\forall$ полилинейная (линейная по каждой строке), кососимметричная функция от столбцов матрицы, равная на $e_n$ единичная является определителем
$$
\square \text{для } n = 2 \\
\text{пусть } f - \text{ функция, для которой выполянются свойство (2), (4b), 7 } \\
f\left(\begin{array}{cc}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{array}\right) = 

f\left(a_{11}\binom{1}{0} + a_{21}\binom{0}{1}, \begin{array}{c}a_{12}\\ a_{22}\end{array}\right) = \\
= a_{11} f\left(\begin{array}{cc}
1 & a_{12} \\
0 & a_{22}
\end{array}\right) + 
a_{21} f\left(\begin{array}{cc}
0 & a_{12} \\
1 & a_{22}
\end{array}\right) =  \\
= a_{11} a_{12} 
f\left(\begin{array}{cc}
1 & 1 \\
0 & 0
\end{array}\right) + 
a_{11} a_{22} 
f\left(\begin{array}{cc}
1 & 0 \\
0 & 1
\end{array}\right) + 

a_{21} a_{12} 
f\left(\begin{array}{cc}
0 & 1 \\
1 & 0
\end{array}\right) + 
a_{21} a_{22} 
f\left(\begin{array}{cc}
0 & 0 \\
1 & 1
\end{array}\right) = \\
= 0 + (a_{11}a_{22} - a_{21} a_{12}) f(e_2) + 0 = a_{11}a_22 - a_{21} a_12 = deta
\blacksquare
$$

лемма. $\forall$ линейной функции свойство (3) (кососимметричность) и (4b) эквивалентны.
$$
\square \text{пусть } f(u, v) - \text{комбинация 2х столбцов (остальные не трогаем)} \\
f(u+v, u+v) = f(u,u) + f(u,v) + f(v, u) + f(v, v) \\
\text{если выполняется (4b), то } f(u, u) = 0, f(v, v) = 0, f(u+v, u+v) = 0 \implies \\
\implies f(u, v) = -f(v, u) \text{(а в обратную сторону было для определителя)}\blacksquare
$$

докажем 12 свойсво
$$
\square \text{рассмотрим функцию } f(b) = det(a \cdot b) \\
\text{покажем, что для } f(b) \text{ выполнены свойсва (2) и (4b)} \\
\text{если это так, то } f(b) = det b \cdot f(e_n) \text{ по ранее доказанному } \\
\text{если столбцы } i, j \text{ одинаковы в матрице } b, \\
\text{то в матрице } a\cdot b
\text{ тоже будут одинаковыми (по свойству умножения матриц) } \implies \\
\implies \text{выполнено свойсво (4b)} \\
2) \text{если в матрице } b \space i\text{-ой столбец меет вид } \lambda a \mu b, \\
\text{в } a\cdot b \text{ он имеет вид } \lambda aa + \mu a \cdot b \text{ и выполнено (2) для определителя } \implies \\
\implies \text{выполняется свойство (2) для } f(b), \text{т. е. она линейна} \implies \\
\implies \text{верно } f(b) = det b \cdot f(e_n), \text{ но } f(e_n) = det(a\cdot e_n) = \\
= det a \implies det(a \cdot b)= f(b) = detb \cdot det a
$$

## вычисление определителей
### элементакрные преобразования
1. при $(i) \iff (j)$ определитель меняет знак
2. при $(i) + \alpha\cdot (k) \to (j)$ ничего не меняетя
3. при $(i)\alpha \to (i), (\alpha \not= 0)$ определитель умножается на $\alpha$

приводим к верхнетреугольному виду методом гауса и применяем свойство (10)

### рекурентные соотношения
$$
\delta = f(\delta_{n-1}, \delta_{n-2}, \dots, \delta_{n-k}), (k < n)
$$

---

**правило крамера**

пусть $a$ - матрица $n*n$ и дана слау $ax = b$. запишем ее в векторном виде:
$$
x_1a_1 + x_2a_2 + \dots + x_na_n = b
$$

**теорема**
пусть у слау $ax = b$ есть решения (т. е. она совместна). тогда $x_i det a = \delta_i, i = \overline{1,n}$, где $\delta_i = det(a_1, \dots, a_{i-1}, b, a_{i+1}, \dots, a_n)$

замечание: если $det a \not= 0$, то $x_i = \frac{\delta_i}{deta}$
$$
\square \delta_i = det(a_1, \dots, a_{i-1}, b, a_{i+1}, \dots, a_n) = \\
= det(a_1, \dots, a_{i-1}, \sum_{j=1}^n x_ja_j, a_{i+1}, \dots, a_n) = \\
= \sum_{j=1}^n x_j det(a_1, \dots, a_{i-1}, a_j, a_{i+1}, \dots, a_n) = \\
= x_i \cdot det(a_1, \dots, a_{i-1}, a_i, a_{i+1}, \dots, a_n) = x_i \cdot deta \blacksquare
$$

следствие. если мы рассматриваем слау $ax = 0$ (она называется однородной), с квадратной матрицей $a$ и $det a\not= 0$, то у этой слау $\exists!$ решение и это $x=0$

## обратные матрицы
**определение** обраной к матрице $a \in m_n(\r)$ является матрица $a^{-1}$ размера $n*n$ такая, что $a\cdot a^{-1} = e = a^{-1}\cdot a$

утверждение. если обраная матрица $\exists$, то она единственна.
$$
\square \text{допустим, что } b_1, b_2 \text{ - обратные к } a \\
b_1 \cdot a = a \cdot b_1 = e \\
b_2 \cdot a = a \cdot b_2 = e \\
b_1 = b_1 \cdot e = b_1 (a \cdot b_2) = (b_1 \cdot a) \cdot b_2 = e \cdot b_2 = b_2
\blacksquare
$$

**теорема** матрица $a \in m_n(\r)$  имеет обратную $\iff deta \not = 0$
$$
\text{необходимость:} \\
\text{дано: } \exists a^{-1} \\
\text{доказать: } det a \not= 0 \\
\text{по определению: } a\cdot a^{-1} = e \\
det(a\cdot a^{-1}) = det e = 1 = \\
deta \cdot deta^{-1}
\text{если } deta = 0, \text{ получаем противоречие} \\
\text{достаточность. дано: } det a \not = 0 \\
\text{доказать: } \exists a^{-1} \\
\text{рассмотрим матрицу } b = \frac{1}{deta} \cdot \widetilde{a}, \\
\text{где } \widetilde{a} - \text{это транспонированная матрица из }\\
\text{алгебраических дополнений (это матрицыа зазывается союзной с a)} \\
\widetilde{a} = \begin{pmatrix}
a_{11} & \dots & a_{1n} \\
\dots & & \dots \\
a_{n1} & \dots & a_{nn}
\end{pmatrix} \\
\text{рассмотрим произведение } a\cdot b: \\
[a \cdot b]_{ij} = \sum_{r=1}^n [a]_{ir} [b]_{rj} - \text{определение умножения} \\
= \frac{1}{deta} \sum_{r=1}^n a_{ir} [\widetilde{a}]_{rj}
$$
