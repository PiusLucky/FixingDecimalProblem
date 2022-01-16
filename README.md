# DecimalProblem
You are working with the python Decimal library. You noticed that the calculation below looks wrong. What could be the problem? ﻿ ﻿Decimal(49000000.0) - Decimal(2000) = Decimal(49000000.0)

## Taking them apart
```python
from decimal import *

a = Decimal(49000000.0) - Decimal(2000) //48998000 
b = Decimal(49000000.0) // 49000000
print(a, b) // 48998000, 49000000 


```



## Back to the problem
```python
from decimal import *

Decimal(49000000.0) - Decimal(2000) =  Decimal(49000000.0)

```

Equating a decimal this way is syntactically incorrect as shown below:
![Screenshot_5](https://user-images.githubusercontent.com/32282934/149671013-53098f2d-0062-4c35-baef-4552ea272e2d.png)




## Using Decimal.compare() method
The best way to compare decimals is by using the <b>".compare"</b> method 

```python
from decimal import *
deci = type(Decimal(49000000.0))
part1 = Decimal(49000000.0) - Decimal(2000)
part2 = Decimal(49000000.0) 
print(part1.compare(part2)) # -1

```


| Result             | Condition   |
| -------------------| ------------|
| 1  | if part1 > part2 |
| -1 | if part1 < part2 |
| 0 | if part1 = part2 |



## Why use decimal numbers?
Python implements decimal numbers as double precision floating point numbers which are machine dependent. For calculations where precision is critical for business reasons, floating points numbers may cause errors when run on a different machine. Therefore, For such applications, we need a machine independent data type to implement decimal numbers which has been implemented using the decimal module in python. Floating numbers cannot be represented using their exact value in python and only an approximation is used which can be dangerous for critical programs.

Due to approximations, floating point values yield different results for different calculations. For example, if we add 1.2 and 2.2 using floating point values the answer should be equal to 3.4. But when we compare the added number and 3.4, it will not be equal. 


```html
Result for float division of 4 by 3:
1.3333333333333333
Result for decimal division of 4 by 3:
1.333333333333333333333333333
```


## Reference
1. https://docs.python.org/3/library/decimal.html
2. https://www.pythonforbeginners.com/basics/decimal-module-in-python
