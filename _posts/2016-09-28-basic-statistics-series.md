---
layout: post
title: Learning stat
tags: statistics, R
---

Firs we begin be importing our dataset. We have to use an additional library to read an \*.xlsx file. After that we assign names to the columns. And we take a look at the first rows of the dataset to see what it looks like.

    data <- read.csv("./data/p1.csv")
    names(data) <- c("id","age","sex","profs")
    head(data)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="right" />

<col  class="right" />

<col  class="right" />

<col  class="right" />
</colgroup>
<tbody>
<tr>
<td class="right">1</td>
<td class="right">16</td>
<td class="right">1</td>
<td class="right">91</td>
</tr>


<tr>
<td class="right">2</td>
<td class="right">20</td>
<td class="right">2</td>
<td class="right">58</td>
</tr>


<tr>
<td class="right">3</td>
<td class="right">24</td>
<td class="right">1</td>
<td class="right">52</td>
</tr>


<tr>
<td class="right">4</td>
<td class="right">22</td>
<td class="right">2</td>
<td class="right">45</td>
</tr>


<tr>
<td class="right">5</td>
<td class="right">18</td>
<td class="right">1</td>
<td class="right">78</td>
</tr>


<tr>
<td class="right">6</td>
<td class="right">14</td>
<td class="right">2</td>
<td class="right">88</td>
</tr>
</tbody>
</table>

# Question 1

*Does the proficiency score increase or decrease with age?*

To answer this question we might simply plot both age and proficiency score and see if there is any clear indication.

    plot(data$age,data$profs)

![img](1.png)

Well, yes, from the scatter plot we built we can see that as the age increases the proficiency decreases.

# Question 2

*Is there a difference in proficiency score between female and male participants?*

    aggregate(data$profs, by=list(Category=data$sex), FUN=mean)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="right" />

<col  class="right" />
</colgroup>
<tbody>
<tr>
<td class="right">1</td>
<td class="right">75.5333333333333</td>
</tr>


<tr>
<td class="right">2</td>
<td class="right">63.6666666666667</td>
</tr>
</tbody>
</table>

# Question 3

*Is there an overall difference in age between male and female participants?*

    m <- data$age[data$sex == 1]
    f <- data$age[data$sex == 2]
    boxplot(m,f)

    aggregate(data$age, by=list(Category=data$sex), FUN=mean)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="right" />

<col  class="right" />
</colgroup>
<tbody>
<tr>
<td class="right">1</td>
<td class="right">20.1333333333333</td>
</tr>


<tr>
<td class="right">2</td>
<td class="right">20.5333333333333</td>
</tr>
</tbody>
</table>
