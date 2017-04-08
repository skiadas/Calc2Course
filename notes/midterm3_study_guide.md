# Midterm 3 Study Guide

This is meant to be a representative sampling of the key concepts you will need to know, and it is not meant to be exhaustive. You should make sure that you are comfortable with all practice problems and homework assignments.

1. Trigonometric substitutions, know when to use which (e.g. $x = 3\tan\theta$ if $x^2+9$).
2. Completing the square as a preparation for a trigonometric substitution.
3. All the things related to computations of integrals of partial fractions:
    - long division,
    - partial fraction decomposition (choosing which terms to include, and how to determine the A, B, C),
    - computing the resulting integrals:
        - linears become $\ln$s,
        - quadratics: absorb the numerator's linear term in the derivative of denominator, for handling part of the integral as $\int\frac{f'}{f} = ln(f)$. Do tangent sub for the rest.
4. Improper integrals at infinity
5. Improper integrals at finite points
    - Cases with both endpoints misbehaving
6. p-power functions and their improper integrals near 0 and near infinity
7. Comparison test for improper integrals
    - Use it to prove certain integrals must converge even though we cannot find their answers (e.g. $\int_0^\infty e^{-x^2}dx$)
8. Numerical Integration via trapezoid rule, midpoint rule, Simpson's rule
9. Taylor polynomials and Maclaurin polynomials
10. Taylor's theorem about the Taylor remainder
11. Error bounds for Taylor polynomials
12. Arc length and Surface area computations (9.1)


More theoretical questions (I will ask you at least one of these):

1. Prove the p-power tests (i.e. when $\int_1^\infty\frac{1}{x^p}dx$ and $\int_0^1\frac{1}{x^p}dx$ converge)
2. Proof of Taylor's theorem for the Taylor remainder
3. Prove the formula for the integral $\int\frac{1}{(x-b)^2 + a^2}dx$
4. Define the gamma function $\Gamma(a)$, prove the integral converges, and show the formula $\Gamma(a+1) = a\Gamma(a)$
