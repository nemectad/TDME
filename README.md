# TDME
Maple script for computation of transition dipole matrix elements (and more).
Author: Tadeáš Němec, 2021

# About
This Maple worksheet enables to compute cartesian p-representation of hydrogen atom ground state wavefunction. Further, it can compute transition dipole matrix elements (TDME) as well as Hess matrix of an arbitrary wavefunction. Finally, it enables to generate fortran code for straightforward implementation.

# How to use

The code *must* be used after the comment ```# USE FROM HERE``` otherwise you risk improper functioning of the code. 

Methods for use are the following:
* ```p_nlm(n,l,m)```: computes the corresponding wavefunction of hydrogen atom eigenstate denoted by quantum numbers $n, l, m$ in the cartesian p-representation.
* ```dipoleElement(p_nlm(n,l,m))```: computes TDME of ```p_nlm(n, l, m)```.
* ```hessMtrx(p_nlm(n,l,m)```: computes Hess matrix of ```p_nlm(n, l, m```.
* ```code(expr)```: generates Fortran code of arbitrary expression computed via the functions above.

*Example:*

Let's say we would like to find p-representation of eigen state n = 2, l = 1, m = 0. Next find the TDNE, compute Hess matrix and finally generate code for TDME. We do the following:
``` Maple
# Wavefunction
expression := p_nlm(2, 1, 0)
# TDME
TDME := dipoleElement(expression)
# Hess Matrix
Hess := hessMtrx(expression)
# Code generation
code(TDME)
```
