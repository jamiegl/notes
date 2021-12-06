# Definitions

## Algebraic object

Typically referring to an algebraic structure consisting of some nonempty set of elements, some non-empty set of operations (i.e. addition, multiplication) and a set of axioms which the elements must satisfy. For example, a vector space is a set of objects called *vectors* equipped with the ability to be added together and multiplied by scalars. The axioms of this space can be seen here [Vector space - Wikipedia](https://en.wikipedia.org/wiki/Vector_space#Notation_and_definition) and are concerned with notions such as commutativity and associativity. 

## Homomorphism

A Homomorphism is a mapping between two algebraic objects of the same type that preserves all operations the object is equipped with. For instance, consider two sets $A$ and $B$ each equipped with an binary operation $*$. Then if

$$
f(x*y) = f(x)*f(y)
$$

for $\forall{x},y \in{A}$, the map $f$ is considered a homomorphism. 

Consider the function $f(x) = 2x$. Our object of interest will be a vector space with elements $\{4, 5, 3\}$ and thus our operations are addition and multiplication by scalar. Then, for multiplication by $2$:

$$
f(3+5) = f(3) + f(5) = 16 \\
f(3\times2) = 3f(2)  = 2f(3) = 12 \\
f(4+5) = f(4) + f(5) = 18 \\
f(4\times{2}) = 4f(2) = 2f(4) = 16 \\
f(4+3) = f(4) + f(3) = 8 + 4 = 14 \\
f(5\times2) = 5f(2) = 2f(5) = 20
$$

and as such $f$ is a homeomorphism on vector spaces. Indeed, all linear maps are homomorphisms on vector spaces.
