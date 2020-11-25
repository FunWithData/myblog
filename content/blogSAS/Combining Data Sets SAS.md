---
title: "Combining Data Sets Vertically with SAS"
date: "2020-11-22T00:00:00Z"
---
Many times, when working on a project (small or big), we have to combine various data sets. SAS is one of the leading languages used for data manipulation and analysis. Combining data sets quickly and accurately with SAS is very useful.
The two main types of joins are vertical joins and horizontal joins.


__I.	Vertical Joins__


Let’s create three datasets in SAS and then experiment with vertical joins. <!--more-->
```SAS
data one;
input VarA $ 1-2 VarB $ 4-6 VarC $ 8-10;
datalines;
a1  b1  c1
a2  b2  c2
a3  b3  c3
;
run;

proc print data=one;
run;
```
### Here is the output from PROC PRINT


![dataset_one](/image/dataset_one.png "Is it working?")

### SAS code to create dataset two:

```SAS
data two;
input VarA $ 1-2 VarB $ 4-6 VarC $ 8-10;
datalines;
a2  b2  c2
a3  b3  c3
a4  b4  c4
;
run;

proc print data=two;
run;
```

### Output for dataset two:

![dataset_two](/image/dataset_two.png)

### SAS code to create dataset three:

```SAS
data three;
input VarA $ 1-2 VarB $ 4-6 VarD 8-10;
datalines;
a1  b1  21
a2  b2  13
a3  b3  15
;
run;

proc print data=three;
run;
```

### Output for dataset three:

![dataset_three](/image/dataset_three.png)

##	*__Concatenating__

In the process of concatenation, all of the observations in the first dataset listed in the SET statement are read first. Then, all of the observations in the second dataset listed in the SET statement are read (and then all of the observations in the third dataset and so on...) until all of the observations in all of the datasets are read. The new dataset contains all of the variables and observations from all of the input data sets.  

### Combining dataset one and dataset two

```SAS
data one_two;
set one two;
run;

proc print data=one_two;
run;
```

### Output table for dataset one_two:

![dataset_one_two](/image/dataset_one_two.png)

As you have noticed, there are repeating observations in the dataset (obs 2 is the same as obs 4, and obs 3 is the same as obs 5). If you don't need the repeating observations, you can use PROC SORT with NODUPRECS option to remove the repeats. 

```sas
proc sort data=one_two noduprecs;
by _all_;
run;

proc print data=one_two;
run;
```
And here is the table after the sort procedure:

![dataset_one_three](/image/ds_one_two_sorted_noduprecs.png)

### Combining dataset one and dataset three:

```SAS
data one_three;
set one three;
run;

proc print data=one_three;
run;
```

### Output table one_three:

![dataset_one_three](/image/dataset_one_three.png)

## Let's see if I can attach a pdf file

![a pdf file](/image/01 review-introduction.pdf)


Try to add content from [GitHub](https://github.com/FunWithData/notebooks/blob/master/Python%20Basics%20-%20Lab1.ipynb)
