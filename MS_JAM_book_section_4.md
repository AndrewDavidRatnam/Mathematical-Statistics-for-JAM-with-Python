# Section 4-A
Descriptive Statistics:
------------------------------
## 1. Measures of Central Tendency
These identify the "center" or typical value of a data set.

* Arithmetic Mean ($\bar{x}$): The sum of all observations divided by the total number of observations.
$$\bar{x} = \frac{\sum x_i}{n}$$ 
* Geometric Mean (GM): The $n^{th}$ root of the product of $n$ observations; ideal for rates and ratios.
$$GM = (x_1 \cdot x_2 \cdot \dots \cdot x_n)^{1/n}$$ 
* Harmonic Mean (HM): The reciprocal of the arithmetic mean of the reciprocals of the observations; used for average speeds/rates.
$$HM = \frac{n}{\sum (1/x_i)}$$ 
* Median: The middle value of a data set when arranged in order. For $n$ observations, it is the $(\frac{n+1}{2})^{th}$ value (if $n$ is odd).
* Mode: The value that appears most frequently in a data set.

------------------------------
## 2. Measures of Dispersion
These describe how "spread out" the data is from the center.

* Range: The simplest measure of spread, calculated as the difference between the maximum and minimum values.
$$Range = X_{max} - X_{min}$$ 
* Interquartile Range (IQR): The difference between the third quartile ($Q_3$) and the first quartile ($Q_1$); covers the middle 50% of data.
$$IQR = Q_3 - Q_1$$ 
* Mean Deviation about a point 'a': The average of the absolute differences between each data point and a specific point $a$ (usually the mean or median).
$$MD_a = \frac{\sum |x_i - a|}{n}$$ 
* Variance ($\sigma^2$): The average of the squared deviations from the mean; it measures the scale of dispersion.
$$\sigma^2 = \frac{\sum (x_i - \bar{x})^2}{n}$$ 
* Standard Deviation ($\sigma$): The positive square root of the variance; it brings the units back to the original scale of the data.
$$\sigma = \sqrt{\sigma^2}$$ 
* Coefficient of Variation (CV): A relative measure of dispersion expressed as a percentage; used to compare consistency between two data sets.
$$CV = \left( \frac{\sigma}{\bar{x}} \right) \times 100$$ 

------------------------------
## 3. Moments, Skewness, and Kurtosis
These describe the "shape" of the distribution.

* Raw Moment ($r^{th}$): Moments taken about the origin (usually zero) to describe the general distribution.
$$\mu'_r = \frac{\sum x_i^r}{n}$$ 
* Central Moment ($r^{th}$): Moments taken about the mean; the $2^{nd}$ central moment is the variance.
$$\mu_r = \frac{\sum (x_i - \bar{x})^r}{n}$$ 
* Skewness ($\beta_1$ or $\gamma_1$): Measures the lack of symmetry in a distribution (left-leaning or right-leaning).
$$\gamma_1 = \frac{\mu_3}{\sigma^3}$$ 
* Kurtosis ($\beta_2$ or $\gamma_2$): Measures the "peakedness" or flatness of the distribution relative to a normal distribution.
$$\beta_2 = \frac{\mu_4}{\mu_2^2}$$ 

------------------------------
## 4. Bivariate Data and Correlation
Relationship between two (or more) variables.

* Covariance ($Cov(x,y)$): Measures how two variables change together; positive means they move in the same direction.
$$Cov(x,y) = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{n}$$ 
* Simple Correlation ($r_{xy}$): Measures the strength and direction of the linear relationship between two variables, ranging from -1 to +1.
$$r_{xy} = \frac{Cov(x,y)}{\sigma_x \sigma_y}$$ 
* Spearman’s Rank Correlation ($\rho$): A non-parametric measure of correlation based on the ranks of data rather than actual values.
$$\rho = 1 - \frac{6 \sum d_i^2}{n(n^2 - 1)}$$ 
### 1. Partial Correlation ($r_{12.3}$) 
This formula removes the shared influence of variable 3 to see the "pure" relationship between 1 and 2. [5, 6] 
$$r_{12.3} = \frac{r_{12} - r_{13}r_{23}}{\sqrt{(1 - r_{13}^2)(1 - r_{23}^2)}}$$ 

* Logic: The numerator subtracts the path through the third variable ($r_{13}r_{23}$), and the denominator normalizes the result using the remaining variance. [1, 3] 

### 2. Multiple Correlation ($R_{1.23}$)
This formula measures how well variable 1 can be predicted by a combination of variables 2 and 3. [7, 8] 
$$R_{1.23} = \sqrt{\frac{r_{12}^2 + r_{13}^2 - 2r_{12}r_{13}r_{23}}{1 - r_{23}^2}}$$ 

* Logic: It combines the individual correlations of 1 with 2 and 3 while adjusting for the fact that 2 and 3 might already be correlated with each other ($r_{23}$). [8, 9] 

#### Essential Tips for JAM MS:

* Non-negativity: Unlike simple or partial correlation (which range from -1 to 1), Multiple Correlation ($R$) is always non-negative and ranges from 0 to 1.
* Relationship to Simple $r$: $R_{1.23}$ is never less than the absolute value of any simple correlation involving the dependent variable (i.e., $R_{1.23} \ge |r_{12}|$ and $R_{1.23} \ge |r_{13}|$).
* Computation Check: If $r_{12.3} = 0$, it implies that $r_{12} = r_{13}r_{23}$. [4, 8, 10, 11] 


# Section 4-B
Descriptive Statistics:

------------------------------
## 1. Random Experiments & Algebra of Events

 Concepts: A Random Experiment must have well-defined outcomes known in advance, but the specific outcome of a single trial is unpredictable. Event Space ($\mathcal{F}$) is a $\sigma$-field: it is closed under complements ($A^c \in \mathcal{F}$) and countable unions ($\cup A_i \in \mathcal{F}$).
* Algebra Rules:
* De Morgan's Laws: $(A \cup B)^c = A^c \cap B^c$ and $(A \cap B)^c = A^c \cup B^c$.
   * Distributive Laws: $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$. [1, 2] 

## 2. Definitions of Probability

* Relative Frequency: $P(A) = \lim_{n \to \infty} \frac{m}{n}$, where $m$ is the number of times $A$ occurs in $n$ trials.
* Axiomatic (Kolmogorov):
1. Non-negativity: $P(A) \geq 0$.
   2. Normalization: $P(S) = 1$.
   3. Countable Additivity: For disjoint $A_1, A_2, \dots$, $P(\cup A_i) = \sum P(A_i)$.
* Key Properties:
* $P(\emptyset) = 0$.
   * $P(A^c) = 1 - P(A)$.
   * If $A \subset B$, then $P(A) \leq P(B)$. [3] 

## 3. Addition Theorem (Inclusion-Exclusion)

* Formula (General):
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$ For $n$ events:
$$P(\cup A_i) = \sum P(A_i) - \sum P(A_i \cap A_j) + \dots + (-1)^{n-1} P(A_1 \cap \dots \cap A_n)$$ 

## 4. Geometric Probability

* Formula: Used for continuous sample spaces (lengths, areas, volumes).
$$P(A) = \frac{\text{Measure of } A}{\text{Total Measure of } S}$$ 
* Tip: In JAM, "Waiting Time" or "Meeting" problems are solved by sketching the $x-y$ region in a unit square. [4] 

## 5. Boole’s and Bonferroni’s Inequalities

* Boole’s Inequality: $P(\cup A_i) \leq \sum P(A_i)$. (The union is never larger than the sum of parts).
* Bonferroni’s Inequality: $P(\cap A_i) \geq \sum P(A_i) - (n-1)$.
* Application: Use this when you are given individual probabilities and asked for the minimum probability that all events occur together.

## 6. Conditional Probability & Multiplication Rule

* Formula: $P(A|B) = \frac{P(A \cap B)}{P(B)}$, provided $P(B) > 0$.
* Multiplication Rule: $P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$.

## 7. Total Probability & Bayes’ Theorem

* Total Probability: If $B_1, \dots, B_n$ partition $S$:
$$P(A) = \sum_{i=1}^n P(A|B_i)P(B_i)$$ 
* Bayes’ Theorem:
$$P(B_k|A) = \frac{P(A|B_k)P(B_k)}{\sum P(A|B_i)P(B_i)}$$ 

## 8. Independence (Pairwise vs. Mutual)

* Pairwise: $P(A_i \cap A_j) = P(A_i)P(A_j)$ for all $i, j$.
* Mutual: Requires all combinations to satisfy the product rule, including triples: $P(A_1 \cap A_2 \cap A_3) = P(A_1)P(A_2)P(A_3)$.
* Caveat: Pairwise independence does not imply mutual independence! (Classic exam trap).

------------------------------
## 5 High-Level Strategy Tips for Probability

   1. Partition First: In Bayes’ problems, the hardest part is identifying the partition $B_i$. They must be mutually exclusive and exhaustive. If you can't find them, you can't solve the denominator.
   2. The "At Least" Trigger: Whenever you see "at least one," immediately try $1 - P(\text{None})$. This turns complex unions into simple intersections.
   3. Venn vs. Algebra: If a problem involves 2-3 events and "exact" counts (e.g., "exactly one occurs"), use a Venn Diagram. If it involves $n$ events or abstract bounds, use Bonferroni.
   4. Mutual vs. Pairwise Trap: If a question asks if $A, B, C$ are independent, checking $P(A \cap B \cap C)$ is not enough. You must check all 3 pairs and the triple.
   5. Conditional logic: Remember that $P(A|B) + P(A^c|B) = 1$, but $P(A|B) + P(A|B^c)$ is usually not equal to 1. Conditioning on the same event behaves like normal probability; conditioning on different events does not. 

#### 1. Random Experiments & Algebra of Events

* Identify the Outcome Space: Before calculating, clearly define what one "outcome" looks like (e.g., a pair $(x,y)$ vs. a single sum).
* The Power of Complements: If "Event A" is hard to count, check if "Not A" is easier. Use De Morgan's Laws to flip between unions and intersections.
* Verify $\sigma$-field Properties: For conceptual questions, remember that an event space must be closed under countable unions, not just finite ones.
* Set Theory Visualisation: Translate word problems into set operations (e.g., "either A or B but not both" becomes $(A \cup B) - (A \cap B)$).
* Exhaustive vs. Mutually Exclusive: Always check if your elementary events cover the entire sample space ($P(S)=1$) and don't overlap ($P(A \cap B)=0$).

#### 2. Definitions of Probability (Axiomatic & Relative Frequency)

* Axiom Check: If a "probability function" is given as a formula, test if it satisfies $P(S)=1$ and non-negativity.
* Frequency Limits: For Relative Frequency, remember it assumes the limit exists as $n \to \infty$; in small samples, frequency is just an estimate.
* Monotonicity Property: Use $A \subseteq B \implies P(A) \leq P(B)$ to quickly eliminate impossible multiple-choice options.
* Finite Additivity: For finite sample spaces, $P(A)$ is just the sum of probabilities of its constituent elementary outcomes.
* Measure Theory Link: Think of probability as "weight." Axiomatic probability is simply a measure with a total mass of 1. [1] 

#### 3. Addition Theorem (Inclusion-Exclusion Principle)

* The "Double Counting" Correction: Always subtract the intersection $P(A \cap B)$ when adding individual probabilities.
* The Pattern of Signs: For 3+ events, remember the alternating sign: $+$ (singles) $-$ (doubles) $+$ (triples).
* Symmetry Shortcut: If events are exchangeable (all $P(A_i)$ are equal and all $P(A_i \cap A_j)$ are equal), use $n \cdot P(A_1) - \binom{n}{2} \cdot P(A_1 \cap A_2) \dots$
* Venn Diagram Limits: For exactly 2 or 3 events, a Venn Diagram is often faster and more accurate than the full algebraic formula.
* Bound Your Answer: If your calculation gives a value $>1$ or $<0$, you likely forgot to subtract an intersection.

#### 4. Geometric Probability

* Boundary Constraints: Always start by sketching the "allowed" region (the total sample space) on a graph.
* Linear vs. Area vs. Volume: Use Length for 1D (time), Area for 2D (darts), and Volume for 3D. Ensure units are consistent.
* The "Meeting Problem" Strategy: For problems like "two people meeting within 10 minutes," the condition is $|x - y| \leq 10$. This creates a "strip" across your square area.
* Ratio of Measures: Focus on the ratio rather than the absolute value. Often, you can use simple geometry (triangles/squares) instead of integration.
* Uniformity Assumption: Geometric probability assumes a "Uniform Distribution" over the space; if the density isn't constant, you must use integration.

#### 5. Boole’s and Bonferroni’s Inequalities

* Minimum Probability Bound: Use Bonferroni when asked for the minimum chance that all $n$ events happen simultaneously ($P(\cap A_i)$).
* Maximum Probability Bound: Use Boole’s to find the maximum possible probability for the union ($P(\cup A_i)$).
* Complementary Bounds: If $P(A_i)$ are all very high (e.g., 0.95), focus on the probabilities of their complements ($0.05$) to bound the intersection.
* The $(n-1)$ Rule: Remember Bonferroni's lower bound is $\sum P(A_i) - (n-1)$. For two events, it's just $P(A) + P(B) - 1$.
* Check for Triviality: If your Bonferroni calculation gives a negative number, the actual minimum bound is simply $0$.

#### 6. Conditional Probability & Multiplication Rule

* Reduced Sample Space: Think of $P(A|B)$ as "zooming in" on event $B$ and treating it as your new entire world (sample space).
* The Order of Events: In the Multiplication Rule, the order matters conceptually: $P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$.
* Conditioning is a Probability: Remember that $P(\cdot | B)$ satisfies all axioms of probability (e.g., $P(A \cup C | B) = P(A|B) + P(C|B) - P(A \cap C | B)$).
* Independence Check: If $P(A|B) = P(A)$, the events are independent. If $P(A|B) > P(A)$, they are "positively associated."
* Tree Diagrams: For sequential experiments (e.g., drawing without replacement), use a tree diagram to visualize the multiplication of probabilities along paths. [2, 3] 

#### 7. Theorem of Total Probability & Bayes’ Theorem

* Identify the Partition: Look for mutually exclusive events that cover everything (e.g., "Machine A, B, or C"). This is your "prior" information.
* Prior vs. Posterior: Always distinguish between $P(\text{Effect}|\text{Cause})$ (likelihood) and $P(\text{Cause}|\text{Effect})$ (Bayes' target).
* Denominator Logic: The denominator in Bayes’ is just the Law of Total Probability. Calculate it first to ensure it's non-zero.
* Odds Form: For binary partitions, sometimes the odds form is easier: $\frac{P(A|B)}{P(A^c|B)} = \frac{P(B|A)}{P(B|A^c)} \cdot \frac{P(A)}{P(A^c)}$.
* False Positive Trap: Be extra careful with "Rare Disease" problems; high accuracy tests can still yield low probability results if the prior is very small. [4] 

#### 8. Independence (Pairwise vs. Mutual)

* Mutual Implies Pairwise: If events are mutually independent, they are always pairwise independent. The reverse is NOT true.
* The $2^n - n - 1$ Check: To prove $n$ events are mutually independent, you technically need to verify conditions for all pairs, triples, quadruples, etc.
* Zero and One: An event with probability $0$ or $1$ is independent of any other event.
* Independent Complements: If $A$ and $B$ are independent, then $A$ and $B^c$, $A^c$ and $B$, and $A^c$ and $B^c$ are all also independent.
* Common Variable Trap: Two events are often dependent if they both depend on a shared "hidden" random variable. Independence usually implies they come from physically unrelated processes.



