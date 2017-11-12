# Apriori-FP_Growth-Rules
# Mining a supermarket dataset with FP-Growth Rule

## Stage 1: Open supermarket.arff file
What is .arff file?
•	Arff (Attribute-Relation File Format) file is an ASCII text file that describes a list of instances sharing a set of attributes
•	ARFF files have two distinct sections. The first section is the Header information, which is followed the Data information.
 
An example header on the standard IRIS dataset looks like this:
[Here are instances of file on Weka]( https://github.com/TrinhDinhPhuc/Apriori-FP_Growth-Rules/blob/master/1.png)

## Stage 2: Get rid of Department instances which are not products 

![asd](https://github.com/TrinhDinhPhuc/Apriori-FP_Growth-Rules/blob/master/1.png)
Department_n are not the noise 
## Stage 3:  Choose FP-Growth in Associate tab
![asd](https://github.com/TrinhDinhPhuc/Apriori-FP_Growth-Rules/blob/master/2.png)

## Stage 4 : Click FP-Growth, there are many customizable options 
![asd](https://github.com/TrinhDinhPhuc/Apriori-FP_Growth-Rules/blob/master/3.png)
### Valid options are:

 -P <attribute index of positive value>
  Set the index of the attribute value to consider as 'positive'
  for binary attributes in normal dense instances. Index 2 is always
  used for sparse instances. (default = 2)
 -I <max items>
  The maximum number of items to include in large items sets (and rules). (default = -1, i.e. no limit.)
 -N <require number of rules>
  The required number of rules. (default = 10)
 -T <0=confidence | 1=lift | 2=leverage | 3=Conviction>
  The metric by which to rank rules. (default = confidence)
 -C <minimum metric score of a rule>
  The minimum metric score of a rule. (default = 0.9)
 -U <upper bound for minimum support>
  Upper bound for minimum support. (default = 1.0)
 -M <lower bound for minimum support>
  The lower bound for the minimum support. (default = 0.1)
 -D <delta for minimum support>
  The delta by which the minimum support is decreased in
  each iteration. (default = 0.05)
 -S Find all rules that meet the lower bound on
  minimum support and the minimum metric constraint.
  Turning this mode on will disable the iterative support reduction
  procedure to find the specified number of rules.
 -transactions <comma separated list of attribute names>
  Only consider transactions that contain these items (default = no restriction)
 -rules <comma separated list of attribute names>
  Only print rules that contain these items. (default = no restriction)
 -use-or
  Use OR instead of AND for must contain list(s). Use in conjunction
  with -transactions and/or –rules

### There are many valid options BUT we just concern 3 main FP-Growth’s options
-M <lower bound for minimum support>			I set up = 0.3
-C <minimum metric score of a rule>  		I set up = 0.6
S  <Find all rules that meet the lower bound on>   I set up = 30
(Check it out again in the picture illustration above)
 
 ## Stage 5: FP-Growth results 
![asd](https://github.com/TrinhDinhPhuc/Apriori-FP_Growth-Rules/blob/master/4.png)
 
### Have a look-see:

 1. [fruit=t, milk-cream=t]: 2038 ==> [bread and cake=t]: 1684   <conf:(0.83)> lift:(1.15) lev:(0.05) conv:(1.61) 
 2. [vegetables=t, milk-cream=t]: 2025 ==> [bread and cake=t]: 1658   <conf:(0.82)> lift:(1.14) lev:(0.04) conv:(1.54) 
 3. [fruit=t, vegetables=t]: 2207 ==> [bread and cake=t]: 1791   <conf:(0.81)> lift:(1.13) lev:(0.04) conv:(1.48) 
 4. [margarine=t]: 2288 ==> [bread and cake=t]: 1831   <conf:(0.8)> lift:(1.11) lev:(0.04) conv:(1.4) 
 5. [biscuits=t]: 2605 ==> [bread and cake=t]: 2083   <conf:(0.8)> lift:(1.11) lev:(0.04) conv:(1.4) 
 6. [milk-cream=t]: 2939 ==> [bread and cake=t]: 2337   <conf:(0.8)> lift:(1.1) lev:(0.05) conv:(1.37) 
 7. [tissues-paper prd=t]: 2247 ==> [bread and cake=t]: 1776   <conf:(0.79)> lift:(1.1) lev:(0.03) conv:(1.33) 
 8. [fruit=t]: 2962 ==> [bread and cake=t]: 2325   <conf:(0.78)> lift:(1.09) lev:(0.04) conv:(1.3) 
 9. [baking needs=t]: 2795 ==> [bread and cake=t]: 2191   <conf:(0.78)> lift:(1.09) lev:(0.04) conv:(1.29) 
10. [frozen foods=t]: 2717 ==> [bread and cake=t]: 2129   <conf:(0.78)> lift:(1.09) lev:(0.04) conv:(1.29) 
11. [bread and cake=t, vegetables=t]: 2298 ==> [fruit=t]: 1791   <conf:(0.78)> lift:(1.22) lev:(0.07) conv:(1.63) 
12. [sauces-gravy-pkle=t]: 2201 ==> [bread and cake=t]: 1710   <conf:(0.78)> lift:(1.08) lev:(0.03) conv:(1.25) 
13. [vegetables=t]: 2961 ==> [bread and cake=t]: 2298   <conf:(0.78)> lift:(1.08) lev:(0.04) conv:(1.25) 
14. [party snack foods=t]: 2330 ==> [bread and cake=t]: 1808   <conf:(0.78)> lift:(1.08) lev:(0.03) conv:(1.25) 
15. [bread and cake=t, fruit=t]: 2325 ==> [vegetables=t]: 1791   <conf:(0.77)> lift:(1.2) lev:(0.07) conv:(1.56) 
16. [juice-sat-cord-ms=t]: 2463 ==> [bread and cake=t]: 1869   <conf:(0.76)> lift:(1.05) lev:(0.02) conv:(1.16) 
17. [vegetables=t]: 2961 ==> [fruit=t]: 2207   <conf:(0.75)> lift:(1.16) lev:(0.07) conv:(1.41) 
18. [fruit=t]: 2962 ==> [vegetables=t]: 2207   <conf:(0.75)> lift:(1.16) lev:(0.07) conv:(1.41) 
19. [bread and cake=t, fruit=t]: 2325 ==> [milk-cream=t]: 1684   <conf:(0.72)> lift:(1.14) lev:(0.04) conv:(1.32) 
20. [bread and cake=t, vegetables=t]: 2298 ==> [milk-cream=t]: 1658   <conf:(0.72)> lift:(1.14) lev:(0.04) conv:(1.31) 
21. [bread and cake=t, milk-cream=t]: 2337 ==> [fruit=t]: 1684   <conf:(0.72)> lift:(1.13) lev:(0.04) conv:(1.29) 
22. [margarine=t]: 2288 ==> [baking needs=t]: 1645   <conf:(0.72)> lift:(1.19) lev:(0.06) conv:(1.41) 
23. [bread and cake=t, milk-cream=t]: 2337 ==> [vegetables=t]: 1658   <conf:(0.71)> lift:(1.11) lev:(0.04) conv:(1.24) 
24. [biscuits=t]: 2605 ==> [fruit=t]: 1837   <conf:(0.71)> lift:(1.1) lev:(0.04) conv:(1.22) 
25. [bread and cake=t]: 3330 ==> [milk-cream=t]: 2337   <conf:(0.7)> lift:(1.1) lev:(0.05) conv:(1.22) 
26. [bread and cake=t]: 3330 ==> [fruit=t]: 2325   <conf:(0.7)> lift:(1.09) lev:(0.04) conv:(1.19) 
27. [baking needs=t]: 2795 ==> [vegetables=t]: 1949   <conf:(0.7)> lift:(1.09) lev:(0.03) conv:(1.19) 
28. [biscuits=t]: 2605 ==> [frozen foods=t]: 1810   <conf:(0.69)> lift:(1.18) lev:(0.06) conv:(1.35) 
29. [milk-cream=t]: 2939 ==> [fruit=t]: 2038   <conf:(0.69)> lift:(1.08) lev:(0.03) conv:(1.17) 
30. [frozen foods=t]: 2717 ==> [vegetables=t]: 1882   <conf:(0.69)> lift:(1.08) lev:(0.03) conv:(1.17) 
Overview, 
•	There are 61 rules have found. 
•	Weka sort decending by Conf (Confidence).
