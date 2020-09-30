# Я чет не понял, если честно
> Я уверен, что конспект переполнен ошибками, опечатками и неточностями
>
> Связи с этим прошу всех людей, которые хорошо поняли материал прошедней лекции внести свой вклад и повысить качество данного конспекта

$A$ - алфавит\
$S(A)$ - множество всех строк над $A$
1. $[] \in S(A)$
2. $\forall s \in S(A) \forall x \in A \quad x:s \in S(A)$

$$
\forall s \forall t \forall x: \\
app([], t) = t \\
app(x:s, t) = x:app(s, t)
$$

**Лемма 1**
$$
\forall s app(s, [])= s \\
n + 0 = 0
$$

**Лемма 2**
$$
\forall r \forall t \forall s \\
app(s, app(t, r)) = app(app(s, t), r)
$$

---

ПИ для $S(A)$\
$\forall$ унарного предиката П над $S(A)$, если $P([]) \land \forall x \forall s (P(s)) \\
\implies P(x:s)$, то $\forall s P(s)$

---

Рассмотрим произвольные $r$ и $t$\
$P(s) := (app(s, app(t, r))) = app(app(s, t), r))$

$$
\text{Нужно} \space \forall s P(s) \\
\underline{\text{база}}: P([]) = (app([],app(t,r)))=app(app([],t),r) \space\text{- хотим}\\
$$
$$
\underline{\text{база}}: P([]) = (app([], app(t, r))) = \\
= app(app([], t), r) \text{- хотим} \\
\text{Левая часть} = app([], app(t, r)) = app(t, r) \\
\text{Правая часть} = app(app([], t), r) = app(t, r)
$$
$$
\underline{\text{шаг}}: \forall s \forall x (P(s) \implies P(x:s)) \\
\text{Рассмотрим произвольные } x \text{ и } y \\
\text{Хотим}: P(s) \implies P(x:s) \\
\text{Допустим, } P(S) \text{. Хотим } P(x:s) \\
P(s) = (app(s, app(t, r))) = app(app(s, t), r) \\
P(x:s) = (app(x:s, app(t, r))) = app(app(x:s, t), r) \\
\text{ЛЧ} = app(x:s, app(t, r)) = x:app(s, app(t, r)) \\
\xlongequal{\text{I.H.}} x:app(app(s, t), r) \xlongequal{\text{опр}} 
app(x: app(s, t), r) \\
\xlongequal{\text{опр}} app(app(x:s, t), r) = \text{ПЧ}
$$

По ПИ: $\forall s P(s)$ т.к. $r$ и $t$ произвольные, имеем $\forall r \forall t \forall s\space
app(s, app(t, r)) = app(app(s, t), r)$

**Лемма 3**

$$
\forall t \forall r \forall s \\
app(s, t) = app(s, r) \implies t = r \\
P(s) := (app(s, t) = app(s, r) \implies t = r)
$$
$$
\underline{\text{база}}: P([]) = (app([], t) = app([], r) \implies t = r) \\
\text{дано: } \underset{\xlongequal{\text{опр}} t}{app([], t)} = 
\underset{\xlongequal{\text{опр}} r}{app([], r)}
$$
$$
\underline{\text{шаг}}: \forall x \forall s \\
\text{Пусть } P(s) \text{ Хотим } P(x:s) \\
P(s) = (app(s, t) = app(s, r) \implies t = r) \\
P(x:s) = (app(x:s, t) = app(x:s, r) \implies t = r) \\
\text{дано: } \underset{\xlongequal{\text{опр}} x:app(s, t)}{app(x:s, t)} = 
\underset{\xlongequal{\text{опр}} x:app(s, r)}{app(x:s, r)}
$$

**Аксиома 2**
$$
\forall x \forall y \forall s \forall t \quad (x:s = y:t \iff x = y \land s = t) \\
\text{По А2} app(s, t) = app(s, r)
$$

**Утверждение** 
$$
\forall s \forall t \quad app(s, t) = [] \implies S = [] \land t = [] \\
\square \text{Рассмотрим произвольные } s \text{ и } t \\
\text{Допустим } app(s, t) = [] \\
\text{I случай } s = [] \cdot app([], t) = [] \\
\text{II случай } \exist y \exist r: \\
s = y:r \quad \text{Тогда } app(y:r, t) = [] \\
\text{По определению: } y:app(r, t) = [] \\
\text{По аксиоме 1: } \forall y \forall r \quad y:r \not= [] \\
\text{Противоречие } \implies s = [] \land t = []
$$

---

ПИ для $\N$\
$\forall$ унарного придиката $P$ над $\N$, если 
$P(0) \land \forall (P(n) \implies P(n + 1))$, то $\forall n P(n)$

> Здесь и далее все числа $\in \N (0 \in \N)$

$$
A \le B \iff \forall x (x \in A \implies x \in B) \\
x \le \N; \varnothing \\
\bar{x} = \N /\ x \\
A /\ b = \{x\in A | x \notin B\}
$$

---

(ПB $\iff$) ПМИ (принцип мат. индукции)\
$\widetilde{\forall X} \le \N$, если $0 \in X \land \forall n(n \in X \implies (n+1) \in X)$,
то $X = \N$
$$
P(n) = (n \in X), x := {n \in \N | P(n)} \\
P(0) \land \underbrace{\forall n(P((0), P(1), P(2), \dots, P(n-1)))}_{\text{I.H.}} \implies P(n)
$$

**Определение**\
Пусть $x \le \N$. Тогда $x$ прогрессивно, если $\forall n ((\forall m < n (m\in X)) \implies
n \in X)$\
$Prog(X)$\
Пример $Prog(\N)$

$$
\cdot X_1 = {0; 2; 4; 6; \dots} \\
\forall m < 1 \quad m \in X_1 \\
1 \notin X_1 \quad \lnot Prog(X_1)
\cdot X_2 = {1; 3; 5; \dots} \\
\forall m < 0: m \in X_2 \\
0 \notin X_2 \\
\forall m < 0, m\in X_2 \iff \forall m \underbrace{(\underbrace{m < 0}_\text{ложь}
\implies m \in X_2)}_\text{истина}
$$

---

**Лемма**\
$$
\forall X \le \N (Prog(X) \implies 0 \in X) \\
\square \text{дано: } Prog(x) (\iff) \forall n (\forall m < n \space m \in X \implies n \in X)\\
\underbrace{\forall m < 0 m \in X}_\text{верно} \implies \underbrace{0 \in X}_\text{верно}
$$

---

**ПСИ** (Принцип сильной индукции)\
$\forall x \le \N$, если $Prog(X)$, то $X = \N$

**ПНЧ** (принцип наименьшего числа)\
Если есть какое-то число со свойством, есть и наименьшее такое число
$$
\forall X \in \N (X \not = \varnothing \implies \exist n 
\underbrace{(n \in X \land \forall m (m \in X \implies n < ))}_{\exist min \space X})
$$

**Теорема**\
Следующие утверждения равносильны:
1. ПСИ
2. ПНЧ
3. ПМИ

$(1) \implies (2)$ Дано ПСИ. Хотим: ПНЧ
$$
\forall X (x \not = 0 \implies \exist min \space X) \\
(\lnot B \implies \lnot A \equiv A \implies B) ||| \\
\forall X (\nexists min \space X \implies x = \varnothing) \\
\text{Утверждение } \nexists min \space X \iff Prog(\bar{X}) \\
\text{Дано } \nexists min \space X \\
\text{Хочу: } \forall n (\forall m < n \space m \notin \bar{x} \implies n\in\bar{X}) \\
\forall n (\forall m < n \space m \notin X \implies n \notin X) \\
\forall n (n \in X \implies \lnot \forall m < n \space m \notin X) \\
\forall n (n\in X \implies \exist m < n \space m \in X) \\
\forall n (n \in X \implies n \not min \space X) \\
\nexists min \space X \\
\forall x (\nexists min \space X \implies x \subset \varnothing) \implies \\
\implies Prog(\bar{x}) \xRightarrow[\text{ПСИ}]{} \bar{X} = \N \implies x = \varnothing
\blacksquare
$$

