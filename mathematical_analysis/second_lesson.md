# Числовые последовательности
Если каждому натуральному числу поставлено соответствие вещественное число $x_n$, 
то заданна числовая последовательность

Способы задания:
1. С помощью формулы; $x_n = n^2 + 1$; $x_1 = 2, x_2 = 5, x_3 = 10, \dots$
2. С помощью рекурентной формулы или рекурентного соотношения; 
$$
x_1=1, x_2 = 1; x_n = x_{n-1} + x_{n-2}, n \ge 3\\
x_3 = 2, x_4 = 3, x_5 = 5, \dots 
$$
3. Описание членов последовательности.
$x_n$ - $n$-ое простое число
$$
x_1 = 2, x_2 = 3, x_3 = 5, x_4 = 7, x_5 = 11, \dots
$$

## Пределы числовой последовательности
$$
x_n = \frac{1}{n}; x_2 = \frac{1}{2}, x_3 = \frac{1}{3}, \dots \\
\lim_{n\to \infin} x_n = 0
$$

**Опр.** $\lim_{n\to\infin} x_n = a (x_n\to a)$ если для всякого $\Epsilon > 0$, начиная с некоторого номера N (зависимого от эпселент) все члены последовательности удовлетворяют: $|x_n a| < \Epsilon$

---

$\forall x$ для всех x, для любого x; $\forall$ - квантор общности (All)

$\exist x$ найдется x, существует x; $\exist$ - квантор существования (Exist)

$A \implies BA \implies$ из утверждения A следует B; если А, то B ($\implies$ импликация)

$A \iff B$ утверждение А равносильно утверждению В ($\iff$ эквивалентность)

---

$$
\forall \Epsilon > 0 \exist N = N(\Epsilon) \space \forall n \ge N \implies |x_n - a| < \Epsilon
$$

---

$$
x_n = \frac{1}{n}; \Epsilon = \frac{1}{1000}; |x_n - 0| < \frac{1}{1000}; N = 1000; N = 1001 \\
\Epsilon > 0 \quad |x_n - 0| < \Epsilon \quad N = \left[\frac{1}{\Epsilon}\right] + 1
$$

---

$a$ - вечественное число, $\Epsilon > 0$

$O_\Epsilon (a)$ - $\Epsilon$ открестности

$$
O_\Epsilon (a) = \{x \in \R | a - \Epsilon < x < a + \Epsilon \} \quad |x - a| < \Epsilon
$$

> Картинка 1

$$
\lim_{n\to\infin} x_n = a \iff \forall \Epsilon > 0 \exist N \forall n \ge N \implies x_n \in O_\Epsilon (a)
$$

**Утв 1** $\lim_{n\to\infin} x_n = a \iff$ вне всякой окрестности та имеет конечное множество членов последовательности

$(\implies)$ Дано $\lim_{n\to\infin} x_n = a$

Рассмотрим $O_\Epsilon (a); \exist N \forall n \ge N \implies x_n \in O_\Epsilon (a)$

только лишь $x_1, x_2, \dots, x_{N-1}$ могуть попасть $O_\Epsilon(a)$

$(\impliedby)$ пусть $\Epsilon > 0$. Рассмотрим $O_\Epsilon(a)$; пусть $x_{n1}, x_{n2}, \dots, x_{nk}$ не принадлежит $O_\Epsilon(a)$

$N = max(n{1}, \dots, n_k) + 1$ то $\forall n \ge N \implies x_n \in O_\Epsilon(a)$ т. е.
$\lim_{n\to\infin} x_n = a$

Пример $1, \frac12, 1, \frac14, \dots, 1, \frac1n$

У данной последовательности нет предела

> Картинка 2

---

**Утв 2** (о единственности предела) Сходящаяся последовательность имеет единственные предел.

**Доказательство** (от противного) пусть $\lim_{n\to\infin} x_n = a_1; \lim_{n\to\infin} x_n = a_2, a_1 < a_2$

$$
\Epsilon = \frac{a_2 - a_1}{3}
$$

> Картинка 3

$$
\exist N_1 \forall n \ge N_1 \implies x_n \in O_\Epsilon (a_1) \\
\exist N_2 \forall n \ge N_2 \implies x_n \in O_\Epsilon (a_2)
$$

Пусть $N=max(N_1, N_2)$; если $n \ge N$, то $x_n \in O_\Epsilon (a1), x_n \in O_\Epsilon (a_2)$

противоречие, т.к. $O_\Epsilon (a1) \land O_\Epsilon (a_2) = \varnothing$

---

Последовательность $\{x_n\}$ ограничена, если $\exist M$, такие, что $m \le x_n \le M$ для всех $n$

$M$ ограничивает $\{x_n\}$ сверху, а $m$ снизу

**Утв 3** Сходящиеса последовательность ограничена

**Доказательство** $\lim_{n\to\infin} x_n = a;$ 

для $\Epsilon = 1 \exist N \forall n \ge N \implies |x_n - a| < 1$

т.е. $x_n < a + 1$

$M = max(a+1, |x_1|, |x_2|, \dots, |x_{N-1}|)$

тогда $\forall n \implies x_n \le M$

Для $m$ аналогично

---

**Утв 4** (теорема о зажатой последовательности)
$$
\lim_{n\to\infin} x_n = \lim_{n\to\infin} x_n = a \\
\{y_n\}: x_n \le y_n \le z_n \space (n=1, 2, \dots)
$$

Утв $\lim_{n\to\infin} y_n = a$

> Картинка 4

**Доказательство** 

$$
\Epsilon > 0 \quad \exist N_1 \forall n \ge N_1 \implies x_n \in O_\Epsilon(a) \\
\exist N_2 \forall n\ge N_2 \implies z_n \in O_\Epsilon(a) \\
N = max(N_1, N_2) \quad \forall n \ge N \implies x_n, y_n \in O_\Epsilon(a) \implies \\
\implies y_n \in O_\Epsilon(a) \\
$$

Пример $a > 1$
$$
\lim_{n\to\infin} \frac{n}{a^n} = 0 \\
a = 1 + \beta; \beta > 0 \\
0 < \frac{n}{a^n} = \frac{n}{(1 + \beta)^n} = \frac{n}{1 + bn + \frac{n(n-1)}{2}\beta^2 +\dots} 
\le \frac{n}{\frac{n(n-1)}{2}\beta^2} = \frac{2}{\beta^2 (n - 1)} \xrightarrow[n\to\infin] 0
$$

$$
x_n = 0 \\
y_n = \frac{n}{a^n} \\
z_n = \frac{2}{\beta^2 (n - 1)}
$$

## Бесконечно малые (б.м.) последовательности
**Опр** $\{x_n\}$ б.м. последовательность, если $\lim_{n\to\infin} x_n = 0$

Пример $\lim_{n\to\infin} x_n = a \iff \lim_{n\to\infin}(x_n - 1) = 0$, т.е. $(x_n - a)$ - б.м. последовательность

**Утв 5** (св-ва б.м. поседовательность)
1. $\{x_n\}, \{y_n\}$ - б.м. $\implies x_n +- \y_n$ - б.м. последовательность
2. $\{x_n\}$ - б.м. $\{y_n\}$ ограниченная последовательность $\implies x_n \cdot y_n$ - б.м. последовательность
