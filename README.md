# Lab7_202001148

## Section-A

Test Cases
| ID | Day | Month | Year| Expected Output |
|----|-----|-------|-----|-----------------|
|  1 | 1   |  5    |2000 | 30-04-2000      |
|  2 | 2   |  2    |2005 | 01-02-2005      |
|  3 | 29  |  2    |2001 | Invalid |
|  4| 1 | 3 | 2001 | 28-2-2001|
|  5| 1 | 3 | 2000 | 29-2-2001|
| 6| 31| 4|2012| Invalid|
| 7| 1| 1| 2000| 31-12-1999|
|8| 31|12|2015| 30-12-2015|
| 9| 30| 4|2016| Invalid|
|10| 1|1|1994|Invalid|


### Equivalence Class
Day:<br />
|ID| class | validity |
|--|-------|----------|
|El| date<1 |Invalid |
|E2 |1<=date<=28| Valid|
|E3 |date=31 |Valid |
|E4| date=29 |Valid |
|ES |date=30| Valid |
|E6| date > 31| Invalid |

Month: <br />

|ID| class | validity |
|--|-------|----------|
|E7| month<1 |Invalid |
|E8 |month = 1,3,5,7,8,10,12(months with 31 days) | Valid|
|E9 |month = 4,6,9,11(months with 30 days) |Valid |
|E10|month = 2(month with either 28 or 29 days) |Valid |
|E11 |month > 12| Invalid |

Year: <br/>
|ID| class | validity |
|--|-------|----------|
|E12| year<1900 |Invalid |
|E13 | leap year 1900<=year<=2015 | Valid|
|E14 |non leap year 1900<=year<=2015  |Valid |
|E15 |year > 2015 |Invalid |


## Program 1
**Equivalence partition for linear search**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [1, 2, 3, 4, 5],v = 1 | 0 |
| [1, 3, 5, 7, 9],v = 2 | -1 |
| [2, 4, 6, 8, 10],v = 11 | -1 |
| [-100, 100] | 0 |
| [1,2,3,4,5,6],v = 6 | 5 |
| [],v = 10 | -1 |
| NULL,v = 111 | -1 |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| NULL | -1 |
| [],v = 10 | -1 |
| [10],v = 10 | 0 |
| [5],v = 10 | -1 |
| [2,5],v = 2 | 0 |
| [3,4],v = 4 | 1 |
| [3,4],v = 20 | -1 |
| [1,2,3],v = 1 | 0 |
| [1,2,3],v = 3 | 2 |
| [1,2,3],v = 10 | -1 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 1| 0 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 111| 12 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 1111| -1 |

## Program 2
**Equivalence Class partitioning for counting occurance**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [10, 20, 30, 40, 50],v = 10 | 1 |
| [10, 20, 30, 40, 50,50],v = 50 | 2 |
| [[10, 20, 30, 40, 50,50]],v = 1 | 0 |
| [[10,10,10,10]],v = 11 | 0 |
| [],v = 10 | 0 |
| NULL,v = 50 | 0 |
| [0],v = 0 | 1 |
| [-89,-89],v = -89 | 2 |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [1, 2, 3, 4],v = 2 | 2 |
| [5, 10, 5, 5],v = 5 | 3 |
| [],v = 10 | 0 |
| NULL,v = 50 | 0 |
|[-100,100,100,100],v = 10000| 0 |
| [-89,89],v = -89 | 1 |
| [-890,890],v = 890 | 1 |

## Program 3
**Equivalent testcases for binary search:**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [1, 21, 30, 40, 50],v = 21 | 1 |
| [10, 20, 30, 40, 50, 60],v = 30 | 2 |
| [10,100,1000,10000],v = 100000 | -1 |
| [11,22,33,44],v = 444 | -1 |
| [11,20,200,300],v=11 | 0 |
| [-100,-90,-80,100,1000],v = 10000 | 4 |
| [],v = 12 | -1 |
| NULL,v = 168 | -1 |
| [1,2],v = 3 | -1 |
| [1,3],v=3 | 1 |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [1, 2, 3, 4, 5],v = 2 | 1 |
| [1, 2, 2, 351, 551],v = 2 | 2 |
| [1,22,33,44,55],v = 66 | -1 |
| [2, 4, 6, 8, 10],v = 51 | -1 |
| [-100, 0, 1000],v = -100 | 0 |
| [-100, 0, 1000],v = 1000 | 2 |
| [],v=0 | -1 |
| NULL,v = 4 | -1 |

## Program 4
**Equivalent class test cases of checking the type of triangle**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| a=2,b=2,c=2 | EQUILATERAL |
| a=1,b=1,c=1 | EQUILATERAL |
| a=0,b=0,c=0 | INVALID |
| a=-1,b=-1,c=-1 | INVALID |
| a=10,b=10,c=0 | INVALID |
| a=17,b=17,c=5 | ISOCELES |
| a=15,b=2,c=15 | ISOCELES |
| a=6,b=11,c=5 | SCALENE |
| a=16,b=21,c=25 | SCALENE |
| a=-1,b=21,c=25 | INVALID |
| a=2,b=3,c=4 | SCALENE |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| a=2,b=2,c=2 | EQUILATERAL |
| a=0,b=0,c=0 | INVALID |
| a=INT_MAX,b = INT_MAX,c = INT_MAX | EQUILATERAL |
| a=INT_MIN,b=INT_MIN,c=INT_MIN | INVALID |
| a=1,b=1,c=2 | ISOCELES |
| a=15,b=12,c=15 | ISOCELES |
| a = INT_MAX,b = 1,c = INT_MAX | ISOCELES |
| a=1,b=2,c=3 | SCALENE |
| a = INT_MAX,b = 1,c = INT_MAX - 1 | SCALENE |

## Program 5
**Equivalent test cases for prefix searching are as follows:**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| s1= "abcd",s2 = "abcd" | true |
| s1 = "",s2 = "" | true |
| s1 = "br",s2 = "brij" | true |
| s1 = "poo",s2 = "po" | false |
| s1 = "abc",s2 = "" | false |
| s1 = "",s2 = "abc" | true |
| s1 = "o",s2 = "ott" | true |
| s1 = "abc",s2 = "def" | false |
| s1 = "deg",s2 = "def" | false |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| s1= "abcd",s2 = "abcd" | true |
| s1= "",s2 = "" | true |
| s1= "abcd",s2 = "" | false |
| s1= "",s2 = "abcd" | true |
| s1 = "aef",s2 = "def" | false |
| s1 = "def",s2 = "deg" | false |
| s1 = "a",s2 = "att" | true |
| s1 = "brij",s2 = "raj" | false |

## Program 6
**(a) All equivalent classes**
| Class ID | Class |
|----------|-------|
| E1 | All sides are positive |
| E2 | two of its sides are zero |
| E3 | One of its sides are negative |
| E4 | Sum of two sides is less than third side |
| E5 | Any of the side/sides is negative |

**(b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.**
| Test Case ID | Class ID | Test Case |
|--------------|----------|-----------|
| T1 | E1 | A = 1,B = 1,C = 1 |
| T2 | E1 | A = 3, B = 4, C= 5 |
| T3 | E2 | A = 0,B = 0,C = 1 |
| T4 | E3 | A = 0,B = 1,C = 2 |
| T5 | E4 | A = 1, B = 3, C = 8 |
| T6 | E5 | A = -1,C = 1,D = 5 |

**(c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.** <br/>
A = 1, B = 3, C = 2
**(d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.** <br/>
A = 3,B = 2, C = 3
**(e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.**<br/>
A = 30,B = 30,C = 30
**(f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.** <br/>
A = 6,B = 8,C = 10
**(g)  For the non-triangle case, identify test cases to explore the boundary.**
A = 20, B = 10,C = 5
**(h) For non-positive input, identify test points.**
A = 0, B = 10, C = 0 <br/>
A = 0,B = 0,C = 0 <br/>
A = 0, B = -1, C = 10<br/>

# Section B
**(1) Control flow graph**

<img width="247" alt="image" src="https://user-images.githubusercontent.com/76478750/231722550-903d6b64-68bd-4e6b-9c9c-bb6040319841.png">
<img width="247" alt="image" src="https://user-images.githubusercontent.com/76478750/231722772-d9a9654d-adfd-4e47-aabb-964d69cd8843.png">



**(2) Test Cases **
**(a) Statement coverage test set: ** In this all the statements in code should be covered
<br/>
| Test Number | Test Case |
|-------------|-----------|
| 1 | p is empty array |
| 2 | p has one point object |
| 3 | p has two points object with different y component |
| 4 | p has two points object with different x component |
| 5 | p has three or more point object with different y component |

**(b) Branch Coverage test set: ** In this all branch are taken atleast once
<br/>

| Test Number | Test Case |
|-------------|-----------|
| 1 | p is empty array |
| 2 | p has one point object |
| 3 | p has two points object with different y component |
| 4 | p has two points object with different x component |
| 5 | p has three or more point object with different y component |
| 6 | p has three or more point object with same y component |
| 7 | p has three or more point object with all same x component |
| 8 | p has three or more point object with all different x component |
| 9 | p has three or more point object with some same and some different x component |

**(c) Basic condition coverage test set: **Each boolean expression has been evaluated to both true and false

| Test Number | Test Case |
|-------------|-----------|
| 1 | p is empty array |
| 2 | p has one point object |
| 3 | p has two points object with different y component |
| 4 | p has two points object with different x component |
| 5 | p has three or more point object with different y component |
| 6 | p has three or more point object with same y component |
| 7 | p has three or more point object with all same x component |
| 8 | p has three or more point object with all different x component |
| 9 | p has three or more point object with some same and some different x component |
| 10 | p has three or more point object with some same and some different y component |
| 11 | p has three or more point object with all different y component |
| 12 | p has three or more point object with all same y component |
