[![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/steepness)](http://cran.r-project.org/web/packages/steepness)
[![Downloads](http://cranlogs.r-pkg.org/badges/steepness)](http://cran.rstudio.com/package=steepness)

Overview
========
steepness package allows users to quantify and test steepness of dominance hierarchies with R.

What's new in version 0.3-0
---------------------------
**5th May 2022**

* Solved code problems when checking sociomatrices in main functions.
* Updated way of using UseDynLib in NAMESPACE.

Installation instructions
=========================
You can install the latest development version of steepness using devtools:

```R
install.packages("devtools", dep = TRUE)
library(devtools)
install_github("DLEIVA/steepness")

library(steepness)
```


The latest release of steepness is available on [CRAN](http://cran.r-project.org/web/packages/steepness/):

```R
install.packages("steepness", dep = TRUE)

library(steepness)
```

Usage
=====

Running steepness test by means of a randomization procedure, summarizing and ploting results. Example taken from Vervaecke et al. (2007):

```R
X <- matrix(c(0,58,50,61,32,37,29,39,25,8,0,22,22,9,27,20,10,48,
              3,3,0,19,29,12,13,19,8,5,8,9,0,33,38,35,32,57,
              4,7,9,1,0,28,26,16,23,4,3,0,0,6,0,7,6,12,
              2,0,4,1,4,4,0,5,3,0,2,1,1,5,8,3,0,10,3,1,3,0,0,4,1,2,0),
              nrow=9,byrow=TRUE)

individuals <- c("V","VS","B","FJ","PR","VB","TOR","MU","ZV")

 STP <- steeptest(X, rep=9999, names=individuals, method="Dij", order=TRUE)
 summary(STP)
 plot(STP)
```


Issues/Contibutions
===================
Happy to hear about issues you encounter using steepness via Github's [issue tracker](https://github.com/DLEIVA/steepness/issues/new).

If you would like to submit a patch to improve steepness, please send a pull request to the *develop branch*.

Change log
===================

-------------
VERSION 0.3-0
-------------
* Solved code problems when checking sociomatrices in main functions.
* Updated way of using UseDynLib in NAMESPACE.

-------------
VERSION 0.2-2
-------------
* New methods for printing and summarizing steepness test and for plotting steepness in linear hierarchies.
* Solved memory-access errors in steep.c code.

-------------
VERSION 0.2-1
-------------
*Some improvements in steep.c file for compatibility with R>=2.15.3.
*.First.Lib replaced by .onLoad function.

-----------
VERSION 0.2
-----------

* A new function, getOrderedMatrix, for ordering the empirical matrix according individuals' NormDS values is included in this new version.
* getinterc is eliminated in this version.
* Methods for quantifying and testing steepness from matrices of win proportions are implemented.
* getw1, getw2, getl1 and getl2 functions in previous version are gathered now in a unique function called getwl.
* "for" loops eliminated in all the functions of steepness package.
* All functions are now constrained to be used for square and numerical matrices.
* cross-calling to steepness functions is avoided in the new version.
* A more efficient way of computing steepness measure, via lm function, is now implemented in getStp, getplot and steeptest functions. 
* Some modifications of the C routine included in the package.
* Improvements in Rd files. New examples for illustrative purposes.

-----------
VERSION 0.1
-----------

First public version in CRAN
