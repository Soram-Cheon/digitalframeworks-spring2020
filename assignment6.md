# Assignment 6
## I got the data from Bureau of Labor Statistics about consumer price index for urban consumers grocery to find price changes. I’d like to find five largest and smallest grocery price changes and here are my answers:

### Top 5	
Expenditure Category | Percent Change
Eggs | 16.1
Other port including roasts, steaks, and ribs|10.1
Pork chops|7.4
Fresh whole chicken|7.1
Chicken|5.8

## Documenting Steps


Documenting steps:


import pandas as pd
import pandas as pd
[28]:
df = pd.read_csv('/Users/SORAM/Downloads/groceryprices.csv')
[ ]:

[31]:
len(df)
[31]:
397
[32]:
df = pd.read_csv('/Users/SORAM/Downloads/groceryprices.csv')
df.head(10)
[32]:
	Expenditure Category	relative_importance	percent_change	adjusted_effect	standard error, median price change	date	PC
0	All items	100.000	-0.8	NaN	0.04	S-Dec. 2008	-0.8
1	Food	13.862	1.5	0.206	0.07	L-Jan. 1990	1.5
2	Food at home	7.652	2.6	0.197	0.12	L-Feb. 1974	2.8
3	Cereals and bakery products	0.989	2.9	0.028	0.30	L-EVER	-
4	Cereals and cereal products	0.304	1.6	0.005	0.54	L-Dec. 2010	1.7
5	Flour and prepared flour mixes	0.042	1.3	0.001	0.83	L-Feb. 2018	1.3
6	Breakfast cereal(4)	0.140	1.5	0.002	0.74	S-Feb. 2020	-0.8
7	Rice, pasta, cornmeal(4)	0.123	2.5	0.003	0.98	L-Jan. 2015	3.4
8	Rice(4)(5)(6)	NaN	3.6	NaN	1.14	L-Aug. 2008	3.8
9	Bakery products(4)	0.684	3.1	0.021	0.36	L-EVER	-
[33]:
df.shape
[33]:
(397, 7)
[34]:
df.dtypes
[34]:
Expenditure Category                    object
relative_importance                    float64
percent_change                         float64
adjusted_effect                        float64
standard error, median price change    float64
date                                    object
PC                                      object
dtype: object
[40]:
df.head()
[40]:
	Expenditure Category	relative_importance	percent_change	adjusted_effect	standard error, median price change	date	PC
0	All items	100.000	-0.8	NaN	0.04	S-Dec. 2008	-0.8
1	Food	13.862	1.5	0.206	0.07	L-Jan. 1990	1.5
2	Food at home	7.652	2.6	0.197	0.12	L-Feb. 1974	2.8
3	Cereals and bakery products	0.989	2.9	0.028	0.30	L-EVER	-
4	Cereals and cereal products	0.304	1.6	0.005	0.54	L-Dec. 2010	1.7
[41]:
df.shape
[41]:
(397, 7)
[42]:
df.dtypes
[42]:
Expenditure Category                    object
relative_importance                    float64
percent_change                         float64
adjusted_effect                        float64
standard error, median price change    float64
date                                    object
PC                                      object
dtype: object
[44]:
df.describe(include='all')
[44]:
	Expenditure Category	relative_importance	percent_change	adjusted_effect	standard error, median price change	date	PC
count	393	312.000000	381.000000	311.000000	382.000000	382	382
unique	393	NaN	NaN	NaN	NaN	96	117
top	Hospital services(16)	NaN	NaN	NaN	NaN	S-Feb. 2020	-
freq	1	NaN	NaN	NaN	NaN	38	79
mean	NaN	5.050006	-0.355381	-0.051444	0.575183	NaN	NaN
std	NaN	14.710650	4.007841	0.188628	0.481233	NaN	NaN
min	NaN	0.006000	-21.200000	-1.002000	0.000000	NaN	NaN
25%	NaN	0.137750	-0.800000	-0.004500	0.170000	NaN	NaN
50%	NaN	0.371500	0.100000	0.000000	0.485000	NaN	NaN
75%	NaN	1.830500	1.200000	0.003500	0.840000	NaN	NaN
max	NaN	100.000000	16.100000	0.209000	2.460000	NaN	NaN
[45]:
del df['relative_importance']
del df['adjusted_effect']
del df['standard error, median price change']
del df['date']
del df['PC']
[46]:
df.shape
[46]:
(397, 2)
[47]:
df.nlargest(5, ['percent_change'])
[47]:
	Expenditure Category	percent_change
52	Eggs	16.1
36	Other pork including roasts, steaks, and ribs(5)	10.1
35	Pork chops(4)	7.4
44	Fresh whole chicken(4)(6)	7.1
43	Chicken(4)(5)	5.8
[48]:
df.nsmallest(5, ['percent_change'])
[48]:
	Expenditure Category	percent_change
130	Gasoline, unleaded regular(6)	-21.2
129	Gasoline (all types)	-20.6
128	Motor fuel	-20.4
124	Energy commodities	-20.0
131	Gasoline, unleaded midgrade(10)(6)	-17.5
[49]:
df.nsmallest(10, ['percent_change'])
[49]:
	Expenditure Category	percent_change
130	Gasoline, unleaded regular(6)	-21.2
129	Gasoline (all types)	-20.6
128	Motor fuel	-20.4
124	Energy commodities	-20.0
131	Gasoline, unleaded midgrade(10)(6)	-17.5
289	Car and truck rental(5)	-16.6
132	Gasoline, unleaded premium(6)	-16.3
126	Fuel oil	-15.6
301	Airline fares	-15.2
169	Men's suits, sport coats, and outerwear	-11.3





## Egg and meat prices surge as gas prices decline

### As ‘Stay at Home’ order continues and as people are not allowed to move around the city unless it’s necessary, the biggest hit market from COVID-19 seems like the gasoline industry. So, Americans started cooking at home instead of going to restaurants. As a result, the food supply chain took the most advantage for Shelter in place order. 
### U.S. Bureau of Labor Statistics released the consumer price index for urban consumers. According to the data, the top five price changes are from the food supply chain, obviously – eggs, pork and chicken, and the bottom five price changes are from one category, gasoline. 
### The price for eggs in April went up 16% compared to March, the largest change in April compared to March 2020 and also the largest percent change since June 2015. 
### The largest decline goes to gasoline (all types), which its price for April went down 20% compared to March, and it is the largest decline since November 2008. 

