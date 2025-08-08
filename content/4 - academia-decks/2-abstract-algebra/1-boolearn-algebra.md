:d Que es la Tautologias, Contradiccion en algebra abstracta?
Definición 1.8 (Contradicción) Son proposiciones siempre falsas.

Que es conjuncion y como se describe matematicamente?
??x
Definición 1.4 ( $\mathbf{Y}$ lógico o conjunción) La proposición $p \wedge q$ se lee " $p$ y $q$ ". Tal como se aprecia en la siguiente tabla de verdad, si se afirma que se tiene $p \wedge q$, lo que se está diciendo es que ambas proposiciones son verdaderas.

| $p$ | $q$ | $p \wedge q$ |
| :-: | :-: | :----------: |
| $V$ | $V$ |     $V$      |
| $V$ | $F$ |     $F$      |
| $F$ | $V$ |     $F$      |
| $F$ | $F$ |     $F$      |
x??

#### Tautologias basicas practicas I
Proposición 1.9 (Tautologías básicas) Las siguientes son tautologías:
Complete the following:
- Dominancia: $p \vee V \Longleftrightarrow ..., \quad p \wedge F \Longleftrightarrow ...$.
- Identidad: $p \wedge V \Longleftrightarrow p, \quad p \vee F \Longleftrightarrow p$.
- Idempotencia: $p \wedge p \Longleftrightarrow ..., \quad p \vee p \Longleftrightarrow ...$.
- Doble negación: $\neg(\neg p) \Longleftrightarrow ...$ (recuerde que $\neg p$ es lo mismo que $\bar{p}$ ).
??x
- Dominancia: $p \vee V \Longleftrightarrow V, \quad p \wedge F \Longleftrightarrow F$.
- Identidad: $p \wedge V \Longleftrightarrow p, \quad p \vee F \Longleftrightarrow p$.
- Idempotencia: $p \wedge p \Longleftrightarrow p, \quad p \vee p \Longleftrightarrow p$.
- Doble negación: $\neg(\neg p) \Longleftrightarrow p$ (recuerde que $\neg p$ es lo mismo que $\bar{p}$ ).
x??


#### Tautologias basicas practicas II
Proposición 1.9 (Tautologías básicas) Las siguientes son tautologías:
Complete the following:

- Tercio excluso: $p \vee \bar{p} \Longleftrightarrow ...$.
- Consistencia: $p \wedge \bar{p} \Longleftrightarrow ...$.
- Absorción: $p \vee(p \wedge q) \Longleftrightarrow ..., \quad p \wedge(p \vee q) \Longleftrightarrow ...$.
- Relajación: $p \wedge q \Longrightarrow ..., \quad p \Rightarrow p \vee q$.
- Caracterización de la implicancia: $(p \Rightarrow q) \Longleftrightarrow ... \vee ...$.
??x
- Tercio excluso: $p \vee \bar{p} \Longleftrightarrow V$.
- Consistencia: $p \wedge \bar{p} \Longleftrightarrow F$.
- Absorción: $p \vee(p \wedge q) \Longleftrightarrow p, \quad p \wedge(p \vee q) \Longleftrightarrow p$.
- Relajación: $p \wedge q \Longrightarrow p, \quad p \Rightarrow p \vee q$.
- Caracterización de la implicancia: $(p \Rightarrow q) \Longleftrightarrow \bar{p} \vee q$.
x??


Proposición 1.10 Las siguientes son tautologías:

Leyes de De Morgan: Mostra un ejemplo de ley de morgan en los siguientes caos
- $\overline{p \wedge q} \Longleftrightarrow ...., \quad \overline{p \vee q} \Longleftrightarrow ...$.
:p completa lo faltante dando ejemplo la ley de Morgan
?x
- $\overline{p \wedge q} \Longleftrightarrow \bar{p} \vee \bar{q}, \quad \overline{p \vee q} \Longleftrightarrow \bar{p} \wedge \bar{q}$.


- Conmutatividad.
:p completa lo faltante dando ejemplo la ley de commutatividad
?x
$$
\begin{aligned}
& -\operatorname{del} \vee: p \vee q \Longleftrightarrow q \vee p . \\
& -\operatorname{del} \wedge: p \wedge q \Longleftrightarrow q \wedge p .
\end{aligned}
$$



- Asociatividad.

$$
\begin{aligned}
& -\operatorname{del} \vee: p \vee(q \vee r) \Longleftrightarrow(p \vee q) \vee r . \\
& -\operatorname{del} \wedge: p \wedge(q \wedge r) \Longleftrightarrow(p \wedge q) \wedge r .
\end{aligned}
$$

- Distributividad.
- del $\wedge$ con respecto al $\vee$ :
$$
p \wedge(q \vee r) \Longleftrightarrow(p \wedge q) \vee(p \wedge r), \quad(q \vee r) \wedge p \Longleftrightarrow(q \wedge p) \vee(r \wedge p) .
$$
- del $\vee$ con respecto al $\wedge$ :
$$
p \vee(q \wedge r) \Longleftrightarrow(p \vee q) \wedge(p \vee r), \quad(q \wedge r) \vee p \Longleftrightarrow(q \vee p) \wedge(r \vee p) .
$$


- Transitividad.
- del $\Rightarrow$ :
$$
(p \Rightarrow q) \wedge(q \Rightarrow r) \Longrightarrow(p \Rightarrow r)
$$
- de la $\Longleftrightarrow$ :
$$
(p \Longleftrightarrow q) \wedge(q \Longleftrightarrow r) \Longrightarrow(p \Longleftrightarrow r)
$$




















