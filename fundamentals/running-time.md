# Running Time `T(n)`
- Used to measure the performance of an algorithm
- Expressed as a function of the number of inputs: `T(n)= ???` , where `n` is the number of inputs

## Orders of Magnitude
Used to express an algorithm's relative running time
    
Orders of Magnitude as a function of the number of inputs (`n`) in order from most efficient to least efficient:
1. `log(⁡n)`
2. `n`
3. `n*log⁡(n)`
4. `n^2`
5. `n^3`
6. `2^n`

## Big Ο, Ω, and ϴ Notation

### The Big-Oh (O)
`T(n) = O(f(n))` when `∃n_0`, `c > 0` s.t. if `n ≥ n_0`  then `T(n) ≤ c∗f(n)`
 
Note: Then `f(n)` is an **upper bound** of the growth rate for `T(n)`

`T(n) ≠ O(f(n))` when `∀n_0`, c s.t. `∃n`, `n ≥ n_0`  and `T(n) > c∗f(n)`

---
    
### The Big-Omega (Ω)
`T(n) = Ω(f(n))` when `∃n_0`, `c > 0` s.t. if `n ≥ n_0`  then `T(n) ≥ c∗f(n)`

Note: Then `f(n)` is a **lower bound** of the growth rate of `T(n)`

`T(n) ≠ Ω(f(n))` when `∀n_0`, `c` s.t. `∃n`, `n ≥ n_0`  and `T(n) < c∗f(n)`

---
    
### The Big-Theta (θ)
`T(n) = θ(f(n))` when `∃n_0`, `c`, `b > 0` s.t. if `n ≥ n_0`  then `c∗f(n) ≤ T(n) ≤ b∗f(n)`
- Equivalent to `T(n) = θ(f(n))` IFF `T(n) = O(f(n))` and `T(n) = Ω(f(n))`

Note: Then `f(n)` is both an upper bound and lower bound of the growth rate of `T(n)`, meaning `f(n)` is the **tight bound** of the growth rate of `T(n)`

## Derivation - To Calculate Running Time of Recursive Algorithm
- Determine `T(n)` as `T(n)=c+T(?)`
- Use derivation to find the pattern of `T(n)`
- Determine the base case / when recursion ends
- Plug in the base case into the pattern to get `T(n)` as a function of `n`

## Master Theorem
Applies to `T(n) = a*T(n/b) + f(n)` where `a ≥ 1` and `b > 1`

---

### Case 1

If: `f(n) = O(n^c)` and `log_b(a) > c`

Then: `T(n) = θ(n^(log_b(a)))`

---

### Case 2

If: `f(n) = Θ(n^c)` and `log_b(a) = c`

Then: `T(n) = Θ(n^(log_b(a))*log(n))`

OR

If: `f(n) = Θ((n^c)*log^k(n))` and `log_b(a) = c`

Then: `T(n) = Θ(n^(log_b(a))*log^(k+1)n)`

---

### Case 3

If: `f(n) = Ω(n^c)` and `log_b(a) < c`

Then: `T(n) = Θ(f(n))`