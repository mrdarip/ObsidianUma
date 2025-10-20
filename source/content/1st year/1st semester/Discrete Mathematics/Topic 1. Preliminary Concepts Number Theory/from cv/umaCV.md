## 1.1 Preliminary concepts. The integer numbers

### Numerical sets and their properties

Let's remember the basic properties that verify the operations addition and product between numbers.

- _Associativity:_ If \(a\), \(b\) and \(c\) are numbers, then \[ (a+b)+c=a+(b+c),\qquad (a\cdot b)\cdot c=a\cdot (b\cdot c). \]
    
- _Existence of the identity element:_ the number \(0\) is the identity element for the addition, that is, for all number \(a\) \[ a+0=0+a=a \]
    
- _Existence of the unit element:_ the number \(1\) is the unit for the product, that is, for all number \(a\) \[ a\cdot 1=1\cdot a=a \]
    
- _Existence of the inverse element:_ the number \(-a\) is the inverse of \(a\) respect to the sum, that is, \(a+(-a)=(-a)+a=0\) for every number \(a\).
    
- __Existence of the inverse element_:_ the number \(a^{-1}=\frac1a\) is the inverse of \(a\) respect to the product, that is, \(a\cdot\frac1a=\frac1a\cdot a=1\), for all number \(a\ne 0\).
    
- _Commutative Law:_ all numbers \(a\) and \(b\) verify \[ a+b=b+a,\qquad a\cdot b=b\cdot a. \]
    
- _Distributive Law:_ if \(a\), \(b\) and \(c\) are numbers, then \[ a\cdot(b+c)= a\cdot b+a\cdot c,\quad (b+c)\cdot a= b\cdot a+c\cdot a. \] If we apply these equalities from right to left, we say that we get a common factor.
    
- _Trichotomy law_: Each pair of numbers \(a\) and \(b\) verify one and only one of the following relations: \[ a=b\qquad a< b\qquad b< a \] This property is also stated by saying that the order is total.
    
- _The sum is closed for the order:_ if \(a> b\), then \(a+c>b+c\).
    
- _The product is closed for the order:_ If \(a> b\), \(c>0\), then \(a\cdot c>b\cdot c\).
    

These properties should be known and will have been used to solve equations and inequalities and to simplify algebraic expressions in solving multiple exercises. It is convenient to get used to their names and to understand their meaning. The real numbers verify all properties, but if we restrict ourselves to numerical subsets such as integers or naturals, some properties are not verified in general.

Theorem

Addition in the set of natural numbers \(\mathbb{N}\), verifies the properties: associativity, existence of an identity element and commutativity. The product in the set of natural numbers verifies the properties: associativity, commutativity and distributivity with respect to the sum. In addition, the sum and the product are closed for the order in \(\mathbb{N}\).

Theorem

The sum in the set of integer numbers \(\mathbb{Z}\), verifies the properties: associativity, existence of identity element, existence of inverse element and commutativity. The product in the set of integers verifies the properties: associativity, commutativity and distributivity with respect to the sum. In addition, the sum and the product are closed for the order in \(\mathbb{Z}\).

Theorem

Addition in the set of rational numbers \(\mathbb{Q}\), verifies the properties: associativity, existence of identity element, existence of inverse element and commutativity. The product in the set of rational numbers verifies the properties: associativity, existence of inverse element, commutativity and distributivity with respect to the sum. In addition, the sum and the product are closed for the order in \(\mathbb{Q}\).

Although neither in \(\mathbb{N}\) nor in \(\mathbb{Z}\) the inverse element existence property is verified, the cancellation property is verified.

Theorem (Cancellation)

If \(n\ne 0\) and \(n \cdot m = n \cdot k\), then \(m = k\).

It is also useful to remember the properties of the order relation between numbers and of absolute value.

1. _Reflexive:_ \(n \leq n\)
    
2. _Antisymmetric:_ If \(n \leq m\), and \(m \leq n\), then \(n = m\)
    
3. _Transitive:_ If \(n \leq m\), and \(m \leq k\), then \(n \leq k\)
    
4. \(|n|\geq 0\)
    
5. \(|n|= 0\), if and only if \(n = 0\)
    
6. \(|n\cdot m| = |n|\cdot |m|\)
    
7. \(|n + m| \leq |n| + |m|\)
## 1.2 Integer Arithmetic

### Euclidean Division

Theorem (Euclidean Division)

For \(n, m\in \mathbb{N}\), where \(m > 0\) there exist then \(q, r \in \mathbb{N}\), unique, such that \[ n = m\cdot q + r \qquad \text{and} \qquad 0\leq r < m \]

Number \(q\) is called _quotient_ of the division of \(n\) by \(m\). Number \(r\) is call _remainder_ of the division of \(n\) by \(m\). The proof of this theorem is based on the usual division algorithm: we look for the greatest natural \(q\) such that \(n-m\cdot q\) is positive; necessarily, this number is less than \(m\). Basically, this is the process we follow when calculating division by hand with the algorithm we have known since elementary school.

Maxima Code

To determine quotient and remainder with Maxima, we use the operators quotient and remainder respectively.

(%i1) quotient(231,17);

\[ 13 \]

(%i2) remainder(231,17);

\[ 10\tag*{ } \]



### Divisibility and prime numbers

Definition

For \(n, m \in \mathbb{Z}\) where \(m \neq 0\). It is said that \(m\) _divides_  \(n\) if there exists \(q \in \mathbb{Z}\) such that \(n = m \cdot q\). In such case, we write either \(m\mid n\), or \(n = \dot{m}\). We also say that \(m\) is _divisor_ of \(n\) or that \(n\) is a _multiple_ of \(m\).

Example

- \(6\mid 192\), since \(192 = 6\cdot 32\)
- \(11\mid 2310\), since \(2310 = 11\cdot 210\)
- \(8\mid (-24)\), since \(24 = 8\cdot (-3)\)

Theorem

The divisibility relation verifies the following properties. If \(n, m, k\in \mathbb{Z}\):

1. _Reflexive:_ \(n \mid n\)
2. _Transitive:_ If \(n \mid m\), and \(m \mid k\), then \(n \mid k\)
3. _Antisymmetric (only for_ \(\mathbb{N}\)_):_ If \(0\le n\), \(0\le m\), \(n\mid m\) and \(m\mid n\), then \(n = m\)

The divisibility relation is not antisymmetric over \(\mathbb{Z}\), since \(n\mid (-n)\), and \((-n)\mid n\). In general, for arbitrary integer number it is verifies that,  if \(n\mid m\) and \(m\mid n\), then either \(n = m\), or \(n=-m\).

The following theorem collects the algebraic properties of divisibility, that is, its behaviour with respect to the operations of addition, subtraction and product.

Theorem

Let \(n, m, k\in \mathbb{Z}\). Then:

1. \(1\mid n\) and \((-1)\mid n\)
2. \(n\mid n\) and \(n\mid (-n)\)
3. If \(k\mid n\) and \(k\mid m\), then \(k\mid (n + m)\), and \(k \mid (n - m)\)
4. If \(n\mid m\), then \(n\mid (k\cdot m)\) for all \(k \in \mathbb{Z}\)
5. If \(k\mid n\) and \(k\mid m\), then \(k\mid (s\cdot n + t\cdot m)\), for all \(s, t \in \mathbb{Z}\)

Example

Given that 27 and 39 are multiple of 3, we could ensure that \[ 3\mid (27\cdot 13721+39\cdot7451) \] without having to perform the operations on the right.

It is important to keep in mind that we cannot apply that property in the opposite direction. In the example above, none of the numbers 27, 13721, 39, 7451 is even, however the following one it is \[ 27\cdot 13721+39\cdot7451=661056\tag*{ } \]

Definition

A positive integer \(p\ne 1\) is said to be a _prime number_, if their only positive divisors are 1 and \(p\). Numbers that are not prime are called _composite_.

Naturally, if a number \(n\) is composite, It is always possible to find a prime number that divides it.

For a long time the doubt remained as to whether the set of prime numbers was finite or not, until Euclid gave a simple proof that there are infinitely many prime numbers.

Theorem (Euclid)

The set of the prime numbers is infinite.

Euclid's proof of this result only makes use of algebraic properties. If \(p_1,\dots,p_n\) are all prime numbers less than \(p_n\), then either \(q=1+p_1\cdot p_2\cdot\dots\cdot p_n\) is another prime number strictly greater than \(p_n\), or is divisible by a prime number greater than \(p_n\). This is true because the number \(q=1+p_1\cdot p_2\cdot\dots\cdot p_n\) is not divisible by any of the numbers \(p_1,\dots,p_n\). Therefore, we can always construct a prime number that is greater than any other, and consequently the set of all of them has to be infinite. 

Determining whether a given number is prime or not is a complex problem from a computational point of view. Currently, some solutions of Computer Science are based on this complexity. Specifically, methods and results for computing sufficiently large prime numbers are important.

_The sieve of Eratosthenes_ is a simple algorithm in order to determine the prime numbers below a given natural number, although it is efficient only for non large numbers.  

The following animation is taken from [Wikipedia](http://es.wikipedia.org/wiki/Criba_de_Erat%C3%B3stenes "Criba de Eratóstenes - Wikipedia"). 

![Sieve_of_Eratosthenes_animation.gif](https://informatica.cv.uma.es/pluginfile.php/690630/mod_lesson/page_contents/5523/Sieve_of_Eratosthenes_animation.gif)

Families or sequences of prime numbers are also important, such as Fermat primes or Mersenne primes.  

Example

A prime number of the form \(a^n-1\) is a _Mersenne prime_. Naturally, not all numbers in this form are prime numbers: \[ 3^2-1=8\quad \text{is not prime.} \] In fact, it is verified that, if \(n>1\) and \(a^n-1\) is a prime number, then \(a=2\) and \(n\) is prime, as we demonstrate below.

Specifically, we are going to use polynomial divisibility to prove this, which is a fairly common technique.

- Necessarily, \(a\ge 2\) and to prove that \(a=2\), we consider the polynomial \(Q(x)=x^n-1\). This polynomial is divisible by \(x-1\), since \(x_0=1\) is a root of \(Q\); moreover, it is not difficult to infer that \[ x^n-1 = (x-1)\sum_{i=0}^{n-1}x^i \] For \(x=a\), then \[ a^n-1 = (a-1)\sum_{i=0}^{n-1}a^i \] Given that \(\displaystyle\sum_{i=0}^{n-1}a^i=1+a+\dots+a^{n-1}\ge 2\), if \(a^n-1\) is prime, necessarily \(a-1=1\) and \(a=2\).
    
- To prove that if \(2^n-1\) is a prime number then \(n\) is also prime, We are going to demonstrate the counterreciprocal of this implication, that is: we are going to demonstrate that if \(n=m\cdot k\), where \(m\ge2\), \(k\ge2\), then \(2^n-1\) is a composite number.
    
    We use again the following equality of polynomials \[ x^k-1 = (x-1)\sum_{i=0}^{k-1}x^i \] For \(x=2^m\), then \[ 2^n-1=(2^{m})^k-1 = (2^m-1)\sum_{i=0}^{k-1}2^{mi}, \] what will provide a factorization of \(2^n-1\); we have to bear in mind that, given that \(m\ge 2\), it is verified that \(2^m-1\ge 3\) and given that \(k\ge 2\) it is verified that \(\displaystyle\sum_{i=0}^{k-1}2^{mi}\ge 2\).
    

That is, the Mersenne primes are of the form \(2^p-1\), where \(p\) is prime. However, it is not true that \(p\) is prime, then \(2^p-1\) is necessarily prime. For example: \[ 2^{11}-1=2047 = 23\cdot 89\tag*{ } \]

The study of primality of a number, or its divisibility properties, involves analyzing whether or not its factorization is possible. In the following video the relationship between the factorization of numbers and polynomials is analyzed and used, as we have used in the previous example.

### Fundamental Theorem of Arithmetic

Fundamental Theorem of arithmetic

For \(n \in \mathbb{N}, \ n>1\). Then, \(n\) can be expressed uniquely as a product of powers of primes. That is, \[ n = p_1^{e_1}\cdot p_2^{e_2} \cdots p_k^{e_k}, \] where \(p_1 < p_2 < \dots < p_k\) are primes and \(e_j\in \mathbb{N}\) for each \(j\).

To obtain the decomposition, we start by dividing \(n\) by successive and increasing prime numbers ​​starting with \(2\). Naturally, it is not necessary to try all the primes smaller than \(n\) and we have several results that determine the largest prime number that should be considered. The simplest criterion is the following: we will try with the primes smaller than the square root of the number.

Example

- To deduce that 101 is prime, just check that it is not divisible by \(2, 3, 5\text{ and }7\).
- Number 90 is composite and \(90=2\cdot 3^2\cdot 5\).

The operator of Maxima that determines the factorization of natural numbers is factor:

(%i1) factor(11016);

\[ 2^3\,3^4\,17 \]

We could also inquire whether a number is prime or not:

(%i2) primep(17);

\[ \text{true} \]

(%i3) primep(22);

\[ \text{false} \]

Definition

For \(n,m\in\mathbb{Z}^\ast\), the _greatest_ _common divisor of_ \(n\) and \(m\) is the largest integer that is divisor of \(n\) and \(m\) and we denote by \(\operatorname{gcd}(n,m)\). That is, \(d=\operatorname{gcd}(n,m)\) is the only positive integer such that

- \(d|n\), \(d|m\) and
- if \(c|n\), \(c|m\), then \(c|d\)

The operator divisors of Maxima determines the set of divisors of a number. We are going to use it in the following example.

  

Maxima Code

Let's calculate the greatest common factor of 30 and 12 using the definition

(%i1) D1: divisors(30);

\[ \{1,2,3,5,6,10,15,30\} \]

(%i2) D2: divisors(12);

\[ \{1,2,3,4,6,12\} \]

The operator intersect determines the intersection of the two sets, that is, the common divisors.

(%i3) intersect(D1,D2);

\[ \{1,2,3,6\} \]

Therefore, the maximum of all divisors is 6: \(\operatorname{gcd}(30,12) = 6\).

We also have an operator that returns the greatest common divisor of two numbers.

(%i4) gcd(30,12);

\[ 6\tag*{ } \]

Definition

Integer numbers \(n\), and \(m\) are said to be _relatively prime or_ _coprime numbers_ if they do not have common divisors, that is, if \(\operatorname{gcd}(n, m) = 1\).

Example

- Integer numbers 9 and 22 are coprime, since \(\operatorname{gcd}(9,22)=1\).
- Integers 9, 22 and 35 are coprime “two by two” since \[ \operatorname{gcd}(9,22) = \operatorname{gcd}(9,35) = \operatorname{gcd}(22, 35) = 1\tag*{ } \]

From the Fundamental Theorem of Arithmetic we obtain the method of calculating the greatest common divisor of two numbers based on the factorial decomposition of natural numbers.

Corollary

If \(n = p_1^{a_1} p_2^{a_2}\cdots p_n^{a_n}\), and \(m = p_1^{b_1} p_2^{b_2}\cdots p_n^{b_n}\) are natural numbers, where \(p_i\) are different prime numbers, then \[ \operatorname{gcd}(n,m) = p_1^{\min(a_1, b_1)}p_2^{\min(a_2, b_2)} \cdots p_n^{\min(a_n, b_n)} \]

Note that, for simplicity, we have written the same sequence of primes in the two numbers, which does not detract from the generality, since the exponents can be null.

Example

\[ \left.\begin{array}{rcl} 2750 & = & 2 \cdot 5^3 \cdot 11\\ 1992 & = & 2^3 \cdot 3 \cdot 83 \end{array}\right\} \ \Longrightarrow \ \left\{\begin{array}{rcl} 2750 & = & 2^1\cdot 3^0 \cdot 5^3 \cdot 11^1\cdot 83^0\\ 1992 & = & 2^3 \cdot 3^1 \cdot 5^0 \cdot 11^0 \cdot 83^1 \end{array}\right. \] Therefore, \[ \operatorname{gcd}(2750,1992) = 2^1 \cdot 3^0 \cdot 5^0 \cdot 11^0 \cdot 83^0 = 2 \tag*{ } \]

Definition

We consider \(n,m\in\mathbb{Z}^+\). The least common multiple of \(n\) and \(m\) is the  minor natural number that is a multiple of \(n\) and \(m\). We denote it by \(\operatorname{lcm}(n,m)\).

The operator lcm of Maxima returns the least common multiple of two numbers.

(%i1) lcm(60,46);

\[ 1380 \]

Corollary

If \(n = p_1^{a_1} p_2^{a_2}\cdots p_n^{a_n}\), and \(m = p_1^{b_1} p_2^{b_2}\cdots p_n^{b_n}\) are natural numbers, then \[ \operatorname{lcm}(n,m) = p_1^{\max(a_1, b_1)}p_2^{\max(a_2, b_2)} \cdots p_n^{\max(a_n, b_n)} \]

Corollary

If \(n,m\in\mathbb{Z}^+\), then, \(\operatorname{lcm}(n, m)\cdot \operatorname{gcd}(n, m) = n\cdot m\).

Corollary

If \(n,m\in\mathbb{Z}^+\) are coprime numbers, then \(\operatorname{lcm} (n, m) = n\cdot m\).