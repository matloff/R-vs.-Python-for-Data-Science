# R vs. Python for Data Science

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/Rlogo.png width = "100" />

<img src = https://raw.githubusercontent.com/matloff/R-vs.-Python-for-Data-Science/master/Images/python-logo.png width = "300" />

### Norm Matloff, Prof. of Computer Science, UC Davis; [my bio](http://heather.cs.ucdavis.edu/matloff.html)


Hello!  This Web page is aimed at shedding some light on the perennial
R-vs.-Python debates in the Data Science community.  As a professional
computer scientist and statistician, I hope to shed some useful light on
the topic.  I have the potential bias &mdash; I've written 4 R-related books,
and currently serve as Editorr-in-Chief of the *R Journal* &mdash; but I hope
this analysis will be considered fair and helpful.

## Elegance

*Clear win for Python.* This is subjective, of course, but having
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

*Huge win for R*.  To even get started in Data Science with Python, one
must learn a lot of material not in base Python, e,g, NumPy, Pandas and
matplotlib.  

By contrast, matrix types and basic graphics are build-in
to base R.  The novice can be doing simple data analyses within minutes.
Python libraries can be tricky to configure, even for the systems-savvy,
while most R packages run right out of the box.

## Available libraries

*Huge win for R*. [CRAN](https://cran.r-project.org/) has over 12,000
packages, extremely useful.

For example, I once needed code to find nearest-neighbors of a given
data point.  I was able to immediately find not one but two packages to
do this.  By contrast, lacking a central repository like CRAN for
Python, just now I tried to find nearest-neighbor code for that
language, and at least with my cursory search, came up empty-handed.
I did fit, e.g. Sci-kit code to do nearest-neighbor *classification*,
but not k-NN code itself.

## Machine learning

*Slight edge to Python here*. The Pythonistas would point to a number of
very finely-tuned libraries, e.g. AlexNet, for image recognition.  Good,
but R versions easily could be developed. The Python libraries' power
comes from setting certain image-smoothing ops, which easily could be
implemented in R's [Keras](https://keras.rstudio.com/) wrapper, and for
that matter, a pure-R version of TensorFlow could be developed.
Meanwhile, I would claim that R's package availabity for random forests
and gradient boosting are outstandng.

(much more coming!)

