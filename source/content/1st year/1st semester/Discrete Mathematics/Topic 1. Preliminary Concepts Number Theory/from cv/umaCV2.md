## 1.3 Diophantine Equations

### The Euclidean Algorithm and the Bézout Identity

Although calculating the common divisors or factoring two numbers allows us to easily determine the greatest common divisor of two small numbers, they are not efficient methods when we work with large numbers. We are going to learn how to use _Euclid's algorithm_ to determine the greatest common divisor of two numbers. This algorithm has two advantages: it is much more efficient than the decomposition into prime factors and it can be completed to obtain an efficient method to determine the _Bézout identity_, which constitutes the fundamental tool for solving the Diophantine equations

Euclid's algorithm is based on the following property, a consequence of the algebraic properties of divisibility: a number \(d\) is a common divisor of two other numbers \(n\) and \(m\) if and only if it is a divisor of \(n-m\) and \(m\). Therefore:

Lemma

Let \(n\) and \(m\) two natural number such that \(n>m\), then \[ \operatorname{gcd}(n,m)=\operatorname{gcd}(n-m,m) \]

We can use this result to calculate the greatest common factor of two numbers by simply subtracting.

Example

Let's calculate the greatest common divisor of \(33\) and \(21\) using the previous lemma as many times as necessary until reaching a trivial calculation:         \begin{multline*} \operatorname{gcd}(33,21) = \operatorname{gcd}(12,21)=\operatorname{gcd}(21,12)=\operatorname{gcd}(9,12)=\\ =\operatorname{gcd}(12,9)=\operatorname{gcd}(3,9)=\operatorname{gcd}(9,3)=\operatorname{gcd}(6,3)=\operatorname{gcd}(3,3)=3\tag*{ } \end{multline*}

---

The method described in this example constitutes an efficient algorithm for calculating the greatest common divisor and is the basis for the demonstration of the following result, which describes Euclid's algorithm to calculate the greatest common divisor of two numbers and which will be the fundamental tool for the rest of the topic.

Let \(n\) and \(m\) two natural numbers such that \(n>m\) y \(n=mq+r\), then \[ \operatorname{gcd}(n,m)=\operatorname{gcd}(m,r) \]

Theorem (Euclidean Algorithm or Euclid's Algorithm)

For \(n,m\in\mathbb{Z}^+\) we consider the sequences of positive integers, \(q_1,\dots,q_{k+1}\) and \(r_1,\dots,r_k\), obtained by applying repeatedly the division algorithm: \[ \begin{aligned} n - m\cdot q_1 & = r_1\\ m - r_1\cdot q_2 & = r_2\\ r_1 - r_2\cdot q_3 & =r_3 \\ \dots &\dots \\ r_{k-3} - r_{k-2}\cdot q_{k-1} & = r_{k-1} =\operatorname{gcd}(n,m)\\ r_{k-2} - r_{k-1}\cdot q_k & = r_k =0 \end{aligned} \] \[ \renewcommand{\arraystretch}{1} \begin{array}{cclcrcclcl} n & = & m\cdot q_1 + r_1 &\qquad & 0 & < & r_1 & < & m \\ m & = & r_1\cdot q_2 + r_2 &\qquad & 0 & < & r_2 & < & r_1 \\ r_1 & = & r_2\cdot q_3 + r_3 &\qquad & 0 & < & r_3 & < & r_2 \\ r_2 & = & r_3\cdot q_4 + r_4 &\qquad & 0 & < & r_4 & < & r_3 \\ &\dots& & && &\dots &\\ r_{k-3} & = & r_{k-2}\cdot q_{k-1} + r_{k-1} &\qquad & 0 & < & r_{k-1}  & < & r_{k-2} \\ r_{k-2} & = & r_{k-1} \cdot q_{k} + 0 &\qquad & & & & & \end{array} \] Then \(r_{k-1} = \operatorname{gcd}(n,m)\)

Example

Numbers 21 are 13 coprime numbers: \[ \begin{array}{ccr} 21 & = & 13\cdot 1 + 8 \\ 13 & = & 8 \cdot 1 + 5 \\ 8 & = & 5 \cdot 1 + 3 \\ 5 & = & 3 \cdot 1 + 2 \\ 3 & = & 2 \cdot 1 + \fbox1 \\ 2 & = & 1 \cdot 2 + 0 \\ \end{array} \tag*{ }\]


---

Theorem (Bézout Identity)

If \(n, m\in \mathbb{Z}^+\), then there exist \(s,t\in\mathbb{Z}\) such that \(\operatorname{gcd}(n,m)=n\cdot s + m\cdot t\).

The proof is based on the sequence of divisions that allow us to calculate the greatest common factor and in addition, the proof establishes the method for calculating the numbers \(s\), \(t\).

Solving the remainders in the sequence of divisions, we obtain the following equalities: \[ \begin{aligned} r_1 & = n - m\cdot q_1 \\ r_2 &= m - r_1\cdot q_2 \\ r_3 & = r_1 - r_2\cdot q_3 \\ &\dots \\ r_{k-1} & = r_{k-3} - r_{k-2}\cdot q_{k-1}\\ \operatorname{gcd}(n,m)= r_k & = r_{k-2} - r_{k-1}\cdot q_k \end{aligned} \]

In this way, if from bottom to top, we substitute the numbers \(r_i\) until we reach the first equality, we will have built the desired linear combination.

Let's see this process in the following example. The only difficulty of the process is that we work with numbers, and it is difficult to distinguish the role they play in each equality (remainder, dividend or divisor). For that reason, we are going to “box” the initial numbers and the remainders to remember that we do not have to operate on them, we can only replace them with the expression given by the previous division.

In general, it is not true that if \(n\cdot s+m\cdot t = d\), then \(d=\operatorname{gcd}(n,m)\). For example, \(2\cdot 2 + 3\cdot 2= 10\) and \(\operatorname{gcd}(2,3)\ne 10\ne \operatorname{gcd}(2,2)\). However, the conclusion is true if the numbers are coprime.

---
Corollary

If there are integers \(s\) and \(t\) such that \(n\cdot s+m\cdot t=1\), then \(\operatorname{gcd}(n,m)=1\), that is, \(n\) and \(m\) are coprime numbers.

The proof is an immediate consequence of the basic properties of divisibility: if \(n\cdot s+m\cdot t=1\), then any common divisor to \(m\) and \(n\) would be divisor of 1 and therefore, 1 is the only common divisor and \(\operatorname{gcd}(n,m)=1\).

This property is useful for proving properties related to divisibility.

---
### Vector Form and Bézout Identity

 Allows to obtain the Bézout identity  using an alternative method that will allow us to recursively define the process. Specifically, we will start from the following trivial equalities, \begin{align*} m & = 1\cdot m + 0\cdot n\\ n & = 0\cdot m + 1\cdot n \end{align*} and from them, we are going to perform elementary operations on the left and right side until we obtain the greatest common divisor on the left side and the combination of the Bézout identity on the right side.

Example

We are going to calculate the greatest common divisor of 250 and 111 and obtain the linear combination established by the Bézout identity.

We start with the following two trivial equalities:

\begin{alignat*}{4} 250 & =& 1&\cdot 250 + 0&&\cdot 111 &&\qquad (1)\\ 111 & =& 0&\cdot 250 + 1&&\cdot 111 &&\qquad (2)\\ \end{alignat*}

The quotient of dividing 250 by 111 is 2 and \(250-2\cdot 111=28\); carrying out this operation with the right and left parts of the previous equalities, we obtain:

\[ 28 = 250 - 2\cdot 111 = 1 \cdot 250 -2 \cdot 111 \qquad (3)=(1)-2\cdot (2) \] Now we divide 111 by 28 and obtain the quotient 3, so: \[ 27=111 - 3\cdot 28 = -3 \cdot 250 +7 \cdot 111 \qquad (4)=(2)-3\cdot (3) \] Finally, we dividide 28 by 27 and obtain quotient and remainder equal to 1: \[ 1= 28-27 = 4 \cdot 250 -9 \cdot 111 \qquad (5)=(3)-(4) \]

That is, the numbers on the right side determine the operations we do, but we perform them on both sides. As we can see, the numbers 250 and 111 on the right side have not been operated on at any time and we have only worked with their “coefficients”. For this reason, the previous process can be simplified by describing it on vectors with three coefficients and therefore, we will call this way of determining the Bezout identity _vector form_.

\begin{align*} \Big\lfloor\frac{250}{111}\Big\rfloor= 2\quad \leadsto \quad \begin{pmatrix}250\\1\\0\end{pmatrix} - 2&\cdot \begin{pmatrix}111\\0\\1\end{pmatrix} = \begin{pmatrix}28\\1\\-2\end{pmatrix}\\ \Big\lfloor\frac{111}{28}\Big\rfloor = 3\quad \leadsto \quad \begin{pmatrix}111\\0\\1\end{pmatrix} - 3 &\cdot \begin{pmatrix}28\\1\\-2\end{pmatrix} = \begin{pmatrix}27\\-3\\7\end{pmatrix} \\ \Big\lfloor\frac{28}{27}\Big\rfloor = 1\quad \leadsto \quad \begin{pmatrix}28\\1\\-2\end{pmatrix} - & \begin{pmatrix}27\\-3\\7\end{pmatrix} =\begin{pmatrix}1\\4\\-9\end{pmatrix} \end{align*}

---
### Diophantine equations

We talk about Diophantine equations if we are interested in solving them within \(\mathbb{Z}\). They are named after the Greek mathematician Diophantus, who wrote extensively about these types of equations. In this course, we are only going to study the linear Diophantine equations, the solution of which can be determined with Euclid's algorithm and Bézout identity.  

Definition

A _two-variable linear Diophantine equation_ is an equation of the form \[ n\cdot x + m\cdot y = k, \] where \(n, m, k\in\mathbb{Z}\), and the unknowns \(x\) and \(y\) should be solve in \(\mathbb{Z}\).

Theorem

The equation \(n\cdot x + m\cdot y = k\) has solutions of \(\mathbb{Z}\) if and only if \(d=\operatorname{gcd}(n,m)\) divides \(k\). In such a case, if the  pair \((x_0, y_0)\) is a solution of the equation, then the remainder of the solutions are given by \[ x = x_0 + \Big(\frac{m}{d}\Big)q, \quad y = y_0 - \Big(\frac{n}{d}\Big)q,\quad q \in \mathbb{Z} \]

##### Proof of the theorem:

- (\(\Rightarrow\)) If \(d=\operatorname{gcd}(n,m)\), then \(d\) divides \(n\) and \(m\) and as a consequence divides \(n\cdot x + m\cdot y=k\) for all \(x,y\in\mathbb{Z}\).
    
- (\(\Leftarrow\)) If \(d=\operatorname{gcd}(n,m)\) divides \(k\), then \(k=d\cdot c\) for some \(c\in\mathbb{Z}\). Furthermore, by Bézout identity, there are integers \(s\) and \(t\) such that \[ d = n\cdot s+m\cdot t \]
    
    and in consequence, \(k=c\cdot d = n\cdot c\cdot s+m\cdot c\cdot t\); that is \(x_0=c\cdot s\) and \(y_0=c\cdot t\) form a solution of the equation.
    
- Let's suppose \((x_0,y_0)\) is a solution of the equation and let \[ x = x_0 + \frac{m}{d} q, \qquad y = y_0 - \frac{n}{d} q \] for any \(q\in\mathbb{Z}\); Let's check that they are also a solution of the equation \begin{multline*} \require{cancel} n\cdot x + m\cdot y = n\cdot \Big(x_0 + \frac{m}{d}q\Big) + m\cdot \Big(y_0 -\frac{n}{d}q\Big) = \\ = n\cdot x_0 + \cancel{\frac{n\cdot m\cdot q}d} + m\cdot y_0 -\cancel{\frac{m\cdot n\cdot q}d} = n\cdot x_0 + m\cdot y_0 = k \end{multline*}
    
- Finally, we have to prove that there are no more solutions than those described in the previous point. Let's suppose that \((x,y)\) is another solution of the equation, besides \((x_0,y_0)\): \[ n\cdot x + m\cdot y = k,\qquad\quad n\cdot x_0 + m\cdot y_0 = k \] We subtract the previous equalities, member by member, and operate as shown below: \begin{align*} n(x-x_0) &+ m(y-y_0) = 0 \\ \frac{n}d(x-x_0) &+ \frac{m}d(y-y_0) = 0 \\ \frac{n}d(x-x_0) &= \frac{m}d(y_0-y) \end{align*}
    
    Given that \(\dfrac{n}{d}\) and \(\dfrac{m}{d}\) are coprime numbers, so that the previous equality is verified, \(\dfrac{n}{d}\) must necessarily divide \((y_0-y)\) and \(\dfrac{m}{d}\) must divide \((x-x_0)\). Therefore, \(\dfrac{x-x_0}{m/d} = \dfrac{y_0-y}{n/d} = q\in\mathbb{Z}\).
---


Corollary

If \(\operatorname{gcdex}(n,m)=\begin{pmatrix}d \\ s\\ t\end{pmatrix}\) and \(d\) divides \(c\), then the solution of the equation \(n\cdot x + m\cdot y = c\) is: \[ \binom x y =\frac1d\left[c\binom s t +q\binom {-m}n\right],\quad \text{for each } q\in\mathbb{Z}, \]

The previous demonstration describes the procedure for solving a Diophantine equation, as we reproduce in the following example.

Example

Let's study the Diophantine equation \(21x + 14y = 70\). We first calculate \(\operatorname{gcdex}(21,14)\): \[ \begin{pmatrix}21\\1\\0\end{pmatrix} - \Big\lfloor\frac{21}{14}\Big\rfloor\cdot \begin{pmatrix}14\\0\\1\end{pmatrix} =\begin{pmatrix}21\\1\\0\end{pmatrix} - \begin{pmatrix}14\\0\\1\end{pmatrix} = \begin{pmatrix}7\\1\\-1\end{pmatrix} \] Given that \(7|14\), \(\operatorname{gcdex}(21,14)=\begin{pmatrix}7\\1\\-1\end{pmatrix}\) and \[ 7=21\cdot 1 + 14\cdot (-1) \] Multiplying both sides of the equality by 10, we find a solution of the proposed equation: \begin{align*} 7\cdot 10 & =(21\cdot 1 + 14\cdot (-1)) 10\\ 70 & =21\cdot 10 + 14\cdot (-10) \end{align*} That is, \(x_0=10\), \(y_0=-10\) is a particular solution of the equation.

Let's suppose \((x,y)\) is another solution. \begin{align*} 21\cdot x &+14\cdot y =70 \\ 21\cdot 10 &+14\cdot (-10) =70 \\ 21(x-10)&+14(y+10) =0 \qquad\text{(We have subtracted the previous two)}\\ 3(x-10)&+2(y+10) =0 \qquad\text{(We have divided by the g.c.d.)}\\ 3(x-10)&=-2(y+10) \\ \frac{x-10}{-2}&=\frac{y+10}{3} = q\in\mathbb{Z} \end{align*} We clear \(x\) and \(y\) as a function of \(q\) to obtain the general solution. \[ x = 10-2\cdot q,\qquad y = -10+3\cdot q,\qquad q\in\mathbb{Z} \]

We can also write the solution using the corollary seen above: \[ \binom x y =\frac17\left[70\binom{1}{-1} +q\binom{-14}{21}\right] =\binom{10-2q}{-10+3q},\quad \text{for each } q\in\mathbb{Z},\tag*{ } \]

---

### Matrix Form

Equality \(r=n - m\cdot q\) obtained with Euclidean division justifies the following equality between matrices \[ \begin{pmatrix} m \\ r \end{pmatrix} = \begin{pmatrix} 0 & 1\\ 1 & -q \end{pmatrix} \begin{pmatrix} n \\ m \end{pmatrix} \] Therefore, if \(d=\operatorname{gcd}(n,m)\) and \(q_1,\dots,q_k\) is the sequence of the quotients obtained in Euclid's algorithm to calculate the greatest common divisor, as it appears in the theorem of Euclid's Algorithm, then \[ \begin{pmatrix} d \\ 0 \end{pmatrix} = \begin{pmatrix} 0 & 1\\ 1 & -q_{k} \end{pmatrix} \cdots \begin{pmatrix} 0 & 1\\ 1 & -q_2 \end{pmatrix} \begin{pmatrix} 0 & 1\\ 1 & -q_1 \end{pmatrix} \begin{pmatrix} n \\ m \end{pmatrix} =\begin{pmatrix} s & t \\ \pm m/d & \mp n/d \end{pmatrix} \begin{pmatrix} n \\ m \end{pmatrix} \] That is, the first row of the square matrix on the right gives us the coefficients whose existence is established by Bézout's identity theorem.

We are going to extend this equality to express the solutions of the Diophantine equation \(nx+my=c\), where \(d=\operatorname{gcd}(n,m)|c\). Simply multiply both sides of the equality by the matrix \((\frac{c}{d}\quad q)\) where \(q\in\mathbb Z\) is a parameter: \begin{align*} \Big(\frac{c}{d}\quad q\Big)\begin{pmatrix} d \\ 0 \end{pmatrix} &=\Big(\frac{c}{d}\quad q\Big)\begin{pmatrix} s & t \\ \pm m/d & \mp n/d \end{pmatrix} \begin{pmatrix} n \\ m \end{pmatrix} \\ c &=\Big(\frac{c}{d}s\pm \frac{m}{d}q\quad \frac{c}{d}t\mp \frac{n}{d}q\Big) \begin{pmatrix} n \\ m \end{pmatrix} \end{align*} That is, the product of matrices on the right side determines the general solution of the Diophantine equation. This development justifies the following result


---

Theorem

Let us consider the Diophantine equation \(nx+my=c\) tal que \(c\) is multiple of \(d=\operatorname{gcd}(n,m)\). Let \(q_1,\dots,q_k\) be the sequence of quotients obtained by applying Euclid's algorithm to numbers \(n\) and \(m\) until reaching the remainder 0. Then, the solutions of the equation are given by the following equality \[ (x\quad y) = \Big(\frac{c}{d}\quad q\Big)\begin{pmatrix} 0 & 1\\ 1 & -q_{k} \end{pmatrix} \cdots \begin{pmatrix} 0 & 1\\ 1 & -q_2 \end{pmatrix} \begin{pmatrix} 0 & 1\\ 1 & -q_1 \end{pmatrix},\quad q\in \mathbb{Z} \]

We must remember that the product of matrices is not commutative and, therefore, take special care when writing the product of matrices according to the sequence of divisions.