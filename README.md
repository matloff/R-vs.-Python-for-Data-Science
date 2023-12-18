# R vs. Python for Data Science

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/Rlogo.png width = "100" />

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/python-logo.png width = "300" />

## Norm Matloff, Prof. of Computer Science, UC Davis; [my bio](http://heather.cs.ucdavis.edu/matloff.html)


Hello!  This Web page is aimed at shedding some light on the perennial
R-vs.-Python debates in the Data Science community.  This is largely
(though not exclusively) a debate between the Statistics (R) and
Computer Science (Python) fields. Since I have a foot in both camps
(I was a founding member of both the Statistics and Computer Science
Departments at UC Davis), I hope to shed some useful light on the topic.  

I have potential bias:  I've written four R-related books; I've given
keynote talks at useR! and other R conferences; I have served as
Editor-in-Chief of the *R Journal*; etc. But I am also an enthusiastic
Python coder, have been for many years, and am the author of a [popular
Python
tutorial](https://www.cs.ucdavis.edu/~matloff/matloff/public_html/Python/PythonIntro.html).
I hope this analysis will be considered fair and helpful.

Again, **please note:**  The emphasis here is on Data Science, not
*Computer* Science.  

## Learning curve

*Huge win for R.*  

This is of particular interest to me, as an educator.  I've taught a
number of subjects -- math, stat, CS and even English As a Second
Language -- and have given intense thought to the learning process for
many, many years.

To even get started in Data Science with Python, one must learn a lot of
material not in base Python, e.g., NumPy, Pandas and matplotlib. These
libraries require a fair amount of computer systems sophistication.

Python libraries can be tricky to configure, even for the systems-savvy,
while most R packages run right out of the box.

## Data Science emphasis

**Huge win for R.**

In my book, *The Art of R Programmming*, I wrote "R is written *by*
statisticians, *for* statisticians," a line I've been pleased to see
quoted by others. One could update that to read "R is written *by*
data scientists, *for* data scientists," and it is of crucial importance
in our discussion here.

Matrix types, data frames, missing-value handling, basic graphics,
data-and-time processing, linear models, basic statistics, contingency
tables and so on are built-in to base R.  The novice can be doing simple
data analyses with these tools within minutes.

Generally an R data science function will be richer in coverage than its
Python counterpart.  For instance, R's histogram plot function,
**hist()**, offers many advanced options, not the case for Python.

All this is the result of the fact that, indeed, "R is written *by* data
scientists, *for* data scientists." 

## Available libraries for Data Science

*Slight edge to R.*

[CRAN](https://cran.r-project.org/) has over 14,000 packages.
[PyPI](https://pypi.org/) has over 183,000 (both numbers are growing),
but it seems thin on Data Science.  

For example, I once needed code to do fast calculation of
nearest-neighbors of a given data point.  (NOT code using that to do
classification.) I was able to immediately find not one but two packages
in CRAN to do this.  By contrast, recently I tried to find
nearest-neighbor code for Python and at least with my cursory search in
PyPi, came up empty-handed; there was just one implementation that
described itself as simple and straightforward, nothing fast.

The following (again, cursory) searches in PyPI turned up nothing: EM
algorithm; log-linear model; Poisson regression; instrumental variables;
spatial data; familywise error rate; etc.

This is not to say no Python libraries exist for these things; I am
simply saying that they are not easily found in PyPI, whereas it is easy
to find them in CRAN, and indeed, such libraries are more likely to be
in CRAN but not PyPI.  Once again, this reflects the difference in
orientation, Data Science for R versus Computer Science for Python.

And the fact that R has a canonical package structure is a big
advantage.  When installing a new package, one knows exactly what to
expect.  Similarly, R's *generic functions* are an enormous plus for R.
When I'm using a new package, I know that I can probably use
**print()**, **plot()**, **summary()**, and so on, while I am exploring,
without checking the documentation.  These form a "universal language"
for packages.

## Visualization tools

*Win for R*

Unlike Python, base R itself has sophisticated graphics utilities built
in, and there are two outstanding graphics packages available,
**ggplot2** and **lattice**.  The former is so widely used that many
probably perceive it as being part of base R.

But it goes far beyond that.  As noted, a major built-in function in R
is **plot()**.  It is *polymorphic*, meaning that its role is different
for each use case it has been written for.  This is a fancy term whose
practical meaning is that the objects returned by R functions are
typically paired with a visualization, which we can invoke simply by
calling the generic **plot()**.

## Machine learning

*Slight (or more) edge to Python*. 

As noted, the R-vs.-Python debate is largely a Statistics-vs.-CS debate,
and since most research in neural networks has come from CS, available
software for NNs is mostly in Python.  To many in CS, machine learning
means neural networks (NNs). 

RStudio/Posit has done some excellent work in developing a Keras
implementation, and there are R interfaces to PyTorch and so on, but so
far R is limited in this realm.  Again, if one's view is that
Data Science = NNs, then Python is the language of choice.

On the other hand, random forest research originated in the
Statistics community, and most research in this field has been conducted
there.  In this realm I'd submit that R has the superior software.  The
**grf** package, for instance, allows linear interpolation within tree
leaves, crucial for removing bias near the edges of the data.  R also
has excellent packages for gradient boosting, another field originally
invented in Statistics.

## Statistical sophistication

*Big win for R*.  

As noted, I use the slogan, "R is written *by* statisticians, *for*
statisticians." It's important!

To be frank, I find the machine learning people, who mostly advocate
Python, often have a poor understanding of, and in some cases even a
disdain for, the statistical issues in ML.  And, sadly, I often see
ignorance.  I was shocked recently, for instance, to see one of the most
prominent ML people state in his otherwise superb book that
standardizing the data to mean-0, variance-1 means one is assuming the
data are Gaussian &mdash; absolutely false and misleading.

## Parallel computation

*Let's call it a tie.*  

Neither the base version of R nor Python have good support for multicore
computation.  Threads in Python are nice for I/O, but multicore
computation using them is difficult, due to the infamous Global
Interpreter Lock.  Python's **multiprocessing** package is much better
than before, but still clunky.  R's **parallel** package does allows
shared memory for Macs or Linux, but not on Windows platforms.  

(See my **Rdsm** package if you wish to use shared memory
at the R level.) 

External libraries supporting cluster computation are OK in both languages.

Currently Python has better interfaces to GPUs, but again, only for NNs.

## C/C++ interface and performance enhancement

*Slight win for R.*

Though there are tools like SWIG etc. for interfacing Python to C/C++,
as far is I know there is nothing remotely as powerful as R's **Rcpp** for
this at present.  The **Pybind11** package is being developed.

In addition, R's new ALTREP idea has great potential for enhancing
performance and usability.

On the other hand, the Cython and PyPy variants of Python can in some
cases obviate the need for explicit C/C++ interface in the first place;
indeed some would say Cython IS a C/C++ interface.

## Object orientation, metaprogramming

*Slight win for R*.

For instance, though functions are objects in both languages, R takes
that further than does Python.  Whenever I work in Python, I'm annoyed
by the fact that I cannot directly print a function to the terminal or
edit it, which I do a lot in R.  (This goes back to the *polymorphic*
nature of R's **print()** function etc.)

Python has just one OOP paradigm.  In R, you have your choice of several
(S3, S4, R6 etc.), though some may debate whether this is a good thing.

R's metaprogramming features (code that produces code) are wonderful,
arguably as powerful as, or more powerful than, those of Python.  In
both languages, these are only for experts, but the point is that R is
competitive with Python even in this highly CS-ish aspect.

## Linked data structures

*Win for Python.*

**This is not a big issue in Data Science**, but it does come up in some
contexts.

Classical computer science data structures, e.g. binary trees, are easy
to implement in Python.  This can be done in R in various ways, e.g.
with the **datastructures** package, which wraps the widely-used **Boost**
C++ library, but it is not base-R.

## Online help

*Big win for R.*

To begin with, R's basic **help()** function is much more informative
than Python's.  It's nicely supplemented by **example()**.  And most
important, the custom of writing vignettes in R packages makes R a
hands-down winner in this aspect.

# Essential for data scientists to know both R and Python

Hopefully I've made a strong case above for using R in data science, in
analytics, visualization and so on.  It is [widely used in business and
industry](https://github.com/ThinkR-open/companies-using-r).
In a very 
significant move, Python **pandas** creator Wes McKinney recently
joined RStudio/Posit as a principal architect (see **reticulate**.
below).

On the other hand, Python is my preferred tool in some applications.  An
example is [OMSI](https://github.com/matloff/omsi), an online
examination tool that my students and I developed.  Python's built-in
threading made our work much easier in that project.

I thus very strongly recommend that those considering a data science
career not only *learn* both languages, but also *use* them, thus
developing expertise.

## Hybrid R/Python applications

For similar reasons, some user apps may be best developed as a mixture
of R and Python.  Here is the current status:

RStudio/Posit is to be commended for developing the **reticulate**
package, to serve as a bridge between Python and R.  The package enables
calling Python from R code.  For the opposite direction, calling R from
Python, I recommend RPpy2, which is the approach we take in our **dsld**
package.

The **reticulate** package is an outstanding effort, and works well for
pure computation.  But as far as I can tell, it does not solve the
knotty problems that arise in Python, e.g. virtual environments and the
like.  The **RPy2** library has similar issues.

At present, computer systems expertise--skill with environment
variables, search paths and general coding ability-- is required for
developing mixed R/Python apps.

## Learning R and Python

I have a [quick tutorial on R for
non-programmers](http:github.com/matloff/fasteR), an evolving project. I
also have a book, *the Art of R Programming*, NSP, 2011.

I have a [tutorial on
Python](http://heather.cs.ucdavis.edu/FastLanePython.pdf), for
those with a strong programming background.

# Thanks

This document has benefited from various reader comments, notably from
Dirk Eddelbuettel, as well as Paul Hewson, Bob Muenchen and Inaki Ucar.

*Updated December 17, 2023*

