# Sampling Theory Foundations

## 1. Sample Spaces & Events
**Sample Space (`S`)**
: the set of all possible outcomes of the experiment

**Event**
: a subset of `S`
- A **simple event** contains exactly one outcome
- A **compound event** contains more than one outcome

## 2. Set Theory Operations
### Complement
`A′` = all outcomes not in `A`
### Union
`A ∪ B` = all outcomes in at least one of `A` and `B`
### Intersection
`A ∩ B` = outcomes in both `A` and `B`     
### Mutually Exclusive / Disjoint Events:
IFF `A ∩ B = ∅`

## 3. Probability Rules

### Probability of an Event

For equally likely outcomes:

`P(A) = (number of outcomes in A) / (number of outcomes in S)`

### Complement Rule

`P(A′) = 1 − P(A)`

### Addition Rule

`P(A ∪ B) = P(A) + P(B) − P(A ∩ B)`

If `A` and `B` are mutually exclusive:

`P(A ∪ B) = P(A) + P(B)`

### Multiplication Rule

`P(A ∩ B) = P(A | B) * P(B)`

If independent:

`P(A ∩ B) = P(A) * P(B)`

## 4. Conditional Probability & Independence

### Conditional Probability

`P(A | B) = P(A ∩ B) / P(B)`  where `P(B) > 0`

### Independence

Events `A` and `B` are independent if:

`P(A | B) = P(A)`

Equivalently:

`P(A ∩ B) = P(A) * P(B)`

## 5. Random Variables

A **random variable** is a function that assigns a numerical value to each outcome in `S`.

Types:

- **Discrete Random Variable** → countable outcomes  
- **Continuous Random Variable** → uncountable outcomes  

### Expected Value (`E(x)`)

For discrete case:

$$
E(X) = \sum_{i} x_i \, P(X = x_i)
$$

### Variance (`Var(x)`)

$$
\mathrm{Var}(X) = E[(X - \mu)^2] = E(X^2) - \mu^2
$$

## 6. Population vs Sample

**Population**
: the entire group of interest

**Sample**
: a subset drawn from the population

**Parameter**
: numerical summary of a population (e.g., `μ`, `σ²`)

**Statistic**
: numerical summary of a sample (e.g., `x̄`, `s²`)

## 7. Sampling Errors
**Sampling error** is error due to a sample rather than the whole population is used.

**Nonsampling error** is error due to low response rate or errors in measuring or recording the variable of interest or detectability problems for sampling from elusive population.

## 8. Sampling Methods

### Simple Random Sampling (SRS)
Every subset of size `n` has equal probability of selection.

### Stratified Sampling
Population divided into strata; random samples taken from each stratum.

### Cluster Sampling
Population divided into clusters; randomly select clusters and sample all or some within them.

### Systematic Sampling
Select every `k`-th observation after a random starting point.

### Convenience Sampling
Selection based on ease of access (non-random).

### Voluntary Response Sampling
Participants self-select into the sample (often biased).