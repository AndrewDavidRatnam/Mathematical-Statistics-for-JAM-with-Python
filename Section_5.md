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



