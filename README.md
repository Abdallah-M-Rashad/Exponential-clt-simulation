# Investigating the Exponential Distribution and the Central Limit Theorem


## Project Overview

This project explores the **Exponential Distribution** and the **Central Limit Theorem (CLT)** through simulations using R. The project involves generating random samples from the exponential distribution, calculating sample means, and comparing them with theoretical values to analyze how they approximate a normal distribution as the sample size increases.

## Simulations

The main steps in the project include:

1. **Generating Samples:** Using the exponential distribution with a rate parameter (`lambda = 0.2`), 40 random exponentials were generated and repeated 1000 times to study the sample means.
2. **Comparing Means:** The sample mean was compared with the theoretical mean, which is `1/lambda`.
3. **Variance Analysis:** The variance of the sample means was compared to the theoretical variance using `(1/lambda)^2 / n`.
4. **Distribution Visualization:** A histogram was plotted to visualize the distribution of the sample means, overlayed with a normal curve to check the approximation to the normal distribution.

## Code Example

```r
# Set parameters
set.seed(123)
lambda <- 0.2
n <- 40
simulations <- 1000

# Simulate means
means <- replicate(simulations, mean(rexp(n, lambda)))

# Theoretical mean and sample mean
theoretical_mean <- 1 / lambda
sample_mean <- mean(means)

# Theoretical variance and sample variance
theoretical_variance <- (1 / lambda)^2 / n
sample_variance <- var(means)

# Plotting the distribution
hist(means, probability = TRUE)
curve(dnorm(x, mean = theoretical_mean, sd = sqrt(theoretical_variance)), add = TRUE)
```

## Results

- **Theoretical Mean:** 5
- **Sample Mean:** ~5.01
- **Theoretical Variance:** 0.625
- **Sample Variance:** ~0.60

The sample statistics closely match the theoretical values, confirming the validity of the Central Limit Theorem as the distribution of sample means approximates a normal distribution.

## Conclusion

The project demonstrates that the sample mean and variance align with theoretical values, and the distribution of sample means approaches normality with increasing sample size, illustrating the Central Limit Theorem.

## Requirements

- **R** programming language

## Usage

To run the simulations, simply execute the provided R script. The required R packages are built-in and no additional libraries are necessary.
