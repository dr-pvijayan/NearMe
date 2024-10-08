# STATATICS AND NUMERICAL METHODS
## ASSIGNMENT - 1

## QUESTION - 1
![Screenshot 2024-10-08 221944](https://github.com/user-attachments/assets/45a17acd-5390-4dc9-b394-87095c7d8071)

## PROGRAM  
```
import scipy.stats as stats
import numpy as np
n = 14  
sample_mean = 17.85 
pop_mean = 18.5  
sample_std = 1.955  
confidence_level = 0.95  
t_statistic = (sample_mean - pop_mean) / (sample_std / np.sqrt(n))
degrees_of_freedom = n - 1
t_critical = stats.t.ppf(1 - (1 - confidence_level) / 2, degrees_of_freedom)
p_value = 2 * (1 - stats.t.cdf(abs(t_statistic), df=degrees_of_freedom))
print(f"T-statistic: {t_statistic}")
print(f"Critical T-value: {t_critical}")
print(f"P-value: {p_value}")
if abs(t_statistic) > t_critical:
    print("The result is significant at the 95% confidence level.")
else:
    print("The result is not significant at the 95% confidence level.")
```
## OUTPUT
![Screenshot 2024-10-08 223040](https://github.com/user-attachments/assets/39029402-bae3-48ce-9f1e-371c332ebe69)

## QUESTION - 2 
![Screenshot 2024-10-08 222855](https://github.com/user-attachments/assets/1dc7b768-bb07-4507-af9b-4c742a4c6326)

## PROGRAM
```
import scipy.stats as stats
import numpy as np

n = 900 
sample_mean = 3.4  # sample mean in cm
pop_mean = 3.25  # population mean in cm
pop_std = 2.61  # population standard deviation in cm
alpha = 0.05  # 5% level of significance
z_score = (sample_mean - pop_mean) / (pop_std / np.sqrt(n))
z_critical = stats.norm.ppf(1 - alpha / 2)
p_value = 2 * (1 - stats.norm.cdf(abs(z_score)))
print(f"Z-score: {z_score}")
print(f"Critical Z-value: {z_critical}")
print(f"P-value: {p_value}")
if abs(z_score) > z_critical:
    print("The result is significant at the 5% level of significance.")
else:
    print("The result is not significant at the 5% level of significance.")
```
## OUTPUT
![Screenshot 2024-10-08 223404](https://github.com/user-attachments/assets/76d5dc78-1721-4510-8a1b-ba97d489e859)

## QUESTION - 3
![Screenshot 2024-10-08 224008](https://github.com/user-attachments/assets/b034e4ae-9f3d-43fe-af73-7c4b1a144489)
## PROGRAM
```
import scipy.stats as stats
import numpy as np

mean1 = 200  # mean production of machine 1
mean2 = 250  # mean production of machine 2
std1 = 20  # standard deviation of machine 1
std2 = 25  # standard deviation of machine 2
n1 = 25  # sample size for machine 1
n2 = 25  # sample size for machine 2
alpha = 0.01  # 1% level of significance
z_score = (mean1 - mean2) / np.sqrt((std1**2 / n1) + (std2**2 / n2))
z_critical = stats.norm.ppf(1 - alpha / 2)
p_value = 2 * (1 - stats.norm.cdf(abs(z_score)))
print(f"Z-score: {z_score}")
print(f"Critical Z-value: {z_critical}")
print(f"P-value: {p_value}")

if abs(z_score) > z_critical:
    print("The result is significant at the 1% level of significance. The machines are not equally efficient.")
else:
    print("The result is not significant at the 1% level of significance. The machines can be considered equally efficient.")
```
## OUTPUT
![Screenshot 2024-10-08 224046](https://github.com/user-attachments/assets/db874a0f-9dc8-4e7c-97bd-0bbbc90207fa)

## QUESTION - 4
![Screenshot 2024-10-08 224236](https://github.com/user-attachments/assets/1e18cbc5-6a54-4bc0-85ea-521b00d5b4bc)

## PROGRAM
```
import scipy.stats as stats
import numpy as np

pop_mean = 6.48  # population mean
pop_std = 1.5  # population standard deviation
sample_mean = 6.75  # sample mean
n = 400  # sample size
alpha = 0.05  # 5% level of significance for a two-tailed test
z_score = (sample_mean - pop_mean) / (pop_std / np.sqrt(n))
z_critical = stats.norm.ppf(1 - alpha / 2)
p_value = 2 * (1 - stats.norm.cdf(abs(z_score)))
print(f"Z-score: {z_score}")
print(f"Critical Z-value: {z_critical}")
print(f"P-value: {p_value}")
if abs(z_score) > z_critical:
    print("The difference is statistically significant at the 5% level of significance.")
else:
    print("The difference is not statistically significant at the 5% level of significance.")
```
## OUTPUT
![Screenshot 2024-10-08 224432](https://github.com/user-attachments/assets/16b92ee9-4e25-42ac-be19-c356c9a761ab)

## QUESTION - 5
![Screenshot 2024-10-08 225146](https://github.com/user-attachments/assets/9049d675-18cc-4609-bff1-76c3bb6f4c78)
## PROGRAM
```
import scipy.stats as statS

n1 = 10  # sample size of the first sample
n2 = 12  # sample size of the second sample
ss1 = 120  # sum of squares for the first sample
ss2 = 314  # sum of squares for the second sample
alpha = 0.05  # 5% level of significance
var1 = ss1 / (n1 - 1)
var2 = ss2 / (n2 - 1)
if var1 > var2:
    f_statistic = var1 / var2
    df1, df2 = n1 - 1, n2 - 1  # degrees of freedom
else:
    f_statistic = var2 / var1
    df1, df2 = n2 - 1, n1 - 1  # degrees of freedom
f_critical = stats.f.ppf(1 - alpha / 2, df1, df2)
p_value = 2 * min(1 - stats.f.cdf(f_statistic, df1, df2), stats.f.cdf(f_statistic, df1, df2))
print(f"F-statistic: {f_statistic}")
print(f"Critical F-value: {f_critical}")
print(f"P-value: {p_value}")
if f_statistic > f_critical:
    print("The result is significant at the 5% level of significance.")
else:
    print("The result is not significant at the 5% level of significance.")

```
## OUTPUT
![Screenshot 2024-10-08 225108](https://github.com/user-attachments/assets/f4021e65-7133-49b0-bde8-30fc47e9de08)





















