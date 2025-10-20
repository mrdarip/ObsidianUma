
- $x\in A$, reads “$x$ _belongs to_ $A$”
- $x\in A$, indicates that $A$ is a _set_
- $x\not\in A$ indicates that $x$ is not an element of $A$
- the order in which the elements are written or the possible repetitions do not matter
-  $A \subseteq B$, reads "$A$ is a _subset_ of $B$"
- $A = B$ if and only if $A\subseteq B$ and $B\subseteq A$
- $a\in\{a,b,c\}$
- $a\not\subset\{a,b,c\}$
- $\{a\}\subset\{a,b,c\}$
- $\{a\}\not\in \{a,b,c\}$
- a set with no element is called _empty set_ and is denoted by $\varnothing$
- For all set $A$, it is verified that $\varnothing\subseteq A$
- $A\cup B \subseteq C$ if, and only if, $A\subseteq C$ and $B\subseteq C$
- $A\cap B$ reads "the intersection of $A$ and $B$"
- $A\cap B =\{x\in A\mid x\in B\}$
- $C\subseteq A\cap B$ if, and only if, $C\subseteq A$ and $C\subseteq B$
- $A \smallsetminus B$ or $A-B$ reads "$A$ minus B" or "the complement of $B$ in $A$"
- $\mathcal{U}$ is the symbol for Universe
- Universe ($\mathcal{U}$) contains all the sets we work with in that application
## Venn diagrams
- Venn diagrams are not allowed as proof
- add the images to anki lol
## IDKTITLE
### Properties
- Commutative: $A \cup B = B\cup A;\quad A \cap B = B\cap A$
- Associative: $A \cup (B \cup C) = (A \cup B)\cup C;\quad A \cap (B \cap C) = (A \cap B)\cap C$
- Absorption: $A \cup (A \cap B) = A;\quad A \cap (A \cup B) = A$
- Idempotency: $A \cup A = A; A \cap A = A$
- Identity: $\varnothing \cup A = A$
- Dominance: $\varnothing \cap A = \varnothing$
- Distributive: $A \cup (B\cap C) = (A \cup B)\cap (A \cup C); A \cap (B\cup C) = (A \cap B)\cup (A \cap C)$
- Bounding ($\cup$): $A \subseteq B$ if, and only if, $A \cup B = B$
- Bounding ($\cap$): $A \subseteq B$ if, and only if, $A \cap B = A$
- If A and B are sets within the universe $\mathcal{U}$, then:
	- Complement: $A \cup \overline{A} = \mathcal U;\quad A \cap \overline{A} = \varnothing$
	- De Morgan: $\overline{A \cup B} = \overline{A} \cap \overline{B};\quad \overline{A \cap B} = \overline{A} \cup \overline{B}$
	- Involution: $\overline{\overline{A}} = A$
## more
- $\wp(A)$ reads "the power set of A"
- $\wp(A)$ is a set that contains all subsets of A
- $\wp(\{1,2\}) = \{\emptyset, \{1\}, \{2\}, \{1,2\}\}$
## Cartesian product, relations, functions
- $A\times B$ reads "the Cartesian product of A and B"
- 

---
# improve
## Definición (Comprehension Axiom)

If A is a set and P is a property applicable to the elements of A, there exists a subset of A formed by the elements of A that verify the property P. This set is written as
$$\{x\in A \mid P(x)\}$$