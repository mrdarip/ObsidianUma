## Modular Congruence Relation
$a \equiv b \pmod m$ means that
$(a-b)$ is a multiple of $m$
$a$ and $b$ have the same remainder when divided by $m$.

## Arithmetic of Congruences
if $a \equiv b \pmod m$ and $c \equiv d \pmod m$
then $a+c \equiv b+d \pmod m$ and $a \cdot c \equiv b \cdot d \pmod m$.

## Linear Congruences and Diophantine Equations
$a \cdot x \equiv b \pmod m$ is equivalent to solving the linear Diophantine equation $a \cdot x + m \cdot y = b$ for integers $x$ and $y$.

## Brahmagupta's Theorem (Solvability)
$a \cdot x \equiv b \pmod m$ has solutions only if $d=\operatorname{gcd}(a, m)$ divides $b$.

## Euclidean Algorithm and Bézout's Identity
Needed to calculate $\operatorname{gcd}(a, m)$ and find the integer coefficients $s$ and $t$ such that $\operatorname{gcd}(a, m) = a \cdot s + m \cdot t$. This is critical for finding particular solutions.

## Modular Inverse
Understanding that the modular inverse of $[a]_m^{-1}$ exists if and only if $\operatorname{gcd}(a, m)=1$.
Its often solved using the Vector Form of the Euclidean Algorithm.

## Euler-Fermat Theorem
Used to simplify large powers modulo $m$. If $\operatorname{gcd}(a, m) = 1$, then $a^{\Phi(m)} \equiv 1 \pmod m$. This requires calculating the Euler function $\Phi(m)$.

## Systems of Congruences
Knowing the condition for solvability of a pair of congruences: $x \equiv b_\alpha \pmod{m_\alpha}$ and $x \equiv b_\beta \pmod{m_\beta}$ has a solution if and only if $b_\alpha- b_\beta$ is a multiple of $d=\operatorname{gcd}(m_\alpha,m_\beta)$. The solution is unique modulo $M=\operatorname{lcm}(m_\alpha,m_\beta)$. If all moduli are coprime (Chinese Remainder Theorem), a solution always exists.
