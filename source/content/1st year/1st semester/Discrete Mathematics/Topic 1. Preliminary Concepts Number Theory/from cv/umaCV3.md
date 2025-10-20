## 1.4 Modular Arithmetic

### Congruence Relation

Two numbers are _congruent_ with respect to a module $m\in \mathbb{N}$ if they differ by a multiple of $m$. We find this relationship in many contexts. For example, when working with angles, if we add any multiple of 360, we obtain essentially the same angle, that is, two numbers represent the same angle if they are congruent modulo 360.  

The measurement of time is another source of examples of congruence relationships. Time is divided into blocks of 12 or 24 hours so, for example, 8 o'clock is also 20:00. The same goes for the days of the week and months.

In computing, the congruence relation is used, among other things, to define control digits, that is, numbers or characters that help detect errors. For example, the letter with which the DNI numbers end are obtained by modulo 23 congruence, in such a way that two numbers with the same letter are congruent modulo 23.

In Mathematics, the congruence relation is a fundamental tool to address certain problems, such as the study of divisibility rules.

  

> [!NOTE] Definition (Congruence modulo $m$)
> 
> For $a, b, m\in \mathbb{Z}$ such that $m\ge 2$, it is said that $a$ is _congruent to_ $b$ _modulo_ $m$ if $(a-b)$ is multiple of $m$. In such case, we write $$ a \equiv b \pmod m $$
> 
Other alternative notations that can be found in the bibliography are $a \equiv_m b$, or $a \equiv b (m)$.

> [!example] Example
> 
> - $23 \equiv 17 \pmod 3$, since $23 - 17 = 6 = 2\cdot 3$.
> - $-12 \equiv 14 \pmod{13}$, since $-12 - 14 = -26 = (-2)13$.

> [!NOTE] Theorem
> 
> For $m \in \mathbb{N}$, $m \ge 2$, and $a,b\in\mathbb{Z}$.
> 
> - $a\equiv b \pmod m$ if and only if $a$ and $b$ have the same remainder when diving them by $m$.
> - Each integer $a\in \mathbb{Z}$ is congruent modulo $m$ to one of the following integers: $0, 1, \dots, m-1$.

> [!example] Example
> 
> Given that $231 = 5\cdot 46 + 1$ and $106 = 5\cdot 21 +1$ we could ensure that $231 \equiv 106 \pmod 5$.

The operator $\mathtt{mod}(n,m)$ of Maxima determines the number between  $0$ and $m-1$ congruent to $n$ modulo $m$, Even though $n$ is negative.

(%i1) mod(231,17)

$$ 10 $$

(%i2) (231-10)/17

$$ 13 $$

(%i3) mod(-231,17)

$$ 7 $$

(%i4) (-231-7)/17

$$ -14 $$

If $n$ is positive, $\mathtt{remainder}(n,m)=\mathtt{mod}(n,m)$, but the same does not happen if the first argument is negative, so we should not confuse the two operators.

> [!NOTE] Theorem
> 
> The congruence relation modulo $m$, verifies the following properties:
> 
> 1. _Reflexive:_ $a \equiv a \pmod m$
>     
> 2. _Symmetric:_ If $a \equiv b \pmod m$, then $b \equiv a \pmod m$.
>     
> 3. _Transitive:_ Si $a \equiv b \pmod m$ and $b \equiv c \pmod m$, then $a \equiv c \pmod m$.
>     

We denote by $[a]_m$ to the set numbers congruent to $a$ modulo $m$, and we call it _class of_ $a$ _modulo_ $m$: $$ [a]_m = \{ b\in\mathbb{Z} \mid b\equiv a \pmod m\} $$ Therefore, as a consequence of the properties of the previous theorem, $$ a\equiv b \pmod m \qquad\Longleftrightarrow\qquad [a]_m = [b]_m $$

### Modular Arithmetic

As we have seen, each number is congruent to a number between 0 and $m-1$, so there is exactly $m$ classes modulo $m$ and they are disjoint two by two. We denote by $\mathbb{Z}_m$ to the set of classes modulo $m$. $$ \mathbb{Z}_m=\{[0]_m, [1]_m, [2]_m,\dots, [m-1]_m\} $$

> [!example] Example
> 
> The four classes of modulo 4 congruence are $$
> \begin{align*} [0]_4 & = \{ \dots, -8, -4, 0, 4, 8, \dots \} \\ [1]_4 & = \{ \dots, -7, -3, 1, 5, 9, \dots \} \\ [2]_4 & = \{ \dots, -6, -2, 2, 6, 10, \dots \} \\ [3]_4 & = \{ \dots, -5, -1, 3, 7, 11, \dots \} \\ \mathbb{Z}_4 & =\Big\{[0]_4, [1]_4, [2]_4, [3]_4\Big\}\tag*{ } \end{align*}$$

The properties of the congruence relation allow arithmetic operations to be carried out between classes of congruence, which is what we call modular arithmetic. We can do this thanks to the following result, which states that if we add any element of one class with any element of another class, the result will always be in the same class, regardless of the choice. The same goes for the difference and the product.

> [!NOTE] Theorem (Arithmetic of the congruences)
> 
> For $a,b,c,d, m \in \mathbb{Z}$, such that $m > 1$ and $a \equiv b \pmod m$ and $c\equiv d \pmod m$. Then:
> 
> 1. $a+c \equiv b + d \pmod m$
> 2. $a-c \equiv b - d \pmod m$
> 3. $a \cdot c \equiv b \cdot d \pmod m$

Proof: The proof is a simple check. $$ \left.\begin{array}{l} a = b +m\cdot k_1 \\ c = d +m\cdot k_2 \end{array}\right\}\Longrightarrow \left\{\begin{array}{l} a+c = b +d +m(k_1+k_2) \\ a-c = b -d +m(k_1-k_2) \\ a\cdot c = b\cdot d +m(d\cdot k_1+b\cdot k_2+m\cdot k_1\cdot k_2) \end{array}\right.\tag*{ } $$

Therefore, this theorem justifies that the following operations are well defined within $\mathbb{Z}_m$: $$ [a]_m+[b]_m = [a+b]_m,\quad [a]_m-[b]_m = [a-b]_m,\quad [a]_m[b]_m = [a\cdot b]_m $$

When we work with congruences, we usually want to express the equivalence classes using a positive number smaller than the base of the congruence, so normally, we will use modular arithmetic to simplify the numbers we operate on.

> [!example] Example
> 
> Let's determine the remainder of dividing $79^{7}$ by 11 helping us with operations with equivalence classes. We start by dividing 79 by 11 to obtain the class of 79 modulo 11: $$ 79=11\cdot 7+2 $$ Therefore, $[79]_{11}=[2]_{11}$. To simplify the powers, we are operating them in parts: $$ [79^{7}]_{11} = [2^7]_{11} =[2^4]_{11}[2^3]_{11}=[16]_{11}[8]_{11} =[5]_{11}[8]_{11}=[40]_{11}=[7]_{11} $$ Therefore, $79^{7}\equiv 7\pmod{11}$.

Note that, among the operations with congruence classes, we have not included division, since, in general, division does not preserve congruences: $$ 2\cdot 9 \equiv 2 \cdot 3 \pmod{12},\qquad \text{ but }\qquad 9 ot\equiv 3 \pmod{12} $$

However, the _cancellation_ property is available.

> [!NOTE] Theorem (Cancellation)
> 
> For $a,b,c,m\in \mathbb{Z}$, $m > 1$ and $\operatorname{gcd}(c,m)=1$. If $a\cdot c \equiv b\cdot c \pmod m$, then $a \equiv b \pmod m$.

The proof of this result is quite simple. If $a\cdot c \equiv b\cdot c \pmod m$, then $$ (a-b)c = a\cdot c - b\cdot c =k\cdot m $$ That is, $c$ divides $k\cdot m$, and given that $c$ and $m$ are coprime, necessarily $c$ divides $k$ and therefore, $\frac{k}c\in\mathbb{Z}$. Therefore, $$ a-b =\frac{k}c\cdot m \qquad\Longrightarrow\qquad a \equiv b \pmod m $$

### Euler-Fermat Theorem

In many applications of modular arithmetic the calculation of powers of modular classes will be necessary. The Euler-Fermat theorem that we see in this section helps us simplify powers in certain cases. To state the result, we need to first introduce the Euler function.

> [!NOTE] Definición
> 
> The _Euler_ _function_ $\Phi\colon\mathbb{Z}^+\to\mathbb{Z}^+$ for $n\geq 2$ is defined as the number of positive integers less than $n$ and coprime to $n$.

The following table shows the values ​​that the Euler function takes on the first 12 natural numbers. $$ \begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|} \hline n & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 \\ \hline \Phi(n)& 1 & 2 & 2 & 4 & 2 & 6 & 4 & 6 & 4 & 10 & 4 \\ \hline \end{array} $$

There is no efficient way to evaluate the Euler function and in fact the simplest way to express its value is by using factorization of the number.

> [!NOTE] Theorem (Properties of $\Phi$)
> 
> 1. If $p$ is a prime number, then $\Phi(p^e) = p^e-p^{e-1}$. In particular, if $p$ is prime, $\Phi(p) = p-1$.
>     
> 2. If $m$ and $n$ are coprime numbers, then $\Phi(m\cdot n) = \Phi(m) \cdot \Phi(n)$.
> 3. As a consequence of the previous points, if $n = p_1^{e_1}p_2^{e_2}\dots p_k^{e_k}$ is the factorisation of $n$, then $$ \Phi(n) = (p_1^{e_1}-p_1^{e_1-1})(p_2^{e_2}-p_2^{e_2-1})\dots (p_k^{e_k}-p_k^{e_k-1}) $$

> [!example] Example
> 
> - $\Phi(11)=11-1=10$
> - $\Phi(12)=\Phi(2^2\cdot 3) = (2^2-2^1)(3^1-3^0)=4$
> - $\Phi(180)=\Phi(2^2\cdot 3^2\cdot5)=(2^2-2)(3^2-3)(5-1)=48$

The Euler function is calculated in Maxima with the operator totient

(%i1) totient(504);

$$ 144 $$

(%i2) factor(504);

$$ 2^33^27 $$

(%i3) (2^3-2^2)*(3^2-3)*(7-1);

$$ 144 $$

We can now state the Euler-Fermat Theorem.

> [!NOTE] Theorem (Euler-Fermat)
> 
> For $m\in \mathbb{Z}^+$, $m>1$, and $a\in \mathbb{Z}$ such that $\operatorname{gcd}(a,m) = 1$. Then: $$ a^{\Phi(m)} \equiv 1 \pmod m $$
> 

In the following example, we simplify a power with the help of the Euler-Fermat theorem.

> [!example] Example
> 
> To determine the smallest positive integer $x$ such that $$ x\equiv 15^{39}\pmod{37} $$ We start by using the Euler-Fermat theorem, as $\operatorname{gcd}(15,37) = 1$, to find a power of 15 congruent to 1: $$ 1\equiv 15^{\Phi(37)} = 15^{36} \pmod{37} $$ In this way, the simplification remains: $$ 15^{39} = 15^{36}15^3 \equiv 1\cdot 15^3 = 225\cdot 15 \equiv 3\cdot 15 \equiv 8 \pmod{37}\tag*{ } $$

The Euler-Fermat theorem is part of the calculations performed by the operator power_mod of Maxima.

(%i1) power_mod(15,39,37);

$$ 8 $$

(%i2) mod(15^39,37);

$$ 8 $$

### Linear Congruences

A frequent problem with important applications when working with congruences is the resolution of equations. Specifically, in this course we are going to solve equations of the type $$ a\cdot x\equiv b \pmod m $$ where $a$ and $b$ are any integers and $m>1$. In this equation, we search for the numbers $x$ that make the congruence relation valid. This type of equation is called _linear congruence._

Actually, we already have the fundamental tool to solve linear congruences, since they are basically Diophantine equations: $a\cdot x\equiv b\pmod{m}$ if and only if there exists $y$ such that $a\cdot x+m\cdot y= b$.

> [!example] Example
> 
> Let's solve the congruence $9x \equiv 12 \pmod{15}$, and for this we solve the Diophantine equation $9x +15y =12$. $$\begin{align*} 15 & = 9\cdot \mathbf 1+ 6\\ 9 &= 6\cdot \mathbf 1 +3\\ 6 &=3\cdot \mathbf 2+0 \end{align*}$$ Por lo tanto, $3=\operatorname{gcd}(15,9)$ y $$ (y\quad x)= \Big(\frac{12}3\quad q\Big) \begin{pmatrix} 0 & 1 \\ 1 & -2 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 1 & -1 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 1 & -1 \end{pmatrix}= \Big(3q-4\quad 8-5q\Big) $$
> 
> The variable $y$ has been an auxiliary variable, we are only interested in the values ​​of $x$: $$ x = 8-5q $$
> 
> We are solving a linear congruence modulo 15 and we can see that the set of solutions that we have obtained is made up of three equivalence classes modulo $15$: $$ [x_1]_{15}=[8]_{15},\quad [x_2]_{15}=[8+5]_{15}=[13]_{15},\quad [x_3]_{15}=[13+5]_{15}=[18]_{15}=[3]_{15}\tag*{ } $$
> 

Therefore, the theory of the Diophantine equations that we have studied previously allows us to deduce the following result.

> [!NOTE] Theorem (Brahmagupta)
> 
> For $a, b, m\in\mathbb{Z}$ and $m>1$, let us consider the linear congruence $\begin{equation} a\cdot x \equiv b \pmod m \end{equation}$
> 
> 1. The congruence has a solution if and only if $\operatorname{gcd}(a,m)$ divides $b$.
> 2. In this case, the set of solutions is given by the union of exactly $d=\operatorname{gcd}(a, m)$ equivalence classes modulo $m$.
> 

Proof:

1. The first section is a consequence of the theory associated with Diophantine equations, since the resolution of congruence $a\cdot x \equiv b \pmod m$ is equivalent to solving the equation $a\cdot x +m\cdot y =b$.
    
2. If the linear congruence has a solution, it is determined by solving the Diophantine equation $a\cdot x +m\cdot y =b$. Therefore, the general solution has the form $$ x_0+\dfrac{m}{d}k,\quad \text{for all } k\in\mathbb{Z}, $$ where $x_0$ is a particular solution.
    
3. Therefore, if $t\in\{0,\dots,d-1\}$, the associated solutions to each $k\in[t]_d$, are in the same equivalence class modulo $m$: $\begin{align*} x_0+\dfrac{m}{d}(t+d\cdot s) &= x_0+\dfrac{m}{d}t+m \cdot s \\ & \equiv x_0+\dfrac{m}{d}t \pmod m \end{align*}$
    
4. As a consequence, The set of all solutions is formed by the union of the $d$ equivalence classes modulo $m$ obtained with $k\in\{0,\dots,d-1\}$.
    

> [!example] Example
> 
> - The congruence $2x \equiv 1 \pmod 4$ has no solution, since $2=\operatorname{gcd}(2,4)$ is not divisor of 1.
> - $10x \equiv 8 \pmod{15}$ has no solution, since $5=\operatorname{gcd}(10,15)$ is not divisor of 8.
> - The second section of Brahmagupta's theorem is expressed more briefly by saying that linear congruence has $d$ _solutions modulo_ $m$ or $d$ _incongruent _solutions__. For example, the congruence $2x \equiv 1 \pmod 5$ has only one modulo 5 solution, since $\operatorname{gcd}(2,5)=1$; the congruence $2x \equiv 0 \pmod 4$ has 2 solutions module 4; the congruence $24x \equiv 8 \pmod{28}$ has 4 solutions modulo 28.
>   

### Modular Inverse

We have already seen above that it is not possible to translate the division of integers into a division of congruence classes. In terms of congruences, to calculate the _inverse_ (with respect to the product) of a class $[a]_m$, we need to find a class $[x]_m$ such that $[a\cdot x]_m=[1]_m$; that is, we need to solve the following congruence: $$ a\cdot x \equiv 1 \pmod m $$ From Brahmagupta's theorem, we can ensure that $[a]_m$ has inverse in $\mathbb{Z}_m$ if and only if $\operatorname{gcd}(a,m)=1$, and in such case, the inverse is unique. The inverse of class $[a]_m$ is denoted by $[a]_m^{-1}$. Naturally, this inverse is not calculated by dividing integers, but by solving the linear congruence $a\cdot x \equiv 1 \pmod m$.
  

> [!example] Example
> 
> The class $[6]_{17}$ has inverse, since $\operatorname{gcd}(17,6)=1$. If we use the vector form of Euclid's algorithm, we will calculate the inverse at the same time as we calculate the greatest common divisor:
> $$
> \begin{align*} \Big\lfloor\frac{17}6\Big\rfloor=2\quad\leadsto\quad \begin{pmatrix} 17 \\ 1 \\ 0 \end{pmatrix} -2 \begin{pmatrix} 6 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \\ -2 \end{pmatrix} \\ \Big\lfloor\frac65\Big\rfloor=1\quad\leadsto\quad \begin{pmatrix} 6 \\ 0 \\ 1 \end{pmatrix} - \begin{pmatrix} 5 \\ 1 \\ -2 \end{pmatrix} = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix} \end{align*}
> $$
>  Let us remember that this means that $$ 1=17\cdot(-1)+6\cdot 3 $$ and therefore we can affirm that $\operatorname{gcd}(17,6)=1$ and that 3 is the inverse of 6 modulo 17.
> 
> As we can see in this example, if we are only interested in calculating the inverse of a number, we only need the third component of the vector. This allows us to simplify Euclid's algorithm if we apply it to this operation:
> 
> $$\begin{align*} \begin{pmatrix} 17 \\ 0 \end{pmatrix} -2 \begin{pmatrix} 6 \\ 1 \end{pmatrix} &= \begin{pmatrix} 5 \\ -2 \end{pmatrix} \\ \begin{pmatrix} 6 \\ 1 \end{pmatrix} - \begin{pmatrix} 5 \\ -2 \end{pmatrix} &= \begin{pmatrix} 1 \\ 3 \end{pmatrix} = \begin{pmatrix} \text{g.c.d.} \\ \text{Inverse} \end{pmatrix} \tag*{ } \end{align*}$$
> 

The operator $\mathtt{inv\_mod}(a,m)$ of Maxima calculates the inverse of $a$ modulo $m$

(%i1) inv_mod(5,17)

$$ 7 $$

(%i2) mod(5*7,17)

$$ 1 $$

The use of inverses gives us an alternative way to resolve linear congruences.

> [!example] Example
> 
> We use the inverse calculated in the previous example to solve the following linear congruence: $$\begin{align*} 6x & \equiv 5\pmod{17} \\ [6]_{17} [x]_{17} &= [5]_{17} \\ [x]_{17} &= [6]_{17}^{-1} [5]_{17} \\ [x]_{17} &= [3]_{17} [5]_{17} \quad \text{(previous example)}\\ [x]_{17} &= [15]_{17} \\ x &= 15+17k,\ k\in\mathbb{Z}\tag*{ } \end{align*}$$

> [!example] Example
> 
> The congruence $12x\equiv 14\pmod{34}$ has two solutions modulo 34, since $\operatorname{gcd}(12,34)=2$ and 14 is a multiple of 2. Since 12 and 34 are not coprime, we cannot use inverses directly. When we reach that point, it is enough to go to the Diophantine equation to be able to simplify before continuing the calculation with congruences. $$\begin{align*} 12x & \equiv 14\pmod{34} \\ 12x & = 14+34k\\ 6x &= 7+17k \\ 6x & \equiv 7\pmod{17} \\ 3\cdot 6x & \equiv 3\cdot 7\pmod{17} \\ x & \equiv 4\pmod{17} \end{align*}$$ Therefore, the two solutions modulo 34 are: $$ x_1\equiv 4\pmod{34}\quad\text{ y }\quad x_2\equiv 4+17=21\pmod{34}\tag*{ } $$
> 

The Euler-Fermat theorem gives us an alternative way to calculate modular inverses. If $\operatorname{gcd}(a,m) = 1$, then $a\cdot a^{\Phi(m)-1}= a^{\Phi(m)} \equiv 1 \pmod m$. Therefore, $[a]^{-1}_m =[a^{\Phi(m)-1}]_m$. However, applying this formula requires evaluating the Euler function and simplifying powers, which is computationally very expensive.

### Systems of linear congruences

On many occasions, solving a problem will involve satisfying more than one linear congruence. For example, if we ask for a number that has the following characteristics: dividing by 3 gives a remainder 1, dividing by 5 gives a remainder 2, and dividing by 7 gives a remainder 3, we are looking for a number that simultaneously satisfies the following linear congruences: $$\begin{align*} x&\equiv 1 \pmod 3 \\ x&\equiv 2 \pmod 5 \\ x&\equiv 3 \pmod 7 \end{align*}$$

The results that allow us to determine if these systems have a solution are the following.

> [!NOTE] Theorem
> 
> Let $m_1, m_2, \dots , m_k$ natural numbers greater than 1 and $b_1, b_2, \dots , b_k\in\mathbb{Z}$.
> 
> 1. The system of congruences, $$\begin{align*} x & \equiv b_1 \pmod{m_1} \\ x & \equiv b_2 \pmod{m_2} \\ & \vdots \\ x & \equiv b_k \pmod{m_k} \end{align*}$$ has a solution if, and only if, the systems formed by each pair of congruences have a solution.
> 2. Each system $$\begin{align*} & x \equiv b_\alpha \pmod{m_\alpha}\\ & x \equiv b_\beta \pmod{m_\beta} \end{align*}$$
>     
>     has a solution if and only if $b_\alpha- b_\beta$ is multiple of $d=\operatorname{gcd}(m_\alpha,m_\beta)$; In that case, the solution is modulo only $M=\operatorname{lcm}(m_\alpha,m_\beta)$.
>     

Proof: We are going to demonstrate only the second part and we are going to use the subscripts 1 and 2 instead of $\alpha$ and $\beta$ for ease of reading.

- The necessity of the condition $b_1 \equiv b_2 \pmod{d}$ is trivial.  
    If $x=b_1+k_1m_1$ and $x=b_2+k_2m_2$, then subtracting the two equalities member by member and rearranging the addends we obtain: $$ b_1-b_2 = k_2m_2-k_1m_1 $$
    
- And since $d$ divides $m_1$ and $m_2$, must necessarily divide $b_1-b_2$.
    
- The proof that, in such a case, we can determine the solutions, describes the method of solution.
    
- Using Ecuclides' algorithm, we find the linear combination of the Bézout identity for $m_1$ and $m_2$: $$ d = t_1\cdot m_1 + t_2\cdot m_2 $$
    
- Given that $b_1-b_2 = k\cdot d$, we can perform the following steps: $$\begin{align*} b_1-b_2 = k\cdot d & = (k\cdot t_1)\cdot m_1 + (k\cdot t_2)\cdot m_2 \\ b_1-(k\cdot t_1)\cdot m_1 & = b_2 + (k\cdot t_2)\cdot m_2 \end{align*}$$
    
- And therefore, this number is the solution of the two equations.
    
- Let's assume now that $x$ and $x'$ are solutions of the system and let us show that, then $x\equiv x'\pmod M$: $$\begin{align*} \left.\begin{array}{c} x = b_1 +k_1 m_1 \\ x' = b_1 +k'_1 m_1 \end{array}\right\}\quad & \Longrightarrow \quad x-x' = (k_1-k_1')m_1 \\ \left.\begin{array}{c} x = b_2 +k_2 m_2 \\ x' = b_2 +k'_2 m_2 \end{array}\right\}\quad & \Longrightarrow \quad x-x' = (k_2-k_2')m_2 \end{align*}$$
    
- Therefore, $x-x'$ is multiple of $m_1$ and $m_2$, and as a consequence multiple of $M=\operatorname{lcm}(m_1,m_2)$.
    

> [!NOTE] Corollary
> 
> Let us consider the following system of congruences $\begin{align*} & x \equiv a \pmod{n}\\ & x \equiv b \pmod{m} \end{align*}$ If $a-b$ is multiple of $d=\operatorname{gcd}(n,m)$, $d=s\cdot n+t\cdot m$, and $M=\operatorname{lcm}(n,m)$, then the solution of the system is $$ x \equiv a-\frac{s\cdot n(a-b)}{d} \pmod{M}, $$

> [!example] Example
> 
> We are going to solve the following system of congruences following the process described in the previous demonstration $\begin{align*} x\equiv 1\pmod{10}\\ x\equiv 11\pmod{15} \end{align*}$
> 
> We begin by determining the identity of Bezout for 15 and 10: $$ \Big\lfloor\frac{15}{10}\Big\rfloor=1\quad\leadsto\quad \begin{pmatrix} 15 \\ 1 \\ 0 \end{pmatrix} - \begin{pmatrix} 10 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \\ -1 \end{pmatrix} $$
> 
> Given that $5 | 10$ we can already affirm that $\operatorname{gcd}(15,10)=5$ and moreover $$ 5 = 15\cdot 1 +10\cdot (-1),\qquad\quad \operatorname{lcm}(15,10)=\frac{15\cdot 10}{5}=30 $$
> 
> Given that $11-1= 10$ is multiple of 5, we can affirm that the system of congruences has a solution and
> 
> $$\begin{align*} x & \equiv 1-\frac{(-1)10(1-11)}{5} \pmod{30} \\ x &\equiv -19 \pmod{30} \\ x & \equiv 11 \pmod{30} \tag*{ } \end{align*}$$

We can also solve the systems using the properties of congruences as we show in the following example.

> [!example] Example
> 
> We return to consider the following system $$\begin{align*} x\equiv 1\pmod{10}\\ x\equiv 11\pmod{15} \end{align*}$$
> 
> From the first equation we obtain that $x=1+10k$, so we are going to find the value of $k$ so that the second congruence is also verified.
> 
> $$\begin{align*} x&=1+10k \\ 1+10k &\equiv 11\pmod{15} \quad \text{ (we substitute in the second congruence)}\\ 10k &\equiv 10\pmod{15} \\ 5k &\equiv 5\pmod{15}\quad \text{ (cancellation, since }\operatorname{gcd}(2,15)=1)\\ 5k & = 5+15 m \\ k & = 1+3 m \\ x &= 1+10(1+3m) =11+30m \\ x &\equiv 11\pmod{30}\tag*{ } \\ \end{align*}$$
> 

As a consequence of the general theorem, if the modulos are coprime two by two, then the system has a solution. This particular case is known as the Chinese remainder theorem.

> [!NOTE] Corollary (Chinese Remainder Theorem)
> 
> Let $m_1, m_2, \dots , m_k$ be positive integers greater than 1 and coprime two by two and let be $b_1, b_2, \dots , b_k\in\mathbb{Z}$. Then, the following system of congruences has a solution: $$\begin{align*} x & \equiv b_1 \pmod{m_1} \\ x & \equiv b_2 \pmod{m_2} \\ & \vdots \\ x & \equiv b_k \pmod{m_k} \end{align*}$$ Furthermore, if $x$ and $x'$ are solutions, then $x\equiv x' \pmod{m_1 m_2 \cdots m_k}$.

> [!example] Example
> 
> Let's solve the system proposed in the introduction of this section: $\begin{align*} x & \equiv 1 \pmod3 \\ x & \equiv 2 \pmod5 \\ x & \equiv 3 \pmod7 \end{align*}$
> 
> 1. From the first equation, we deduce that $x=3k+1$. We use this equality to substitute $x$ in the second equation, which we will work on using the representation of congruence classes: $\begin{align*} [x]_5 = [3k+1]_5 & =[2]_5 \\ [3k]_5 & =[1]_5 \\ [k]_5 & =[3]^{-1}_5[1]_5 = [3^3]_5= [2]_5 \\ k & =5m+2 \\ x & =3k+1=3(5m+2)+1=15m+7 \end{align*}$
> 2. Next we take this expression for $x$ to the last congruence: 
> $$\begin{align*} [x]_7 =[15m+7]_7& =[3]_7 \\ [m]_7 &=[3]_7\qquad \text{(Since $15\equiv 1\pmod7$, $7\equiv 0\pmod7$)} \\ m & =7q+3 \\ x &=15m+7= 15(7q+3)+7=105q+52\\ x & \equiv 52 \pmod{105}\tag*{ } \end{align*}$$

> [!NOTE] Maxima Code
> 
> The operator $$ \texttt{chinese(coefs,mods)} $$ determines the solutions of a system of congruences with a solution or returns false if there is no solution. The system that we have solved in the previous example would be written:
> 
> (%i1) chinese([1,2,3],[3,5,7);
> 
> $$ 52 $$
> 
> Other examples with modules that are not two-to-two coprime:
> 
> (%i2) chinese([14,20,34],[15,21,35]);  
> 
> $$ 104 $$
> 
> (%i3) chinese([13,20,33],[15,21,35]);
> 
> $$ \text{false}\tag*{ } $$

  

> [!example] Example
> 
> We see a final example in which the solution is not unique modulo the least common multiple of the modules, but the learned method is still applicable.
> 
> $$\begin{align*} 8x & \equiv 2 \pmod{30} \\ x & \equiv 10 \pmod{21} \end{align*}$$
> 
> We start with the second congruence, which is already resolved, $x=10+21q$, and we substitute in the first: $$ \begin{align*} 8(10+21q) \equiv\ & 2 \pmod{30} \\ 8(10-9q) \equiv\ & 2 \pmod{30} \\ 80-72q \equiv\ & 2 \pmod{30} \\ -72q \equiv\ & -78 \pmod{30} \\ 72q \equiv\ & 78 \pmod{30} \\ 12q \equiv\ & 18 \pmod{30} \\ 2q \equiv\ & 3 \pmod{5} \\ 3\cdot 2q \equiv\ & 3\cdot 3 \pmod{5} \\ q \equiv\ & 4 \pmod{5} \\ x & =10+21(4+5m)= 94+105m \\ x & \equiv 94\pmod{105} \end{align*}$$
> 
> The modules of the initial system were 21 and 30, so the solutions must be expressed modulo $\operatorname{lcm}(21,30)=210=2\cdot 105$. Therefore, the system has two solutions: $$ x \equiv 94\pmod{210},\qquad\qquad x \equiv 94+105 = 199\pmod{210}\tag*{ } $$

### Application: divisibility criteria

One of the applications of modular arithmetic is obtaining divisibility criteria described on the digits of the decimal expression. Let us first observe that if a number $N$ is divisible by another number $p$, then the remainder of the division of $N$ by $p$ is 0, that is, the class of $N$ modulo $p$ is the class of 0. Therefore, in order to determine if $N$ is divisible by $p$, it is enough to simplify the class of $N$, using the properties of modular arithmetic.

To make this simplification in a general way, we use the expression of the numbers determined by their expression in base ten. If $N=(\delta_\ell\delta_{\ell-1}\delta_{\ell-2}\dots\delta_{1}\delta_{0})_{(10}$, then $$ N=\sum_{i=0}^\ell \delta_i10^i $$ Por lo tanto, $N$ is divisible by $p$ if and only if $$ \left[\sum_{i=0}^\ell \delta_i10^i\right]_p = [0]_p $$ Therefore, to determine if $N$ is divisible by $p$ it is enough to simplify the above class in $\mathbb{Z}_p$ using the properties of congruences. This simplification will only depend on the digits $\delta_i$ since powers of 10 are constant. This allows us to obtain divisibility rules based on the digits.

> [!example] Example
> 
> We are going to deduce the divisibility rule by $p=3$. To do this we simplify the powers of 10 modulo 3. $$\begin{align*} [10]_3 & = [1+3\cdot 3]_3=[1]_3 \\ [10^i]_3 & = [1^i]_3=[1]_3 \end{align*}$$ Therefore, $$ \left[\sum_{i=0}^\ell \delta_i10^i\right]_3= \left[\sum_{i=0}^\ell \delta_i \right]_3 $$ That is, a number $N$ is divisible by 3 if and only if the sum of its digits is divisible by 3. For example, $$ [12473]_3 = [1+2+4+7+3]_3 =[1+2+1+1+0]_3 =[5]_3=[2]_3 $$ and as a consequence 12473 is not a multiple of 3.
> 

### Positional Number Systems

A _number system_ is a set of symbols and rules by which we can represent integers. The numbering system that we usually use is a _positional_ system defined on the basis of numbering 10. This means that we use ten symbols that represent the quantities from zero to nine, but when written in a concatenated way they take on a value that depends on the position in chain. For example, the digit string 34735 represents the number $$ 3\cdot 10^4 + 4 \cdot 10^3 + 7 \cdot 10^2 + 3 \cdot 10^1 + 5 \cdot 10^0 $$

 Similar representations can be defined using any number as a base. In fact, different civilizations have used bases other than 10, such as the Babylonians, who used the base six or the Mayans who used the base twenty.

Currently, the use of different numbering bases has important applications in computing. For example, base two is commonly used to represent low-level computer data, and bases eight and sixteen are used in cryptography and communications.

> [!NOTE] Theorem
> 
> Let $b$ be a a positive integer, $b > 1$. Then, every positive integer $n$ can be written uniquely as a linear combination of powers of $b$ $$ n = a_k\cdot b^k + a_{k-1} \cdot b^{k-1} + \dots + a_1 \cdot b^1 + a_0 \cdot b^0 $$ where each $a_j$ is an integer such that $0 \leq a_j \leq b-1$ and $a_ke 0$.
> 

According to this theorem, the number $n$ is written as $$ n = (a_k \ a_{k-1} \ \dots \ a_1 \ a_0)_{(b} $$ We will omit the parentheses if it does not lead to confusion, and we will not add the base indicator when this is the decimal base. Typically, a single symbol is used to represent each number between 0 and $b-1$. If the base $b$ is less than 10, these symbols are the digits that we usually use and if the base is greater than 10, we use letters to represent numbers greater than 10. For example, in base 16, or hexadecimal, the symbols used are 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, where $\mathrm A= 10$, $\mathrm B=11$, $\mathrm C=12$, $\mathrm D=13$, $\mathrm E=14$ and $\mathrm F=15$.

> [!NOTE] Example
> 
> Let's determine the number represented by the sequence 1B03A3 in the hexadecimal base passing it to the decimal base. $$ \mathrm{1B03A3}_{(16}= 1\cdot 16^5+11\cdot 16^4+0\cdot 16^3+3\cdot 16^2+10\cdot 16+3 =1\,770\,403\tag*{ } $$
> 

The proof of the previous theorem consists of establishing the procedure to find the numbers $a_j$ that will form the representation. These numbers are the remainders obtained by successively applying the division algorithm, as we see in the following example.  

> [!example] Example
> 
> Let's write the number $n= 3785$ in base $b = 7$; naturally, we use the digits 0, 1, 2, 3, 4, 5, 6. To construct the sequences in this numbering base we have to: $\begin{alignat*}{2} 3785 &= 7\cdot 540 + 5\quad & \Longrightarrow\quad & a_0=5 \\ 540 &= 7\cdot 77 + 1 & \Longrightarrow\quad & a_1=1 \\ 77 &= 7\cdot 11 + 0 & \Longrightarrow\quad & a_2=0 \\ 11 &= 7\cdot 1 + 4 & \Longrightarrow\quad & a_3=4 \\ 1 &= 7\cdot 0 + 1 & \Longrightarrow\quad & a_4=1 \end{alignat*}$ The quotient of the last division is 0 and therefore we cannot continue dividing, so the remainder of that division is the last digit of the representation. Consequently $$ 3785 = 14015_{(7} $$ We are not going to do the formal proof of the theorem, but we are going to verify in this example that the process of chained divisions generates the representation in the given base. We can also observe that the sequence of digits obtained is unique, since the quotient and the remainder in the integer division are unique for each dividend-divisor pair. We do the verification by replacing the numbers on the left, in the sequence of divisions, with the expression on the right: $\begin{align*} 3785 &= 7\cdot 540 + 5= \\ &= 7\cdot (7\cdot 77 + 1)+ 5= \\ &= 7\cdot (7\cdot (7\cdot 11 + 0) + 1)+ 5= \\ &= 7\cdot (7\cdot (7\cdot (7\cdot 1 + 4) + 0) + 1)+ 5 \end{align*}$ If we now remove the parentheses without operating the powers of 7, we obtain the expression of the number as a linear combination of powers of 7: $\begin{align*} 3785 &= 7\cdot (7\cdot (7\cdot (7\cdot 1 + 4) + 0) + 1)+ 5 =\\ &= 7\cdot (7\cdot (7^2\cdot 1 + 7\cdot 4 + 0) + 1)+ 5 =\\ &= 7\cdot (7^3\cdot 1 + 7^2\cdot 4 + 7\cdot 0 + 1)+ 5 =\\ &= 7^4\cdot 1 + 7^3\cdot 4 + 7^2\cdot 0 + 7\cdot 1+ 5 =\\ &= 1\cdot 7^4 + 4\cdot 7^3 + 0\cdot 7^2 + 1\cdot 7+ 5 \tag*{ } \end{align*}$

Maxima does not have any predefined operators to convert numbers between different bases, but it is easy to do it using the operators available on lists. When we deal with numbers written with digits in a positional system, these numbers must be understood as lists:

$$ 3785 \leadsto [3,7,8,5] $$

_L__ists_ are a basic data structure in programming and all languages ​​include a set of basic operators to manipulate them. As we have seen above, the usual way of representing lists is by delimiting their elements, which will be separated by commas, between square brackets. Unlike sets, the order in which the elements are placed in the list determines the list and can contain repeated elements: $$ [1,2,3]e [3,2,1];\qquad [2,2,1,3]e [2,1,3] $$

Maxima includes different operators to work with lists; Below we see the most basic ones, those that define the structure, and throughout the course we will learn some more:

- $\mathtt{cons}(x,[x_1,\dots,x_n]) = [x,x_1,\dots,x_n]$
    
- $\mathtt{first}([x_1,\dots,x_n]) = x_1$
    
- $\mathtt{rest}([x_1,x_2,\dots,x_n])= [x_2,\dots,x_n]$
    
- Si $x$ es una lista, $x[i]$ representa al $i$-ésimo elemento de $x$.
    

As we said above, the representation of numbers using a number base is essentially a representation using lists. But usually, we represent the digits with a single symbol, so we can do without the brackets and commas:

$$ 31AB_{(16} \leadsto [3,1,10,11] $$

To work with Maxima, however, we will use full list notation and can use numbers greater than 10 as digits.  

To define the conversion of a number in a base other than 10 to the base 10, we are going to use the operator lreduce, _reduction on the left_. If $f(x,y)$ is a function of two arguments and $\ell$ is a list of more than two elements, lreduce $(f,\ell)$ applies the function $f$ to the list elements grouping them from the left:

$$ \texttt{lreduce}(f,[a,b,c])=f(f(a,b),c) $$

If we look at the example above, we see that to convert a number from base 7 to base 10, we have used the function $f(x,y)=7x+y$ grouping the digits two by two from the left. Therefore, we can use the following instructions:

(%i1) b7(x,y):=7*x+y$ (%i2) lreduce(b7,[1,4,0,1,5]);

$$ 3785 $$

We can also do it using the summation operator

(%i1) a: [1,4,0,1,5])$ (%i13) sum(a[k]*7^(5-k),k,1,5);

$$ 3785 $$

We have seen that the inverse process consists of carrying out a series of successive divisions, which we can easily describe with a recursive definition:

(%i1) base(b,N,res):= if N=0 then res else base(b,quotient(N,b),cons(remainder(N,b),res))$ (%i2) base(7,3785,[]);

$$ [1,4,0,1,5] $$
