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

## Problem 3: Children and hotel reservations

**Model Building** First of all, we add some variables to the dataset
for constructing our best model, then we split the data into training
and testing datasets. Moreover, we build baseline model 1, baseline
model 2, and our best model. We try different ways to construct a better
model instead of including all variables. We add year and month
variables for time-fixed effects. In addition, we add the quadratic
terms for average\_daily\_rate, lead\_time, stays\_in\_week\_nights, and
stays\_in\_weekend\_nights. This makes the effect of these variables
some flexibility. Lastly, we exclude some variables that seem irrelevant
to the number of children, which are adults, is\_repeated\_guest,
previous\_bookings\_not\_canceled, previous\_cancellations,
deposit\_type, and days\_in\_waiting\_list. After constructing our best
model, we generate the confusion matrixes to compare the out-of-sample
performance of these models. Below are the accuracies of the models,
baseline 1, baseline 2, and the best model respectively. We could find
that the accuracies of baseline 2 and the best model are quite close. It
could mean that in this case maybe adding all variables into the
regression is good enough to have a prediction. Both of them are better
than baseline 1 apparently.

    ## [1] 91.42

    ## [1] 92.56

    ## [1] 92.74

**Model Validation: Step 1** In this section, we validate our best model
by testing on the hotels\_val data and draw the graph of the ROC curve
of this prediction using the threshold of 0.01 to 0.9.

Below is our ROC curve for the best model. By observing the shape of the
ROC, since the area below the line is larger than 0.5, we can say this
model can predict the result at a certain level.

![](Chia-Sheng-Tu---PS2_files/figure-markdown_strict/problem%203_model1-1.png)

**Model Validation: Step 2** In Step 2, we do 20 folds cross-validation
using the hotels\_val data, and we use a sample to create random fold
numbers 1 to 20 onto each data entry. For each fold, we store the sum of
predicted bookings with children and the actual bookings with children
to see how well is this model performing.

Below is the line graph that shows the sum of predicted bookings with
children and the actual bookings with children. The predicted values are
not always close to the actual values, especially in the extreme value.
However, it can still have a precise prediction in some folds.
![](Chia-Sheng-Tu---PS2_files/figure-markdown_strict/problem%203_model2-1.png)
