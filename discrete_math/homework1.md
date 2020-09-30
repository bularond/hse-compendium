# Домашка №1 (1-4)
> Ну вот так я техаю, ничего с со мной не поделаешь

## Номер 1
а)
$$
((((A \to B) \to A) \to A) \to A) \to A \\
A \to B \equiv \lnot A \lor B \\
(A \to B) \to A \equiv \lnot (\lnot A \lor B) \lor A \equiv A\land\lnot B \lor A \equiv A \\
((A\to B) \to A) \to A \equiv 1 \to A \equiv A \\
(((A\to B)\to A)\to A)\to A \equiv A \to A \equiv A \\
((((A \to B)\to A)\to A)\to A)\to A \equiv A\to A \equiv 1
$$
б)
$$
(A \to (B \to C)) \to ((A \to B) \to (A \to C)) \\
A \to (B \to C) \equiv \lnot A \lor \lnot B \lor C \\
(A \to B) \to (A \to C) \equiv (\lnot A \lor B) \to (\lnot A \lor C) \equiv
\lnot(\lnot A \lor B) \lor \lnot A \lor C \equiv \\
\equiv A\land\lnot B \lor \lnot A \lor C \equiv \lnot(\lnot(A \land \lnot B)\land A) \lor C 
\equiv \lnot ((\lnot A \lor B)\land A) \lor C \equiv \\
\equiv \lnot(A \land \lnot A \lor A \land B) \lor C \equiv \lnot A \lor \lnot B \lor C \\
(\lnot A \lor \lnot B \lor C) \to (\lnot A \lor \lnot B \lor C) \equiv 1
$$
в)
$$
(A \to (C \land D)) \to (((A \to B) \land (E \to \lnot D)) \to ((C \to B) \lor (D \land B \land \lnot E))) \\
$$
| Истина                            | Ложь                                                                               |
|:---------------------------------:|:----------------------------------------------------------------------------------:|
| $A \to (C \land D)$               | $((A \to B) \land (E \to \lnot D)) \to ((C \to B) \lor (D \land B \land \lnot E))$ |
| $(A \to B) \land (E \to \lnot D)$ | $(C \to B) \lor (D \land B \land \lnot E)$                                         |
| $A \to B$                         | $C \to B$                                                                          |
| $C \to \lnot D$                   | $D \land B \land \lnot E$                                                          |
| $C$                               | $B$                                                                                |
|                                   | $A$                                                                                |
Можем найти пример, когда выражение равно нулю:
- $A = 0$
- $B = 0$
- $C = 1$
- $D = 0$
- $E = 0$

$$
(0 \to (1 \land 0)) \to (((0 \to 0) \land (0 \to \lnot 0)) \to ((1 \to 0) \lor (0 \land 0 \land \lnot 0))) \equiv \\
\equiv (0 \to 0) \to ((1 \land 1) \to (0 \land 0)) \equiv 1 \to (1 \to 0) \equiv 1 \to 0 \equiv 0
$$

## Номер 2
a)
$$
(A \land B) \lor C \equiv (A \lor C) \land (B \lor C) \\
(A \lor C) \land (B \lor C) \equiv (A \land B) \lor (A \land C) \lor (B \land C)\lor C \equiv \\
\equiv (A \land B) \lor (C \land (A \lor B \lor 1)) \equiv (A \land B) \lor C
$$
б)
$$
(A \land B) \lor A \equiv A \equiv A \land (A \lor B) \\
\begin{array}{c|c|c|c}
A & B & (A \land B) \lor A & A \land (A \lor B) \\
\hline \\
0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
1 & 0 & 1 & 1 \\
1 & 1 & 1 & 1
\end{array}
$$
в)
$$
\lnot A \to B \equiv \lnot B \to A \\
\lnot A \to B \equiv \lnot\lnot A \lor B \equiv A \lor B \\
\lnot B \to A \equiv A \lor \lnot\lnot B \equiv A \lor B
$$

## Номер 3
a) $x=1 \lor x=2 \lor x=3 \lor x=4 \lor x=6 \lor x=12$\
b) $x=4 \lor x=11$\
c) $x \in \{2k + 1 | k \in \N\} \lor x=6$\
d) $x=4 \lor x=5 \lor x=6$\
e) $x=1 \lor x=2 \lor x=11$\
f) $x=7 \lor x=12$\
Ответ: При $x=9$ выполняется только (с)

## Номер 4
$$
\begin{array}{c|c|c|c|c|c}
& 1 & 2 & 3 & 4 & 5 \\
\hline \\
1 & H & & S & \\
\hline \\
2 & & H \space R & & R & \\
\hline \\
3 & S & B \space S & S & S & S \space H \\
\hline \\
4 & B & & & & B \\
\hline \\
5 & B & & R & & S \space R
\end{array}
$$
a) 
$$ \exists j: \sum_{i=1}^5 B(i, j) = 2 $$

b)
$$
\forall i \forall j H(i, j) \to \lnot B(i, j)
$$

c)
$$
\forall i (\exists j S(i, j) \to \exists m R(i, m))
$$

d)
$$
\forall i \forall j (B(i, j) = B(j, i)) \land (H(i, j) = H(j, i)) \land (S(i, j) = S(j, i))
\land (R(i, j) = R(j, i))
$$

e) 
$$
(\exists m \forall n S(n, m)) \to (\forall n \exists m R(n, m))
$$
Если найдется улица, где на всех перекрестках стоят универсамы, тогда тогда на всех проспектах найдется ресторан

f)
$$
\exists i \exists j \exists n \exists m (B(i, j) \land S(i, m) \land S(n, j) \land B(n, m))
$$
Найдется проспект $i$ такой, что найдется улица $j$ такая, что найдется 
