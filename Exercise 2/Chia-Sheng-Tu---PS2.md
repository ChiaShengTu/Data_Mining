## 2) Classification and retrospective sampling

**Question:**
![](Chia-Sheng-Tu---PS2_files/figure-markdown_strict/problem%202b%20test-1.png)

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
<td style="text-align: right;">-0.73</td>
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
<td style="text-align: right;">0.26</td>
</tr>
<tr class="odd">
<td style="text-align: left;">age</td>
<td style="text-align: right;">-0.02</td>
</tr>
<tr class="even">
<td style="text-align: left;">historypoor</td>
<td style="text-align: right;">-1.22</td>
</tr>
<tr class="odd">
<td style="text-align: left;">historyterrible</td>
<td style="text-align: right;">-2.07</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposeedu</td>
<td style="text-align: right;">0.48</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposegoods/repair</td>
<td style="text-align: right;">0.19</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposenewcar</td>
<td style="text-align: right;">0.88</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposeusedcar</td>
<td style="text-align: right;">-0.56</td>
</tr>
<tr class="even">
<td style="text-align: left;">foreigngerman</td>
<td style="text-align: right;">-1.14</td>
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
    ## -2.0433  -0.8094  -0.5690   1.0049   2.4600  
    ## 
    ## Coefficients:
    ##                       Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)         -7.341e-01  5.385e-01  -1.363  0.17287    
    ## duration             2.725e-02  9.049e-03   3.011  0.00260 ** 
    ## amount               1.142e-04  4.149e-05   2.752  0.00593 ** 
    ## installment          2.591e-01  8.681e-02   2.984  0.00284 ** 
    ## age                 -2.378e-02  8.269e-03  -2.876  0.00403 ** 
    ## historypoor         -1.222e+00  2.826e-01  -4.324 1.53e-05 ***
    ## historyterrible     -2.065e+00  3.218e-01  -6.417 1.39e-10 ***
    ## purposeedu           4.778e-01  4.358e-01   1.096  0.27289    
    ## purposegoods/repair  1.942e-01  2.931e-01   0.663  0.50755    
    ## purposenewcar        8.815e-01  3.138e-01   2.809  0.00497 ** 
    ## purposeusedcar      -5.577e-01  3.970e-01  -1.405  0.16013    
    ## foreigngerman       -1.138e+00  5.983e-01  -1.903  0.05707 .  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 984.07  on 799  degrees of freedom
    ## Residual deviance: 852.83  on 788  degrees of freedom
    ## AIC: 876.83
    ## 
    ## Number of Fisher Scoring iterations: 4

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
