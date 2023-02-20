## 2) Classification and retrospective sampling

**Question:**
![](Chia-Sheng-Tu---PS2_files/figure-markdown_strict/problem%202_bar_chart-1.png)

According to the bar chart above, borrowers whose credit ratings
classified as “good” have the highest possibility (60%) to default on
the loan. On the other hand, borrowers with “poor” and “terrible” credit
ratings, however, have lower default probability than borrowers with
“good”.

<table>
<thead>
<tr class="header">
<th style="text-align: left;"></th>
<th style="text-align: right;">x</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">(Intercept)</td>
<td style="text-align: right;">-0.87</td>
</tr>
<tr class="even">
<td style="text-align: left;">duration</td>
<td style="text-align: right;">0.03</td>
</tr>
<tr class="odd">
<td style="text-align: left;">amount</td>
<td style="text-align: right;">0.00</td>
</tr>
<tr class="even">
<td style="text-align: left;">installment</td>
<td style="text-align: right;">0.30</td>
</tr>
<tr class="odd">
<td style="text-align: left;">age</td>
<td style="text-align: right;">-0.02</td>
</tr>
<tr class="even">
<td style="text-align: left;">historypoor</td>
<td style="text-align: right;">-1.27</td>
</tr>
<tr class="odd">
<td style="text-align: left;">historyterrible</td>
<td style="text-align: right;">-1.99</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposeedu</td>
<td style="text-align: right;">0.84</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposegoods/repair</td>
<td style="text-align: right;">0.28</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposenewcar</td>
<td style="text-align: right;">0.89</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposeusedcar</td>
<td style="text-align: right;">-0.72</td>
</tr>
<tr class="even">
<td style="text-align: left;">foreigngerman</td>
<td style="text-align: right;">-1.33</td>
</tr>
</tbody>
</table>

    ## 
    ## Call:
    ## glm(formula = Default ~ duration + amount + installment + age + 
    ##     history + purpose + foreign, family = binomial, data = credit_train)
    ## 
    ## Deviance Residuals: 
    ##     Min       1Q   Median       3Q      Max  
    ## -2.0237  -0.8188  -0.5610   0.9892   2.5521  
    ## 
    ## Coefficients:
    ##                       Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)         -8.682e-01  5.281e-01  -1.644 0.100130    
    ## duration             3.273e-02  9.169e-03   3.570 0.000357 ***
    ## amount               8.907e-05  4.217e-05   2.112 0.034662 *  
    ## installment          2.975e-01  8.545e-02   3.481 0.000499 ***
    ## age                 -2.412e-02  8.101e-03  -2.977 0.002907 ** 
    ## historypoor         -1.271e+00  2.870e-01  -4.428 9.52e-06 ***
    ## historyterrible     -1.990e+00  3.213e-01  -6.195 5.82e-10 ***
    ## purposeedu           8.390e-01  4.193e-01   2.001 0.045416 *  
    ## purposegoods/repair  2.782e-01  2.909e-01   0.956 0.338889    
    ## purposenewcar        8.881e-01  3.132e-01   2.835 0.004579 ** 
    ## purposeusedcar      -7.203e-01  4.089e-01  -1.761 0.078158 .  
    ## foreigngerman       -1.334e+00  6.773e-01  -1.970 0.048838 *  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 984.07  on 799  degrees of freedom
    ## Residual deviance: 850.69  on 788  degrees of freedom
    ## AIC: 874.69
    ## 
    ## Number of Fisher Scoring iterations: 5

The bank could not predict the outcome accurately based on class of
credit history. Based on information above, the coefficient of “poor”
and “terrible” credit history are negative, saying that people with bad
credit history have lower chance to default on the loan.

For this reason, it may not be appropriate to use this data set alone
for building a predictive model of “Default” to screen prospective
borrowers into “high” versus “low” probability of default. The data is
full of defaulted loans, creating biased estimator or even selection
bias. The bank should use random sampling data than this “case-control”
designed data.
