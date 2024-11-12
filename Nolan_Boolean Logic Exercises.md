# Activity: Boolean Logic Exercises

## Name: Nolan Trinh

See the PDF file for the reference material on Boolean operations,
constants, identities, and basic laws.

Reminder:  A' means NOT A;  A + B means A OR B;  AB and A * B both mean A AND B

#### Proving Identities


|  A  |  A'  |  A + A'  |
| --- | ---- | -------- |
|  F  |  T   |    T     |
|  T  |  F   |    T     |


|  A  |  A'  |  A * A'  |
| --- | ---- | -------- |
|  F  |  T   |    F     |
|  T  |  F   |    F     |


#### Proving One of the Associative Laws

|  A  |  B  |  C  |  BC  |  A(BC)  |  AB  |  (AB)C  |
| --- | --- | --- | ---- | ------- | ---- | ------- |
|  F  |  F  |  F  |  F   |    F    |  F   |    F    |
|  F  |  F  |  T  |  F   |    F    |  F   |    F    |
|  F  |  T  |  F  |  F   |    F    |  F   |    F    |
|  F  |  T  |  T  |  T   |    F    |  F   |    F    |
|  T  |  F  |  F  |  F   |    F    |  F   |    F    |
|  T  |  F  |  T  |  F   |    F    |  F   |    F    |
|  T  |  T  |  F  |  F   |    F    |  T   |    F    |
|  T  |  T  |  T  |  T   |    T    |  T   |    T    |

<em>Which two columns provide the proof?
In other words, what have you proven?</em>

The two columns to provide the truth are A(BC) and (AB)C. It proves that if we swap the statements A,B and C in and outside the parentheses, the end result will not change. [ A(BC) = (AB)C ] because they have values for every possible combination.

#### Proving One of the Distributive Laws


|  A  |  B  |  C  |  B+C  |  A(B+C)  |  AB  |  AC  |  (AB)+(AC)  |
| --- | --- | --- | ----- | -------- | ---- | ---- | ----------- |
|  F  |  F  |  F  |   F   |     F    |  F   |  F   |      F      |
|  F  |  F  |  T  |   T   |     F    |  F   |  F   |      F      |
|  F  |  T  |  F  |   T   |     F    |  F   |  F   |      F      |
|  F  |  T  |  T  |   T   |     F    |  F   |  F   |      F      |
|  T  |  F  |  F  |   F   |     F    |  F   |  F   |      F      |
|  T  |  F  |  T  |   T   |     T    |  F   |  T   |      T      |
|  T  |  T  |  F  |   T   |     T    |  T   |  F   |      T      |
|  T  |  T  |  T  |   T   |     T    |  T   |  T   |      T      |

<em>Which two columns provide the proof?
In other words, what have you proven?</em>

We can prove that through eevry possible combination of statements, there is proof for the Distributive Law that: A(B + C) = (AB) + (AC).

#### Proving DeMorgan's Laws (part A)

|  A  |  B  |  A+B  |  (A+B)'  |
| --- | --- | ----- | -------- |
|  F  |  F  |   F   |    T     |
|  F  |  T  |   T   |    F     |
|  T  |  F  |   T   |    F     |
|  T  |  T  |   T   |    F     |

|  A  |  B  |  A'  |  B'  |  A'B'  |
| --- | --- | ---- | ---- | ------ |
|  F  |  F  |  T   |  T   |   T    |
|  F  |  T  |  T   |  F   |   F    |
|  T  |  F  |  F   |  T   |   F    |
|  T  |  T  |  F   |  F   |   F    |

<em>Which two columns provide the proof?
In other words, what have you proven?</em>

We can prove that at every possible combination of statments, there is proof for Demorgan's Laws that: (A+B)' = A'B'.

#### Proving DeMorgan's Laws (part B)

|  A  |  B  |  AB  |  (AB)'  |
| --- | --- | ---- | ------- |
|  F  |  F  |   F  |    T    |
|  F  |  T  |   F  |    T    |
|  T  |  F  |   F  |    T    |
|  T  |  T  |   T  |    F    |

|  A  |  B  |  A'  |  B'  |  A'+ B' |
| --- | --- | ---- | ---- | ------- |
|  F  |  F  |  T   |  T   |    T    |
|  F  |  T  |  T   |  F   |    T    |
|  T  |  F  |  F   |  T   |    T    |
|  T  |  T  |  F   |  F   |    F    |

<em>Which two columns provide the proof?
In other words, what have you proven?</em>

We can prove that at every possible combination, there is proof for Demorgan's Laws that: (AB)' = A' + B'. In other words, the not of statements A and B is equal to not A and not B.

#### Another Proof Exercise:  A(A+B) = ???

|  A  |  B  |  A+B  |  A(A+B)  |
| --- | --- | ----- | -------- |
|  F  |  F  |   F   |    F     |
|  F  |  T  |   T   |    F     |
|  T  |  F  |   T   |    T     |
|  T  |  T  |   T   |    T     |

<em>Which two columns are the same?
In other words, what have you proven?</em>

The set of statement combinations above prove that if we take a identity OR of A and (A+B), we come to the result that A = A(A+B).

#### Proofs Using Boolean Algebra

Using Boolean Algebra rather than Truth Tables, and in particular using
the Distributive Property, Identities, and your result from the previous
exercise, prove:

    A + (AB)  =  A

Proof:

    A + (AB)  = (A + A)(A + B)    (using Distributive Laws)
              = A(A+B)            (using A OR A equals A)
              = A                 (using proof from above proof exercise)


#### Proofs Using Boolean Algebra

Using Boolean Algebra, including DeMorgan's Laws, prove:

    (A'B)' =  A + B'

Proof:

    (A'B)' =  ((A')B)'      (add parentheses, without changing meaning)
           =  (A')'+B'      (using Demorgan's Law)
           =  A + B'        (using identity)
        