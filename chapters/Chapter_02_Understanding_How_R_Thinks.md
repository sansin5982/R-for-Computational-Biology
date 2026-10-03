Chapter 2 — Understanding How R Thinks
================
Sandeep Kumar Singh, PhD

- [Chapter 2 — Understanding How R
  Thinks](#chapter-2--understanding-how-r-thinks)
  - [Where This Chapter Fits](#where-this-chapter-fits)
- [Learning Objectives](#learning-objectives)
- [1. R Evaluates Expressions](#1-r-evaluates-expressions)
- [2. Values](#2-values)
- [3. Objects and Names](#3-objects-and-names)
- [4. Why Do We Need Objects?](#4-why-do-we-need-objects)
- [5. Creating Objects with `<-`](#5-creating-objects-with--)
- [6. Assignment Does Not Normally Print the
  Value](#6-assignment-does-not-normally-print-the-value)
- [7. Can `=` Be Used for Assignment?](#7-can--be-used-for-assignment)
- [8. Assignment Is Not Comparison](#8-assignment-is-not-comparison)
- [9. Reassignment](#9-reassignment)
- [10. Objects Can Be Created from Other
  Objects](#10-objects-can-be-created-from-other-objects)
- [11. Reassignment Does Not Automatically Recalculate Dependent
  Objects](#11-reassignment-does-not-automatically-recalculate-dependent-objects)
- [12. Naming Objects](#12-naming-objects)
- [13. R Is Case Sensitive](#13-r-is-case-sensitive)
- [14. Inspecting Objects](#14-inspecting-objects)
- [15. `typeof()`](#15-typeof)
- [16. `class()`](#16-class)
- [17. `str()`](#17-str)
- [18. `length()`](#18-length)
- [19. Atomic Types](#19-atomic-types)
- [20. Logical Values](#20-logical-values)
- [21. Integer Values](#21-integer-values)
- [22. Double Values](#22-double-values)
- [23. Character Values](#23-character-values)
- [24. Complex and Raw Types](#24-complex-and-raw-types)
- [25. Type Testing Functions](#25-type-testing-functions)
- [26. Explicit Type Conversion](#26-explicit-type-conversion)
- [27. Coercion](#27-coercion)
- [28. A Simplified Coercion
  Hierarchy](#28-a-simplified-coercion-hierarchy)
- [29. Why Coercion Matters in Real
  Data](#29-why-coercion-matters-in-real-data)
- [30. General Coercion Example](#30-general-coercion-example)
  - [Logical + integer](#logical--integer)
  - [Integer + double](#integer--double)
  - [Numeric + character](#numeric--character)
- [31. Computational Biology Coercion
  Example](#31-computational-biology-coercion-example)
- [32. R Often Works on Whole
  Vectors](#32-r-often-works-on-whole-vectors)
- [33. Why Is Vectorization Useful?](#33-why-is-vectorization-useful)
- [34. Vectorized Arithmetic](#34-vectorized-arithmetic)
- [35. Vectorized Comparisons](#35-vectorized-comparisons)
- [36. Vectorized Functions](#36-vectorized-functions)
- [37. General Vectorization Example](#37-general-vectorization-example)
- [38. Computational Biology Vectorization
  Example](#38-computational-biology-vectorization-example)
- [39. Recycling](#39-recycling)
- [40. Why Does Recycling Exist?](#40-why-does-recycling-exist)
- [41. Recycling Can Also Be
  Dangerous](#41-recycling-can-also-be-dangerous)
- [42. Recycling in Scientific Code](#42-recycling-in-scientific-code)
- [43. Check Lengths Explicitly](#43-check-lengths-explicitly)
- [44. Missing Values: `NA`](#44-missing-values-na)
- [45. Why Does R Propagate Missing
  Values?](#45-why-does-r-propagate-missing-values)
- [46. Detect Missing Values with
  `is.na()`](#46-detect-missing-values-with-isna)
- [47. Why `x == NA` Does Not Work](#47-why-x--na-does-not-work)
- [48. Typed Missing Values](#48-typed-missing-values)
- [49. `NaN`](#49-nan)
- [50. Positive and Negative
  Infinity](#50-positive-and-negative-infinity)
- [51. A Computational Biology Example:
  `-log10(P)`](#51-a-computational-biology-example--log10p)
- [52. `NULL`](#52-null)
  - [`NA`](#na)
  - [`NULL`](#null)
- [53. `NULL` Versus an Empty Vector](#53-null-versus-an-empty-vector)
- [54. Summary of Special Values](#54-summary-of-special-values)
- [55. Attributes](#55-attributes)
- [56. Inspecting Attributes](#56-inspecting-attributes)
- [57. Names Are Attributes](#57-names-are-attributes)
- [58. Class Can Also Be an
  Attribute](#58-class-can-also-be-an-attribute)
- [59. Why Attributes Matter](#59-why-attributes-matter)
- [60. Do Not Modify Attributes
  Randomly](#60-do-not-modify-attributes-randomly)
- [61. Copy-on-Modify: Why This Concept
  Matters](#61-copy-on-modify-why-this-concept-matters)
- [62. Why Does This Happen?](#62-why-does-this-happen)
- [63. Why Copy-on-Modify Matters
  Later](#63-why-copy-on-modify-matters-later)
- [64. An Important Exception: Not Every R Object Behaves
  Identically](#64-an-important-exception-not-every-r-object-behaves-identically)
- [65. Floating-Point Numbers Are
  Approximate](#65-floating-point-numbers-are-approximate)
- [66. Comparing Floating-Point
  Results](#66-comparing-floating-point-results)
- [67. Expressions Return Values](#67-expressions-return-values)
- [68. Some Results Print, Others Are
  Stored](#68-some-results-print-others-are-stored)
- [69. General Example: Measurements](#69-general-example-measurements)
- [70. Computational Biology Example: Allele
  Frequencies](#70-computational-biology-example-allele-frequencies)
- [71. A Complete “How R Thinks”
  Example](#71-a-complete-how-r-thinks-example)
  - [What is the name?](#what-is-the-name)
  - [What value does it refer to?](#what-value-does-it-refer-to)
  - [What is the underlying type?](#what-is-the-underlying-type)
  - [What is the class?](#what-is-the-class)
  - [How many elements?](#how-many-elements)
  - [Which are missing?](#which-are-missing)
  - [Which observed values are at least
    30?](#which-observed-values-are-at-least-30)
  - [What is the mean?](#what-is-the-mean)
  - [Convert to a character object
    accidentally:](#convert-to-a-character-object-accidentally)
- [72. Common Mistakes](#72-common-mistakes)
  - [Mistake 1 — Thinking a Name and a Value Are the Same
    Thing](#mistake-1--thinking-a-name-and-a-value-are-the-same-thing)
  - [Mistake 2 — Expecting Spreadsheet-Style Automatic
    Recalculation](#mistake-2--expecting-spreadsheet-style-automatic-recalculation)
  - [Mistake 3 — Confusing Assignment and Equality
    Testing](#mistake-3--confusing-assignment-and-equality-testing)
  - [Mistake 4 — Thinking Every Number Is an
    Integer](#mistake-4--thinking-every-number-is-an-integer)
  - [Mistake 5 — Ignoring Automatic
    Coercion](#mistake-5--ignoring-automatic-coercion)
  - [Mistake 6 — Ignoring Recycling
    Warnings](#mistake-6--ignoring-recycling-warnings)
  - [Mistake 7 — Testing Missingness with
    `== NA`](#mistake-7--testing-missingness-with--na)
  - [Mistake 8 — Treating `NA`, `NaN`, `Inf`, and `NULL` as
    Equivalent](#mistake-8--treating-na-nan-inf-and-null-as-equivalent)
  - [Mistake 9 — Assuming `class()` and `typeof()` Should Always
    Match](#mistake-9--assuming-class-and-typeof-should-always-match)
  - [Mistake 10 — Comparing Floating-Point Results Using Exact Equality
    Automatically](#mistake-10--comparing-floating-point-results-using-exact-equality-automatically)
- [73. Debugging Clinic](#73-debugging-clinic)
  - [Problem 1 — Object Not Found](#problem-1--object-not-found)
  - [Problem 2 — Mean Does Not Work](#problem-2--mean-does-not-work)
  - [Problem 3 — Unexpected `NA`](#problem-3--unexpected-na)
  - [Problem 4 — Strange Result from Different Vector
    Lengths](#problem-4--strange-result-from-different-vector-lengths)
  - [Problem 5 — Value Looks Like a Number but Is
    Character](#problem-5--value-looks-like-a-number-but-is-character)
  - [Problem 6 — Exact Decimal Comparison
    Fails](#problem-6--exact-decimal-comparison-fails)
- [74. Performance Corner](#74-performance-corner)
- [75. Why Beginner Courses Often Skip These
  Ideas](#75-why-beginner-courses-often-skip-these-ideas)
- [76. Expert Commentary](#76-expert-commentary)
- [77. From the Reviewer’s
  Perspective](#77-from-the-reviewers-perspective)
- [78. Practice Questions — Basic
  Level](#78-practice-questions--basic-level)
- [79. Practical Exercises](#79-practical-exercises)
  - [Exercise 1 — Values and
    Assignment](#exercise-1--values-and-assignment)
  - [Exercise 2 — Reassignment](#exercise-2--reassignment)
  - [Exercise 3 — Integer Versus
    Double](#exercise-3--integer-versus-double)
  - [Exercise 4 — Type Coercion](#exercise-4--type-coercion)
  - [Exercise 5 — Explicit Conversion](#exercise-5--explicit-conversion)
  - [Exercise 6 — Vectorization](#exercise-6--vectorization)
  - [Exercise 7 — Recycling](#exercise-7--recycling)
  - [Exercise 8 — Missing Values](#exercise-8--missing-values)
  - [Exercise 9 — Special Values](#exercise-9--special-values)
  - [Exercise 10 — Attributes](#exercise-10--attributes)
  - [Exercise 11 — Copy-on-Modify](#exercise-11--copy-on-modify)
  - [Exercise 12 — Floating-Point
    Comparison](#exercise-12--floating-point-comparison)
- [80. Computational Biology
  Practice](#80-computational-biology-practice)
  - [Exercise 13 — Allele Frequencies](#exercise-13--allele-frequencies)
  - [Exercise 14 — Sequencing Depth Data
    Quality](#exercise-14--sequencing-depth-data-quality)
  - [Exercise 15 — Variant IDs and
    P-values](#exercise-15--variant-ids-and-p-values)
- [81. Intermediate Thinking
  Exercises](#81-intermediate-thinking-exercises)
  - [Exercise 16 — Diagnose a Character
    Conversion](#exercise-16--diagnose-a-character-conversion)
  - [Exercise 17 — Is Recycling
    Appropriate?](#exercise-17--is-recycling-appropriate)
  - [Exercise 18 — `NA`, `NaN`, or `Inf`?](#exercise-18--na-nan-or-inf)
    - [A](#a)
    - [B](#b)
    - [C](#c)
    - [D](#d)
- [82. Challenge — Build an R Object Inspection
  Notebook](#82-challenge--build-an-r-object-inspection-notebook)
  - [Part A — Ordinary objects](#part-a--ordinary-objects)
  - [Part B — Coercion experiments](#part-b--coercion-experiments)
  - [Part C — Vectorization](#part-c--vectorization)
  - [Part D — Recycling](#part-d--recycling)
  - [Part E — Missing and special
    values](#part-e--missing-and-special-values)
  - [Part F — Computational biology
    example](#part-f--computational-biology-example)
- [83. Chapter Competency Check](#83-chapter-competency-check)
- [84. Key Takeaways](#84-key-takeaways)
- [85. Repository Output from This
  Chapter](#85-repository-output-from-this-chapter)
- [References and Further Reading](#references-and-further-reading)
  - [Essential Reading](#essential-reading)
  - [Additional Reading](#additional-reading)
  - [Scientific Computing Context](#scientific-computing-context)
  - [Useful R Documentation](#useful-r-documentation)
- [Next Chapter](#next-chapter)
  - [Chapter 3 — Mastering R Data
    Structures](#chapter-3--mastering-r-data-structures)

# Chapter 2 — Understanding How R Thinks

## Where This Chapter Fits

Chapter 1 taught us how to work professionally with R:

``` text
R installation
      ↓
RStudio
      ↓
projects
      ↓
files and paths
      ↓
scripts
      ↓
packages
      ↓
documentation
      ↓
sessions and reproducibility
```

We are now ready to learn the R language itself.

Before learning large data structures, data manipulation, loops,
functions, or statistical models, we need a mental model of what R is
actually doing when we type code.

For example, consider:

``` r
x <- 10
```

A beginner may read this as:

> Put 10 into x.

That is useful at first, but it is incomplete.

We eventually need to understand:

``` text
What is x?
What is 10?
What does <- do?
What type of value is 10?
What changes if x is assigned another value?
What does R return when an expression is evaluated?
Why can TRUE become 1?
Why can a number become character?
Why does NA behave differently from NULL?
Why can x + c(1, 2) work even when the vectors have different lengths?
Why do class() and typeof() sometimes disagree?
```

These questions are not advanced trivia.

They explain many of the errors and surprises that beginners encounter
later.

This chapter therefore teaches **how R thinks about values, names,
types, operations, missingness, attributes, and evaluation**.

Chapter 3 will then build on these ideas and teach the major R data
structures in depth.

------------------------------------------------------------------------

# Learning Objectives

By the end of this chapter, you should be able to:

- explain the difference between a value, an object, and a name;
- create objects using assignment;
- explain what reassignment does;
- distinguish assignment from comparison;
- explain that R evaluates expressions and returns values;
- inspect objects with `typeof()`, `class()`, `str()`, and `length()`;
- recognize the major atomic types;
- distinguish integer and double values;
- explain automatic coercion;
- perform explicit type conversion safely;
- explain vectorized operations conceptually;
- understand R’s recycling rule;
- recognize when recycling is useful and when it is dangerous;
- distinguish `NA`, typed `NA`, `NaN`, `Inf`, `-Inf`, and `NULL`;
- test missing and special values correctly;
- understand why `x == NA` does not work as intended;
- explain what attributes are;
- understand the difference between underlying type and higher-level
  class;
- recognize the role of names and class attributes;
- understand copy-on-modify at a conceptual level;
- recognize the limitations of floating-point arithmetic;
- develop the habit of inspecting R objects rather than guessing.

------------------------------------------------------------------------

# 1. R Evaluates Expressions

Before discussing objects, it helps to understand one of the simplest
things R does:

> R evaluates expressions.

An **expression** is code that R can interpret and evaluate.

For example:

``` r
2 + 3
```

R evaluates the expression and returns:

``` text
5
```

Another expression:

``` r
10 * 4
```

returns:

``` text
40
```

We can think of this as:

``` text
R code
   ↓
evaluation
   ↓
value
```

This idea remains important throughout the course.

For example:

``` r
sqrt(25)
```

is evaluated and returns:

``` text
5
```

and:

``` r
10 > 5
```

is evaluated and returns:

``` text
TRUE
```

R is not simply “executing commands.”

Many pieces of R code are expressions that evaluate to values.

------------------------------------------------------------------------

# 2. Values

A **value** is the actual piece of information being represented.

Examples include:

``` r
10
```

``` r
3.14
```

``` r
TRUE
```

``` r
"BRCA1"
```

These represent different kinds of values.

For example:

``` r
10
```

is numeric.

``` r
TRUE
```

is logical.

``` r
"BRCA1"
```

is character.

Values can exist temporarily as the result of an expression:

``` r
10 + 20
```

returns the value:

``` text
30
```

But if we want to use a value again, we normally assign it a name.

------------------------------------------------------------------------

# 3. Objects and Names

Consider:

``` r
age <- 44
```

We now have a name:

``` text
age
```

associated with the value:

``` text
44
```

For beginner purposes, we can say:

> `age` is an R object containing the value 44.

A more precise mental model is:

``` text
name
age
 |
 v
value
44
```

The name lets us refer to the value later.

For example:

``` r
age + 1
```

R looks up the value associated with `age` and evaluates:

``` text
44 + 1
```

giving:

``` text
45
```

------------------------------------------------------------------------

# 4. Why Do We Need Objects?

Without objects, we would repeatedly type literal values.

For example:

``` r
(78.5 / (1.75 ^ 2))
```

This works.

But what does:

``` text
78.5
```

mean?

What does:

``` text
1.75
```

mean?

Using names makes the code understandable:

``` r
weight_kg <- 78.5
height_m <- 1.75

bmi <- weight_kg / (
  height_m ^ 2
)

bmi
```

Now the meaning is visible.

Good object names make code easier to:

- understand;
- reuse;
- debug;
- review;
- modify.

This becomes even more important in scientific code.

------------------------------------------------------------------------

# 5. Creating Objects with `<-`

The most common R assignment operator is:

``` r
<-
```

Example:

``` r
sample_size <- 120
```

Read this as:

> Assign the value 120 to the name `sample_size`.

Another example:

``` r
study_name <- "Example Study"
```

And:

``` r
passed_qc <- TRUE
```

After assignment, type the object name:

``` r
sample_size
```

R retrieves its value.

------------------------------------------------------------------------

# 6. Assignment Does Not Normally Print the Value

If you type:

``` r
sample_size <- 120
```

R normally performs the assignment without printing:

``` text
120
```

But:

``` r
sample_size
```

prints the value.

You can also write:

``` r
(sample_size <- 120)
```

The parentheses cause the resulting assigned value to be printed.

You do not need this pattern often as a beginner, but it demonstrates an
important point:

> Assignment itself is also part of R’s evaluation system.

------------------------------------------------------------------------

# 7. Can `=` Be Used for Assignment?

You may also see:

``` r
sample_size = 120
```

At the top level, this can assign a value.

However, this course will generally use:

``` r
<-
```

for ordinary object assignment.

Why?

Because `=` is also widely used for supplying named arguments inside
function calls:

``` r
mean(
  x,
  na.rm = TRUE
)
```

Using `<-` for assignment makes the visual distinction clearer:

``` r
sample_size <- 120
```

versus:

``` r
mean(
  x,
  na.rm = TRUE
)
```

This is a convention, not a claim that `=` is always invalid.

------------------------------------------------------------------------

# 8. Assignment Is Not Comparison

This distinction is essential.

Assignment:

``` r
x <- 10
```

means:

> associate the name `x` with the value 10.

Comparison:

``` r
x == 10
```

means:

> is the value represented by `x` equal to 10?

The result of:

``` r
x == 10
```

is logical:

``` text
TRUE
```

or:

``` text
FALSE
```

Do not confuse:

``` text
=
```

with:

``` text
==
```

In many beginner programming errors, assignment and comparison are mixed
up.

------------------------------------------------------------------------

# 9. Reassignment

An R name can be assigned another value.

Example:

``` r
x <- 10
```

Then:

``` r
x <- 20
```

Now:

``` r
x
```

returns:

``` text
20
```

The name `x` now refers to the new value.

Conceptually:

``` text
First:

x
|
v
10

Then:

x
|
v
20
```

The original script still contains both lines, so the **history of
instructions** remains visible in the script.

But the live object currently represented by `x` contains the newer
value.

------------------------------------------------------------------------

# 10. Objects Can Be Created from Other Objects

Example:

``` r
width <- 5
height <- 10

area <- width * height
```

Here:

``` text
width → 5
height → 10
```

Then R evaluates:

``` r
width * height
```

as:

``` r
5 * 10
```

and assigns the result:

``` text
50
```

to:

``` text
area
```

Now:

``` r
area
```

returns:

``` text
50
```

This is a fundamental programming pattern:

``` text
input objects
      ↓
calculation
      ↓
new object
```

------------------------------------------------------------------------

# 11. Reassignment Does Not Automatically Recalculate Dependent Objects

This is a very important beginner concept.

Run:

``` r
width <- 5
height <- 10

area <- width * height
```

Now change:

``` r
width <- 7
```

What is `area`?

``` r
area
```

It is still:

``` text
50
```

Why?

Because R evaluated:

``` r
width * height
```

when `area` was created.

R does not automatically create spreadsheet-like dependencies between
ordinary objects.

To update `area`, evaluate the calculation again:

``` r
area <- width * height
```

Now:

``` r
area
```

becomes:

``` text
70
```

This difference between R and spreadsheet software is worth
understanding early.

------------------------------------------------------------------------

# 12. Naming Objects

Good names should communicate meaning.

Weak:

``` r
x <- 53386
```

Better:

``` r
n_cases <- 53386
```

Weak:

``` r
p <- 5e-8
```

Better:

``` r
genome_wide_threshold <- 5e-8
```

Common R naming styles include:

``` text
snake_case
camelCase
```

This course will generally prefer:

``` text
snake_case
```

Examples:

``` r
sample_size
```

``` r
mean_expression
```

``` r
variant_count
```

Consistency matters more than arguing over every naming style.

------------------------------------------------------------------------

# 13. R Is Case Sensitive

These names are different:

``` r
sample
```

``` r
Sample
```

``` r
SAMPLE
```

Example:

``` r
sample_size <- 100
```

Then:

``` r
Sample_size
```

will not refer to the same object.

This matters when working with:

``` text
column names
gene identifiers
sample IDs
function names
file names
```

Always respect exact spelling and capitalization.

------------------------------------------------------------------------

# 14. Inspecting Objects

When you encounter an object, do not assume what it contains.

Useful inspection tools include:

``` r
typeof()
class()
str()
length()
```

Example:

``` r
sample_size <- 120
```

Inspect:

``` r
typeof(sample_size)
```

``` r
class(sample_size)
```

``` r
str(sample_size)
```

``` r
length(sample_size)
```

These functions answer different questions.

------------------------------------------------------------------------

# 15. `typeof()`

`typeof()` asks:

> What is the object’s underlying R type?

Example:

``` r
typeof(10)
```

Typically:

``` text
"double"
```

Example:

``` r
typeof(TRUE)
```

returns:

``` text
"logical"
```

Example:

``` r
typeof("BRCA1")
```

returns:

``` text
"character"
```

Understanding type helps explain what operations R can perform safely.

------------------------------------------------------------------------

# 16. `class()`

`class()` asks:

> What higher-level class does R use to interpret this object?

Example:

``` r
x <- 10
```

``` r
class(x)
```

usually returns:

``` text
"numeric"
```

while:

``` r
typeof(x)
```

returns:

``` text
"double"
```

These answers are not contradictory.

They describe different aspects of the object.

Later, this becomes especially important for:

``` text
factors
dates
model objects
GRanges
SummarizedExperiment
```

------------------------------------------------------------------------

# 17. `str()`

`str()` means:

``` text
structure
```

Example:

``` r
x <- 10

str(x)
```

For simple objects, the output is brief.

For complicated objects, `str()` becomes extremely valuable.

It tells us about:

- object type/class;
- length;
- dimensions;
- names;
- nested components.

A strong R habit is:

``` r
str(object)
```

whenever an unfamiliar object arrives from:

``` text
a file
a package
a statistical model
a collaborator
a Bioconductor function
```

------------------------------------------------------------------------

# 18. `length()`

`length()` reports how many elements an object contains at its current
level.

Example:

``` r
x <- 10
```

``` r
length(x)
```

returns:

``` text
1
```

Example:

``` r
x <- c(
  10,
  20,
  30
)
```

``` r
length(x)
```

returns:

``` text
3
```

Chapter 3 will examine how `length()` behaves across different data
structures.

------------------------------------------------------------------------

# 19. Atomic Types

At the lowest practical level, many R values belong to atomic types.

Important types include:

``` text
logical
integer
double
complex
character
raw
```

For everyday data analysis, the most common are:

``` text
logical
integer
double
character
```

We introduce them here because R’s behavior depends heavily on type.

Chapter 3 will teach atomic **vectors** and data structures in depth.

------------------------------------------------------------------------

# 20. Logical Values

Logical values are:

``` r
TRUE
```

and:

``` r
FALSE
```

Example:

``` r
passed <- TRUE
```

Inspect:

``` r
typeof(passed)
```

Expected:

``` text
"logical"
```

Comparisons also return logical values.

Example:

``` r
10 > 5
```

returns:

``` text
TRUE
```

Example:

``` r
10 == 20
```

returns:

``` text
FALSE
```

Logical values become central to:

- filtering;
- conditions;
- QC rules;
- missing-value checks.

------------------------------------------------------------------------

# 21. Integer Values

An integer is a whole number stored specifically as integer type.

Create one using:

``` r
10L
```

Check:

``` r
typeof(10L)
```

Expected:

``` text
"integer"
```

The `L` means that R should treat the literal as an integer.

Compare:

``` r
typeof(10)
```

This usually returns:

``` text
"double"
```

So:

``` text
10
```

and:

``` text
10L
```

look similar when printed, but their underlying R types differ.

------------------------------------------------------------------------

# 22. Double Values

Most ordinary numeric values in R are stored as:

``` text
double
```

Example:

``` r
weight <- 78.5
```

Check:

``` r
typeof(weight)
```

returns:

``` text
"double"
```

Even:

``` r
x <- 10
```

is normally stored as a double unless explicitly written as:

``` r
10L
```

In ordinary R conversation, doubles and integers are often both
described as:

``` text
numeric
```

Check:

``` r
is.numeric(10)
```

and:

``` r
is.numeric(10L)
```

Both are usually `TRUE`.

------------------------------------------------------------------------

# 23. Character Values

Text is represented using character values.

Example:

``` r
gene <- "TP53"
```

Inspect:

``` r
typeof(gene)
```

returns:

``` text
"character"
```

Quotation marks matter.

This:

``` r
"TP53"
```

means:

> the character string TP53.

But:

``` r
TP53
```

means:

> find an object whose name is `TP53`.

If no such object exists, R reports an error.

------------------------------------------------------------------------

# 24. Complex and Raw Types

R also supports:

``` text
complex
raw
```

Example:

``` r
z <- 2 + 3i

typeof(z)
```

returns:

``` text
"complex"
```

Raw values represent bytes.

Example:

``` r
charToRaw(
  "R"
)
```

These types are useful in specialized applications but are not central
to our early computational-biology workflow.

------------------------------------------------------------------------

# 25. Type Testing Functions

R provides many functions beginning with:

``` text
is.
```

Examples:

``` r
is.numeric(10)
```

``` r
is.integer(10L)
```

``` r
is.logical(TRUE)
```

``` r
is.character("TP53")
```

These answer questions about objects.

Example:

``` r
x <- "10"

is.numeric(x)
```

returns:

``` text
FALSE
```

even though the text looks like a number.

This difference becomes important during data import and cleaning.

------------------------------------------------------------------------

# 26. Explicit Type Conversion

R provides conversion functions beginning with:

``` text
as.
```

Examples:

``` r
as.numeric()
```

``` r
as.integer()
```

``` r
as.character()
```

``` r
as.logical()
```

Example:

``` r
x <- "10"

as.numeric(x)
```

returns numeric 10.

But:

``` r
as.numeric("ten")
```

cannot interpret the word as a number and produces a missing result with
a warning.

Therefore:

> type conversion is not merely changing a label; the value must be
> meaningfully convertible.

------------------------------------------------------------------------

# 27. Coercion

R sometimes converts values automatically.

This is called **coercion**.

Consider:

``` r
x <- c(
  1,
  2,
  3
)
```

These values can share a numeric type.

Now:

``` r
x <- c(
  1,
  2,
  "3"
)
```

An atomic vector cannot preserve some elements as numbers and another as
character.

R therefore chooses a common type.

Check:

``` r
typeof(x)
```

You should see:

``` text
"character"
```

The values become conceptually:

``` text
"1"
"2"
"3"
```

------------------------------------------------------------------------

# 28. A Simplified Coercion Hierarchy

A useful beginner model is:

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

If R needs one common atomic type, values can be promoted in this
general direction.

Example:

``` r
x <- c(
  TRUE,
  5L
)

typeof(x)
```

Likely:

``` text
"integer"
```

Why?

Because logical values can be represented numerically:

``` text
FALSE → 0
TRUE  → 1
```

Another example:

``` r
x <- c(
  5L,
  2.5
)

typeof(x)
```

Likely:

``` text
"double"
```

------------------------------------------------------------------------

# 29. Why Coercion Matters in Real Data

Suppose numeric measurements are:

``` r
measurement <- c(
  10.2,
  11.5,
  9.8
)
```

Now someone enters:

``` text
"not measured"
```

instead of a proper missing value.

If combined directly:

``` r
measurement <- c(
  10.2,
  11.5,
  "not measured"
)
```

the whole object may become character.

Then:

``` r
mean(measurement)
```

fails.

This is why inspection after importing real data is essential.

------------------------------------------------------------------------

# 30. General Coercion Example

Run each separately.

### Logical + integer

``` r
x <- c(
  TRUE,
  5L
)

x
typeof(x)
```

### Integer + double

``` r
x <- c(
  5L,
  2.5
)

x
typeof(x)
```

### Numeric + character

``` r
x <- c(
  5,
  "6"
)

x
typeof(x)
```

Before running each example, predict the result.

That prediction habit is more useful than memorizing rules passively.

------------------------------------------------------------------------

# 31. Computational Biology Coercion Example

Suppose sequencing depths should be numeric:

``` r
depth <- c(
  32,
  41,
  28,
  55
)

typeof(depth)
```

Now imagine the fourth value was recorded as:

``` text
"low"
```

``` r
depth_bad <- c(
  32,
  41,
  28,
  "low"
)

typeof(depth_bad)
```

The object becomes character.

That means the problem is no longer:

> How do I calculate mean sequencing depth?

The first problem is:

> Why does the supposed numeric variable contain a text category?

This is an example of distinguishing a **data-quality problem** from a
calculation problem.

------------------------------------------------------------------------

# 32. R Often Works on Whole Vectors

One of R’s defining strengths is **vectorized evaluation**.

Suppose:

``` r
x <- c(
  1,
  2,
  3,
  4
)
```

Run:

``` r
x * 10
```

R returns:

``` text
10 20 30 40
```

You did not explicitly write a loop.

R applies the arithmetic operation across the vector.

Conceptually:

``` text
1 × 10
2 × 10
3 × 10
4 × 10
```

This is called **vectorization**.

------------------------------------------------------------------------

# 33. Why Is Vectorization Useful?

Imagine 10,000 measurements.

Without vectorized thinking, a beginner may imagine writing:

``` text
multiply measurement 1
multiply measurement 2
multiply measurement 3
...
```

Instead:

``` r
measurements * 100
```

can operate on the complete vector.

Vectorized programming often produces code that is:

- shorter;
- clearer;
- closer to the mathematical idea;
- efficient.

But vectorization must still be understood.

It is not magic.

------------------------------------------------------------------------

# 34. Vectorized Arithmetic

Example:

``` r
x <- c(
  10,
  20,
  30
)

y <- c(
  1,
  2,
  3
)
```

Addition:

``` r
x + y
```

R performs element-wise addition:

``` text
10 + 1
20 + 2
30 + 3
```

Result:

``` text
11 22 33
```

Similarly:

``` r
x - y
```

``` r
x * y
```

``` r
x / y
```

These are element-wise operations.

Matrix multiplication is a different concept and will be introduced
later.

------------------------------------------------------------------------

# 35. Vectorized Comparisons

Comparisons are vectorized too.

Example:

``` r
p_values <- c(
  0.50,
  0.03,
  0.001,
  0.80
)

p_values < 0.05
```

Result conceptually:

``` text
FALSE
TRUE
TRUE
FALSE
```

This logical vector can later be used for filtering.

That is why understanding vectors and logical evaluation is fundamental
to data analysis in R.

------------------------------------------------------------------------

# 36. Vectorized Functions

Many functions naturally work on vectors.

Example:

``` r
x <- c(
  1,
  4,
  9,
  16
)

sqrt(x)
```

returns:

``` text
1 2 3 4
```

Similarly:

``` r
log(x)
```

operates on every element.

Not every R function behaves identically, so always check documentation.

But vectorized behavior is common throughout R.

------------------------------------------------------------------------

# 37. General Vectorization Example

Suppose temperature is recorded in Celsius:

``` r
temp_c <- c(
  20,
  25,
  30,
  35
)
```

Convert to Fahrenheit:

``` r
temp_f <- (
  temp_c * 9 / 5
) + 32

temp_f
```

One expression processes every value.

------------------------------------------------------------------------

# 38. Computational Biology Vectorization Example

Suppose allele frequencies are:

``` r
af <- c(
  0.12,
  0.04,
  0.31,
  0.48
)
```

Convert to percentages:

``` r
af_percent <- af * 100

af_percent
```

Check a threshold:

``` r
af >= 0.05
```

The output is one logical value for each variant.

This is a common R programming pattern.

------------------------------------------------------------------------

# 39. Recycling

What happens when vectors have different lengths?

Consider:

``` r
x <- c(
  1,
  2,
  3,
  4
)

y <- c(
  10,
  20
)

x + y
```

R reuses, or **recycles**, the shorter vector.

Conceptually:

``` text
x: 1   2   3   4
y: 10  20  10  20
```

Result:

``` text
11 22 13 24
```

This is called the **recycling rule**.

------------------------------------------------------------------------

# 40. Why Does Recycling Exist?

Recycling allows expressions such as:

``` r
x + 10
```

to work naturally.

The value:

``` text
10
```

has length 1.

R conceptually reuses it:

``` text
x:  1  2  3  4
10: 10 10 10 10
```

This is extremely useful.

Without recycling, simple vectorized arithmetic with constants would
require extra work.

------------------------------------------------------------------------

# 41. Recycling Can Also Be Dangerous

Consider:

``` r
x <- c(
  1,
  2,
  3,
  4,
  5
)

y <- c(
  10,
  20
)

x + y
```

The longer length is:

``` text
5
```

The shorter length is:

``` text
2
```

Two does not divide evenly into five.

R may produce a warning about incompatible recycling.

Warnings should not be ignored.

The result may still be returned, but the question should be:

> Did I really intend these vectors to have different lengths?

------------------------------------------------------------------------

# 42. Recycling in Scientific Code

Suppose:

``` r
beta <- c(
  0.10,
  -0.20,
  0.30,
  0.05
)
```

and:

``` r
scale_factor <- 100
```

Then:

``` r
beta * scale_factor
```

is sensible.

But suppose sample-specific scaling factors accidentally contain:

``` r
scale_factor <- c(
  100,
  200,
  300
)
```

while `beta` has four values.

Now a recycling warning signals a possible alignment error.

In scientific computing, mismatched lengths should be investigated
rather than “fixed” automatically.

------------------------------------------------------------------------

# 43. Check Lengths Explicitly

Useful:

``` r
length(x)
```

and:

``` r
length(y)
```

You can test:

``` r
length(x) == length(y)
```

Later, more sophisticated alignment will use:

``` text
names
IDs
joins
indices
dimensions
```

For now, learn this habit:

> Before combining two biological vectors element by element, confirm
> that their relationship is understood.

------------------------------------------------------------------------

# 44. Missing Values: `NA`

Real data are often incomplete.

R represents a missing value using:

``` r
NA
```

Example:

``` r
age <- c(
  34,
  41,
  NA,
  29
)
```

This means:

``` text
one age value is missing
```

It does not mean zero.

It does not mean an empty string.

It does not mean “not applicable” automatically.

It means the value is missing or unknown in this context.

------------------------------------------------------------------------

# 45. Why Does R Propagate Missing Values?

Consider:

``` r
x <- c(
  10,
  20,
  NA
)
```

Now:

``` r
mean(x)
```

returns:

``` text
NA
```

Why?

Because the mean cannot be fully determined if one value is unknown.

If the analysis justifiably intends to remove missing values:

``` r
mean(
  x,
  na.rm = TRUE
)
```

returns the mean of the observed values.

The important word is:

> justifiably

Do not automatically remove missing data simply to make functions run.

Missingness can itself be scientifically important.

------------------------------------------------------------------------

# 46. Detect Missing Values with `is.na()`

Correct:

``` r
is.na(x)
```

Example:

``` r
x <- c(
  10,
  NA,
  30
)

is.na(x)
```

Result:

``` text
FALSE TRUE FALSE
```

Count missing values:

``` r
sum(
  is.na(x)
)
```

Check whether any are missing:

``` r
anyNA(x)
```

These are common data-quality operations.

------------------------------------------------------------------------

# 47. Why `x == NA` Does Not Work

A common beginner mistake is:

``` r
x == NA
```

Suppose:

``` r
x <- c(
  10,
  NA,
  30
)
```

Then:

``` r
x == NA
```

does not tell us which values are missing.

Why?

Because `NA` represents an unknown value.

The question:

``` text
Is 10 equal to an unknown value?
```

cannot be answered definitively.

Likewise:

``` text
Is an unknown value equal to an unknown value?
```

is still unknown.

Use:

``` r
is.na(x)
```

instead.

------------------------------------------------------------------------

# 48. Typed Missing Values

R has missing values associated with particular atomic types.

Examples include:

``` r
NA_integer_
```

``` r
NA_real_
```

``` r
NA_character_
```

``` r
NA_complex_
```

Example:

``` r
typeof(
  NA_integer_
)
```

returns:

``` text
"integer"
```

and:

``` r
typeof(
  NA_character_
)
```

returns:

``` text
"character"
```

This becomes relevant when constructing typed vectors and programming
functions.

You do not need to use typed `NA` constantly as a beginner, but it is
useful to know that missingness still exists within R’s type system.

------------------------------------------------------------------------

# 49. `NaN`

`NaN` means:

``` text
Not a Number
```

It represents an undefined numeric result.

Example:

``` r
0 / 0
```

returns:

``` text
NaN
```

Check:

``` r
is.nan(
  0 / 0
)
```

A `NaN` is also considered missing by:

``` r
is.na()
```

Try:

``` r
is.na(
  NaN
)
```

This usually returns:

``` text
TRUE
```

But not every `NA` is `NaN`.

------------------------------------------------------------------------

# 50. Positive and Negative Infinity

Example:

``` r
1 / 0
```

returns:

``` text
Inf
```

And:

``` r
-1 / 0
```

returns:

``` text
-Inf
```

Test:

``` r
is.infinite(
  1 / 0
)
```

Infinity is not the same as `NA`.

For example:

``` r
is.na(
  Inf
)
```

is generally:

``` text
FALSE
```

These distinctions matter when mathematical transformations produce
unexpected values.

------------------------------------------------------------------------

# 51. A Computational Biology Example: `-log10(P)`

Genome-wide association and other omics plots often use:

``` r
-log10(p_value)
```

Example:

``` r
p <- c(
  0.05,
  1e-4,
  5e-8
)

-log10(p)
```

But consider:

``` r
p <- c(
  0.05,
  0
)
```

Then:

``` r
-log10(p)
```

produces:

``` text
Inf
```

for:

``` text
p = 0
```

This may occur when extremely small P-values are stored as zero because
of numeric underflow or output formatting.

The correct response is not simply:

> delete infinity.

The correct first question is:

> Why is the P-value recorded as zero, and what does the source
> software/documentation say?

This is an example of R behavior interacting with scientific data
interpretation.

------------------------------------------------------------------------

# 52. `NULL`

`NULL` is different from `NA`.

This distinction is fundamental.

### `NA`

means roughly:

> a value should exist here, but it is missing/unknown.

### `NULL`

often means:

> there is no value/object/component here.

Example:

``` r
x <- NULL
```

Inspect:

``` r
typeof(x)
```

``` r
length(x)
```

`NULL` has length zero.

Compare:

``` r
length(
  NA
)
```

which is:

``` text
1
```

So:

``` text
NA
```

is a missing element.

``` text
NULL
```

represents absence.

------------------------------------------------------------------------

# 53. `NULL` Versus an Empty Vector

Also distinguish:

``` r
NULL
```

from:

``` r
numeric(0)
```

Both may have length zero, but they are different objects.

Check:

``` r
typeof(NULL)
```

and:

``` r
typeof(
  numeric(0)
)
```

This distinction becomes more important when writing functions and
working with lists.

For now, simply learn:

> missing, undefined, infinite, empty, and absent are not all the same
> concept in R.

------------------------------------------------------------------------

# 54. Summary of Special Values

| Value  | Meaning                             |
|--------|-------------------------------------|
| `NA`   | Missing/unknown value               |
| `NaN`  | Undefined numeric result            |
| `Inf`  | Positive infinity                   |
| `-Inf` | Negative infinity                   |
| `NULL` | Absence of a value/object/component |

Useful tests:

``` r
is.na()
```

``` r
is.nan()
```

``` r
is.infinite()
```

``` r
is.null()
```

------------------------------------------------------------------------

# 55. Attributes

An R object can carry additional metadata called **attributes**.

Attributes do not necessarily change the raw underlying values.

They tell R something about how those values should be interpreted.

Common attributes include:

``` text
names
dim
dimnames
class
levels
```

Attributes are one of the key mechanisms through which R builds richer
objects from simpler underlying values.

------------------------------------------------------------------------

# 56. Inspecting Attributes

Example:

``` r
x <- c(
  10,
  20,
  30
)

attributes(x)
```

A plain unnamed vector may have:

``` text
NULL
```

attributes.

Now add names:

``` r
names(x) <- c(
  "A",
  "B",
  "C"
)

attributes(x)
```

Now the object has a:

``` text
names
```

attribute.

The underlying numeric values have not changed.

But additional metadata now exists.

------------------------------------------------------------------------

# 57. Names Are Attributes

Example:

``` r
gene_expression <- c(
  BRCA1 = 10.2,
  TP53 = 8.4,
  APOE = 4.7
)
```

Inspect:

``` r
names(
  gene_expression
)
```

and:

``` r
attributes(
  gene_expression
)
```

The names tell us which value corresponds to which gene.

That makes the object safer and easier to interpret than relying only on
positions.

------------------------------------------------------------------------

# 58. Class Can Also Be an Attribute

Consider:

``` r
today <- as.Date(
  "2026-10-03"
)
```

Inspect:

``` r
typeof(today)
```

and:

``` r
class(today)
```

The underlying type may be numeric-like, but the class tells R:

> interpret this value as a date.

Try:

``` r
attributes(today)
```

This shows how higher-level meaning can be added to underlying storage.

This is why:

``` r
typeof()
```

and:

``` r
class()
```

can legitimately return different answers.

------------------------------------------------------------------------

# 59. Why Attributes Matter

Attributes underpin many important R structures.

Conceptually:

``` text
numeric vector
+
names
=
named numeric vector
```

``` text
atomic vector
+
dim
=
matrix
```

``` text
integer vector
+
levels
+
class = "factor"
=
factor
```

These structures will be taught properly in Chapter 3.

For now, the important principle is:

> R frequently builds richer objects by combining underlying values with
> metadata.

------------------------------------------------------------------------

# 60. Do Not Modify Attributes Randomly

You can manipulate attributes directly:

``` r
attr(
  x,
  "something"
) <- "value"
```

But direct attribute modification should not be treated as a casual
beginner technique.

Specialized classes may rely on internal consistency.

Whenever a class provides a documented constructor or accessor, prefer
that interface.

Later, this becomes especially important with Bioconductor S4 objects.

------------------------------------------------------------------------

# 61. Copy-on-Modify: Why This Concept Matters

Consider:

``` r
x <- c(
  1,
  2,
  3
)

y <- x
```

Now:

``` r
y
```

contains the same values.

Then change:

``` r
y[1] <- 100
```

What happens to `x`?

Check:

``` r
x
```

You should see:

``` text
1 2 3
```

while:

``` r
y
```

is:

``` text
100 2 3
```

Changing `y` did not change `x`.

This is the practical behavior beginners need to understand.

------------------------------------------------------------------------

# 62. Why Does This Happen?

A useful beginner mental model is:

> R behaves as though an object is copied when a modification needs to
> make one binding differ from another.

This is often called **copy-on-modify** behavior.

The internal memory implementation is more sophisticated than “always
copy immediately.”

R may share memory until modification makes separation necessary.

We do not need the full memory model yet.

The useful behavior is:

``` text
x <- original value
y <- x

modify y

x remains unchanged
y gets modified value
```

------------------------------------------------------------------------

# 63. Why Copy-on-Modify Matters Later

For small objects, you rarely notice memory consequences.

For large objects, such as:

``` text
millions of GWAS variants
large expression matrices
large genomic tables
```

unnecessary copies can consume substantial memory.

Later, in the performance chapter, we will revisit:

``` r
object.size()
```

``` r
tracemem()
```

and memory-aware programming.

At this stage, understand the behavior conceptually.

------------------------------------------------------------------------

# 64. An Important Exception: Not Every R Object Behaves Identically

Some R systems intentionally provide different reference-like semantics.

Examples include:

``` text
environments
R6 objects
data.table in certain operations
```

We will not study those deeply yet.

The reason to mention them is to avoid turning a useful beginner mental
model into an absolute law.

For most ordinary atomic vectors, lists, data frames, and related base
objects, copy-on-modify is the right early mental model.

------------------------------------------------------------------------

# 65. Floating-Point Numbers Are Approximate

This is another important concept that beginner courses often skip.

Try:

``` r
0.1 + 0.2
```

You may expect exactly:

``` text
0.3
```

Now test:

``` r
0.1 + 0.2 == 0.3
```

Depending on floating-point representation, this may be:

``` text
FALSE
```

Why?

Because many decimal fractions cannot be represented exactly in binary
floating-point arithmetic.

R is not uniquely broken here.

This is a general property of computer arithmetic.

------------------------------------------------------------------------

# 66. Comparing Floating-Point Results

For approximate numeric equality, use tools such as:

``` r
all.equal(
  0.1 + 0.2,
  0.3
)
```

This asks whether values are equal within a reasonable numeric
tolerance.

This matters later for:

- statistical calculations;
- simulations;
- optimization;
- unit tests.

Do not compare every computed decimal value using exact `==` without
understanding the implications.

------------------------------------------------------------------------

# 67. Expressions Return Values

Consider:

``` r
x <- 5

y <- x * 2
```

The expression:

``` r
x * 2
```

evaluates to:

``` text
10
```

That returned value is then assigned to:

``` r
y
```

Functions also return values.

Example:

``` r
mean(
  c(
    10,
    20,
    30
  )
)
```

returns:

``` text
20
```

We can store that:

``` r
mean_value <- mean(
  c(
    10,
    20,
    30
  )
)
```

Understanding returned values is essential before we write our own
functions in Chapter 5.

------------------------------------------------------------------------

# 68. Some Results Print, Others Are Stored

Compare:

``` r
2 + 3
```

R prints the result because the expression is evaluated interactively.

Now:

``` r
x <- 2 + 3
```

R stores the result in `x`.

Then:

``` r
x
```

prints it.

This distinction between:

``` text
evaluation
assignment
printing
returning
```

will become more important later.

For now, understand that these are separate concepts.

------------------------------------------------------------------------

# 69. General Example: Measurements

Create:

``` r
measurements <- c(
  10,
  20,
  30,
  NA
)
```

Inspect:

``` r
typeof(measurements)
```

``` r
class(measurements)
```

``` r
length(measurements)
```

``` r
str(measurements)
```

Multiply:

``` r
measurements * 2
```

Check missingness:

``` r
is.na(measurements)
```

Mean with missing value:

``` r
mean(measurements)
```

Mean after explicitly removing missing values:

``` r
mean(
  measurements,
  na.rm = TRUE
)
```

This one small example demonstrates:

``` text
object
type
length
vectorization
missing values
function arguments
returned values
```

------------------------------------------------------------------------

# 70. Computational Biology Example: Allele Frequencies

Suppose:

``` r
allele_frequency <- c(
  0.12,
  0.04,
  NA,
  0.31
)
```

Inspect:

``` r
typeof(
  allele_frequency
)
```

Check missing values:

``` r
is.na(
  allele_frequency
)
```

Convert to percentages:

``` r
af_percent <- allele_frequency * 100

af_percent
```

Check frequencies above 5%:

``` r
allele_frequency >= 0.05
```

Because one value is missing, the logical result for that position is
also missing.

This demonstrates a key principle:

> Missing information propagates when R cannot determine a result.

Now create variant identifiers:

``` r
variant_id <- c(
  "rs1",
  "rs2",
  "rs3",
  "rs4"
)
```

Check lengths:

``` r
length(
  variant_id
)
```

``` r
length(
  allele_frequency
)
```

Then:

``` r
length(
  variant_id
) == length(
  allele_frequency
)
```

Equal length does **not** prove that identifiers and values are
correctly aligned.

That requires stronger checks later.

But it is a useful first structural check.

------------------------------------------------------------------------

# 71. A Complete “How R Thinks” Example

Run this slowly.

``` r
sample_depth <- c(
  20,
  35,
  42,
  NA
)
```

Ask:

### What is the name?

``` text
sample_depth
```

### What value does it refer to?

A vector containing four elements.

### What is the underlying type?

``` r
typeof(
  sample_depth
)
```

### What is the class?

``` r
class(
  sample_depth
)
```

### How many elements?

``` r
length(
  sample_depth
)
```

### Which are missing?

``` r
is.na(
  sample_depth
)
```

### Which observed values are at least 30?

``` r
sample_depth >= 30
```

### What is the mean?

``` r
mean(
  sample_depth,
  na.rm = TRUE
)
```

### Convert to a character object accidentally:

``` r
depth_bad <- c(
  sample_depth,
  "unknown"
)
```

Inspect:

``` r
typeof(
  depth_bad
)
```

This sequence connects the entire chapter.

------------------------------------------------------------------------

# 72. Common Mistakes

## Mistake 1 — Thinking a Name and a Value Are the Same Thing

``` r
x <- 10
```

`x` is the name used to refer to a value.

Understanding this distinction becomes important for reassignment and
functions.

------------------------------------------------------------------------

## Mistake 2 — Expecting Spreadsheet-Style Automatic Recalculation

``` r
x <- 10
y <- x * 2
x <- 20
```

`y` remains 20 until its expression is evaluated again.

------------------------------------------------------------------------

## Mistake 3 — Confusing Assignment and Equality Testing

Assignment:

``` r
x <- 10
```

Comparison:

``` r
x == 10
```

These do different things.

------------------------------------------------------------------------

## Mistake 4 — Thinking Every Number Is an Integer

``` r
typeof(
  10
)
```

usually gives:

``` text
double
```

Use:

``` r
10L
```

for an explicit integer literal.

------------------------------------------------------------------------

## Mistake 5 — Ignoring Automatic Coercion

``` r
c(
  1,
  2,
  "3"
)
```

becomes character.

This can make later numeric operations fail.

------------------------------------------------------------------------

## Mistake 6 — Ignoring Recycling Warnings

A warning about vector lengths may indicate a real alignment problem.

Do not silence it without understanding it.

------------------------------------------------------------------------

## Mistake 7 — Testing Missingness with `== NA`

Wrong:

``` r
x == NA
```

Correct:

``` r
is.na(x)
```

------------------------------------------------------------------------

## Mistake 8 — Treating `NA`, `NaN`, `Inf`, and `NULL` as Equivalent

They represent different states.

Use the correct test for each.

------------------------------------------------------------------------

## Mistake 9 — Assuming `class()` and `typeof()` Should Always Match

They answer different questions.

------------------------------------------------------------------------

## Mistake 10 — Comparing Floating-Point Results Using Exact Equality Automatically

Use:

``` r
all.equal()
```

when approximate equality is appropriate.

------------------------------------------------------------------------

# 73. Debugging Clinic

## Problem 1 — Object Not Found

Error:

``` text
object 'sample_size' not found
```

Check:

``` r
ls()
```

and the script execution order.

Possible causes include:

``` text
object never created
different capitalization
misspelled name
script run out of order
clean session exposed hidden dependency
```

------------------------------------------------------------------------

## Problem 2 — Mean Does Not Work

Suppose:

``` r
x <- c(
  10,
  20,
  "missing"
)
```

Then:

``` r
mean(x)
```

fails.

Do not immediately change `mean()`.

Inspect:

``` r
typeof(x)
str(x)
```

The problem is the object type.

------------------------------------------------------------------------

## Problem 3 — Unexpected `NA`

Suppose:

``` r
x <- c(
  10,
  NA,
  30
)

x > 20
```

The result includes:

``` text
NA
```

This is not a software error.

R cannot determine whether an unknown value is greater than 20.

------------------------------------------------------------------------

## Problem 4 — Strange Result from Different Vector Lengths

Inspect:

``` r
length(x)
length(y)
```

Then determine whether recycling was intended.

In scientific data, do not assume it was.

------------------------------------------------------------------------

## Problem 5 — Value Looks Like a Number but Is Character

Example:

``` r
x <- "10"
```

Inspect:

``` r
typeof(x)
```

If conversion is intended:

``` r
as.numeric(x)
```

But ask why the data were character in the first place.

------------------------------------------------------------------------

## Problem 6 — Exact Decimal Comparison Fails

Instead of assuming R calculated incorrectly:

``` r
0.1 + 0.2 == 0.3
```

try:

``` r
all.equal(
  0.1 + 0.2,
  0.3
)
```

The issue is floating-point representation.

------------------------------------------------------------------------

# 74. Performance Corner

This chapter is mostly about correctness and mental models, not
optimization.

However, several concepts introduced here will later affect performance:

``` text
vectorization
copy-on-modify
object type
object size
temporary objects
```

A vectorized expression can often be faster and clearer than repeated
scalar operations.

But vectorization can also create large temporary objects.

Copy-on-modify can matter when large objects are changed repeatedly.

These issues will be measured properly in later performance chapters.

For now:

> First understand what R is doing. Then optimize only when measurement
> shows that optimization is necessary.

------------------------------------------------------------------------

# 75. Why Beginner Courses Often Skip These Ideas

Many introductory R courses quickly move to:

``` text
data frames
ggplot2
dplyr
statistical tests
```

because those produce useful outputs quickly.

But skipping the underlying language model causes later confusion.

A learner may know how to type:

``` r
filter()
```

without understanding:

``` text
what object entered the function
what type its columns have
why NA propagated
why a comparison returned logical values
why coercion occurred
why a vector was recycled
why class differs from typeof
```

This chapter deliberately slows down before speeding up later.

The aim is not theoretical complexity.

The aim is to make later R programming easier.

------------------------------------------------------------------------

# 76. Expert Commentary

Experienced R programmers routinely ask questions like:

``` text
What object is this?
What is its underlying type?
What is its class?
What is its length?
What attributes does it carry?
Is missingness present?
Is coercion occurring?
Are two vectors aligned?
Did recycling happen?
```

They do not rely only on how an object prints.

This is why inspection tools such as:

``` r
typeof()
class()
str()
length()
attributes()
is.na()
```

will recur throughout the course.

A good R programmer does not merely know many functions.

A good R programmer understands the objects those functions receive and
return.

------------------------------------------------------------------------

# 77. From the Reviewer’s Perspective

Suppose a scientific script creates:

``` r
p_values <- c(
  0.01,
  0.20,
  "missing"
)
```

The object silently becomes character.

Later code may fail or, worse, perform inappropriate conversion.

A reviewer should care because object type is not only a software
detail.

It can influence:

``` text
filtering
sorting
mathematical operations
missing-value handling
model input
scientific interpretation
```

Similarly, unexpected recycling could combine values that do not belong
together.

Understanding R’s internal behavior is therefore part of scientific
reproducibility.

------------------------------------------------------------------------

# 78. Practice Questions — Basic Level

1.  What does it mean when we say R evaluates an expression?
2.  What is a value?
3.  What is an object?
4.  What is a name?
5.  What does `<-` do?
6.  What is reassignment?
7.  Does changing `x` automatically recalculate an object previously
    created from `x`?
8.  What is the difference between `<-` and `==`?
9.  Why does this course generally use `<-` for object assignment?
10. Is R case sensitive?
11. What does `typeof()` tell us?
12. What does `class()` tell us?
13. What does `str()` do?
14. What does `length()` report?
15. What are the four most common atomic types in ordinary data
    analysis?
16. What is a logical value?
17. What is the difference between `10` and `10L`?
18. What does `typeof(10)` normally return?
19. Why must character strings be quoted?
20. What is coercion?
21. Why can `c(1, "2")` become character?
22. What does `as.numeric()` do?
23. Why can `as.numeric("ten")` not produce the intended number?
24. What does vectorized evaluation mean?
25. What happens in `c(1,2,3) * 10`?
26. What is recycling?
27. Why is recycling a useful R feature?
28. Why can recycling also be dangerous?
29. What does `NA` mean?
30. Why does `mean(c(1, NA))` return `NA` by default?
31. How do you test for missing values?
32. Why should you not use `x == NA`?
33. What is `NaN`?
34. What is `Inf`?
35. What is `NULL`?
36. How is `NULL` different from `NA`?
37. What is an attribute?
38. What kinds of information can attributes store?
39. Why can `class()` and `typeof()` differ?
40. What is copy-on-modify conceptually?
41. If `y <- x` and then `y` is modified, should ordinary `x` also
    change?
42. Why can floating-point equality be surprising?
43. What does `all.equal()` help with?
44. Why should warnings about vector recycling be investigated?
45. Why is understanding object type relevant to scientific analysis?

------------------------------------------------------------------------

# 79. Practical Exercises

## Exercise 1 — Values and Assignment

Create:

``` r
age <- 25
name <- "Alex"
passed <- TRUE
```

For each object, run:

``` r
typeof()
class()
str()
length()
```

Write down what each function tells you.

------------------------------------------------------------------------

## Exercise 2 — Reassignment

Run:

``` r
x <- 10
y <- x * 2
```

Then:

``` r
x <- 20
```

Check:

``` r
x
y
```

Explain why `y` did not change automatically.

Then recalculate:

``` r
y <- x * 2
```

------------------------------------------------------------------------

## Exercise 3 — Integer Versus Double

Compare:

``` r
x <- 10
y <- 10L
```

Run:

``` r
typeof(x)
typeof(y)

class(x)
class(y)

is.numeric(x)
is.numeric(y)
```

Explain the differences.

------------------------------------------------------------------------

## Exercise 4 — Type Coercion

Predict before running:

``` r
c(
  TRUE,
  FALSE,
  5L
)
```

Then:

``` r
c(
  1L,
  2.5
)
```

Then:

``` r
c(
  1,
  "2"
)
```

Inspect with:

``` r
typeof()
```

------------------------------------------------------------------------

## Exercise 5 — Explicit Conversion

Create:

``` r
x <- c(
  "10",
  "20",
  "30"
)
```

Run:

``` r
as.numeric(x)
```

Then try:

``` r
as.numeric(
  c(
    "10",
    "twenty",
    "30"
  )
)
```

Read the warning carefully.

------------------------------------------------------------------------

## Exercise 6 — Vectorization

Create:

``` r
x <- c(
  2,
  4,
  6,
  8
)
```

Calculate:

``` r
x + 10
x * 2
x ^ 2
sqrt(x)
x > 5
```

Explain which operations produce numeric values and which produce
logical values.

------------------------------------------------------------------------

## Exercise 7 — Recycling

Create:

``` r
x <- c(
  1,
  2,
  3,
  4
)

y <- c(
  10,
  20
)
```

Run:

``` r
x + y
```

Write out the recycled form of `y` manually.

Then try:

``` r
z <- c(
  10,
  20,
  30
)

x + z
```

Read any warning.

------------------------------------------------------------------------

## Exercise 8 — Missing Values

Create:

``` r
x <- c(
  10,
  NA,
  30,
  NA
)
```

Run:

``` r
is.na(x)
sum(is.na(x))
anyNA(x)
mean(x)
mean(x, na.rm = TRUE)
```

Explain each result.

------------------------------------------------------------------------

## Exercise 9 — Special Values

Run:

``` r
0 / 0
1 / 0
-1 / 0
```

Then test:

``` r
is.nan(0 / 0)
is.infinite(1 / 0)
is.na(NaN)
is.null(NULL)
```

Explain why these concepts are not interchangeable.

------------------------------------------------------------------------

## Exercise 10 — Attributes

Create:

``` r
x <- c(
  A = 10,
  B = 20,
  C = 30
)
```

Run:

``` r
attributes(x)
names(x)
```

Then remove names:

``` r
names(x) <- NULL
```

Inspect again.

Did the numeric values change?

------------------------------------------------------------------------

## Exercise 11 — Copy-on-Modify

Run:

``` r
x <- c(
  1,
  2,
  3
)

y <- x

y[1] <- 100
```

Inspect:

``` r
x
y
```

Explain what happened.

------------------------------------------------------------------------

## Exercise 12 — Floating-Point Comparison

Run:

``` r
0.1 + 0.2
```

Then:

``` r
0.1 + 0.2 == 0.3
```

Then:

``` r
all.equal(
  0.1 + 0.2,
  0.3
)
```

Explain why the last comparison is useful.

------------------------------------------------------------------------

# 80. Computational Biology Practice

## Exercise 13 — Allele Frequencies

Create:

``` r
af <- c(
  0.12,
  0.04,
  NA,
  0.31,
  0.55
)
```

Answer using R:

1.  What is the type?
2.  How many values exist?
3.  Which values are missing?
4.  Which observed values are at least 0.05?
5.  Convert frequencies to percentages.
6.  Calculate mean frequency while explicitly handling missingness.

Do not interpret these as population-genetic results. This is an R
exercise.

------------------------------------------------------------------------

## Exercise 14 — Sequencing Depth Data Quality

Create:

``` r
depth <- c(
  35,
  42,
  "low",
  28
)
```

Before calculating anything:

1.  inspect `typeof(depth)`;
2.  inspect `str(depth)`;
3.  explain why the object is not numeric;
4.  explain why replacing `"low"` blindly with a number would be
    scientifically questionable;
5.  suggest what information you would need before correcting the source
    data.

------------------------------------------------------------------------

## Exercise 15 — Variant IDs and P-values

Create:

``` r
variant_id <- c(
  "rs1",
  "rs2",
  "rs3",
  "rs4"
)

p_value <- c(
  0.20,
  0.01,
  5e-8,
  NA
)
```

Check:

``` r
length(variant_id)
length(p_value)
```

Then:

``` r
length(variant_id) ==
  length(p_value)
```

Explain why equal lengths are necessary but do not prove correct
alignment.

------------------------------------------------------------------------

# 81. Intermediate Thinking Exercises

## Exercise 16 — Diagnose a Character Conversion

A collaborator writes:

``` r
measurement <- c(
  2.1,
  3.5,
  4.2,
  "NA"
)
```

They expect:

``` r
mean(
  measurement,
  na.rm = TRUE
)
```

to work.

Answer:

1.  What is wrong with `"NA"`?
2.  What does `typeof(measurement)` return?
3.  Why does `na.rm = TRUE` not solve this?
4.  How should a true missing value be represented?

------------------------------------------------------------------------

## Exercise 17 — Is Recycling Appropriate?

A researcher has:

``` r
effect <- c(
  0.1,
  0.2,
  0.3,
  0.4
)

weight <- c(
  1,
  2
)
```

They run:

``` r
effect * weight
```

R produces a result without an error.

Does this prove the operation is scientifically correct?

Explain.

------------------------------------------------------------------------

## Exercise 18 — `NA`, `NaN`, or `Inf`?

For each scenario, identify the most likely R representation.

### A

A patient’s measurement was not recorded.

### B

A numeric calculation evaluates `0 / 0`.

### C

A transformation calculates `1 / 0`.

### D

An optional list component does not exist.

Use:

``` text
NA
NaN
Inf
NULL
```

once each where appropriate.

------------------------------------------------------------------------

# 82. Challenge — Build an R Object Inspection Notebook

Create:

``` text
Chapter_02_Object_Inspection.Rmd
```

The notebook should contain at least:

## Part A — Ordinary objects

Create:

``` text
logical value
integer value
double value
character value
numeric vector
character vector
vector containing NA
```

For every object, record:

``` r
typeof()
class()
length()
str()
attributes()
```

where relevant.

## Part B — Coercion experiments

Demonstrate:

``` text
logical + integer
integer + double
double + character
```

Predict first, then run.

## Part C — Vectorization

Use one numeric vector to demonstrate:

``` text
addition
multiplication
comparison
mathematical function
```

## Part D — Recycling

Show:

``` text
length 4 + length 1
length 4 + length 2
length 4 + length 3
```

Explain which are naturally compatible and which require caution.

## Part E — Missing and special values

Demonstrate:

``` r
NA
NaN
Inf
-Inf
NULL
```

and the appropriate testing functions.

## Part F — Computational biology example

Create:

``` text
variant IDs
P-values
allele frequencies
sequencing depth values
```

and inspect their types, lengths, missingness, and vectorized
comparisons.

The objective is not biological analysis.

The objective is to demonstrate that you understand how R represents and
evaluates values.

------------------------------------------------------------------------

# 83. Chapter Competency Check

Before moving to Chapter 3, you should be able to explain:

``` text
expression
evaluation
value
name
object
assignment
reassignment
atomic type
coercion
vectorization
recycling
missing value
attribute
class
copy-on-modify
floating-point approximation
```

You should be comfortable using:

``` r
<-
==
typeof()
class()
str()
length()
is.numeric()
is.integer()
is.logical()
is.character()
as.numeric()
as.integer()
as.character()
is.na()
anyNA()
is.nan()
is.infinite()
is.null()
attributes()
names()
all.equal()
```

Most importantly, when something surprising happens, you should begin
asking:

``` text
What object do I have?
What is its type?
What is its class?
What is its length?
Does it contain missing values?
Did coercion occur?
Did recycling occur?
What value did this expression return?
```

That is the beginning of thinking like an R programmer.

------------------------------------------------------------------------

# 84. Key Takeaways

1.  **R evaluates expressions and produces values.**

2.  **Names let us refer to values through objects.**

3.  **Assignment and comparison are different operations.**

4.  **Reassignment changes what a name currently refers to; it does not
    automatically recalculate previously created objects.**

5.  **R values have underlying types that affect how operations
    behave.**

6.  **`typeof()` and `class()` answer different questions.**

7.  **R can automatically coerce values to a common type.**

8.  **Vectorized operations allow one expression to act across multiple
    values.**

9.  **Recycling makes vectorization convenient but can hide alignment
    mistakes.**

10. **`NA`, `NaN`, `Inf`, and `NULL` have different meanings.**

11. **Use `is.na()` to test missing values—not `== NA`.**

12. **Attributes add metadata and help R construct richer objects.**

13. **Ordinary R objects generally behave according to copy-on-modify
    semantics.**

14. **Floating-point values are approximate, so exact equality is not
    always the correct comparison.**

15. **Inspect objects before changing code.**

------------------------------------------------------------------------

# 85. Repository Output from This Chapter

A useful Chapter 2 practice structure is:

``` text
code/
└── 02_Understanding_How_R_Thinks/
    ├── 01_objects_and_assignment.R
    ├── 02_types_and_coercion.R
    ├── 03_vectorized_evaluation.R
    ├── 04_recycling.R
    ├── 05_missing_and_special_values.R
    ├── 06_attributes_and_class.R
    └── 07_copy_on_modify.R

exercises/
└── chapter02/

projects/
└── beginner/
    └── object_inspection_notebook/
```

The exact number of scripts is not important.

What matters is that practice remains organized and meaningful.

------------------------------------------------------------------------

# References and Further Reading

## Essential Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

2.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

## Additional Reading

4.  R Core Team. *R Language Definition*. R Foundation for Statistical
    Computing.

5.  Wickham H. *Advanced R*: sections on vectors, objects, names and
    values, and memory.

## Scientific Computing Context

6.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

7.  Sandve GK, Nekrutenko A, Taylor J, Hovig E. Ten simple rules for
    reproducible computational research. *PLoS Computational Biology*.
    2013;9(10):e1003285.

## Useful R Documentation

Explore:

``` r
?typeof
?class
?str
?length
?Comparison
?NA
?is.na
?is.nan
?is.finite
?NULL
?attributes
?names
?all.equal
```

Do not try to memorize the documentation.

Read it, test a small example, and observe what R returns.

------------------------------------------------------------------------

# Next Chapter

## Chapter 3 — Mastering R Data Structures

Chapter 2 explained how R represents and evaluates values.

The next question is:

> How does R organize many values into useful structures?

Chapter 3 will teach in detail:

- atomic vectors;
- matrices;
- arrays;
- lists;
- factors;
- data frames;
- names;
- dimensions;
- attributes;
- nested objects;
- and specialized R classes.

The progression is deliberate:

``` text
Chapter 2
How R thinks about values
        ↓
Chapter 3
How R organizes values
        ↓
Chapter 4
How we extract values from those structures
```

This foundation will make later `dplyr`, `ggplot2`, statistics,
Bioconductor, GWAS, and RNA-seq programming much easier to understand.
