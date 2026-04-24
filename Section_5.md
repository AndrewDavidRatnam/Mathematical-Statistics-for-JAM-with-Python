 # Section 5
## 1. Definition of Random Variables (R.V.)

* Formula: $X: S \to \mathbb{R}$ (A mapping from Sample Space to Real Numbers).
* Critical Thinking / Exam Tips:
1. Measurability: In advanced theory, an R.V. is only valid if the set $\{\omega : X(\omega) \leq x\}$ is an event in your $\sigma$-field.
   2. Not "Random": Think of an R.V. as a deterministic function. The "randomness" comes from the underlying outcome of the experiment, not the function itself.
   3. Range vs. Codomain: Always identify the support (the set of values where $P(X=x) > 0$). This is the first step in solving any transformation problem.
   4. Inverse Image: Remember that $P(X \in B)$ is actually $P(\{\omega \in S : X(\omega) \in B\})$.
   5. Types: Recognize that an R.V. can be neither purely discrete nor purely continuous (Mixed R.V.s), though JAM focuses on the pure types.

## 2. Cumulative Distribution Function (c.d.f.)

* Formula: $F_X(x) = P(X \leq x)$ for $-\infty < x < \infty$.
* Critical Thinking / Exam Tips:
1. The "Jump" Logic: For discrete R.V.s, $P(X=x) = F(x) - F(x^-)$. The "jump" height at a point is its probability.
   2. Interval Probabilities: Always use $P(a < X \leq b) = F(b) - F(a)$. Pay close attention to the < vs. $\leq$ signs in discrete cases.
   3. Horizontal Asymptotes: If a function doesn't approach 0 at $-\infty$ and 1 at $+\infty$, it is not a valid c.d.f.
   4. Right-Continuity: In multiple-choice questions, verify $F(x) = \lim_{h \to 0^+} F(x+h)$. If it's left-continuous instead, it’s a trick question.
   5. Percentiles: The $p^{th}$ percentile is the value $\eta_p$ such that $F(\eta_p) \geq p$. Use the c.d.f. to find medians and quartiles.

## 3. Discrete & Continuous Random Variables

* Discrete: Support is countable. $\sum_{x \in S} P(X=x) = 1$.
* Continuous: Support is an interval. $P(X=x) = 0$ for any specific $x$.
* Critical Thinking / Exam Tips:
1. The "Zero Probability" Paradox: In continuous R.V.s, an event with $P(A)=0$ is not necessarily impossible (e.g., picking exactly $(1/\pi)$ from $[0, 1]$).
   2. Support Identification: Always check the limits of the variable. If $x \in \{0, 1, 2...\}$, use sums. If $x \in [0, \infty)$, use integrals.
   3. Mixed Distributions: If a c.d.f. has a "jump" but also a "slope," it's mixed. Total probability is the sum of the jump heights + the integral of the slope.
   4. Uniformity: If a continuous R.V. has a constant p.d.f. over an interval, it is a Uniform distribution—calculations usually simplify to basic geometry.
   5. Countability: Remember that "Countable" includes both finite sets $\{1, 2, 3\}$ and infinite sets like the integers $\mathbb{Z}$.

## 4. Probability Mass Function (p.m.f.) & Density Function (p.d.f.)

* p.m.f. (Discrete): $f(x) = P(X=x)$ where $f(x) \geq 0$ and $\sum f(x) = 1$.
* p.d.f. (Continuous): $f(x) = \frac{d}{dx}F(x)$ where $f(x) \geq 0$ and $\int_{-\infty}^{\infty} f(x)dx = 1$.
* Critical Thinking / Exam Tips:
1. The $f(x) > 1$ Trap: For a p.d.f., $f(x)$ can be greater than 1 (e.g., $f(x) = 2$ on $[0, 0.5]$). Only probabilities ($F(x)$ or p.m.f.) are capped at 1.
   2. Area Under Curve: For p.d.f., the probability is the area, not the height. For p.m.f., the probability is the height.
   3. Finding the Constant $k$: If given a p.d.f. like $k \cdot x^2$, the first step is always $\int f(x) = 1$ to solve for $k$.
   4. Change of Variables: If $Y = g(X)$, the new p.d.f. is $f_Y(y) = f_X(x) \left| \frac{dx}{dy} \right|$. Don't forget the Jacobian (absolute derivative).
   5. Symmetry: If a p.d.f. is symmetric about $a$ ($f(a-x) = f(a+x)$), then $E(X) = a$ (if the expectation exists).

### 5 more Critical Thinking "Checkpoints" for this Concept:

   1. The "Total Mass" Check: If the question gives you $F(x) = k \cdot \arctan(x)$, you don't integrate it. You set the limit as $x \to \infty$ to $1$ to find $k$.
   2. PDF $\to$ CDF: To get a CDF, you integrate the PDF: $F(x) = \int_{-\infty}^{x} f(t) dt$. This automatically ensures the horizontal asymptote is 1.
   3. Monotonicity is King: Even if a function goes from 0 to 1, if it dips down anywhere (negative derivative), it is not a CDF. Normalizing won't fix a lack of monotonicity.
   4. Area vs. Value: For a PDF, the area is the probability. For a CDF, the vertical height at $x$ is the probability $P(X \leq x)$.
   5. Differentiating the CDF: If you "normalize" a function to be a CDF, its derivative (the PDF) will also be scaled by that same factor.


Short version: You normalize PDFs using integrals; you solve for constants in CDFs using limits.

---

## 5. Distributions of a Function of a Random Variable (Transformation Method)

This subtopic involves finding the distribution of a new random variable $Y = g(X)$ when the distribution of $X$ is known.

#### **The Formula (Univariate Transformation)**
If $X$ is a continuous random variable with p.d.f. $f_X(x)$, and $Y = g(X)$ is a monotonic (strictly increasing or decreasing) differentiable function, the p.d.f. of $Y$ is:
$$f_Y(y) = f_X(x) \left| \frac{dx}{dy} \right| \quad \text{where } x = g^{-1}(y)$$

#### **5 Critical Points for JAM**
1.  **Monotonicity Check:** Always ensure $g(X)$ is monotonic over the support of $X$. If it is not (e.g., $Y = X^2$ where $X$ can be negative), you must split the domain into monotonic intervals and sum the resulting densities.
2.  **The Absolute Value:** Never forget the absolute value in the Jacobian term $\left| \frac{dx}{dy} \right|$. A common mistake is losing the negative sign when $g(X)$ is decreasing, leading to a "negative" probability density.
3.  **Change of Support (Crucial):** The most common error in JAM is forgetting to transform the limits. If $X \in [a, b]$, then the support of $Y$ is the range of $g(x)$ for $x \in [a, b]$. Always write down the new bounds for $Y$.
4.  **Inverse Function Mastery:** You must be able to solve for $x$ in terms of $y$ quickly. If $y = e^x$, then $x = \ln y$. If you cannot express $x$ as $g^{-1}(y)$, the transformation method fails.
5.  **CDF Method as an Alternative:** If the transformation is complex or non-monotonic, use the CDF method: Find $F_Y(y) = P(g(X) \le y)$, solve the inequality for $X$, and then differentiate $F_Y(y)$ to get $f_Y(y)$.

---

## 6. Multivariate Transformation (Jacobian Method)

This involves transforming a vector of random variables $(X_1, X_2, \dots, X_n)$ into $(Y_1, Y_2, \dots, Y_n)$.

#### **The Formula**
If $Y_1 = g_1(X_1, \dots, X_n), \dots, Y_n = g_n(X_1, \dots, X_n)$, then the joint p.d.f. of $Y$ is:
$$f_{Y_1, \dots, Y_n}(y_1, \dots, y_n) = f_{X_1, \dots, X_n}(x_1, \dots, x_n) \cdot |J|$$
Where $J$ is the **Jacobian determinant**:
$$J = \det \begin{pmatrix} \frac{\partial x_1}{\partial y_1} & \dots & \frac{\partial x_1}{\partial y_n} \\ \vdots & \ddots & \vdots \\ \frac{\partial x_n}{\partial y_1} & \dots & \frac{\partial x_n}{\partial y_n} \end{pmatrix}$$

#### **5 Critical Points for JAM**
1.  **Direction of Jacobian:** You can compute $J = \frac{\partial(x_1, \dots, x_n)}{\partial(y_1, \dots, y_n)}$ or $J = \frac{\partial(y_1, \dots, y_n)}{\partial(x_1, \dots, x_n)}$. If you use the latter, the formula is $f_Y = f_X \cdot |1/J|$. Usually, solving for $x$ in terms of $y$ and using $\frac{\partial x}{\partial y}$ is safer.
2.  **Support Transformation in 2D/3D:** In multivariate problems, the boundaries often change from rectangular (e.g., $0 < x < 1, 0 < y < 1$) to triangular or circular. Always sketch the new region in the $(y_1, y_2)$ plane.
3.  **Independence Check:** If the question asks if $Y_1$ and $Y_2$ are independent, find their joint p.d.f. and check if it can be factored into $h_1(y_1) \cdot h_2(y_2)$ **and** that the support is rectangular.
4.  **Common Transformations:** Memorize the Jacobian for Polar Coordinates $(x=r\cos\theta, y=r\sin\theta \implies |J| = r)$ and Exponential/Log transformations. JAM often uses these.
5.  **The "Zero" Jacobian:** If $|J| = 0$, the transformation is not one-to-one, and the method cannot be applied directly. This happens if one variable is a constant function of another.

---

## 7. Mathematical Expectation and Moments

Expectation is the "center of mass" of a distribution, and moments describe its shape.

#### **The Formulas**
*   **Expectation (Discrete):**  $E[X]=\sum_{x}x\cdot p(x)$

*   **Expectation (Continuous):** $E[X]=\int_{-\infty}^{\infty} x \cdot f(x) dx$
*   **$r^{th}$ Moment about Origin ($\mu'_r$):** $E[X^r] = \int x^r f(x) dx$
*   **$r^{th}$ Central Moment ($\mu_r$):** $E[(X - E[X])^r]$
*   **Variance:** $\text{Var}(X) = E[X^2] - (E[X])^2$

#### **5 Critical Points for JAM**
1.  **Linearity of Expectation:** $E[aX+bY+c]=aE[X]+bE[Y]+c$ .This is your most powerful tool. This holds **even if $X$ and $Y$ are dependent**. Do not waste time finding the joint distribution if you only need $E[X+Y]$. 
2.  **Expectation of a Function:** $E[g(X)] = \int g(x) f(x) dx$. This is the "Law of the Unconscious Statistician." You do not need to find the p.d.f. of $g(X)$ to find its expectation; just integrate $g(x)$ against the original $f(x)$.
3.  **Moment Generating Function (MGF) Shortcut:** If the MGF $M_X(t) = E[e^{tX}]$ is given, the $r^{th}$ moment is the $r^{th}$ derivative of $M_X(t)$ evaluated at $t=0$.
    $$E[X^r] = \left. \frac{d^r}{dt^r} M_X(t) \right|_{t=0}$$
4.  **Variance and Covariance Nuances:** While $E[X+Y] = E[X]+E[Y]$, the variance is $Var(X+Y) = Var(X) + Var(Y) + 2Cov(X,Y)$. If $X, Y$ are independent, $Cov(X,Y) = 0$.
5.  **Symmetry Trick:** If a p.d.f. is symmetric about a point $a$ (i.e., $f(a+x)=f(a-x)$), then $E[X]=a$. Also, all odd central moments ($\mu_1, \mu_3, \dots$) of a symmetric distribution are zero. This can save minutes of integration.
---


## 8. Measures of Central Tendency and Dispersion
These describe the "location" and "spread" of a distribution.

#### **The Formulas**
*   **Mean ($\mu$):** $E[X]=\int x f(x) dx$ (continuous) or $\sum x p(x)$ (discrete).
*   **Median ($m$):** The value such that $P(X \le m) \ge 0.5$ and $P(X \ge m) \ge 0.5$.
*   **Mode:** The value $x$ where $f(x)$ is maximum (for continuous) or $p(x)$ is maximum (for discrete).
*   **Variance ($\sigma^2$):** $E[(X - \mu)^2] = E[X^2] - (E[X])^2$.
*   **Standard Deviation ($\sigma$):** $\sqrt{\text{Var}(X)}$.
*   **Coefficient of Variation (CV):** $\frac{\sigma}{\mu} \times 100\%$.
*   **Quantiles ($q_p$):** The value such that $F(q_p) = p$ (e.g., Quartiles $Q_1, Q_2, Q_3$ are $p=0.25, 0.5, 0.75$).

#### **5 Critical Points for JAM**
1.  **The Empirical Relationship:** For moderately skewed distributions, remember the rule of thumb: $\text{Mean} - \text{Mode} \approx 3(\text{Mean} - \text{Median})$.
2.  **Robustness:** Understand that the **Median** is "robust" (not heavily affected by outliers), whereas the **Mean** and **Variance** are highly sensitive to extreme values.
3.  **Scaling and Shifting:** If $Y = aX + b$, then:
    *   $\text{Mean}(Y) = a\text{Mean}(X) + b$
    *   $\text{Var}(Y) = a^2\text{Var}(X)$ (Note: $b$ disappears)
    *   $\text{SD}(Y) = |a|\text{SD}(X)$
4.  **CV Application:** CV is a **dimensionless** measure. It is used to compare the variability of two datasets with different units (e.g., comparing the variation in weight in kg vs. height in cm).
5.  **Quantile Calculation:** For continuous variables, $Q_p$ is found by solving $F(x) = p$ for $x$. For discrete variables, it is the smallest $x$ such that $F(x) \ge p$.

---

## 9. Skewness and Kurtosis
These describe the "shape" of the distribution.

#### **The Formulas**
*   **Skewness ($\gamma_1$):** $\gamma_1 = \frac{\mu_3}{\sigma^3}$ (where $\mu_3$ is the 3rd central moment).
*   **Kurtosis ($\beta_2$):** $\beta_2 = \frac{\mu_4}{\sigma^4}$ (where $\mu_4$ is the 4th central moment).
*   **Excess Kurtosis:** $\gamma_2 = \beta_2 - 3$.

#### **5 Critical Points for JAM**
1.  **Skewness Direction:** $\gamma_1 > 0$ means Right-skewed (tail to the right); $\gamma_1 < 0$ means Left-skewed (tail to the left); $\gamma_1 = 0$ implies symmetry.
2.  **Kurtosis Classification:**
    *   $\beta_2 > 3$ (or $\gamma_2 > 0$): **Leptokurtic** (sharper peak, fatter tails).
    *   $\beta_2 < 3$ (or $\gamma_2 < 0$): **Platykurtic** (flatter peak, thinner tails).
    *   $\beta_2 = 3$ (or $\gamma_2 = 0$): **Mesokurtic** (Normal distribution).
3.  **Symmetry Implication:** If a distribution is symmetric about its mean, all odd central moments ($\mu_1, \mu_3, \mu_5 \dots$) are zero.
4.  **Moment Calculation:** In JAM, you often have to find $\mu_3$ or $\mu_4$ using the relation between central moments and raw moments ($E[X^r]$). Practice the expansion of $E[(X-\mu)^r]$.
5.  **Relationship to Mean/Median/Mode:** In a positively skewed distribution, typically $\text{Mode} < \text{Median} < \text{Mean}$.

---

## 10. Moment Generating Function (MGF)

#### **The Formula**
$$M_X(t) = E[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) dx$$

#### **5 Critical Points for JAM**
1.  **Uniqueness Theorem:** This is a frequent theoretical question. If two random variables have the same MGF in a neighborhood of $t=0$, they have the **same distribution**.
2.  **Finding Moments:** You don't need the distribution to find moments if you have the MGF. Use: $E[X^n] = \left. \frac{d^n}{dt^n} M_X(t) \right|_{t=0}$.
3.  **Linear Transformation Property:** $M_{aX+b}(t) = e^{bt} M_X(at)$. This is a very common shortcut for exam questions.
4.  **Sum of Independent Variables:** If $X$ and $Y$ are independent, then $M_{X+Y}(t) = M_X(t) \cdot M_Y(t)$. This is the fastest way to find the distribution of a sum.
5.  **Existence:** Not all distributions have an MGF (e.g., Cauchy distribution). An MGF exists only if the integral converges in an interval around $t=0$.

---

## 11. Markov and Chebyshev Inequalities

#### **The Formulas**
*   **Markov's Inequality:** For a non-negative random variable $X$ and $a > 0$:
    $$P(X \ge a) \le \frac{E[X]}{a}$$
*   **Chebyshev's Inequality:** For any random variable with mean $\mu$ and variance $\sigma^2$:
    $$P(|X - \mu| \ge k\sigma) \le \frac{1}{k^2} \quad \text{or} \quad P(|X - \mu| < k\sigma) \ge 1 - \frac{1}{k^2}$$

#### **5 Critical Points for JAM**
1.  **The "Non-Negative" Constraint:** **Markov's Inequality ONLY applies if $X \ge 0$.** If the question involves a variable that can be negative, you cannot use Markov directly on $X$ (you might use it on $|X|$).
2.  **Bounds vs. Exact Values:** These inequalities do **not** give you the exact probability; they give you an **upper bound** (for Markov/Chebyshev) or a **lower bound**. JAM often asks for "the maximum possible probability" or "the minimum possible probability."
3.  **Chebyshev's Strength:** Chebyshev's inequality is more powerful than Markov's because it uses the variance. It works for any distribution, regardless of shape.
4.  **Interpretation of $k$:** In Chebyshev, $k$ is the number of standard deviations away from the mean. If a question asks for $P(X \le \mu + 2\sigma)$, you are looking for the complement of the tail probability.
5.  **Application Strategy:** If a question provides only the Mean and Variance and asks for a probability range, **immediately** think of Chebyshev. If only the Mean is provided and $X \ge 0$, think of Markov.
---
This is a comprehensive guide tailored specifically for the **IIT JAM Mathematical Statistics** pattern. For this exam, you don't just need to memorize formulas; you need to understand **identifying properties, MGFs, and limiting behaviors.**

---

# I. Discrete Distributions

### 1. Degenerate Distribution
*   **PMF:** $P(X = c) = 1$ for some constant $c$.
*   **Properties:** $E[X]=c$, $Var(X)=0$, $MGF(t)=e^{ct}$.
*   **JAM Tips:**
    1. Often used as a "base case" in proofs.
    2. If $Var(X)=0$, the distribution is degenerate.
    3. Useful in delta-method problems.

### 2. Bernoulli Distribution
*   **PMF:** $P(X=1)=p$, $P(X=0)=q=(1-p)$.
*   **Properties:** $E[X]=p$, $Var(X)=pq$, $MGF(t)=q + pe^t$.
*   **JAM Tips:**
    1. It is the building block for Binomial.
    2. $X^n = X$ for any $n \geq 1$ (because $0^n=0$ and $1^n=1$). This simplifies $E[X^n]$ calculations.
    3. Use Indicator Variables (Bernoulli) to find the mean of complex sums.

### 3. Binomial Distribution
*   **PMF:** $P(X=k) = \binom{n}{k} p^k q^{n-k}, \quad k=0, 1, \dots, n$.
*   **Properties:** $E[X]=np$, $Var(X) = npq$, $MGF(t) = (q + pe^t)^n$.
*   **JAM Tips:**
    1. **Relationship:** Sum of $n$ independent Bernoulli($p$) trials.
    2. If $n$ is large and $p$ is small, it approximates Poisson.
    3. Look for "success/failure" language in word problems.
    4. $E[X(X-1)\dots(X-k+1)] = n(n-1)\dots(n-k+1)p^k$ (Factorial Moments).

### 4. Geometric Distribution
*   **PMF:** $P(X=k) = q^{k-1}p$ (for $k=1, 2, \dots$) OR $P(X=k) = q^k p$ (for $k=0, 1, \dots$). *Check the question's definition of $k$!*
*   **Properties:** $E[X]=1/p$ (for $k \in \{1,2..\}$), $Var(X) = q/p^2$.
*   **JAM Tips:**
    1. **Memoryless Property:** $P(X > s+t | X > s) = P(X > t)$. This is the *only* discrete memoryless distribution.
    2. It is a special case of Negative Binomial where $r=1$.
    3. If the question says "number of trials until first success," use $k=1,2..$. If "number of failures before success," use $k=0,1..$.

### 5. Negative Binomial Distribution
*   **PMF:** $P(X=k) = \binom{k-1}{r-1} p^r q^{k-r}$ (for $k = r, r+1, \dots$).
*   **Properties:** $E[X]=r/p$, $Var(X) = rq/p^2$.
*   **JAM Tips:**
    1. **Relationship:** Sum of $r$ independent Geometric($p$) variables.
    2. Often used in "waiting time" problems for the $r$-th success.
    3. Distinguish carefully between the "number of trials" and "number of failures" versions.

### 6. Poisson Distribution
*   **PMF:** $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}, \quad k=0, 1, 2, \dots$
*   **Properties:** $E[X]=\lambda$, $Var(X)=\lambda$, $MGF(t) = e^{\lambda(e^t-1)}$.
*   **JAM Tips:**
    1. **Limiting Case:** $Binomial(n, p) \to Poisson(\lambda)$ as $n \to \infty, p \to 0$ and $np = \lambda$.
    2. If $X, Y \sim Poisson(\lambda_1, \lambda_2)$ are independent, then $X+Y \sim Poisson(\lambda_1 + \lambda_2)$.
    3. It models "rare events" in a fixed interval of time/space.
    4. The mean equals the variance.

### 7. Hypergeometric Distribution
*   **PMF:** $P(X=k) = \frac{\binom{K}{k} \binom{N-K}{n-k}}{\binom{N}{n}}$.
*   **Properties:** $E[X]=n \frac{K}{N}$, $Var(X) = n \frac{K}{N} \frac{N-K}{N} \frac{N-n}{N-1}$.
*   **JAM Tips:**
    1. **Sampling WITHOUT replacement** (Binomial is sampling WITH replacement).
    2. **Limiting Case:** As $N \to \infty$, Hypergeometric $\to$ Binomial.
    3. Look for terms like "urns," "balls," or "population" where items aren't returned.

---

# II. Continuous Distributions

### 1. Uniform Distribution $U(a, b)$
*   **PDF:** $f(x) = \frac{1}{b-a}, \quad a \le x \le b$.
*   **Properties:** $E[X]=\frac{a+b}{2}$, $Var(X) = \frac{(b-a)^2}{12}$.
*   **JAM Tips:**
    1. The PDF is constant; the CDF is linear.
    2. Very common in "random number generator" problems.
    3. Frequently used in transformations (e.g., $X \sim U(0,1) \implies -\ln(X) \sim Exp(1)$).

### 2. Exponential Distribution
*   **PDF:** $f(x) = \lambda e^{-\lambda x}, \quad x \ge 0$.
*   **Properties:** $E[X]=1/\lambda$, $Var(X)=1/\lambda^2$, $MGF(t) = \frac{\lambda}{\lambda - t}$ for $t < \lambda$.
*   **JAM Tips:**
    1. **Memoryless Property:** $P(X > s+t | X > s) = P(X > t)$.
    2. **Relationship:** If $X_i \sim Exp(\lambda)$, then $\sum X_i \sim Gamma(n, \lambda)$.
    3. The rate parameter $\lambda$ is the reciprocal of the mean.

### 3. Double Exponential (Laplace) Distribution
*   **PDF:** $f(x) = \frac{1}{2b} e^{-\frac{|x-\mu|}{b}}$.
*   **Properties:** $E[X]=\mu$, $Var(X) = 2b^2$.
*   **JAM Tips:**
    1. It is symmetric around $\mu$.
    2. It has "heavier tails" than the Normal distribution.
    3. It can be thought of as the difference of two independent Exponential variables.

### 4. Gamma Distribution
*   **PDF:** $f(x) = \frac{1}{\Gamma(\alpha)\beta^\alpha} x^{\alpha-1} e^{-x/\beta}, \quad x > 0$.
*   **Properties:** $E[X]=\alpha\beta$, $Var(X) = \alpha\beta^2$.
*   **JAM Tips:**
    1. **Relationship:** If $\alpha=1$, it is Exponential.
    2. **Relationship:** If $\alpha = n/2$ and $\beta = 2$, it is Chi-square ($\chi^2_n$).
    3. Used to model waiting times for the $\alpha$-th event in a Poisson process.
    4. Note the parameterization: some books use $\beta$ as a rate ($e^{-\beta x}$), others as a scale ($e^{-x/\beta}$). **Check the formula provided in the question carefully.**

### 5. Beta Distribution
*   **Type I (Standard Beta):** $f(x) = \frac{1}{B(\alpha, \beta)} x^{\alpha-1} (1-x)^{\beta-1}, \quad 0 < x < 1$.
*   **Type II (Beta Prime):** $f(x) = \frac{1}{B(\alpha, \beta)} \frac{x^{\alpha-1}}{(1+x)^{\alpha+\beta}}, \quad x > 0$.
*   **Properties (Type I):** $E[X]=\frac{\alpha}{\alpha+\beta}$, $Var(X) = \frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$.
*   **JAM Tips:**
    1. **Interrelation:** If $X \sim Beta(\alpha, \beta)$, then $Y = \frac{X}{1-X} \sim Beta\text{ Prime}(\alpha, \beta)$.
    2. Beta is often the **conjugate prior** for Binomial/Bernoulli (important for Bayesian context, though JAM is mostly frequentist).
    3. Use the Beta function identity: $B(\alpha, \beta) = \frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+\beta)}$.

### 6. Normal (Gaussian) Distribution
*   **PDF:** $f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}$.
*   **Properties:** $E[X]=\mu$, $Var(X) = \sigma^2$.
*   **JAM Tips:**
    1. **Standardization:** $Z = \frac{X-\mu}{\sigma} \sim N(0,1)$. This is the most used technique.
    2. If $X \sim N(\mu_1, \sigma_1^2)$ and $Y \sim N(\mu_2, \sigma_2^2)$, then $aX+bY$ is also Normal.
    3. **Symmetry:** $P(X > \mu + a) = P(X < \mu - a)$.
    4. Central Limit Theorem (CLT) connection: Sums of i.i.d. variables converge to Normal.

### 7. Cauchy Distribution
*   **PDF:** $f(x) = \frac{1}{\pi \gamma [1 + (\frac{x-x_0}{\gamma})^2]}$.
*   **Properties:** Mean and Variance **do not exist** (the integral diverges).
*   **JAM Tips:**
    1. **The "Trap" Distribution:** If a question asks for the mean or variance of a Cauchy distribution, the answer is "Does not exist."
    2. It has extremely heavy tails.
    3. **Property:** The sample mean of i.i.d. Cauchy variables is *still* Cauchy (it does not follow CLT).

---

# Summary of Limiting Cases (High Priority for JAM)

| From Distribution | To Distribution | Condition |
| :--- | :--- | :--- |
| **Binomial** | **Poisson** | $n \to \infty, p \to 0, np = \lambda$ |
| **Hypergeometric** | **Binomial** | $N \to \infty$ (Population becomes infinite) |
| **Geometric** | **Exponential** | Continuous limit of discrete waiting time |
| **Binomial/Poisson** | **Normal** | $n$ is large (Central Limit Theorem) |
| **Gamma** | **Normal** | $\alpha \to \infty$ |


