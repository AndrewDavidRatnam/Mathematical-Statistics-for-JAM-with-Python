## Random Vectors

### Definition of Random Vectors

A **random vector** is a vector whose components are random variables. If $X_1, X_2, \ldots, X_n$ are random variables defined on the same probability space, then $\mathbf{X} = (X_1, X_2, \ldots, X_n)^T$ is an $n$-dimensional random vector.

**Critical Tips & High-Order Thinking Tips:**

1.  **Understand the "Vector" Aspect:** Don't just think of them as a collection of individual random variables. The "vector" implies a relationship and joint behavior among its components. This is crucial for understanding joint distributions.
2.  **Sample Space Perspective:** Each component $X_i$ maps outcomes from the sample space $\Omega$ to real numbers. The random vector $\mathbf{X}$ maps $\Omega$ to $\mathbb{R}^n$. Visualizing this mapping can help.
3.  **IIT JAM Context:** In IIT JAM, random vectors often appear in bivariate (2D) or sometimes trivariate (3D) forms. Familiarize yourself with how concepts extend from univariate to multivariate.
4.  **Foundation for Multivariate Analysis:** Random vectors are the building blocks for multivariate statistics. A strong grasp here will help with topics like multivariate normal distribution, principal component analysis (if you encounter it), and regression.
5.  **Distinguish from Independent Variables:** A random vector *can* have independent components, but it doesn't *have* to. The general case assumes dependence, which is what joint distributions help characterize.
6.  **Notation Matters:** Be precise with bolding for vectors ($\mathbf{X}$) versus scalars ($X_i$). This reduces ambiguity.

## Joint and Marginal Cumulative Distribution Functions (CDFs) of a Random Vector

### Joint CDF

The **joint cumulative distribution function (CDF)** of an $n$-dimensional random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is given by:

$F_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = P(X_1 \le x_1, \ldots, X_n \le x_n)$

For a bivariate random vector $(X, Y)$, this simplifies to:

$F_{X,Y}(x, y) = P(X \le x, Y \le y)$

**Properties of Joint CDF:**

1.  $0 \le F(x_1, \ldots, x_n) \le 1$
2.  $F(-\infty, \ldots, -\infty) = 0$
3.  $F(\infty, \ldots, \infty) = 1$
4.  If $x_i \le x_i'$ for all $i$, then $F(x_1, \ldots, x_n) \le F(x_1', \ldots, x_n')$ (Non-decreasing)
5.  $F$ is right-continuous in each argument.
6.  For a bivariate CDF, $P(a < X \le b, c < Y \le d) = F(b,d) - F(a,d) - F(b,c) + F(a,c)$

### Marginal CDF

The **marginal CDF** of a component $X_i$ of the random vector $\mathbf{X}$ is obtained by letting all other components tend to infinity:

$F_{X_i}(x_i) = P(X_i \le x_i) = F_{X_1, \ldots, X_n}(\infty, \ldots, \infty, x_i, \infty, \ldots, \infty)$ (where $x_i$ is in the $i$-th position)

For a bivariate random vector $(X, Y)$:

$F_X(x) = F_{X,Y}(x, \infty) = P(X \le x)$
$F_Y(y) = F_{X,Y}(\infty, y) = P(Y \le y)$

**Critical Tips & High-Order Thinking Tips:**

1.  **Geometric Interpretation:** For $F(x,y)$, think of it as the probability mass in the region $(-\infty, x] \times (-\infty, y]$ in the 2D plane. This helps visualize properties and calculations.
2.  **From Joint to Marginal (and NOT vice-versa):** You can always derive marginal CDFs from a joint CDF. However, you generally cannot reconstruct a joint CDF from marginal CDFs unless the variables are independent. This is a fundamental concept.
3.  **Independence Condition:** If $X$ and $Y$ are independent, then $F_{X,Y}(x,y) = F_X(x)F_Y(y)$. Recognize this condition instantly.
4.  **Handling Discontinuities:** For discrete random vectors, the CDF will have jump discontinuities. For continuous, it will be continuous. Pay attention to strict vs. non-strict inequalities in probability statements.
5.  **IIT JAM Problem Solving:** Often, you'll be given a joint CDF and asked to find marginals, or calculate probabilities for specific regions using the inclusion-exclusion principle property. Practice these manipulations.
6.  **Difference between $P(X<x)$ and $P(X \le x)$:** This is especially important for discrete distributions. CDF is defined with $\le$.
7.  **Limits to Infinity:** Understanding why "setting other variables to infinity" works for marginal CDFs is key. It means we are considering all possible values for those variables.
8.  **Extension to More Variables:** While IIT JAM typically focuses on bivariate cases, understand the conceptual extension to $n$-dimensions.

## Discrete and Continuous Type Random Vectors

### Discrete Type Random Vector

A random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is of **discrete type** if its components $X_i$ are discrete random variables and the vector can take on at most a countably infinite number of values. The probability mass is concentrated at specific points.

### Continuous Type Random Vector

A random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is of **continuous type** if its joint CDF $F_{X_1, \ldots, X_n}(x_1, \ldots, x_n)$ is continuous everywhere and can be expressed as an integral of a joint probability density function. The probability of the vector taking any specific value is 0.

**Critical Tips & High-Order Thinking Tips:**

1.  **Distinguishing Feature:** The fundamental difference lies in how probabilities are assigned: point probabilities for discrete, and probabilities over intervals/regions via integration for continuous.
2.  **Support of the Random Vector:** For discrete, this is a set of points. For continuous, it's typically a region in $\mathbb{R}^n$. Defining the support correctly is crucial for setting up summations/integrals.
3.  **Mixed Distributions (Less Common in IIT JAM):** While possible for a random vector to have some discrete and some continuous components, this is rarely tested in IIT JAM. Focus on purely discrete or purely continuous cases.
4.  **From CDF to PMF/PDF:** The process of differentiation/summation to go from CDF to PMF/PDF is fundamental and should be mastered for both types.
5.  **Real-World Context:** Think about examples: discrete (e.g., number of heads and tails in multiple coin tosses), continuous (e.g., height and weight of individuals). This helps build intuition.
6.  **Impact on Calculations:** The type of random vector dictates whether you use summations (discrete) or integrals (continuous) for probabilities and expected values.

## Joint and Marginal Probability Mass Functions (PMF) / Probability Density Functions (PDF)

### Joint PMF (for Discrete Random Vectors)

The **joint probability mass function (PMF)** of a discrete random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is given by:

$p_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = P(X_1 = x_1, \ldots, X_n = x_n)$

For a bivariate discrete random vector $(X, Y)$:

$p_{X,Y}(x, y) = P(X = x, Y = y)$

**Properties of Joint PMF:**

1.  $0 \le p(x_1, \ldots, x_n) \le 1$ for all $(x_1, \ldots, x_n)$ in the support.
2.  $\sum_{x_1} \ldots \sum_{x_n} p(x_1, \ldots, x_n) = 1$
3.  $F(x_1, \ldots, x_n) = \sum_{t_1 \le x_1} \ldots \sum_{t_n \le x_n} p(t_1, \ldots, t_n)$

### Marginal PMF (for Discrete Random Vectors)

The **marginal PMF** of a component $X_i$ is obtained by summing the joint PMF over all possible values of the other components:

$p_{X_i}(x_i) = \sum_{x_1} \ldots \sum_{x_{i-1}} \sum_{x_{i+1}} \ldots \sum_{x_n} p_{X_1, \ldots, X_n}(x_1, \ldots, x_n)$

For a bivariate discrete random vector $(X, Y)$:

$p_X(x) = \sum_{y} p_{X,Y}(x, y)$
$p_Y(y) = \sum_{x} p_{X,Y}(x, y)$

### Joint PDF (for Continuous Random Vectors)

The **joint probability density function (PDF)** of a continuous random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is a non-negative function $f_{X_1, \ldots, X_n}(x_1, \ldots, x_n)$ such that:

$F_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = \int_{-\infty}^{x_1} \ldots \int_{-\infty}^{x_n} f_{X_1, \ldots, X_n}(t_1, \ldots, t_n) dt_1 \ldots dt_n$

And, conversely (if the derivatives exist):

$f_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = \frac{\partial^n F_{X_1, \ldots, X_n}(x_1, \ldots, x_n)}{\partial x_1 \ldots \partial x_n}$

For a bivariate continuous random vector $(X, Y)$:

$f_{X,Y}(x, y) = \frac{\partial^2 F_{X,Y}(x,y)}{\partial x \partial y}$

**Properties of Joint PDF:**

1.  $f(x_1, \ldots, x_n) \ge 0$ for all $(x_1, \ldots, x_n)$.
2.  $\int_{-\infty}^{\infty} \ldots \int_{-\infty}^{\infty} f(x_1, \ldots, x_n) dx_1 \ldots dx_n = 1$
3.  For any region $A \subseteq \mathbb{R}^n$, $P(\mathbf{X} \in A) = \int_A f(x_1, \ldots, x_n) dx_1 \ldots dx_n$.

### Marginal PDF (for Continuous Random Vectors)

The **marginal PDF** of a component $X_i$ is obtained by integrating the joint PDF over all possible values of the other components:

$f_{X_i}(x_i) = \int_{-\infty}^{\infty} \ldots \int_{-\infty}^{\infty} f_{X_1, \ldots, X_n}(x_1, \ldots, x_n) dx_1 \ldots dx_{i-1} dx_{i+1} \ldots dx_n$

For a bivariate continuous random vector $(X, Y)$:

$f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) dy$
$f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) dx$

**Critical Tips & High-Order Thinking Tips:**

1.  **Normalization Condition:** Always check that the sum of PMF (discrete) or integral of PDF (continuous) over the entire sample space equals 1. This is a common way to find unknown constants in problems.
2.  **Support of the Joint Distribution:** Carefully define the region over which the PMF/PDF is non-zero. This dictates the limits of summation/integration for marginals and probabilities. A mistake here is a common error.
3.  **Order of Integration/Summation:** When finding marginals, ensure you integrate/sum out the correct variables. For $f_X(x)$, you integrate out $y$.
4.  **Independence using PMF/PDF:** $X$ and $Y$ are independent if and only if $p_{X,Y}(x,y) = p_X(x)p_Y(y)$ for all $x,y$ (discrete), or $f_{X,Y}(x,y) = f_X(x)f_Y(y)$ for all $x,y$ (continuous). This is a crucial test for independence.
5.  **Relationship between PMF/PDF and CDF:** Understand the differentiation/integration link. You should be able to go from joint CDF to joint PDF/PMF and back.
6.  **IIT JAM Focus on Bivariate:** Expect many problems involving finding marginal PDFs/PMFs from a given joint distribution, calculating probabilities over specific regions (e.g., $P(X+Y < c)$), or checking for independence.
7.  **Geometric Interpretation for PDF:** The joint PDF $f(x,y)$ represents the "density" of probability around the point $(x,y)$. The probability over a region is the volume under the surface $f(x,y)$ over that region.
8.  **Careful with Limits for Non-Rectangular Regions:** When the support is not rectangular (e.g., $0 < x < y < 1$), the limits of integration for marginals will depend on the other variable. Master iterated integrals. 


## Conditional CDF, Conditional PMF, and Conditional PDF

### Conditional CDF

The **conditional cumulative distribution function (CDF)** of $Y$ given $X=x$ is:

$F_{Y|X}(y|x) = P(Y \le y | X = x)$

**Formula for Discrete Case:**

If $p_X(x) > 0$:
$F_{Y|X}(y|x) = \sum_{t \le y} p_{Y|X}(t|x)$

## Independence of Random Variables

Two random variables $X$ and $Y$ (components of a random vector) are said to be **independent** if the occurrence of an event defined by $X$ does not affect the probability of an event defined by $Y$.

**Formulas/Conditions for Independence:**

1.  **Using Joint and Marginal CDFs:**
    $X$ and $Y$ are independent if and only if $F_{X,Y}(x,y) = F_X(x)F_Y(y)$ for all $x,y \in \mathbb{R}$.

2.  **Using Joint and Marginal PMFs (for Discrete Variables):**
    $X$ and $Y$ are independent if and only if $p_{X,Y}(x,y) = p_X(x)p_Y(y)$ for all possible values $x,y$.

3.  **Using Joint and Marginal PDFs (for Continuous Variables):**
    $X$ and $Y$ are independent if and only if $f_{X,Y}(x,y) = f_X(x)f_Y(y)$ for all $x,y \in \mathbb{R}^2$.

4.  **Using Conditional PMF/PDF:**
    $X$ and $Y$ are independent if and only if $p_{Y|X}(y|x) = p_Y(y)$ (for discrete, where $p_X(x)>0$) or $f_{Y|X}(y|x) = f_Y(y)$ (for continuous, where $f_X(x)>0$). (And similarly for $p_{X|Y}(x|y)$ or $f_{X|Y}(x|y)$).

**Critical Tips & High-Order Thinking Tips:**

1.  **Fundamental Concept:** Independence is one of the most crucial concepts in probability and statistics. It simplifies calculations significantly.
2.  **Product Rule:** The core idea is that the joint distribution "factors" into the product of the marginal distributions. This is your primary test.
3.  **Beware of Correlation vs. Independence:** Remember that uncorrelatedness (covariance = 0) implies independence *only* for jointly normal random variables. In general, independence implies uncorrelatedness, but not vice-versa. This is a common trap.
4.  **Support Matters:** For the product rule to hold, the support of the joint distribution must be a rectangular region. If the support is triangular, circular, or any non-rectangular shape where the range of one variable depends on the other, the variables *cannot* be independent.
5.  **Functions of Independent Variables:** If $X$ and $Y$ are independent, and $g(X)$ and $h(Y)$ are functions of $X$ and $Y$ respectively, then $g(X)$ and $h(Y)$ are also independent. This is a powerful property.
6.  **IIT JAM Problem Solving:** Expect problems where you're given a joint distribution and asked to determine if $X$ and $Y$ are independent. This usually involves finding marginals and checking the product rule.
7.  **Extension to Multiple Variables:** For $n$ random variables $X_1, \ldots, X_n$ to be mutually independent, their joint PMF/PDF must factor into the product of all $n$ marginal PMFs/PDFs: $f_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = f_{X_1}(x_1) \ldots f_{X_n}(x_n)$. Pairwise independence is not enough for mutual independence.
8.  **Intuitive Meaning:** Think about scenarios where variables would naturally be independent (e.g., outcomes of two separate dice rolls) vs. dependent (e.g., height and weight of a person).
9.  **Simplification of Conditional Distributions:** If independent, $P(Y \le y | X=x) = P(Y \le y)$, meaning the information about $X$ gives no additional information about $Y$.

## Distribution of Functions of Random Vectors using Transformation of Variables and Jacobian Method

This method is used to find the PDF of a new random vector $\mathbf{Y}$ which is a function of an existing random vector $\mathbf{X}$.

Let $\mathbf{X} = (X_1, \ldots, X_n)^T$ be a continuous random vector with joint PDF $f_{\mathbf{X}}(x_1, \ldots, x_n)$.
Let $\mathbf{Y} = (Y_1, \ldots, Y_n)^T$ be a new random vector defined by the transformation $Y_i = u_i(X_1, \ldots, X_n)$ for $i=1, \ldots, n$.

Assume the transformation is one-to-one and has continuous partial derivatives.
Then, we can find the inverse transformation: $X_i = w_i(Y_1, \ldots, Y_n)$ for $i=1, \ldots, n$.

The **Jacobian of the transformation** from $\mathbf{X}$ to $\mathbf{Y}$ (or $\mathbf{Y}$ to $\mathbf{X}$) is a determinant of a matrix of partial derivatives.

**Formula for Joint PDF of $\mathbf{Y}$:**

$f_{\mathbf{Y}}(y_1, \ldots, y_n) = f_{\mathbf{X}}(w_1(y_1, \ldots, y_n), \ldots, w_n(y_1, \ldots, y_n)) \cdot |J|$

Where $|J|$ is the absolute value of the Jacobian determinant:

$J = \det \begin{pmatrix}
\frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} & \ldots & \frac{\partial x_1}{\partial y_n} \\
\frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2} & \ldots & \frac{\partial x_2}{\partial y_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial x_n}{\partial y_1} & \frac{\partial x_n}{\partial y_2} & \ldots & \frac{\partial x_n}{\partial y_n}
\end{pmatrix}$

The support of $\mathbf{Y}$ must be carefully determined by mapping the support of $\mathbf{X}$ through the transformation.

**Important Note for a single function of two variables:**
If $Z = g(X,Y)$ and we want to find $f_Z(z)$, we often introduce an auxiliary variable, say $W=Y$ (or $W=X$), to form a bivariate transformation $(Z,W)$. Then find $f_{Z,W}(z,w)$ and integrate out $W$ to get $f_Z(z)$.

**Critical Tips & High-Order Thinking Tips:**

1.  **One-to-One Transformation:** The Jacobian method works directly for one-to-one transformations. If it's not one-to-one, you need to split the domain into regions where it is, and sum the results. (e.g., $Y=X^2$ is not one-to-one, need to consider positive and negative roots).
2.  **Inverse Transformation is Key:** The first step is almost always to express $X_i$ in terms of $Y_i$. If you struggle with this, the problem will be difficult.
3.  **Correct Jacobian:** Make sure you're computing the Jacobian of the *inverse* transformation (i.e., $\partial x_i / \partial y_j$). If you compute $\partial y_i / \partial x_j$, you need to use $|J^{-1}| = 1/|J|$. Be consistent.
4.  **Absolute Value:** Don't forget the absolute value of the Jacobian determinant. Probabilities are non-negative.
5.  **New Support:** After finding $f_{\mathbf{Y}}(y_1, \ldots, y_n)$, the critical step is to determine the correct support for $\mathbf{Y}$. Substitute the ranges of $X_i$ into the transformation equations. This is where many errors occur.
6.  **Auxiliary Variable Technique (for IIT JAM):** This is extremely common for problems like finding the distribution of $X+Y$, $X-Y$, $XY$, or $X/Y$. Practice this setup repeatedly.
    *   Example: For $Z = X+Y$, let $W=X$. Then $X=W$, $Y=Z-W$. Find Jacobian, then $f_{Z,W}(z,w)$, then integrate $f_{Z,W}(z,w)$ with respect to $w$ to get $f_Z(z)$.
7.  **Order of Operations:**
    *   Define transformation $Y_i = u_i(\mathbf{X})$.
    *   Find inverse transformation $X_i = w_i(\mathbf{Y})$.
    *   Compute the Jacobian determinant $J = \det(\partial x_i / \partial y_j)$.
    *   Substitute $w_i(\mathbf{Y})$ into $f_{\mathbf{X}}(\mathbf{x})$.
    *   Multiply by $|J|$.
    *   Determine the new support for $\mathbf{Y}$.
8.  **Alternative Method: CDF Method (High-Order):** For some simpler transformations, especially for a single random variable, the CDF method ($F_Y(y) = P(Y \le y)$) can be easier. For multivariate transformations, Jacobian is usually more direct.
9.  **Standard Distributions:** Be familiar with common distributions resulting from transformations (e.g., sum of independent normal is normal, sum of independent Poisson is Poisson, sum of independent gamma with same scale is gamma). This helps verify your answers.
10. **Practice with Examples:** Work through examples like $Z=X+Y$, $Z=X/Y$, $Z=XY$ for various parent distributions (Uniform, Exponential, Normal). These are frequently tested.

## Mathematical Expectation of Functions of Random Vectors

The **mathematical expectation** (or expected value) of a function $g(X_1, \ldots, X_n)$ of a random vector $\mathbf{X} = (X_1, \ldots, X_n)^T$ is given by:

### For Discrete Random Vectors:

$E[g(X_1, \ldots, X_n)] = \sum_{x_1} \ldots \sum_{x_n} g(x_1, \ldots, x_n) p_{X_1, \ldots, X_n}(x_1, \ldots, x_n)$

### For Continuous Random Vectors:

$E[g(X_1, \ldots, X_n)] = \int_{-\infty}^{\infty} \ldots \int_{-\infty}^{\infty} g(x_1, \ldots, x_n) f_{X_1, \ldots, X_n}(x_1, \ldots, x_n) dx_1 \ldots dx_n$

**Specific Examples of Expectations:**

*   **Mean Vector:** $E[\mathbf{X}] = (E[X_1], \ldots, E[X_n])^T$
    *   $E[X_i] = \sum_{x_i} x_i p_{X_i}(x_i)$ or $\int_{-\infty}^{\infty} x_i f_{X_i}(x_i) dx_i$ (using marginals)
*   **Covariance:** For two components $X_i$ and $X_j$:
    $Cov(X_i, X_j) = E[(X_i - E[X_i])(X_j - E[X_j])] = E[X_i X_j] - E[X_i]E[X_j]$
    *   $E[X_i X_j] = \sum_{x_i} \sum_{x_j} x_i x_j p_{X_i,X_j}(x_i,x_j)$ or $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x_i x_j f_{X_i,X_j}(x_i,x_j) dx_i dx_j$ (using joint distribution)
*   **Correlation Coefficient:** $\rho_{X_i, X_j} = \frac{Cov(X_i, X_j)}{\sqrt{Var(X_i)Var(X_j)}}$

**Properties of Expectation:**

1.  **Linearity:** $E[a g(\mathbf{X}) + b h(\mathbf{X})] = a E[g(\mathbf{X})] + b E[h(\mathbf{X})]$
2.  **Constant:** $E[c] = c$ for a constant $c$.
3.  **For Independent Variables:** If $X$ and $Y$ are independent, then $E[g(X)h(Y)] = E[g(X)]E[h(Y)]$. (This is a powerful simplification!).
    *   Specifically, $E[XY] = E[X]E[Y]$ if $X$ and $Y$ are independent. This implies $Cov(X,Y)=0$.

**Critical Tips & High-Order Thinking Tips:**

1.  **LOTUS (Law of the Unconscious Statistician):** This is the fundamental principle here. You *don't* need to find the distribution of $Y=g(\mathbf{X})$ first to calculate $E[Y]$. You can directly use the joint distribution of $\mathbf{X}$. This saves immense time.
2.  **Correct Joint Distribution:** Always use the *joint* PMF/PDF of $\mathbf{X}$ when computing $E[g(\mathbf{X})]$. Do not use marginals unless the function only involves a subset of the variables and you integrate/sum over the rest correctly.
3.  **Limits of Integration/Summation:** Be very careful with the support of the random vector when setting up the integrals or summations. This is a common source of error.
4.  **Linearity is Your Friend:** Leverage the linearity of expectation whenever possible. For example, $E[X+Y] = E[X]+E[Y]$ *always*, regardless of independence. This is a very powerful property.
5.  **Independence Simplification:** If variables are independent, the calculation of $E[XY]$ simplifies dramatically to $E[X]E[Y]$. Always check for independence if you need to compute such expectations.
6.  **Covariance and Correlation:** Understand these as measures of linear association. A positive covariance means they tend to increase/decrease together. Negative means one increases as the other decreases. Zero means no linear relationship (but not necessarily independence).
7.  **Variance of a Sum (High-Order):**
    $Var(X+Y) = Var(X) + Var(Y) + 2 Cov(X,Y)$
    If $X,Y$ are independent, $Var(X+Y) = Var(X) + Var(Y)$. This formula is often tested.
8.  **Conditional Expectation (Connection to previous topic):** $E[Y|X=x]$ is a function of $x$. Its expectation $E[E[Y|X]] = E[Y]$. This is called the Law of Total Expectation and is a powerful tool for complex problems.
9.  **Moment Generating Functions (MGFs) (High-Order):** While not explicitly asked in your prompt, MGFs are often used to find moments (expectations) and to determine the distribution of sums of independent random variables.
10. **Practice with Standard Examples:** Calculate $E[X]$, $Var(X)$, $Cov(X,Y)$ for common bivariate distributions (e.g., bivariate uniform, bivariate exponential if possible, discrete joint distributions).



**Formula for Continuous Case:**

If $f_X(x) > 0$:
$F_{Y|X}(y|x) = \int_{-\infty}^{y} f_{Y|X}(t|x) dt$

### Conditional PMF (for Discrete Random Vectors)

The **conditional probability mass function (PMF)** of $Y$ given $X=x$ is:

$p_{Y|X}(y|x) = P(Y=y | X=x) = \frac{P(X=x, Y=y)}{P(X=x)} = \frac{p_{X,Y}(x,y)}{p_X(x)}$, provided $p_X(x) > 0$.

Similarly, $p_{X|Y}(x|y) = \frac{p_{X,Y}(x,y)}{p_Y(y)}$, provided $p_Y(y) > 0$.

### Conditional PDF (for Continuous Random Vectors)

The **conditional probability density function (PDF)** of $Y$ given $X=x$ is:

$f_{Y|X}(y|x) = \frac{f_{X,Y}(x,y)}{f_X(x)}$, provided $f_X(x) > 0$.

Similarly, $f_{X|Y}(x|y) = \frac{f_{X,Y}(x,y)}{f_Y(y)}$, provided $f_Y(y) > 0$.

**Critical Tips & High-Order Thinking Tips:**

1.  **"Given That" is Key:** Conditional distributions describe the distribution of one variable when we *know* the value of another. This is crucial for understanding relationships between variables.
2.  **Definition of Conditional Probability:** Remember the fundamental definition $P(A|B) = P(A \cap B) / P(B)$. This extends directly to random variables.
3.  **Numerator is Joint, Denominator is Marginal:** This is the universal structure for conditional PMF/PDF. You must be able to compute both the joint and the relevant marginal.
4.  **Support of Conditional Distribution:** The support of $Y|X=x$ might be different from the marginal support of $Y$. Always consider the condition $X=x$ when determining the range of $Y$.
5.  **Normalization of Conditional PMF/PDF:** A conditional PMF/PDF itself must sum/integrate to 1 over its respective domain. This can be used as a check.
    *   $\sum_y p_{Y|X}(y|x) = 1$
    *   $\int_{-\infty}^{\infty} f_{Y|X}(y|x) dy = 1$
6.  **Independence using Conditional Distributions:** If $X$ and $Y$ are independent, then:
    *   $p_{Y|X}(y|x) = p_Y(y)$ (discrete)
    *   $f_{Y|X}(y|x) = f_Y(y)$ (continuous)
    This provides another powerful way to check for independence.
7.  **Bayes' Theorem for Random Variables (High-Order):** While not explicitly asked, understanding that conditional distributions are a basis for Bayes' theorem is a high-order connection. For example, $f_{X|Y}(x|y) = \frac{f_{Y|X}(y|x)f_X(x)}{f_Y(y)}$.
8.  **Expected Values (High-Order):** Once you have conditional distributions, you can calculate conditional expectations and variances (e.g., $E[Y|X=x]$). This often appears in IIT JAM.
9.  **Careful with Division by Zero:** The condition $p_X(x) > 0$ or $f_X(x) > 0$ is vital. If the marginal probability/density is zero at a certain point, the conditional distribution is undefined.
10. **Problem-Solving Strategy:** When asked for a conditional distribution, first identify the joint, then the relevant marginal, and then perform the division. Ensure you specify the range for which the conditional distribution is valid.

