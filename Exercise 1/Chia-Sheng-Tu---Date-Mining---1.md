## 1) Data visualization: flights at ABIA

\*\*\*\*Question: What is the best Month to fly in and fly out to Austin
to minimize delays?\*\*

    ## # A tibble: 7 x 2
    ##   Month avg_Delay
    ##   <dbl>     <dbl>
    ## 1     1     0.038
    ## 2     2     0.053
    ## 3     3     0.073
    ## 4     4     0.043
    ## 5     5     0.049
    ## 6     6     0.064
    ## 7     7     0.041

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%201-1.png)

**Figure 1:** \#Plot for average delay time per mile bt month

Figure 1 refers to the best months to fly in and fly out to Austin to
minimize delays are September and November. September has the lowest
delay time per mile (0.009). On the Other hand, December would be the
worst time to fly, since the average delay time per mile is the highst
among 12 months (0.077). The results seems reasonible. The demnd of
flights in September might decreas, as September is the second month of
the semester for most students. However, many people, not only students,
are flying in/out to Austin due to Christmas and new year hoildays, the
demand of flights increased.

## 2) Wrangling the Olympics

#### A) What is 95th percentile of heights for female competitiors across Athletics events?

<table>
<thead>
<tr class="header">
<th style="text-align: left;"></th>
<th style="text-align: left;">quantile</th>
<th style="text-align: right;">height</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">output</td>
<td style="text-align: left;">95%</td>
<td style="text-align: right;">183</td>
</tr>
</tbody>
</table>

95th percentile of heights for female competitors across Athletcis
events is 183cm.

#### B) Which single women’s event had the greatest variability in competitor’s heights across the entire history of the Olympics, as measured by the standard deviation?

    ## # A tibble: 6 x 2
    ##   event                                 sd_height
    ##   <chr>                                     <dbl>
    ## 1 Rowing Women's Coxed Fours                10.9 
    ## 2 Basketball Women's Basketball              9.70
    ## 3 Rowing Women's Coxed Quadruple Sculls      9.25
    ## 4 Rowing Women's Coxed Eights                8.74
    ## 5 Swimming Women's 100 metres Butterfly      8.13
    ## 6 Volleyball Women's Volleyball              8.10

Event Rowing Woman’s Coxed Fours has the highest standard deviation with
10.9

#### C) How has the average age of Olympic swimmers changed over time? Does this trend look different depending on the gender?

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%202C-1.png)![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%202C-2.png)

**Figure 3&4:** Line graph showing the change in average age of Olympic
swimmers between 1600 - 2016 How has the average age of Olympic swimmers
changed over time? Compared to early 1900’s, the average age of Olympic
swimmers has became bigger in 2000’s. The average age in the early
1900’s has the lowest value, and kept increasing until around 1920.
After 1920, the the average age of Olympic swimmers stared to decreased
until 1975.

Does the trend look different for male swimmers relative to female
swimmers? Average age of female swimmers is lower than that of male
swimmers throughout history. Also, number of male swimmer was higher
than female swimmers from 1900 to 1925, since the pattern in Figure 3 in
primary is affected by male swimmers, as Figure 4 has showed.

## 3) K-nearest neighbors: cars

### Car trim level 350

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%203_1.1-1.png)
**Figure 5:** Plot showing RMSE for each value of K (from 2 to 150)

Here, we can see which K value has the lowest RMSE, and this is the
optimal value of K

**Optimal value of K**

    ## [1] 53

**RMSE from the Optimal value of K**

    ## [1] 8481.191

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%203_1.4-1.png)

**Figure 2:** Plot of the fitted model, predicted price and real price

### Car trim level 65 AMG

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%203_2.1-1.png)

**Figure 7:** Plot showing RMSE for each value of K (from 2 to 150)

Here, we can see which K value has the lowest RMSE, and this is the
optimal value of K

**Optimal value of K**

    ## [1] 5

**RMSE from the Optimal value of K**

    ## [1] 17185.43

![](Chia-Sheng-Tu---Date-Mining---1_files/figure-markdown_strict/problem%203_2.4-1.png)

**Figure 8:** Plot of the fitted model, predicted price and real price

**Result: Trim 350 yields a larger optimal value of K**

<table>
<thead>
<tr class="header">
<th style="text-align: left;"></th>
<th style="text-align: right;">Trim 350</th>
<th style="text-align: right;">Trim 65 AMG</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">Number of rows</td>
<td style="text-align: right;">416</td>
<td style="text-align: right;">292</td>
</tr>
</tbody>
</table>

Trim 350 has larger optimal K value as it contains more data points than
trim 65 AMG. More data points means lower variance, less chance of
memorizing random noise.
