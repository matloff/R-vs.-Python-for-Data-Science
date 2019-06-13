# R vs. Python for Data Science

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/Rlogo.png width = "100" />

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/python-logo.png width = "300" />

### Norm Matloff, Prof. of Computer Science, UC Davis; [my bio](http://heather.cs.ucdavis.edu/matloff.html)


Hello!  This Web page is aimed at shedding some light on the perennial
R-vs.-Python debates in the Data Science community.  As a professional
computer scientist and statistician, I hope to shed some useful light on
the topic.  I have potential bias &mdash; I've written 4 R-related books,
and currently serve as Editor-in-Chief of the *R Journal* &mdash; but I hope
this analysis will be considered fair and helpful.

## Elegance

*Clear win for Python.* 

This is subjective, of course, but having
written (and taught) in many different programming languages, I really
appreciate Python's greatly reduced use of parentheses and braces:

``` python
if x > y: 
   z = 5
   w = 8
```

vs.

``` r
if (x > y)
{ 
   z = 5
   w = 8
}
```

Python is sleek!

## Learning curve

*Huge win for R*.  

To even get started in Data Science with Python, one must learn a lot of
material not in base Python, e.g., NumPy, Pandas and matplotlib.  

By contrast, matrix types and basic graphics are built-in
to base R.  The novice can be doing simple data analyses within minutes.
Python libraries can be tricky to configure, even for the systems-savvy,
while most R packages run right out of the box.

## Available libraries

*Call it a tie.*

[CRAN](https://cran.r-project.org/) has over 14,371 in addition to several other packages that are in [GitHub](https://github.com/).
packages. [PyPI](https://pypi.org/) has over 183,000,
but it seems thin on Data Science.

For example, I once needed code to do fast calculation of
nearest-neighbors of a given data point.  (NOT code using that to do
classification.) I was able to immediately find not one but two packages
to do this.  By contrast, just now I tried to find nearest-neighbor code
for Python and at least with my cursory search, came up empty-handed;
there was just one implementation that described itself as simple and
straightforward, nothing fast.

The following searches in PyPI turned up nothing: log-linear model;
Poisson regression; instrumental variables; spatial
data; familywise error rate; etc.

## Machine learning

*Slight edge to Python here*. 

The Pythonistas would point to a number of
very finely-tuned libraries, e.g. AlexNet, for image recognition.  Good,
but R versions easily could be developed. The Python libraries' power
comes from setting certain image-smoothing ops, which easily could be
implemented in R's [Keras](https://keras.rstudio.com/) wrapper, and for
that matter, a pure-R version of TensorFlow could be developed.
Meanwhile, I would claim that R's package availabity for random forests
and gradient boosting are outstandng.

## Statisical correctness

*Big win for R*.  

In my book, *the Art of R Programming*, I made the
statement, "R is written *by* statisticians, *for* statisticians," which
I'm pleased to see pop up here and there on occasion.  It's important!

To be blunt, I find the machine learning people, who
mostly advocate Python, often have a poor understanding of, and in
some cases even a disdain for, the statistical issues in ML.  I was
shocked recently, for instance, to see one of the most prominent ML
people, state in his otherwise outstanding book that standardizing the
data to mean-0, variance-1 means one is assuming the data are Gaussian
&mdash; absolutely false and misleading.

## Parallel computation

*Let's call it a tie.*  

Neither the base version of R nor Python have good support for multicore
computation.  Threads in Python are nice for I/O, but parallel
computation using them is impossible, due to the infamous Global
Interpreter Lock.  Python's multiprocessing package is not a good
workaround, nor is R's 'parallel' package.  External libraries
supporting cluster computation are OK in both languages.

Currently Python has better interfaces to GPUs.

## C/C++ interface

*Slight win for R.*

Though there are tools like swig etc. for interfacing Python to C/C++,
as far is I know there is nothing remotely as powerful as R's Rcpp for
this at present.  The Pybind11 package is being developed.

In addition, R's new ALTREP idea has great potential for enhancing
performance and usability.

On the other hand, the Cython and PyPy variants of Python can in some
cases obviate the need for explicit C/C++ interface in the first place.
## Object orientation, metaprogramming

*Slight win for R*.

For instance, though functions are objects in both languages, R takes
that more seriously than does Python.  Whenever I work in Python, I'm
annoyed by the fact that I cannot print a function to the terminal,
which I do a lot in R.

Python has just one OOP paradigm.  In R, you have your choice of
several, though some may debate that this is a good thing.

Given R's magic metaprogramming features (code that produces code),
computer scientists ought to be drooling over R.

## Language unity

*Horrible loss for R*.

Python is currently undergoing a transition from version 2.7 to 3.x.
This will cause some disruption, but nothing too elaborate.

By contrast, R is rapidly devolving into two mutually unintelligible
dialects, ordinary R and the Tidyverse.  Sadly, this is a conscious
effort by a commercial entity that has come to dominate the R world,
RStudio.  I know and admire the people at RStudio, but a commercial
entity should not have such undue influence on an open-source project.

It might be more acceptable if the Tidyverse were superior to ordinary
R, but in my opinion it is not.  It makes things more difficult for
beginners.  E.g. the Tidyverse has so many functions, some complex, that
must be learned to do what are very simple operations in base R.  Pipes,
apparently meant to help beginners learn R, actually make it more
difficult, I believe.  And the Tidyverse is of questionable value for
advanced users.  

## Linked data structures

*Likely win for Python.*

Classical computer science data structures, e.g. binary trees, are easy
to implement in Python.  While this can be done in R using its 'list'
class, I'd guess that it is slow.

## R/Python interoperability

RStudio is to be commended for developing the reticulate package, to
serve as a bridge between Python and R.  It's an outstanding effort, and
works well for pure computation.  But as far as I can tell, it does not
solve the knotty problems that arise in Python, e.g. virtual
environments and the like.

At present, I do not recommend writing mixed Python/R code.


## GraalVM

[**GraalVM**](https://www.graalvm.org/) implementation of R, also known as FastR, is compatible with GNU R, can run R code at unparalleled performance, integrates with the GraalVM ecosystem and provides additional R level features.
