---
title: "Combining Data Sets with SAS"
date: "2020-11-22T00:00:00Z"
---
Many times, when working on a project (small or big), we have to combine various data sets. SAS is one of the leading languages used for data manipulation and analysis. Combining data sets quickly and accurately with SAS is very useful.
The two main types of joins are vertical joins and horizontal joins.
I.	Vertical Joins
Let’s create three datasets in SAS and then experiment with vertical joins.
```javascript
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
---
Obs |	VarA |	VarB |VarC
---
1	a1 |	b1 |	c1
2	a2 |	b2 |	c2
3	a3 |	b3 |	c3
