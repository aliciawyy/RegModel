Is an automatic or manual transmission better for MPG ?
========================================================

In this study, we are paricularly interested in answering the two questions below

* Is an automatic or manual transmission better for miles/(US) gallon (MPG) ?
* Quantifying how different is the MPG between automatic and manual transmissions?

Our dataset `mtcars` contains **32** observations on  the following **11** variables.
* [, 1]  `mpg`	 Miles/(US) gallon
* [, 2]	 `cyl`	 Number of cylinders
* [, 3]	 `disp`	 Displacement (cu.in.)
* [, 4]	 `hp`	 Gross horsepower
* [, 5]	 `drat`	 Rear axle ratio
* [, 6]	 `wt`	 Weight (lb/1000)
* [, 7]	 `qsec`	 1/4 mile time
* [, 8]	 `vs`	 V/S
* [, 9]	 `am`	 Transmission (0 = automatic, 1 = manual)
* [,10]	 `gear`	 Number of forward gears
* [,11]	 `carb`	 Number of carburetors


```r
str(mtcars)
```

```
## 'data.frame':	32 obs. of  11 variables:
##  $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
##  $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
##  $ disp: num  160 160 108 258 360 ...
##  $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
##  $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
##  $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
##  $ qsec: num  16.5 17 18.6 19.4 17 ...
##  $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
##  $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
##  $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
##  $ carb: num  4 4 1 1 2 1 4 2 2 4 ...
```

Let's first do an unadjusted regression, for which we suppose that the `mpg` only depends linearly on the transmission of the car `am` is manual or automatic the coefficients will be

```r
summary(lm(mpg ~ am, data = mtcars))$coefficients
```

```
##             Estimate Std. Error t value  Pr(>|t|)
## (Intercept)   17.147      1.125  15.247 1.134e-15
## am             7.245      1.764   4.106 2.850e-04
```



