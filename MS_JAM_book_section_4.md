# Section 4 
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
#### 1. Partial Correlation ($r_{12.3}$) 
This formula removes the shared influence of variable 3 to see the "pure" relationship between 1 and 2. [5, 6] 
$$r_{12.3} = \frac{r_{12} - r_{13}r_{23}}{\sqrt{(1 - r_{13}^2)(1 - r_{23}^2)}}$$ 

* Logic: The numerator subtracts the path through the third variable ($r_{13}r_{23}$), and the denominator normalizes the result using the remaining variance. [1, 3] 

#### 2. Multiple Correlation ($R_{1.23}$)
This formula measures how well variable 1 can be predicted by a combination of variables 2 and 3. [7, 8] 
$$R_{1.23} = \sqrt{\frac{r_{12}^2 + r_{13}^2 - 2r_{12}r_{13}r_{23}}{1 - r_{23}^2}}$$ 

* Logic: It combines the individual correlations of 1 with 2 and 3 while adjusting for the fact that 2 and 3 might already be correlated with each other ($r_{23}$). [8, 9] 

##### Essential Tips for JAM MS:

* Non-negativity: Unlike simple or partial correlation (which range from -1 to 1), Multiple Correlation ($R$) is always non-negative and ranges from 0 to 1.
* Relationship to Simple $r$: $R_{1.23}$ is never less than the absolute value of any simple correlation involving the dependent variable (i.e., $R_{1.23} \ge |r_{12}|$ and $R_{1.23} \ge |r_{13}|$).
* Computation Check: If $r_{12.3} = 0$, it implies that $r_{12} = r_{13}r_{23}$. [4, 8, 10, 11] 



-------------------------------


