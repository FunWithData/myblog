---
title: "Combining Data Sets Horizontally (I) with SAS Data Step"
date: "2021-01-16T00:00:00Z"
---

Two data sets can be combined horizontally by _interleaving_ or _match-merging_. Both methods use one or more common variables in the datasets that are to be connected. Interleaving uses the statements SET and BY, while the match-merge uses the statements MERGE and BY. 

To create the datasets for the illustration we can use the following SAS code: 
```SAS
data one;
input VarA $ 1-2 VarB $ 4-6 VarC $ 8-10;
datalines;
a1  b1  c1
a2  b2  c2
a3  b3  c3
;
run;

data two;
input VarA $ 1-2 VarB $ 4-6 VarD $ 8-10;
datalines;
a2  b2  c2
a3  b3  c2
a4  b4  c4
;
run;
```
![dataset_one](/image/dataset_one.png)           ![hor_two](/image/hor_two.png)

### I. Interleaving

When you combine datasets using the BY statement, the method intersperses the observations from the datasets (two or more) based on the common variables specified in the BY statement. SAS processes the observations sequentially by starting with the first row of the first dataset listed in the BY statement. It continues to read observations until it processes all of the observations from the datasets. The resulting dataset contains all the variables and observations from all datasets listed in the BY statement.

The following code will combine data set one and two using interleaving: 

```SAS
data hor_one_two;
set one two;
by VarA;
run;

proc print data=hor_one_two;
run;
```

This is the resulting table:

![hor_one_two](/image/hor_one_two.png)

### II. Match-Merging

The DATA step match-merge processes the data by sequentially checking each data set's observation to see if the BY values match. If the BY variable's observations in the data sets don't match, it writes the observation with the smallest value to the output data set. If the observations match, it writes the combined observation to the new data set. For this reason, the data sets have to be sorted (PROC SORT) by the BY variable(s). In the basic match-merge processing, the resulting dataset contains all variables and observations from the datasets listed in the SET statement.  

Let's see what will happen when we match-merge data sets one and two above. (Don't forget to sort the datasets!)

```SAS
proc sort data=one;
by VarA;
run;
proc sort data=two;
by VarA;
run;

data merged;
merge one two;
by VarA;
run;

proc print data=merged;
run;
```

Data set merged:

![merged](/image/merged_one_two.png)

Content from [wikipedia](https://en.wikipedia.org/wiki/Triangle)
