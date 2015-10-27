## Условна вероятност
P(A|B)=P(AB)/P(B)

```R
  > smokes = c('y', 'n', 'n', 'y', 'n', 'y', 'y', 'y', 'n', 'y')
  > amount = c(1, 2, 2, 3, 3, 1, 2, 1, 3, 2)
  > prop.table(table(smokes, amount))
        amount
  smokes   1   2   3
       n 0.0 0.2 0.2
       y 0.3 0.2 0.1
  > prop.table(table(smokes, amount), 1)
        amount
  smokes         1         2         3
       n 0.0000000 0.5000000 0.5000000
       y 0.5000000 0.3333333 0.1666667
  > prop.table(table(smokes, amount), 2)
        amount
  smokes         1         2         3
       n 0.0000000 0.5000000 0.6666667
       y 1.0000000 0.5000000 0.3333333
```

```R
  > barplot(table(smokes, amount))
  > barplot(table(smokes, amount), beside=TRUE)
  > barplot(table(smokes, amount), beside=TRUE, legend.text = c('<5', '=5', '>5'))
  > barplot(table(smokes, amount), beside=TRUE, legend.text = c('no', 'yes'))
```

```R
  > barplot(table(amount, smokes), main='table for smokes', beside=TRUE, legend.text = c('<5', '=5', '>5'))
```

```R
  > nums = c(5, 5, 5, 13, 7, 11, 11, 9, 8, 9)
  > boxlot(nums)
  x = nums
  > y = c(11, 8, 4, 5, 9, 5, 10, 5, 4, 10)
  > boxplot(x, y)
  > nm = matrix(c(1:100), nrow = 20, ncol= 5)
  > nm
          [,1] [,2] [,3] [,4] [,5]
   [1,]    1   21   41   61   81
   [2,]    2   22   42   62   82
   [3,]    3   23   43   63   83
   [4,]    4   24   44   64   84
   [5,]    5   25   45   65   85
   [6,]    6   26   46   66   86
   [7,]    7   27   47   67   87
   [8,]    8   28   48   68   88
   [9,]    9   29   49   69   89
  [10,]   10   30   50   70   90
  [11,]   11   31   51   71   91
  [12,]   12   32   52   72   92
  [13,]   13   33   53   73   93
  [14,]   14   34   54   74   94
  [15,]   15   35   55   75   95
  [16,]   16   36   56   76   96
  [17,]   17   37   57   77   97
  [18,]   18   38   58   78   98
  [19,]   19   39   59   79   99
  [20,]   20   40   60   80  100

  > cc = matrix(c(1:10), nrow = 2, ncol= 12)
  > cc
       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12]
  [1,]    1    3    5    7    9    1    3    5    7     9     1     3
  [2,]    2    4    6    8   10    2    4    6    8    10     2     4
  
  > apply(nm, 1, mean)
  [1] 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60
  > apply(nm, 2, mean)
  [1] 10.5 30.5 50.5 70.5 90.5
  > apply(nm, 1, sum)
   [1] 205 210 215 220 225 230 235 240 245 250 255 260 265 270 275 280 285 290 295 300
  > apply(nm, 2, sum)
  [1]  210  610 1010 1410 1810
```

```R
  > amount = c(5, 5, 5, 13, 7, 11, 11, 9, 8, 9, 11, 8, 4, 5, 9, 5, 10, 5, 4, 10);
  > category=c(10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2);
  > boxplot(category, amount)
  > boxplot(amount, category)
  > boxplot(amount ~ category)
  > category[21]=3
  > amount[21]=15
```
amount ~ category - направи boxplot на amount по категории

## Библиотеки
```
  > install.packages('UsingR');
  > library(UsingR);
```

```R
  > home
      old    new
  1   64200 257500
  2   72100 276800
  3   87600 364600
  4   59000 160400
  5   83200 333500
  6   49100 145600
  7   79600 350200
  8   69300 205200
  9   93100 599300
  10 105400 514400
  11  74500 309700
  12 105900 437000
  13  82600 306400
  14  77800 354400
  15  77200 324800
  > data(home) // по този навин зареждаме този data set
  
  > home $old
   [1]  64200  72100  87600  59000  83200  49100  79600  69300  93100 105400  74500 105900  82600  77800  77200
  > names(home)
  [1] "old" "new"
  > old
  Error: object 'old' not found
  > attach(home) // закача ги за global scope
  > old
   [1]  64200  72100  87600  59000  83200  49100  79600  69300  93100 105400  74500 105900  82600  77800  77200
```
### Иползване:
  > data(..)
  > attach(..)
  > detach(..)
