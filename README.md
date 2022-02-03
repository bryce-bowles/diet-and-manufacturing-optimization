# diet-and-manufacturing-optimization
Diet Problem and Manufacturing Problem: Decided how much of each of each dessert to consume per day so that taste index is maximized, and calories and grams of fat are minimized, subject to constraints (Algebraic Formulation). 


# Diet Problem Solution

February 21, 2020

## 1	Problem
For the following problems, provide the "Essential Components of an Optimization Solution" (objective in words, variable definition, algebraic formulation (using summation notation and with labels for the objective function and constraints), summary of results).  For your implementation, implement and solve the problem using Python/Pyomo and turn in your code (.py or .ipynb). 

(Albright and Winston, 13.30).  Maggie Stewart loves desserts, but due to weight and cholesterol concerns, she has decided that she must plan her desserts carefully. There are two possible desserts she is considering: snack bars and ice cream. After reading the nutrition labels on the snack bar and ice cream packages, she learns that each serving of a snack bar weighs 37 grams and contains 120 calories and 5 grams of fat. Each serving of ice cream weighs 65 grams and contains 160 calories and 10 grams of fat. Maggie will allow herself no more than 450 calories and 25 grams of fat in her daily desserts, but because she loves desserts so much, she requires at least 120 grams of dessert per day. Also, she assigns a “taste index” to each gram of each dessert, where 0 is the lowest and 100 is the highest. She assigns a taste index of 95 to ice cream and 85 to snack bars (because she prefers ice cream to snack bars).

## 2	Data
1. Let D={snack bars,ice cream} be the set of desserts, 
2. taste〗_i = taste index for dessert ⅈ, ⅈ∈D
3. 〖weight〗_i = weight of dessert ⅈ, ⅈ∈D
4. 〖calories〗_i = calories for dessert ⅈ, ⅈ∈D
5.〖fat〗_i = fat for dessert ⅈ, ⅈ∈D 
6.〖weightReq〗_ = minimum weight (grams) of dessert required
7.〖caloriesAllowed〗_i = maximum calories allowed per day
8.〖fatAllowed〗_i = maximum grams of fat required per day

## 3	Objective in Words
Decide how much of each of each dessert to consume per day so that taste index is maximized and calories and grams of fat are minimized, subject to the following constraints:
* Total calories do not exceed 450
* Total grams of fat do not exceed 25
* Each day requires 120 grams (weight) of desserts

## 4	Algebraic Formulation
#### Decision Variables:
Let x_i = the # servings of dessert ⅈ per day, for ⅈ∈D. 
#### Objectives and constraints: 
<img width="259" alt="image" src="https://user-images.githubusercontent.com/65502025/152342332-94ac6f11-6a4a-4ee0-b31a-8d41fbe2524b.png">

## 5	Implementation
See attached file, HW_Dessert.ipynb, for the implementation and solution
of the model using Pyomo and GLPK in Python.

## 6	Results and Interpretation
The optimal solution is for Maggie Stewart to eat 1.25 snack bars and 1.875 servings of ice cream each day to get the optimal objective function taste index of 15509.375.
 
# Manufacturing Problem Solution

February 21, 2020

## 1	Problem
For the following problems, provide the "Essential Components of an Optimization Solution" (objective in words, variable definition, algebraic formulation (using summation notation and with labels for the objective function and constraints), summary of results).  For your implementation, implement and solve the problem using Python/Pyomo and turn in your code (.py or .ipynb). 

(Albright and Winston, 13.33).  A manufacturing company makes two products.  Each product can be made on either of two machines.  The time (in hours) required to make each product on each machine is listed in the file P13_33.xlsx.  Each month, 500 hours of time are available on each machine.  Each month, customers are willing to buy up to the quantities of each product at the prices also given in the same file.  The company's goal is to maximize the revenue from selling units during the next two months.
## 2	Data: 
Times (hours) needed to product each product on each machine
<img width="225" alt="image" src="https://user-images.githubusercontent.com/65502025/152342603-71459d70-d136-4653-968a-b5c2f3888bb5.png">

Let
1. P = {Product 1, Product 2} be the set of products
2. M = {Machine 1, Machine 2} be the set of machine hours for machine j, j∈M
3. T = {Month 1, Month 2} be month k, k ∈T
4.〖price〗_ik = price ($ per month) for product i, i∈P; month k, k∈T
5.〖demand〗_ik = demand of product i, i∈P; month k, k∈T
6.〖time〗_ij = amount of time (hours) it takes to produce of product i, with machine j; ⅈ∈P, j∈M. 

## 3	Objective in Words: 
Decide how much of each product to produce on each machine, each month,
so that revenue is maximized and demand is met for the two months.
* 500 hours of time is available on each machine per month
* Demand is met for each month
* (At most 1000 units of product 1 are bought during month 1, At most 1900 units of product 1 are bought during month 2, At most 1400 units of product 2 are bought during month 1, At most 1300 units of product 2 are bought during month 2)

## 4	Algebraic Formulation
<img width="274" alt="image" src="https://user-images.githubusercontent.com/65502025/152342834-6ecd894e-a31a-4752-a454-f81151c09d8d.png">

## 5 Implementation
See attached file, Manufacturing.ipynb, for the implementation and solution of the model using Pyomo and GLPK.

## 6 Interpret the Results
The optimal solution is for Manufacturing Company to produce _________  of Product 1 and _____  of Product 2 and the optimal objective function value is $______.
