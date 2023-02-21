## Problem 1: Saratoga House Prices

The linear model which outperformed the medium linear model is: price =
lotSize + age + landValue + livingArea + bedrooms + bathrooms + rooms +
heating + waterfront + newConstruction + centralAir (by using Stepwise
regression)

By using a cross validated RMSE, we found that the linear medium model
had a RMSE of 68077.25 and our chosen linear model had a RMSE of
63437.27. The KNN model had a RMSE of 66280.28 which was selected by
using repeated cross validation and then refitted to the testing set.
Our chosen linear model is the best at predicting market values for
properties in Saratoga (do better at achieving lower out-of-sample
mean-squared error). For a taxing authority, it is clear that there are
some important factors in determining property value compared to the
medium model, including Land Value, Waterfront Property and whether a
house is a new construction.

## Problem 2: Classification and retrospective sampling

![](Chia-Sheng-Tu---PS2_files/figure-markdown_strict/problem%202_bar_chart-1.png)

According to the bar chart above, borrowers whose credit ratings
classified as “good” have the highest possibility (60%) to default on
the loan. On the other hand, borrowers with “poor” and “terrible” credit
ratings, however, have lower default probability than borrowers with
“good” credit ratings.

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
<td style="text-align: right;">-0.75</td>
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
<td style="text-align: right;">0.25</td>
</tr>
<tr class="odd">
<td style="text-align: left;">age</td>
<td style="text-align: right;">-0.03</td>
</tr>
<tr class="even">
<td style="text-align: left;">historypoor</td>
<td style="text-align: right;">-0.88</td>
</tr>
<tr class="odd">
<td style="text-align: left;">historyterrible</td>
<td style="text-align: right;">-1.75</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposeedu</td>
<td style="text-align: right;">0.74</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposegoods/repair</td>
<td style="text-align: right;">-0.15</td>
</tr>
<tr class="even">
<td style="text-align: left;">purposenewcar</td>
<td style="text-align: right;">0.66</td>
</tr>
<tr class="odd">
<td style="text-align: left;">purposeusedcar</td>
<td style="text-align: right;">-1.07</td>
</tr>
<tr class="even">
<td style="text-align: left;">foreigngerman</td>
<td style="text-align: right;">-1.08</td>
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
    ## -2.2675  -0.7934  -0.5336   0.9909   2.4737  
    ## 
    ## Coefficients:
    ##                       Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)         -7.490e-01  5.531e-01  -1.354  0.17573    
    ## duration             3.018e-02  9.438e-03   3.198  0.00138 ** 
    ## amount               8.702e-05  4.280e-05   2.033  0.04203 *  
    ## installment          2.547e-01  8.864e-02   2.874  0.00405 ** 
    ## age                 -2.640e-02  8.570e-03  -3.081  0.00206 ** 
    ## historypoor         -8.806e-01  2.806e-01  -3.138  0.00170 ** 
    ## historyterrible     -1.752e+00  3.225e-01  -5.433 5.54e-08 ***
    ## purposeedu           7.427e-01  4.198e-01   1.769  0.07686 .  
    ## purposegoods/repair -1.479e-01  2.898e-01  -0.510  0.60976    
    ## purposenewcar        6.640e-01  3.140e-01   2.115  0.03446 *  
    ## purposeusedcar      -1.073e+00  4.227e-01  -2.538  0.01115 *  
    ## foreigngerman       -1.078e+00  5.854e-01  -1.842  0.06547 .  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 956.18  on 799  degrees of freedom
    ## Residual deviance: 824.76  on 788  degrees of freedom
    ## AIC: 848.76
    ## 
    ## Number of Fisher Scoring iterations: 5

The bank could not predict the outcome accurately based on class of
credit history. Based on information above, the coefficients of “poor”
and “terrible” credit history are both negative, saying that borrowers
with bad credit history have lower chance to default on the loan.

For this reason, it may not be appropriate to use this data set alone
for building a predictive model of “Default” to screen prospective
borrowers into “high” versus “low” probability of default. The data is
full of defaulted loans, creating biased estimator or even selection
bias. The bank should use random sampling data than this “case-control”
designed data.
