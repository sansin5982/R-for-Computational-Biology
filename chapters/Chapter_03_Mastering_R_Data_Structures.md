Chapter 3 — Mastering R Data Structures
================
Sandeep Kumar Singh, PhD

- [Chapter 3 — Mastering R Data
  Structures](#chapter-3--mastering-r-data-structures)
  - [Where This Chapter Fits](#where-this-chapter-fits)
- [1. Why Does R Need Different Data
  Structures?](#1-why-does-r-need-different-data-structures)
- [2. Atomic Vectors](#2-atomic-vectors)
  - [2.1 What Is an Atomic Vector?](#21-what-is-an-atomic-vector)
  - [2.2 Why Do We Need Atomic
    Vectors?](#22-why-do-we-need-atomic-vectors)
  - [2.3 Creating a Vector with `c()`](#23-creating-a-vector-with-c)
  - [2.4 A Vector Can Have One Value](#24-a-vector-can-have-one-value)
- [3. Atomic Vector Types](#3-atomic-vector-types)
  - [3.1 Logical Vectors](#31-logical-vectors)
  - [3.2 Integer Vectors](#32-integer-vectors)
  - [3.3 Double Vectors](#33-double-vectors)
  - [3.4 Character Vectors](#34-character-vectors)
  - [3.5 Complex Vectors](#35-complex-vectors)
  - [3.6 Raw Vectors](#36-raw-vectors)
- [4. Inspecting a Vector](#4-inspecting-a-vector)
  - [`typeof()`](#typeof)
  - [`class()`](#class)
  - [`length()`](#length)
  - [`str()`](#str)
- [5. Homogeneity: Why All Vector Elements Must Have One
  Type](#5-homogeneity-why-all-vector-elements-must-have-one-type)
- [6. Vector Coercion](#6-vector-coercion)
  - [6.1 Why Does Coercion Happen?](#61-why-does-coercion-happen)
  - [6.2 Why Is This Important?](#62-why-is-this-important)
- [7. Creating Vectors in Other Ways](#7-creating-vectors-in-other-ways)
  - [7.1 Sequences with `:`](#71-sequences-with-)
  - [7.2 Sequences with `seq()`](#72-sequences-with-seq)
  - [7.3 Repeated Values with `rep()`](#73-repeated-values-with-rep)
  - [7.4 Empty Vectors with `vector()`](#74-empty-vectors-with-vector)
- [8. Named Vectors](#8-named-vectors)
- [9. General Vector Example](#9-general-vector-example)
- [10. Computational Biology Vector
  Example](#10-computational-biology-vector-example)
- [11. Matrices](#11-matrices)
  - [11.1 What Is a Matrix?](#111-what-is-a-matrix)
  - [11.2 Why Do We Need Matrices?](#112-why-do-we-need-matrices)
- [12. Creating a Matrix with
  `matrix()`](#12-creating-a-matrix-with-matrix)
- [13. Inspecting a Matrix](#13-inspecting-a-matrix)
- [14. Row Names and Column Names](#14-row-names-and-column-names)
- [15. Matrix Homogeneity and
  Coercion](#15-matrix-homogeneity-and-coercion)
- [16. Useful Matrix Calculations](#16-useful-matrix-calculations)
- [17. General Matrix Example](#17-general-matrix-example)
- [18. Computational Biology Matrix
  Example](#18-computational-biology-matrix-example)
- [19. Arrays](#19-arrays)
  - [19.1 What Is an Array?](#191-what-is-an-array)
  - [19.2 Why Do We Need Arrays?](#192-why-do-we-need-arrays)
- [20. Creating an Array](#20-creating-an-array)
- [21. Naming Array Dimensions](#21-naming-array-dimensions)
- [22. Matrix Versus Array](#22-matrix-versus-array)
- [23. Lists](#23-lists)
  - [23.1 What Is a List?](#231-what-is-a-list)
  - [23.2 Why Do We Need Lists?](#232-why-do-we-need-lists)
- [24. Creating a List](#24-creating-a-list)
- [25. Why `str()` Is Especially Useful for
  Lists](#25-why-str-is-especially-useful-for-lists)
- [26. Lists Can Contain Other Lists](#26-lists-can-contain-other-lists)
- [27. Accessing List Elements: A
  Preview](#27-accessing-list-elements-a-preview)
- [28. Computational Biology List
  Example](#28-computational-biology-list-example)
- [29. `unlist()` and Why It Must Be Used
  Carefully](#29-unlist-and-why-it-must-be-used-carefully)
- [30. Factors](#30-factors)
  - [30.1 What Is a Factor?](#301-what-is-a-factor)
- [31. Why Do Factors Exist?](#31-why-do-factors-exist)
- [32. Understanding Factor Storage](#32-understanding-factor-storage)
- [33. Specifying Factor Levels](#33-specifying-factor-levels)
- [34. Ordered Factors](#34-ordered-factors)
- [35. A Famous Factor Mistake](#35-a-famous-factor-mistake)
- [36. Computational Biology Factor
  Example](#36-computational-biology-factor-example)
- [37. Data Frames](#37-data-frames)
  - [37.1 What Is a Data Frame?](#371-what-is-a-data-frame)
- [38. Why Do We Need Data Frames?](#38-why-do-we-need-data-frames)
- [39. Creating a Data Frame](#39-creating-a-data-frame)
- [40. Why Is a Data Frame a List?](#40-why-is-a-data-frame-a-list)
- [41. Inspecting a Data Frame](#41-inspecting-a-data-frame)
  - [`head()`](#head)
  - [`str()`](#str-1)
  - [`summary()`](#summary)
  - [`names()`](#names)
  - [`dim()`](#dim)
- [42. Data Frames and Character
  Columns](#42-data-frames-and-character-columns)
- [43. General Data-Frame Example](#43-general-data-frame-example)
- [44. Computational Biology Data-Frame
  Example](#44-computational-biology-data-frame-example)
- [45. Matrix Versus Data Frame](#45-matrix-versus-data-frame)
  - [Matrix](#matrix)
  - [Data frame](#data-frame)
- [46. Names, Dimensions, and Dimension
  Names](#46-names-dimensions-and-dimension-names)
- [47. `names()`](#47-names)
- [48. `dim()`](#48-dim)
- [49. `dimnames()`](#49-dimnames)
- [50. Attributes](#50-attributes)
- [51. Nested Structures](#51-nested-structures)
- [52. Why Nested Structures Matter](#52-why-nested-structures-matter)
- [53. Specialized R Classes](#53-specialized-r-classes)
- [54. `typeof()` Versus `class()`](#54-typeof-versus-class)
- [55. S3 and S4: A Brief Preview](#55-s3-and-s4-a-brief-preview)
- [56. Bioconductor Example: Why Specialized Classes
  Exist](#56-bioconductor-example-why-specialized-classes-exist)
- [57. Choosing the Right Data
  Structure](#57-choosing-the-right-data-structure)
  - [Use an atomic vector when:](#use-an-atomic-vector-when)
  - [Use a matrix when:](#use-a-matrix-when)
  - [Use an array when:](#use-an-array-when)
  - [Use a list when:](#use-a-list-when)
  - [Use a factor when:](#use-a-factor-when)
  - [Use a data frame when:](#use-a-data-frame-when)
- [58. Comparison Table](#58-comparison-table)
- [59. A Complete General Example](#59-a-complete-general-example)
  - [Vector](#vector)
  - [Factor](#factor)
  - [Matrix](#matrix-1)
  - [Data frame](#data-frame-1)
  - [List](#list)
- [60. Complete Computational Biology
  Example](#60-complete-computational-biology-example)
  - [Sample metadata](#sample-metadata)
  - [Expression matrix](#expression-matrix)
  - [Analysis settings](#analysis-settings)
  - [Combine into a list](#combine-into-a-list)
- [61. Common Mistakes](#61-common-mistakes)
  - [Mistake 1 — Thinking `c()` Can Preserve Mixed
    Types](#mistake-1--thinking-c-can-preserve-mixed-types)
  - [Mistake 2 — Using a Matrix for Mixed-Type Tabular
    Data](#mistake-2--using-a-matrix-for-mixed-type-tabular-data)
  - [Mistake 3 — Treating a Factor as Plain Character
    Data](#mistake-3--treating-a-factor-as-plain-character-data)
  - [Mistake 4 — Converting a Factor Directly with
    `as.numeric()`](#mistake-4--converting-a-factor-directly-with-asnumeric)
  - [Mistake 5 — Using `unlist()` Without
    Thinking](#mistake-5--using-unlist-without-thinking)
  - [Mistake 6 — Assuming Same Dimensions Mean Same Biological
    Alignment](#mistake-6--assuming-same-dimensions-mean-same-biological-alignment)
  - [Mistake 7 — Ignoring Names and
    Dimnames](#mistake-7--ignoring-names-and-dimnames)
  - [Mistake 8 — Confusing `class()` with
    `typeof()`](#mistake-8--confusing-class-with-typeof)
- [62. Debugging Clinic](#62-debugging-clinic)
  - [Problem 1 — `mean()` Says the Argument Is Not
    Numeric](#problem-1--mean-says-the-argument-is-not-numeric)
  - [Problem 2 — Matrix Became
    Character](#problem-2--matrix-became-character)
  - [Problem 3 — Factor Gives Strange
    Numbers](#problem-3--factor-gives-strange-numbers)
  - [Problem 4 — A Function Returned a Huge Complicated
    Object](#problem-4--a-function-returned-a-huge-complicated-object)
  - [Problem 5 — Data Frame Has an Unexpected Column
    Type](#problem-5--data-frame-has-an-unexpected-column-type)
  - [Problem 6 — Expression Matrix and Metadata Do Not
    Match](#problem-6--expression-matrix-and-metadata-do-not-match)
- [63. Performance Corner](#63-performance-corner)
  - [Numeric matrix](#numeric-matrix)
  - [Data frame](#data-frame-2)
  - [List](#list-1)
- [64. Expert Commentary](#64-expert-commentary)
- [65. From the Reviewer’s
  Perspective](#65-from-the-reviewers-perspective)
- [66. Practice Questions — Basic
  Level](#66-practice-questions--basic-level)
- [67. Practical Exercises](#67-practical-exercises)
  - [Exercise 1 — Build Atomic
    Vectors](#exercise-1--build-atomic-vectors)
  - [Exercise 2 — Demonstrate
    Coercion](#exercise-2--demonstrate-coercion)
  - [Exercise 3 — Create a Named
    Vector](#exercise-3--create-a-named-vector)
  - [Exercise 4 — Create a Matrix](#exercise-4--create-a-matrix)
  - [Exercise 5 — Demonstrate Matrix
    Coercion](#exercise-5--demonstrate-matrix-coercion)
  - [Exercise 6 — Create a Three-Dimensional
    Array](#exercise-6--create-a-three-dimensional-array)
  - [Exercise 7 — Create a Heterogeneous
    List](#exercise-7--create-a-heterogeneous-list)
  - [Exercise 8 — Work with Factors](#exercise-8--work-with-factors)
  - [Exercise 9 — Create a Data Frame](#exercise-9--create-a-data-frame)
  - [Exercise 10 — Matrix or Data
    Frame?](#exercise-10--matrix-or-data-frame)
    - [Case A](#case-a)
    - [Case B](#case-b)
    - [Case C](#case-c)
    - [Case D](#case-d)
- [68. Intermediate Thinking
  Exercises](#68-intermediate-thinking-exercises)
  - [Exercise 11 — Diagnose the
    Object](#exercise-11--diagnose-the-object)
  - [Exercise 12 — Why Did the Matrix
    Break?](#exercise-12--why-did-the-matrix-break)
  - [Exercise 13 — Factor Conversion
    Error](#exercise-13--factor-conversion-error)
  - [Exercise 14 — Biological
    Alignment](#exercise-14--biological-alignment)
- [69. Challenge — Build a Structured Study
  Object](#69-challenge--build-a-structured-study-object)
  - [A. Sample metadata](#a-sample-metadata)
  - [B. Expression matrix](#b-expression-matrix)
  - [C. Analysis settings](#c-analysis-settings)
  - [D. Complete study object](#d-complete-study-object)
- [70. Chapter Competency Check](#70-chapter-competency-check)
  - [Atomic vectors](#atomic-vectors)
  - [Matrices](#matrices)
  - [Arrays](#arrays)
  - [Lists](#lists)
  - [Factors](#factors)
  - [Data frames](#data-frames)
  - [Object inspection](#object-inspection)
- [71. Key Takeaways](#71-key-takeaways)
- [72. Repository Output from This
  Chapter](#72-repository-output-from-this-chapter)
- [References and Further Reading](#references-and-further-reading)
  - [Essential Reading](#essential-reading)
  - [Additional Reading](#additional-reading)
  - [Computational Biology Context](#computational-biology-context)
  - [Useful R Documentation](#useful-r-documentation)
- [Next Chapter](#next-chapter)
  - [Chapter 4 — Indexing, Subsetting and Data
    Extraction](#chapter-4--indexing-subsetting-and-data-extraction)

# Chapter 3 — Mastering R Data Structures

## Where This Chapter Fits

In Chapter 2, we learned that R works with **objects**, and that every
object has properties such as a type, class, length, and sometimes
attributes.

We now need to answer a more practical question:

> How does R organize multiple values inside an object?

Suppose we want to store:

- five temperatures;
- the expression values of 10,000 genes;
- information about one patient;
- metadata for 500 study participants;
- a gene-expression matrix;
- several analysis results returned together.

These are not all the same kind of information, so we should not force
them into the same kind of R object.

R provides several fundamental **data structures** for organizing
values:

``` text
atomic vector
matrix
array
list
factor
data frame
```

These structures are foundational. Nearly everything we do later with
`dplyr`, `ggplot2`, statistical models, Bioconductor, GWAS data, RNA-seq
data, Shiny, and machine learning will involve one or more of them.

The purpose of this chapter is therefore not simply to memorize the
names of R structures.

The goal is to understand:

``` text
What is this structure?
Why does R need it?
What kind of data should it hold?
How do I create it?
How do I inspect it?
How does R store it?
What mistakes do beginners commonly make with it?
When should I choose it over another structure?
```

------------------------------------------------------------------------

# 1. Why Does R Need Different Data Structures?

Imagine that you are organizing information in the physical world.

You would not normally store:

- books,
- laboratory samples,
- computer cables,
- patient records,
- and liquid reagents

in exactly the same kind of container.

The same principle applies to programming.

Different types of information need different ways of being organized.

For example, this:

``` r
c(12.4, 15.1, 11.8, 16.3)
```

is naturally a one-dimensional sequence of values.

But this:

``` text
             Sample1 Sample2
GENE1            10      12
GENE2            30      28
GENE3             5       8
```

has rows and columns, so a matrix is more natural.

And this information:

``` text
study name
sample IDs
expression matrix
analysis settings
QC status
```

contains different kinds of objects, so a list may be more appropriate.

A **data structure** describes how values are organized inside an R
object.

A useful first decision is:

``` text
Are all values the same basic type?
```

and then:

``` text
How many dimensions do I need?
```

A simplified mental model is:

``` text
                         R object
                            |
        -------------------------------------------
        |                                         |
   homogeneous                               heterogeneous
 same basic type                           mixed object types
        |                                         |
   -------------                                  |
   |     |     |                                  |
vector matrix array                              list
                                                  |
                                             data frame
                                      (special list structure)
```

Factors require a slightly different mental model because they represent
**categorical data** using integer codes plus category labels.

------------------------------------------------------------------------

# 2. Atomic Vectors

## 2.1 What Is an Atomic Vector?

An **atomic vector** is the simplest and most fundamental data structure
in R.

It is:

1.  **one-dimensional**;
2.  contains zero or more values;
3.  all values must have the **same atomic type**.

For example:

``` r
ages <- c(21, 35, 42, 29)
```

`ages` is a vector containing four numeric values.

Another example:

``` r
sample_ids <- c(
  "S001",
  "S002",
  "S003"
)
```

This is a character vector.

And:

``` r
passed_qc <- c(
  TRUE,
  TRUE,
  FALSE,
  TRUE
)
```

is a logical vector.

The word **atomic** does not mean that the object contains atoms in the
biological or chemical sense.

It means that the elements belong to one basic underlying R type and are
stored as one homogeneous vector.

------------------------------------------------------------------------

## 2.2 Why Do We Need Atomic Vectors?

Many real datasets naturally contain repeated values of the same kind.

Examples include:

``` text
ages of participants
body weights
temperatures
P-values
allele frequencies
gene-expression values
sample identifiers
TRUE/FALSE QC results
```

All of these can be represented naturally as vectors.

For example:

``` r
p_values <- c(
  0.51,
  0.034,
  0.0002,
  5e-8
)
```

Instead of creating:

``` r
p1 <- 0.51
p2 <- 0.034
p3 <- 0.0002
p4 <- 5e-8
```

we put related values into one object.

That allows R to operate on the entire group:

``` r
min(p_values)
```

``` r
length(p_values)
```

``` r
p_values < 0.05
```

Vectors are therefore central to R’s programming model.

------------------------------------------------------------------------

## 2.3 Creating a Vector with `c()`

The most common way to create a vector is:

``` r
c()
```

The `c` stands for **combine** or **concatenate**.

Example:

``` r
heights <- c(
  168,
  175,
  181,
  169
)

heights
```

Conceptually:

``` text
168   175   181   169
```

These four values now belong to one vector called `heights`.

------------------------------------------------------------------------

## 2.4 A Vector Can Have One Value

This is an important R concept.

In R:

``` r
x <- 10
```

`x` is still a vector.

It is simply a vector of length 1.

Check:

``` r
length(x)
```

So in R, what we casually call a “single number” is usually a
one-element vector.

This helps explain why so many R functions are naturally vectorized.

------------------------------------------------------------------------

# 3. Atomic Vector Types

R has several atomic vector types.

The most important for beginners are:

``` text
logical
integer
double
character
complex
raw
```

We will focus mainly on the first four because they appear constantly in
data analysis.

------------------------------------------------------------------------

## 3.1 Logical Vectors

Logical vectors contain:

``` text
TRUE
FALSE
```

and possibly missing values.

Example:

``` r
qc_pass <- c(
  TRUE,
  FALSE,
  TRUE,
  TRUE
)

qc_pass
```

Inspect:

``` r
typeof(qc_pass)
```

Expected type:

``` text
"logical"
```

Logical vectors are extremely important because comparisons return
logical values.

Example:

``` r
depth <- c(
  15,
  30,
  42,
  12
)

depth >= 20
```

Conceptually, R returns:

``` text
FALSE TRUE TRUE FALSE
```

This type of logical result later becomes the foundation of filtering
and subsetting.

------------------------------------------------------------------------

## 3.2 Integer Vectors

An integer is a whole number stored specifically as an integer type.

In R, append:

``` text
L
```

to a number to create an explicit integer.

Example:

``` r
chromosome <- c(
  1L,
  2L,
  6L,
  22L
)

typeof(chromosome)
```

Expected:

``` text
"integer"
```

Notice that:

``` r
x <- 1
```

is usually **not** stored as an integer.

Check:

``` r
typeof(1)
```

R normally returns:

``` text
"double"
```

But:

``` r
typeof(1L)
```

returns:

``` text
"integer"
```

This surprises many beginners.

------------------------------------------------------------------------

## 3.3 Double Vectors

Most ordinary numeric values in R are stored as **double-precision
floating-point numbers**.

Example:

``` r
weights <- c(
  62.5,
  71.2,
  80.0
)

typeof(weights)
```

returns:

``` text
"double"
```

Even:

``` r
x <- 10
```

normally has:

``` r
typeof(x)
```

equal to:

``` text
"double"
```

In everyday R usage, people often call these values simply **numeric**.

Check:

``` r
is.numeric(weights)
```

------------------------------------------------------------------------

## 3.4 Character Vectors

Character vectors store text.

Example:

``` r
genes <- c(
  "BRCA1",
  "TP53",
  "APOE"
)

typeof(genes)
```

returns:

``` text
"character"
```

Strings must usually be written inside quotation marks.

Correct:

``` r
gene <- "TP53"
```

Not:

``` r
# gene <- TP53
```

Without quotes, R interprets `TP53` as an object name and tries to find
an object with that name.

------------------------------------------------------------------------

## 3.5 Complex Vectors

R also supports complex numbers.

Example:

``` r
z <- c(
  1 + 2i,
  3 + 4i
)

typeof(z)
```

returns:

``` text
"complex"
```

Complex numbers are useful in some mathematical and signal-processing
applications but are less common in routine biological data analysis.

------------------------------------------------------------------------

## 3.6 Raw Vectors

Raw vectors store bytes.

Example:

``` r
x <- charToRaw("R")

x
```

``` r
typeof(x)
```

Raw vectors are useful in low-level binary-data work, serialization,
cryptography, and file handling.

They are not a major focus of this beginner chapter.

------------------------------------------------------------------------

# 4. Inspecting a Vector

Never rely only on how an object prints.

Useful inspection functions include:

``` r
typeof()
class()
length()
str()
```

Example:

``` r
p_values <- c(
  0.4,
  0.01,
  5e-8,
  0.8
)

typeof(p_values)
class(p_values)
length(p_values)
str(p_values)
```

These answer different questions.

### `typeof()`

``` r
typeof(p_values)
```

asks:

> What is the underlying R storage type?

### `class()`

``` r
class(p_values)
```

asks:

> How should R interpret this object at a higher level?

### `length()`

``` r
length(p_values)
```

asks:

> How many elements are in the vector?

### `str()`

``` r
str(p_values)
```

gives a compact structural summary.

A strong R habit is:

``` text
receive unfamiliar object
        ↓
str(object)
        ↓
class(object)
        ↓
typeof(object)
```

rather than guessing.

------------------------------------------------------------------------

# 5. Homogeneity: Why All Vector Elements Must Have One Type

An atomic vector is **homogeneous**.

This means all its elements must share one atomic type.

Consider:

``` r
x <- c(
  10,
  20,
  30
)
```

All values are numeric.

Now:

``` r
y <- c(
  "A",
  "B",
  "C"
)
```

All values are character.

But what happens here?

``` r
mixed <- c(
  10,
  20,
  "thirty"
)

mixed
```

R cannot keep two elements as numeric and one as character inside the
same atomic vector.

Instead, it finds a common type.

Inspect:

``` r
typeof(mixed)
```

You should see:

``` text
"character"
```

R converts:

``` text
10
20
```

into:

``` text
"10"
"20"
```

This process is called **coercion**.

------------------------------------------------------------------------

# 6. Vector Coercion

## 6.1 Why Does Coercion Happen?

Atomic vectors require one common type.

So when values of different types are combined, R may convert them to a
type that can represent all values.

A useful simplified coercion hierarchy is:

``` text
logical
   ↓
integer
   ↓
double
   ↓
complex
   ↓
character
```

For example:

``` r
x <- c(
  TRUE,
  5L
)

typeof(x)
```

The logical value can be converted to integer.

Another example:

``` r
x <- c(
  1L,
  2.5
)

typeof(x)
```

The integer values are converted to double.

And:

``` r
x <- c(
  1,
  "two"
)

typeof(x)
```

becomes character.

------------------------------------------------------------------------

## 6.2 Why Is This Important?

Suppose a column that should contain numeric measurements accidentally
contains:

``` text
"not measured"
```

If those values are combined into one atomic vector, the entire vector
may become character.

Then this fails:

``` r
mean(x)
```

because R no longer sees numeric data.

This is why data type inspection is important during data cleaning.

------------------------------------------------------------------------

# 7. Creating Vectors in Other Ways

## 7.1 Sequences with `:`

``` r
1:5
```

returns:

``` text
1 2 3 4 5
```

------------------------------------------------------------------------

## 7.2 Sequences with `seq()`

``` r
seq(
  from = 0,
  to = 10,
  by = 2
)
```

returns:

``` text
0 2 4 6 8 10
```

`seq()` is more flexible than `:`.

------------------------------------------------------------------------

## 7.3 Repeated Values with `rep()`

``` r
rep(
  "control",
  times = 4
)
```

returns four copies of `"control"`.

Another example:

``` r
rep(
  c("case", "control"),
  each = 3
)
```

------------------------------------------------------------------------

## 7.4 Empty Vectors with `vector()`

You can create an empty or preallocated vector.

Example:

``` r
result <- vector(
  mode = "double",
  length = 5
)

result
```

This becomes important later when we learn efficient loops.

------------------------------------------------------------------------

# 8. Named Vectors

A vector can have names associated with its elements.

Example:

``` r
expression <- c(
  BRCA1 = 12.4,
  TP53 = 9.8,
  APOE = 5.1
)

expression
```

Inspect:

``` r
names(expression)
```

Names provide labels without changing the vector’s underlying type.

You can also assign names later:

``` r
x <- c(
  12.4,
  9.8,
  5.1
)

names(x) <- c(
  "BRCA1",
  "TP53",
  "APOE"
)

x
```

Names become especially valuable when row order should not be trusted
blindly.

------------------------------------------------------------------------

# 9. General Vector Example

Suppose we record resting heart rates:

``` r
heart_rate <- c(
  72,
  68,
  75,
  80,
  71
)
```

Inspect:

``` r
typeof(heart_rate)
class(heart_rate)
length(heart_rate)
str(heart_rate)
```

Calculate:

``` r
mean(heart_rate)
min(heart_rate)
max(heart_rate)
```

Create logical values:

``` r
heart_rate > 75
```

This example demonstrates why R vectors are so useful:

> one operation can naturally act on a complete set of related values.

------------------------------------------------------------------------

# 10. Computational Biology Vector Example

Suppose we have allele frequencies for five variants:

``` r
allele_frequency <- c(
  0.12,
  0.35,
  0.04,
  0.48,
  0.21
)
```

Inspect:

``` r
str(allele_frequency)
```

Check whether all values are in the valid frequency range:

``` r
allele_frequency >= 0 &
  allele_frequency <= 1
```

Create variant IDs:

``` r
variant_id <- c(
  "rs1001",
  "rs1002",
  "rs1003",
  "rs1004",
  "rs1005"
)
```

Check:

``` r
length(variant_id)
length(allele_frequency)
```

Both vectors should have the same length if each frequency corresponds
to one variant.

This does not constitute a full genetic analysis. It simply demonstrates
how biological values can be stored in vectors.

------------------------------------------------------------------------

# 11. Matrices

## 11.1 What Is a Matrix?

A **matrix** is a two-dimensional homogeneous R data structure.

It has:

``` text
rows
×
columns
```

For example:

``` text
       Sample1 Sample2
Gene1       10      12
Gene2       20      18
Gene3        5       7
```

A crucial property is:

> Every element in a matrix must belong to the same atomic type.

A numeric matrix contains numeric values.

A character matrix contains character values.

A matrix cannot preserve one numeric column and one character column as
separate atomic types.

If you need columns with different types, a data frame is usually more
appropriate.

------------------------------------------------------------------------

## 11.2 Why Do We Need Matrices?

Matrices are natural when data form a rectangular grid and all cells
represent the same kind of measurement.

Examples include:

``` text
student × exam scores
sample × metabolite measurements
gene × sample expression values
individual × SNP genotype dosages
correlation matrices
distance matrices
```

Matrices are particularly important because many statistical and
mathematical operations are defined directly on them.

------------------------------------------------------------------------

# 12. Creating a Matrix with `matrix()`

Example:

``` r
scores <- matrix(
  c(
    80,
    85,
    90,
    75,
    88,
    92
  ),
  nrow = 3,
  ncol = 2
)

scores
```

By default, R fills matrices **column by column**.

This surprises many beginners.

To fill by row:

``` r
scores_by_row <- matrix(
  c(
    80,
    85,
    90,
    75,
    88,
    92
  ),
  nrow = 3,
  ncol = 2,
  byrow = TRUE
)

scores_by_row
```

------------------------------------------------------------------------

# 13. Inspecting a Matrix

Useful functions include:

``` r
class(scores)
typeof(scores)
dim(scores)
nrow(scores)
ncol(scores)
length(scores)
str(scores)
```

Notice the difference between:

``` r
dim(scores)
```

and:

``` r
length(scores)
```

If the matrix has 3 rows and 2 columns:

``` text
dim = 3 × 2
length = 6
```

A matrix is still built from a vector internally, with a dimension
attribute attached.

This is an important mental model:

``` text
atomic vector
+
dim attribute
=
matrix
```

------------------------------------------------------------------------

# 14. Row Names and Column Names

A matrix becomes easier to interpret when rows and columns have names.

Example:

``` r
expression <- matrix(
  c(
    10,
    20,
    5,
    12,
    18,
    7
  ),
  nrow = 3,
  ncol = 2
)

rownames(expression) <- c(
  "GENE1",
  "GENE2",
  "GENE3"
)

colnames(expression) <- c(
  "SampleA",
  "SampleB"
)

expression
```

Inspect:

``` r
rownames(expression)
colnames(expression)
dimnames(expression)
```

In scientific analysis, labels are not merely decoration.

They help prevent mistakes such as assuming that two matrices have
samples in the same order.

------------------------------------------------------------------------

# 15. Matrix Homogeneity and Coercion

Consider:

``` r
x <- matrix(
  c(
    1,
    2,
    3,
    "missing"
  ),
  nrow = 2
)

x
```

Inspect:

``` r
typeof(x)
```

Because one value is character, the entire matrix becomes character.

This is one of the most important differences between a matrix and a
data frame.

------------------------------------------------------------------------

# 16. Useful Matrix Calculations

Suppose:

``` r
m <- matrix(
  c(
    10,
    20,
    30,
    40,
    50,
    60
  ),
  nrow = 3
)
```

Row sums:

``` r
rowSums(m)
```

Column sums:

``` r
colSums(m)
```

Row means:

``` r
rowMeans(m)
```

Column means:

``` r
colMeans(m)
```

These functions are often preferable to manually looping through rows or
columns.

------------------------------------------------------------------------

# 17. General Matrix Example

Suppose rows represent students and columns represent two exams:

``` r
exam_scores <- matrix(
  c(
    80,
    92,
    75,
    85,
    88,
    90
  ),
  nrow = 3,
  byrow = TRUE
)

rownames(exam_scores) <- c(
  "Student1",
  "Student2",
  "Student3"
)

colnames(exam_scores) <- c(
  "Exam1",
  "Exam2"
)

exam_scores
```

Calculate average score for each student:

``` r
rowMeans(exam_scores)
```

This is a natural matrix problem because every cell contains the same
kind of measurement: an exam score.

------------------------------------------------------------------------

# 18. Computational Biology Matrix Example

A gene-expression matrix commonly follows:

``` text
genes × samples
```

Example:

``` r
expression <- matrix(
  c(
    10,
    20,
    5,
    12,
    18,
    7
  ),
  nrow = 3
)

rownames(expression) <- c(
  "GENE1",
  "GENE2",
  "GENE3"
)

colnames(expression) <- c(
  "SampleA",
  "SampleB"
)

expression
```

Inspect:

``` r
dim(expression)
str(expression)
```

Calculate mean expression by gene:

``` r
rowMeans(expression)
```

This is still only a teaching example. Real RNA-seq workflows require
appropriate count structures, normalization, metadata, and statistical
models.

------------------------------------------------------------------------

# 19. Arrays

## 19.1 What Is an Array?

An **array** is a homogeneous data structure with two or more
dimensions.

A matrix is essentially a two-dimensional case.

An array can have:

``` text
2 dimensions
3 dimensions
4 dimensions
...
```

For example:

``` text
gene × sample × time
```

could naturally be represented as a three-dimensional array.

------------------------------------------------------------------------

## 19.2 Why Do We Need Arrays?

Suppose we measure:

``` text
3 genes
×
2 samples
×
4 time points
```

A matrix can represent only two dimensions directly.

An array allows us to retain all three dimensions in one structure.

Arrays are useful when data naturally have several repeated axes.

Examples include:

``` text
height × width × color channel in an image
gene × sample × time
latitude × longitude × time
simulation × variable × parameter
```

------------------------------------------------------------------------

# 20. Creating an Array

Example:

``` r
x <- array(
  1:24,
  dim = c(
    3,
    2,
    4
  )
)

x
```

Inspect:

``` r
dim(x)
```

Expected dimensions:

``` text
3 2 4
```

Total elements:

``` r
length(x)
```

should be:

``` text
24
```

because:

``` text
3 × 2 × 4 = 24
```

------------------------------------------------------------------------

# 21. Naming Array Dimensions

We can give each dimension meaningful names.

Example:

``` r
expression_array <- array(
  1:12,
  dim = c(
    2,
    2,
    3
  ),
  dimnames = list(
    gene = c(
      "GENE1",
      "GENE2"
    ),
    sample = c(
      "SampleA",
      "SampleB"
    ),
    time = c(
      "T1",
      "T2",
      "T3"
    )
  )
)

expression_array
```

Inspect:

``` r
dimnames(expression_array)
```

Named dimensions make multidimensional data much easier to understand.

------------------------------------------------------------------------

# 22. Matrix Versus Array

A matrix:

``` text
row × column
```

An array:

``` text
dimension 1 × dimension 2 × dimension 3 × ...
```

Both are homogeneous.

That means both can be affected by type coercion.

Use a matrix when two dimensions are enough.

Use an array when the scientific structure genuinely contains additional
dimensions.

------------------------------------------------------------------------

# 23. Lists

## 23.1 What Is a List?

A **list** is a heterogeneous R data structure.

Unlike an atomic vector, list elements do **not** need to have the same
type.

A list can contain:

``` text
numbers
character vectors
logical values
matrices
data frames
other lists
functions
model objects
```

all at the same time.

Example:

``` r
student <- list(
  id = "S001",
  age = 24,
  scores = c(
    82,
    91,
    87
  ),
  passed = TRUE
)

student
```

------------------------------------------------------------------------

## 23.2 Why Do We Need Lists?

Suppose one analysis result contains:

``` text
study name              character
sample size             integer/numeric
P-values                numeric vector
expression matrix       matrix
metadata                data frame
analysis settings       list
```

An atomic vector cannot store these while preserving their structures.

A matrix cannot either.

A list can.

That makes lists extremely important in R.

Many R functions return lists or list-like objects because a single
analysis can produce several different outputs.

------------------------------------------------------------------------

# 24. Creating a List

Use:

``` r
list()
```

Example:

``` r
analysis <- list(
  study = "Example Study",
  n = 120,
  significant = TRUE,
  p_values = c(
    0.2,
    0.01,
    5e-8
  )
)

analysis
```

Inspect:

``` r
class(analysis)
typeof(analysis)
length(analysis)
names(analysis)
str(analysis)
```

A list has:

``` text
typeof = "list"
```

and each element can have its own type and structure.

------------------------------------------------------------------------

# 25. Why `str()` Is Especially Useful for Lists

Printing a large list can be overwhelming.

`str()` shows the hierarchy compactly.

Example:

``` r
str(analysis)
```

This tells us:

``` text
how many elements exist
their names
their types
their internal structures
```

For unfamiliar R output objects, `str()` is often the first function to
use.

------------------------------------------------------------------------

# 26. Lists Can Contain Other Lists

Example:

``` r
project <- list(
  study = "Example",
  settings = list(
    threshold = 0.05,
    method = "standard"
  ),
  results = list(
    n_significant = 12,
    completed = TRUE
  )
)

str(project)
```

This is called a **nested list**.

Nested structures are extremely common in R.

------------------------------------------------------------------------

# 27. Accessing List Elements: A Preview

Chapter 4 will explain indexing properly.

For now, recognize these common forms:

``` r
analysis$study
```

and:

``` r
analysis[["study"]]
```

Both can retrieve a list element.

The difference between:

``` r
[
```

and:

``` r
[[
```

is important and will be taught carefully in the next chapter.

------------------------------------------------------------------------

# 28. Computational Biology List Example

Suppose we want one object to hold several parts of a small genomic
study:

``` r
study <- list(
  study_name = "Toy GWAS",
  genome_build = "GRCh38",
  sample_size = 5000,
  variant_ids = c(
    "rs1",
    "rs2",
    "rs3"
  ),
  p_values = c(
    0.30,
    0.002,
    5e-8
  ),
  settings = list(
    significance_threshold = 5e-8,
    chromosome = 6
  )
)

str(study)
```

The value of this example is structural.

A list lets us preserve different kinds of information in one logically
organized object.

------------------------------------------------------------------------

# 29. `unlist()` and Why It Must Be Used Carefully

`unlist()` attempts to flatten a list into an atomic vector.

Example:

``` r
x <- list(
  a = 1,
  b = 2,
  c = 3
)

unlist(x)
```

This can be useful when the list contains compatible simple values.

But consider:

``` r
x <- list(
  id = "S001",
  age = 24,
  passed = TRUE
)

unlist(x)
```

Because an atomic vector must have one type, values may be coerced.

So:

> Do not use `unlist()` automatically on every list.

Flattening can destroy meaningful structure.

------------------------------------------------------------------------

# 30. Factors

## 30.1 What Is a Factor?

A **factor** is R’s traditional data structure for representing
categorical variables.

Examples of categorical variables include:

``` text
sex
treatment group
disease status
tissue
genotype category
study site
```

For example:

``` r
group <- c(
  "control",
  "case",
  "control",
  "case"
)
```

This is currently a character vector.

Convert it to a factor:

``` r
group_factor <- factor(group)

group_factor
```

Inspect:

``` r
class(group_factor)
typeof(group_factor)
levels(group_factor)
```

This reveals an important fact.

A factor is not simply a character vector with a special label.

Internally, a factor commonly uses integer codes plus a `levels`
attribute.

------------------------------------------------------------------------

# 31. Why Do Factors Exist?

Suppose we have:

``` text
control
case
control
control
case
```

There are only two distinct categories.

A factor records the allowed categories explicitly:

``` r
levels(group_factor)
```

This is useful because statistical models and plotting systems often
need to know:

- which values are categories;
- what the possible categories are;
- what their order is;
- which category should serve as a reference.

------------------------------------------------------------------------

# 32. Understanding Factor Storage

Example:

``` r
group <- factor(
  c(
    "control",
    "case",
    "control"
  )
)

group
```

Inspect:

``` r
typeof(group)
```

This often returns:

``` text
"integer"
```

But:

``` r
class(group)
```

returns:

``` text
"factor"
```

And:

``` r
levels(group)
```

shows category labels.

This beautifully illustrates the difference between:

``` text
underlying type
```

and:

``` text
class
```

------------------------------------------------------------------------

# 33. Specifying Factor Levels

You can control category order:

``` r
group <- factor(
  c(
    "case",
    "control",
    "case",
    "control"
  ),
  levels = c(
    "control",
    "case"
  )
)

levels(group)
```

Now `"control"` is the first level.

This can matter in statistical modelling.

------------------------------------------------------------------------

# 34. Ordered Factors

Some categories have a meaningful order.

Example:

``` text
low
medium
high
```

Create:

``` r
severity <- factor(
  c(
    "low",
    "high",
    "medium",
    "low"
  ),
  levels = c(
    "low",
    "medium",
    "high"
  ),
  ordered = TRUE
)

severity
```

This is an **ordered factor**.

Do not mark a variable as ordered unless the categories genuinely have
an ordered interpretation.

------------------------------------------------------------------------

# 35. A Famous Factor Mistake

Consider:

``` r
x <- factor(
  c(
    "10",
    "20",
    "30"
  )
)
```

A beginner may try:

``` r
as.numeric(x)
```

This may return internal factor codes such as:

``` text
1 2 3
```

rather than:

``` text
10 20 30
```

Why?

Because the factor is internally represented using integer codes.

If numeric conversion is genuinely needed:

``` r
as.numeric(
  as.character(x)
)
```

But first ask:

> Why was this variable a factor if it was supposed to represent a
> numeric measurement?

Often the real problem occurred during data import or data cleaning.

------------------------------------------------------------------------

# 36. Computational Biology Factor Example

Sample tissue:

``` r
tissue <- factor(
  c(
    "Blood",
    "Brain",
    "Blood",
    "Liver"
  )
)

tissue
```

Inspect:

``` r
levels(tissue)
table(tissue)
```

This is appropriate because tissue is categorical.

But gene-expression values themselves should not normally be factors.

Choosing the correct structure depends on the meaning of the data.

------------------------------------------------------------------------

# 37. Data Frames

## 37.1 What Is a Data Frame?

A **data frame** is the standard base-R structure for rectangular
tabular data.

It has:

``` text
rows
×
columns
```

Like a matrix.

But unlike a matrix, different columns can contain different types.

Example:

``` r
students <- data.frame(
  id = c(
    "S001",
    "S002",
    "S003"
  ),
  age = c(
    21,
    24,
    20
  ),
  passed = c(
    TRUE,
    TRUE,
    FALSE
  )
)

students
```

Here:

``` text
id       character
age      numeric
passed   logical
```

A matrix could not preserve these three different column types without
coercion.

A data frame can.

------------------------------------------------------------------------

# 38. Why Do We Need Data Frames?

Most real-world tabular datasets contain multiple variable types.

For example:

``` text
sample_id       character
age             numeric
sex             factor/character
disease         logical/factor
blood_pressure  numeric
collection_date Date
```

This is exactly the kind of information a data frame is designed to
hold.

Examples include:

``` text
clinical tables
sample metadata
GWAS summary statistics
phenotype tables
survey data
experimental metadata
```

------------------------------------------------------------------------

# 39. Creating a Data Frame

Use:

``` r
data.frame()
```

Example:

``` r
patients <- data.frame(
  patient_id = c(
    "P001",
    "P002",
    "P003"
  ),
  age = c(
    45,
    52,
    39
  ),
  treatment = c(
    "A",
    "B",
    "A"
  ),
  response = c(
    TRUE,
    FALSE,
    TRUE
  )
)

patients
```

Inspect:

``` r
class(patients)
typeof(patients)
str(patients)
dim(patients)
nrow(patients)
ncol(patients)
names(patients)
```

A data frame usually has:

``` text
class = "data.frame"
typeof = "list"
```

This is important.

------------------------------------------------------------------------

# 40. Why Is a Data Frame a List?

A data frame can be understood as:

> a named list of equal-length vectors arranged as columns.

Conceptually:

``` text
data frame
   |
   |-- patient_id : character vector length 3
   |-- age        : numeric vector length 3
   |-- treatment  : character vector length 3
   |-- response   : logical vector length 3
```

All columns must have compatible row lengths.

This list-based design allows each column to retain its own type.

That is why a data frame can represent heterogeneous tabular data.

------------------------------------------------------------------------

# 41. Inspecting a Data Frame

Useful functions include:

``` r
head(patients)
```

``` r
str(patients)
```

``` r
summary(patients)
```

``` r
names(patients)
```

``` r
dim(patients)
```

Use them for different purposes.

### `head()`

Shows the first rows.

### `str()`

Shows structure and types.

### `summary()`

Provides column-specific summaries.

### `names()`

Shows column names.

### `dim()`

Shows:

``` text
number of rows
number of columns
```

------------------------------------------------------------------------

# 42. Data Frames and Character Columns

Older versions of R commonly converted character columns to factors
automatically in `data.frame()`.

Modern R versions use:

``` r
stringsAsFactors = FALSE
```

as the default behavior.

So:

``` r
data.frame(
  id = c(
    "A",
    "B"
  )
)
```

normally keeps `id` as character.

However, you should always inspect imported or externally supplied data
rather than assuming how a column was represented.

------------------------------------------------------------------------

# 43. General Data-Frame Example

``` r
students <- data.frame(
  student_id = c(
    "S1",
    "S2",
    "S3",
    "S4"
  ),
  age = c(
    19,
    21,
    20,
    22
  ),
  group = factor(
    c(
      "A",
      "A",
      "B",
      "B"
    )
  ),
  score = c(
    82,
    91,
    76,
    88
  )
)

students
```

Inspect:

``` r
str(students)
```

``` r
summary(students)
```

This object now combines:

``` text
character
numeric
factor
numeric
```

within one rectangular table.

------------------------------------------------------------------------

# 44. Computational Biology Data-Frame Example

A small GWAS-like table:

``` r
gwas <- data.frame(
  SNP = c(
    "rs1001",
    "rs1002",
    "rs1003"
  ),
  CHR = c(
    6L,
    6L,
    6L
  ),
  BP = c(
    26000000L,
    27500000L,
    31300000L
  ),
  A1 = c(
    "A",
    "C",
    "G"
  ),
  A2 = c(
    "G",
    "T",
    "A"
  ),
  BETA = c(
    0.12,
    -0.08,
    0.25
  ),
  P = c(
    0.04,
    0.002,
    5e-8
  )
)

str(gwas)
```

Different columns naturally require different types.

For example:

``` text
SNP   character
CHR   integer
BP    integer
A1    character
A2    character
BETA  double
P     double
```

This is why a data frame is more appropriate than a matrix for GWAS
summary-statistic tables.

------------------------------------------------------------------------

# 45. Matrix Versus Data Frame

This distinction is essential.

## Matrix

``` text
rectangular
homogeneous
all cells one atomic type
excellent for numeric computation
```

## Data frame

``` text
rectangular
heterogeneous by column
each column can have its own type
excellent for tabular records
```

Example:

``` r
m <- matrix(
  c(
    1,
    2,
    "A",
    "B"
  ),
  nrow = 2
)

typeof(m)
```

Likely:

``` text
"character"
```

But:

``` r
df <- data.frame(
  value = c(
    1,
    2
  ),
  group = c(
    "A",
    "B"
  )
)

str(df)
```

preserves:

``` text
value = numeric
group = character
```

------------------------------------------------------------------------

# 46. Names, Dimensions, and Dimension Names

R objects can carry metadata called **attributes**.

Some important attributes include:

``` text
names
dim
dimnames
class
levels
```

These attributes help R interpret the underlying values.

------------------------------------------------------------------------

# 47. `names()`

Vectors and lists can have names.

Example:

``` r
x <- c(
  height = 175,
  weight = 78
)

names(x)
```

Lists:

``` r
person <- list(
  id = "P001",
  age = 44
)

names(person)
```

Names improve readability and can protect against relying only on
positions.

------------------------------------------------------------------------

# 48. `dim()`

Matrices, arrays, and data frames have dimensions.

Example:

``` r
m <- matrix(
  1:12,
  nrow = 3
)

dim(m)
```

returns:

``` text
3 4
```

A data frame:

``` r
dim(students)
```

returns:

``` text
number of rows
number of columns
```

------------------------------------------------------------------------

# 49. `dimnames()`

Matrices and arrays can have labels for dimensions.

Example:

``` r
m <- matrix(
  1:4,
  nrow = 2,
  dimnames = list(
    c(
      "Row1",
      "Row2"
    ),
    c(
      "Col1",
      "Col2"
    )
  )
)

dimnames(m)
```

For matrices, convenience functions include:

``` r
rownames(m)
colnames(m)
```

------------------------------------------------------------------------

# 50. Attributes

Inspect attributes using:

``` r
attributes(m)
```

Example:

``` r
f <- factor(
  c(
    "case",
    "control",
    "case"
  )
)

attributes(f)
```

You should see attributes related to:

``` text
levels
class
```

This explains an important R idea:

> many higher-level R objects are ordinary underlying data plus
> attributes.

For example:

``` text
matrix
=
atomic vector
+
dim attribute
```

and conceptually:

``` text
factor
=
integer vector
+
levels attribute
+
class attribute
```

This idea becomes extremely important later.

------------------------------------------------------------------------

# 51. Nested Structures

A nested structure is an object containing another structured object.

Example:

``` r
study <- list(
  name = "Study A",
  metadata = data.frame(
    sample_id = c(
      "S1",
      "S2"
    ),
    tissue = c(
      "Blood",
      "Brain"
    )
  ),
  expression = matrix(
    c(
      10,
      20,
      12,
      18
    ),
    nrow = 2
  ),
  settings = list(
    genome_build = "GRCh38",
    threshold = 0.05
  )
)

str(study)
```

This one object contains:

``` text
character value
data frame
matrix
list
```

This is common in real R software.

------------------------------------------------------------------------

# 52. Why Nested Structures Matter

A statistical model may return:

``` text
coefficients
residuals
fitted values
model call
diagnostics
```

A bioinformatics package may return:

``` text
assay data
sample metadata
feature metadata
analysis parameters
results
```

Lists and specialized classes allow these related components to remain
together.

------------------------------------------------------------------------

# 53. Specialized R Classes

As you progress, you will encounter objects that are not simply called:

``` text
vector
matrix
list
data.frame
```

Examples include:

``` text
Date
POSIXct
lm
GRanges
SummarizedExperiment
DESeqDataSet
```

These are **specialized classes**.

Do not panic when:

``` r
class(x)
```

returns something unfamiliar.

Use:

``` r
class(x)
typeof(x)
str(x)
attributes(x)
```

and documentation.

------------------------------------------------------------------------

# 54. `typeof()` Versus `class()`

This distinction deserves repetition.

Consider:

``` r
x <- factor(
  c(
    "A",
    "B",
    "A"
  )
)
```

Run:

``` r
typeof(x)
```

and:

``` r
class(x)
```

You may see:

``` text
typeof = integer
class  = factor
```

This is not contradictory.

It means:

``` text
underlying storage
=
integer

higher-level interpretation
=
factor
```

Similarly, many sophisticated R objects are built on simpler underlying
structures.

------------------------------------------------------------------------

# 55. S3 and S4: A Brief Preview

Later in the course, we will study R’s object systems in more detail.

For now, know that R packages can create specialized classes.

Common systems include:

``` text
S3
S4
R6
```

Base statistical models often use S3 classes.

Bioconductor makes extensive use of S4 classes.

Do not try to dismantle these objects manually unless you understand
their interface.

Prefer documented accessor functions.

------------------------------------------------------------------------

# 56. Bioconductor Example: Why Specialized Classes Exist

Suppose genomic intervals were stored only as:

``` text
chromosome
start
end
```

in a generic data frame.

That can work.

But genomic analysis also needs concepts such as:

``` text
strand
sequence naming
range operations
overlap operations
genome metadata
```

Bioconductor’s `GRanges` class provides a structured representation for
genomic ranges.

We will study it properly later.

The important lesson now is:

> specialized classes exist because some domains need stronger structure
> and behavior than a generic data frame provides.

------------------------------------------------------------------------

# 57. Choosing the Right Data Structure

Use this decision guide.

## Use an atomic vector when:

``` text
you have one-dimensional values
all values share one basic type
```

Examples:

``` text
P-values
ages
gene names
QC pass/fail indicators
```

------------------------------------------------------------------------

## Use a matrix when:

``` text
you need rows and columns
all cells represent the same basic type
```

Examples:

``` text
expression matrix
genotype dosage matrix
correlation matrix
```

------------------------------------------------------------------------

## Use an array when:

``` text
you need more than two dimensions
all values remain one atomic type
```

Example:

``` text
gene × sample × time
```

------------------------------------------------------------------------

## Use a list when:

``` text
you need to combine different object types
or store nested information
```

Examples:

``` text
model output
analysis results
configuration plus data
```

------------------------------------------------------------------------

## Use a factor when:

``` text
you have categorical values
and category levels matter
```

Examples:

``` text
case/control
tissue
treatment group
severity category
```

------------------------------------------------------------------------

## Use a data frame when:

``` text
you have rows and columns
different columns may have different types
```

Examples:

``` text
sample metadata
clinical data
GWAS summary statistics
phenotype tables
```

------------------------------------------------------------------------

# 58. Comparison Table

| Structure | Dimensions | Same type required? | Can contain mixed object types? | Typical use |
|----|---:|----|----|----|
| Atomic vector | 1 | Yes | No | Measurements, IDs, P-values |
| Matrix | 2 | Yes | No | Numeric rectangular data |
| Array | 2+ | Yes | No | Multidimensional measurements |
| List | 1 logical container | No | Yes | Complex/nested results |
| Factor | 1 | Categorical representation | No | Categories |
| Data frame | 2 | Per column | Yes, across columns | Tabular datasets |

------------------------------------------------------------------------

# 59. A Complete General Example

Suppose we have a small student study.

## Vector

Student scores:

``` r
scores <- c(
  82,
  91,
  76,
  88
)
```

## Factor

Group membership:

``` r
group <- factor(
  c(
    "A",
    "B",
    "A",
    "B"
  )
)
```

## Matrix

Two exam scores:

``` r
exam_matrix <- matrix(
  c(
    82,
    85,
    91,
    93,
    76,
    79,
    88,
    90
  ),
  nrow = 4,
  byrow = TRUE
)

rownames(exam_matrix) <- c(
  "S1",
  "S2",
  "S3",
  "S4"
)

colnames(exam_matrix) <- c(
  "Exam1",
  "Exam2"
)
```

## Data frame

Student metadata:

``` r
students <- data.frame(
  student_id = c(
    "S1",
    "S2",
    "S3",
    "S4"
  ),
  age = c(
    19,
    21,
    20,
    22
  ),
  group = group,
  final_score = scores
)
```

## List

Whole study:

``` r
student_study <- list(
  metadata = students,
  exam_scores = exam_matrix,
  passing_score = 70,
  study_name = "Student Performance Study"
)
```

Inspect:

``` r
str(student_study)
```

This example shows why R needs multiple structures.

Each structure solves a different organizational problem.

------------------------------------------------------------------------

# 60. Complete Computational Biology Example

Suppose we have:

``` text
sample metadata
gene-expression matrix
study settings
```

## Sample metadata

``` r
metadata <- data.frame(
  sample_id = c(
    "SampleA",
    "SampleB",
    "SampleC"
  ),
  tissue = factor(
    c(
      "Blood",
      "Brain",
      "Blood"
    )
  ),
  age = c(
    42,
    51,
    38
  )
)
```

## Expression matrix

``` r
expression <- matrix(
  c(
    10,
    20,
    5,
    12,
    18,
    7,
    11,
    24,
    6
  ),
  nrow = 3
)

rownames(expression) <- c(
  "GENE1",
  "GENE2",
  "GENE3"
)

colnames(expression) <- c(
  "SampleA",
  "SampleB",
  "SampleC"
)
```

## Analysis settings

``` r
settings <- list(
  genome_build = "GRCh38",
  minimum_expression = 5,
  normalization = "Teaching example only"
)
```

## Combine into a list

``` r
study <- list(
  metadata = metadata,
  expression = expression,
  settings = settings
)
```

Inspect:

``` r
str(study)
```

Now compare sample names:

``` r
metadata$sample_id
```

and:

``` r
colnames(expression)
```

These identifiers should correspond.

This introduces a professional scientific habit:

> Do not assume that two biological objects are aligned merely because
> they have the same number of samples.

Identity and order should be checked explicitly.

------------------------------------------------------------------------

# 61. Common Mistakes

## Mistake 1 — Thinking `c()` Can Preserve Mixed Types

``` r
x <- c(
  10,
  "A"
)
```

The numeric value is coerced.

Check:

``` r
typeof(x)
```

If you need heterogeneous objects, use a list.

------------------------------------------------------------------------

## Mistake 2 — Using a Matrix for Mixed-Type Tabular Data

A matrix containing age, sex, ID, and score will often become character.

Use a data frame when columns have different meanings and types.

------------------------------------------------------------------------

## Mistake 3 — Treating a Factor as Plain Character Data

Factors contain levels and internal integer codes.

Always inspect:

``` r
class(x)
levels(x)
```

before transforming.

------------------------------------------------------------------------

## Mistake 4 — Converting a Factor Directly with `as.numeric()`

This can return internal category codes rather than numeric labels.

Understand the object first.

------------------------------------------------------------------------

## Mistake 5 — Using `unlist()` Without Thinking

Flattening a list can coerce types and destroy hierarchy.

------------------------------------------------------------------------

## Mistake 6 — Assuming Same Dimensions Mean Same Biological Alignment

Two matrices may both have:

``` text
100 samples
```

but in different orders.

Use identifiers.

------------------------------------------------------------------------

## Mistake 7 — Ignoring Names and Dimnames

Unnamed rows and columns are much easier to misalign.

------------------------------------------------------------------------

## Mistake 8 — Confusing `class()` with `typeof()`

They describe different aspects of an object.

------------------------------------------------------------------------

# 62. Debugging Clinic

## Problem 1 — `mean()` Says the Argument Is Not Numeric

Inspect:

``` r
typeof(x)
str(x)
```

Possible cause:

``` text
a character value caused coercion
```

Example:

``` r
x <- c(
  10,
  20,
  "missing"
)
```

Better representation:

``` r
x <- c(
  10,
  20,
  NA
)
```

if the third value truly means missing.

------------------------------------------------------------------------

## Problem 2 — Matrix Became Character

Inspect:

``` r
typeof(m)
```

Look for any character value used during matrix creation.

Remember:

``` text
matrix = homogeneous
```

------------------------------------------------------------------------

## Problem 3 — Factor Gives Strange Numbers

Inspect:

``` r
class(x)
levels(x)
typeof(x)
```

Do not assume:

``` r
as.numeric(x)
```

returns the printed labels.

------------------------------------------------------------------------

## Problem 4 — A Function Returned a Huge Complicated Object

Start with:

``` r
class(result)
str(result)
names(result)
```

Do not print thousands of lines immediately.

------------------------------------------------------------------------

## Problem 5 — Data Frame Has an Unexpected Column Type

Inspect:

``` r
str(data)
```

Then inspect the original input values.

A malformed value may have changed how the column was read.

------------------------------------------------------------------------

## Problem 6 — Expression Matrix and Metadata Do Not Match

Check:

``` r
colnames(expression)
metadata$sample_id
```

Then:

``` r
identical(
  colnames(expression),
  metadata$sample_id
)
```

Do not proceed until the relationship is understood.

------------------------------------------------------------------------

# 63. Performance Corner

Choosing the correct data structure can affect both clarity and
performance.

## Numeric matrix

A numeric matrix is compact and efficient for homogeneous numeric
operations.

## Data frame

A data frame is flexible because each column can have its own type.

## List

A list is flexible enough to hold arbitrary objects, but many
matrix-style operations do not apply directly.

Do not choose a structure because someone told you it is “faster.”

Choose a structure because it correctly represents the data and supports
the operations you need.

Performance optimization comes after correctness.

------------------------------------------------------------------------

# 64. Expert Commentary

Experienced R programmers do not immediately ask:

> Which function should I run?

They often first ask:

``` text
What object do I have?
What is its class?
What is its underlying type?
What are its dimensions?
Does it have names?
Does it contain nested objects?
```

This is why functions such as:

``` r
str()
class()
typeof()
length()
dim()
names()
attributes()
```

appear repeatedly throughout this course.

Understanding structure makes later code much easier to reason about.

------------------------------------------------------------------------

# 65. From the Reviewer’s Perspective

Suppose a scientific script contains:

``` r
expression <- as.matrix(data)
```

A reviewer should ask:

``` text
What were the original column types?
Did any character column cause coercion?
Are the rows genes?
Are the columns samples?
Are sample names preserved?
Does the metadata use the same sample order?
```

Similarly, if a factor was converted to numeric, a reviewer should check
whether internal codes were accidentally used as measurements.

Data structures are therefore not merely programming details.

They can affect scientific validity.

------------------------------------------------------------------------

# 66. Practice Questions — Basic Level

1.  What is a data structure?
2.  Why does R need more than one data structure?
3.  What is an atomic vector?
4.  Why is an atomic vector called homogeneous?
5.  What does `c()` do?
6.  Is `x <- 10` a vector in R?
7.  What does `length()` return?
8.  What is a logical vector?
9.  What is an integer vector?
10. What does the `L` mean in `10L`?
11. What is usually returned by `typeof(10)`?
12. What is a character vector?
13. Why must text normally be quoted?
14. What does `typeof()` tell us?
15. What does `class()` tell us?
16. What does `str()` do?
17. What is coercion?
18. Why does `c(1, "A")` become character?
19. What is a named vector?
20. What is a matrix?
21. Why must a matrix contain one atomic type?
22. What does `dim()` return?
23. What is the difference between `length()` and `dim()` for a matrix?
24. Why are row names and column names useful?
25. What is an array?
26. When would an array be more appropriate than a matrix?
27. What is a list?
28. Why can a list contain objects of different types?
29. What is a nested list?
30. What is a factor?
31. Why does a factor have levels?
32. Why can `as.numeric(factor_object)` be dangerous?
33. What is a data frame?
34. Why can a data frame preserve different column types?
35. Why is a data frame internally list-like?
36. What is the difference between a matrix and a data frame?
37. What are attributes?
38. What does `names()` inspect?
39. What does `dimnames()` inspect?
40. Why can `class()` and `typeof()` return different answers?

------------------------------------------------------------------------

# 67. Practical Exercises

## Exercise 1 — Build Atomic Vectors

Create:

``` text
one logical vector
one integer vector
one double vector
one character vector
```

For each, run:

``` r
typeof()
class()
length()
str()
```

Explain the output.

------------------------------------------------------------------------

## Exercise 2 — Demonstrate Coercion

Create:

``` r
c(
  TRUE,
  5L
)
```

Then:

``` r
c(
  5L,
  2.5
)
```

Then:

``` r
c(
  5,
  "five"
)
```

Inspect `typeof()` each time.

Explain why the result changes.

------------------------------------------------------------------------

## Exercise 3 — Create a Named Vector

Create gene-expression values:

``` r
c(
  BRCA1 = 12.4,
  TP53 = 8.7,
  APOE = 4.2
)
```

Inspect:

``` r
names()
str()
```

------------------------------------------------------------------------

## Exercise 4 — Create a Matrix

Create a:

``` text
3 × 4
```

numeric matrix.

Add row and column names.

Inspect:

``` r
dim()
nrow()
ncol()
length()
rownames()
colnames()
```

------------------------------------------------------------------------

## Exercise 5 — Demonstrate Matrix Coercion

Create a matrix containing three numeric values and one character value.

Inspect:

``` r
typeof()
```

Explain what happened.

------------------------------------------------------------------------

## Exercise 6 — Create a Three-Dimensional Array

Create an array with dimensions:

``` text
2 × 3 × 4
```

Calculate:

``` r
length()
dim()
```

Verify mathematically that the total number of elements is correct.

------------------------------------------------------------------------

## Exercise 7 — Create a Heterogeneous List

Create a list containing:

``` text
student ID
age
numeric scores vector
logical pass/fail
small matrix
```

Inspect with:

``` r
str()
```

------------------------------------------------------------------------

## Exercise 8 — Work with Factors

Create:

``` r
factor(
  c(
    "control",
    "case",
    "control",
    "case"
  ),
  levels = c(
    "control",
    "case"
  )
)
```

Inspect:

``` r
class()
typeof()
levels()
```

Explain why `typeof()` and `class()` differ.

------------------------------------------------------------------------

## Exercise 9 — Create a Data Frame

Create a data frame containing:

``` text
sample ID
age
tissue
sequencing depth
QC pass
```

Inspect:

``` r
str()
dim()
names()
summary()
```

------------------------------------------------------------------------

## Exercise 10 — Matrix or Data Frame?

For each case, decide which structure is more appropriate and explain
why.

### Case A

``` text
100 genes × 20 samples of numeric expression values
```

### Case B

``` text
sample ID, age, sex, tissue, sequencing depth
```

### Case C

``` text
correlation coefficients between 50 variables
```

### Case D

``` text
GWAS summary statistics with SNP, CHR, BP, A1, A2, BETA, P
```

------------------------------------------------------------------------

# 68. Intermediate Thinking Exercises

## Exercise 11 — Diagnose the Object

You receive:

``` r
x <- c(
  1.2,
  3.4,
  "NA",
  5.6
)
```

A colleague says:

``` r
mean(x)
```

does not work.

Without changing the object immediately:

1.  What functions would you run first?
2.  What do you expect `typeof(x)` to be?
3.  Why?
4.  How should a true missing numeric value have been represented?

------------------------------------------------------------------------

## Exercise 12 — Why Did the Matrix Break?

A researcher writes:

``` r
m <- matrix(
  c(
    10,
    20,
    30,
    "control",
    "case",
    "case"
  ),
  nrow = 3
)
```

They intended:

``` text
one numeric column
one group column
```

Explain why a matrix is the wrong structure.

Create a better representation.

------------------------------------------------------------------------

## Exercise 13 — Factor Conversion Error

A file produced:

``` r
dose <- factor(
  c(
    "10",
    "20",
    "30"
  )
)
```

Compare:

``` r
as.numeric(dose)
```

with:

``` r
as.numeric(
  as.character(dose)
)
```

Explain the difference.

------------------------------------------------------------------------

## Exercise 14 — Biological Alignment

You have:

``` r
colnames(expression)
```

equal to:

``` text
S1 S2 S3
```

but:

``` r
metadata$sample_id
```

equal to:

``` text
S2 S1 S3
```

Both contain three samples.

Why is that still a problem?

Do not solve the reordering yet; that belongs to later indexing/joining
lessons.

Explain only the structural issue.

------------------------------------------------------------------------

# 69. Challenge — Build a Structured Study Object

Create a small study object containing:

## A. Sample metadata

A data frame containing:

``` text
sample_id
age
tissue
case_control_status
```

## B. Expression matrix

A numeric matrix containing:

``` text
5 genes × 4 samples
```

with meaningful row and column names.

## C. Analysis settings

A list containing:

``` text
genome_build
minimum_expression
analysis_name
```

## D. Complete study object

Combine these into:

``` r
study <- list(
  metadata = ...,
  expression = ...,
  settings = ...
)
```

Then inspect:

``` r
class(study)
typeof(study)
length(study)
names(study)
str(study)
```

Finally, verify:

``` r
identical(
  colnames(study$expression),
  study$metadata$sample_id
)
```

Your goal is not advanced biological analysis.

Your goal is to demonstrate that you understand why different components
require different R data structures.

------------------------------------------------------------------------

# 70. Chapter Competency Check

Before moving to Chapter 4, you should be able to answer these questions
without guessing.

## Atomic vectors

- What makes a vector atomic?
- Why must all elements have one type?
- What happens when types are mixed?
- How do you create and inspect a vector?

## Matrices

- Why is a matrix homogeneous?
- How are dimensions stored?
- Why can one character value change an entire numeric matrix?

## Arrays

- How are arrays different from matrices?
- When is a third dimension meaningful?

## Lists

- Why can lists hold mixed objects?
- Why do many R functions return lists?

## Factors

- What are factor levels?
- Why is a factor usually backed by integer codes?
- Why can direct numeric conversion be dangerous?

## Data frames

- Why can columns have different types?
- Why is a data frame internally list-like?
- When should you choose a data frame over a matrix?

## Object inspection

You should be comfortable using:

``` r
typeof()
class()
str()
length()
names()
dim()
nrow()
ncol()
rownames()
colnames()
dimnames()
attributes()
levels()
```

------------------------------------------------------------------------

# 71. Key Takeaways

The most important ideas from this chapter are:

1.  **Data structure determines how R organizes values.**

2.  **Atomic vectors are one-dimensional and homogeneous.**

3.  **Matrices and arrays are homogeneous multidimensional structures.**

4.  **Lists are heterogeneous and can contain almost any R object.**

5.  **Factors represent categorical data using levels and underlying
    integer codes.**

6.  **Data frames are rectangular, list-like structures whose columns
    can have different types.**

7.  **Names, dimensions, levels, and classes are attributes that help R
    interpret values.**

8.  **`typeof()` and `class()` answer different questions.**

9.  **`str()` is one of the most useful functions for understanding
    unfamiliar objects.**

10. **Choosing the wrong structure can cause coercion, lost information,
    or scientifically incorrect alignment.**

11. **In computational biology, row names, column names, sample
    identifiers, and feature identifiers are part of data integrity—not
    cosmetic labels.**

------------------------------------------------------------------------

# 72. Repository Output from This Chapter

A practical Chapter 3 area could contain:

``` text
code/
└── 03_Mastering_R_Data_Structures/
    ├── 01_atomic_vectors.R
    ├── 02_matrices_and_arrays.R
    ├── 03_lists.R
    ├── 04_factors.R
    ├── 05_data_frames.R
    └── 06_structured_study_object.R

exercises/
└── chapter03/

projects/
└── beginner/
    └── structured_study_dataset/
```

Do not create separate scripts merely for appearance.

The purpose of the structure is to support meaningful practice.

------------------------------------------------------------------------

# References and Further Reading

## Essential Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

2.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

## Additional Reading

4.  Wickham H. *Advanced R*: chapters on vectors, attributes, and
    object-oriented systems.

5.  R Core Team. *R Language Definition*. R Foundation for Statistical
    Computing.

## Computational Biology Context

6.  Gentleman RC, Carey VJ, Bates DM, et al. Bioconductor: open software
    development for computational biology and bioinformatics. *Genome
    Biology*. 2004;5:R80.

7.  Huber W, Carey VJ, Gentleman R, et al. Orchestrating high-throughput
    genomic analysis with Bioconductor. *Nature Methods*.
    2015;12:115–121.

## Useful R Documentation

Explore:

``` r
?vector
?c
?matrix
?array
?list
?factor
?data.frame
?str
?typeof
?class
?attributes
?dim
```

Do not try to memorize every argument.

Practice reading the documentation and then testing the function on a
small object.

------------------------------------------------------------------------

# Next Chapter

## Chapter 4 — Indexing, Subsetting and Data Extraction

Now that we understand how R stores data, the next question is:

> How do we retrieve exactly the elements we want from these structures?

Chapter 4 will build carefully on this chapter and explain:

- positional indexing;
- negative indexing;
- logical indexing;
- named indexing;
- matrix row/column extraction;
- data-frame extraction;
- list extraction;
- `[`;
- `[[`;
- `$`;
- dimension dropping;
- safe filtering;
- and common subsetting mistakes.

The goal will be to learn not merely the syntax of indexing, but how the
**structure of the object determines what R returns**.
