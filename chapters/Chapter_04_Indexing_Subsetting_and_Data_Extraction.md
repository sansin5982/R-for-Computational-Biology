Chapter 4 — Indexing, Subsetting and Data Extraction
================
Sandeep Kumar Singh, PhD

- [Chapter 4 — Indexing, Subsetting and Data
  Extraction](#chapter-4--indexing-subsetting-and-data-extraction)
  - [Where This Chapter Fits](#where-this-chapter-fits)
- [Learning Objectives](#learning-objectives)
- [1. What Is Indexing?](#1-what-is-indexing)
- [2. Why Do We Need Indexing?](#2-why-do-we-need-indexing)
- [3. R Uses 1-Based Indexing](#3-r-uses-1-based-indexing)
- [4. Positive Integer Indexing](#4-positive-integer-indexing)
- [5. The Order of the Index Controls the
  Output](#5-the-order-of-the-index-controls-the-output)
- [6. Repeated Indices Repeat Values](#6-repeated-indices-repeat-values)
- [7. Creating Index Sequences](#7-creating-index-sequences)
- [8. Why `seq_along()` Is Often Safer](#8-why-seq_along-is-often-safer)
- [9. Zero as an Index](#9-zero-as-an-index)
- [10. Out-of-Range Positive Indices](#10-out-of-range-positive-indices)
- [11. Negative Indexing](#11-negative-indexing)
- [12. You Cannot Mix Positive and Negative
  Indices](#12-you-cannot-mix-positive-and-negative-indices)
- [13. Excluding the Last Element](#13-excluding-the-last-element)
- [14. General Example: Positional
  Indexing](#14-general-example-positional-indexing)
- [15. Computational Biology Example: Positional
  Indexing](#15-computational-biology-example-positional-indexing)
- [16. Logical Indexing](#16-logical-indexing)
- [17. Logical Conditions Create Logical
  Indices](#17-logical-conditions-create-logical-indices)
- [18. Build the Condition Separately When
  Learning](#18-build-the-condition-separately-when-learning)
- [19. Combining Conditions with `&`](#19-combining-conditions-with-)
- [20. Combining Conditions with `|`](#20-combining-conditions-with-)
- [21. Negating a Condition with `!`](#21-negating-a-condition-with-)
- [22. Missing Values in Logical
  Indices](#22-missing-values-in-logical-indices)
- [23. Do Not Hide Missingness
  Accidentally](#23-do-not-hide-missingness-accidentally)
- [24. Logical Index Recycling](#24-logical-index-recycling)
- [25. Named Indexing](#25-named-indexing)
- [26. Why Named Indexing Is Useful](#26-why-named-indexing-is-useful)
- [27. What Happens If a Name Does Not
  Exist?](#27-what-happens-if-a-name-does-not-exist)
- [28. Duplicate Names Require Care](#28-duplicate-names-require-care)
- [29. `%in%` — Membership Testing](#29-in--membership-testing)
- [30. Why `%in%` Is Often Better Than Repeated
  `==`](#30-why-in-is-often-better-than-repeated-)
- [31. `match()` — Finding Positions](#31-match--finding-positions)
- [32. Missing Matches with `match()`](#32-missing-matches-with-match)
- [33. Reordering with `match()`](#33-reordering-with-match)
- [34. Matrix Indexing](#34-matrix-indexing)
- [35. Extract One Matrix Element](#35-extract-one-matrix-element)
- [36. Extract an Entire Row](#36-extract-an-entire-row)
- [37. Extract an Entire Column](#37-extract-an-entire-column)
- [38. Select Multiple Rows and
  Columns](#38-select-multiple-rows-and-columns)
- [39. Matrix Row and Column Names](#39-matrix-row-and-column-names)
- [40. Matrix Dimension Dropping](#40-matrix-dimension-dropping)
- [41. Preserve Matrix Structure with
  `drop = FALSE`](#41-preserve-matrix-structure-with-drop--false)
- [42. Why Dimension Dropping
  Matters](#42-why-dimension-dropping-matters)
- [43. `drop()`](#43-drop)
- [44. Matrix Linear Indexing](#44-matrix-linear-indexing)
- [45. Index Matrices: An Advanced
  Preview](#45-index-matrices-an-advanced-preview)
- [46. Array Indexing](#46-array-indexing)
- [47. Select an Array Slice](#47-select-an-array-slice)
- [48. Data-Frame Subsetting](#48-data-frame-subsetting)
- [49. Data-Frame Row and Column
  Indexing](#49-data-frame-row-and-column-indexing)
- [50. Select Data-Frame Columns by
  Name](#50-select-data-frame-columns-by-name)
- [51. One-Column Selection Can
  Simplify](#51-one-column-selection-can-simplify)
- [52. `students["score"]`](#52-studentsscore)
- [53. `[` Versus `[[`](#53--versus-)
- [54. `[` Usually Returns a Subset of the
  Container](#54--usually-returns-a-subset-of-the-container)
- [55. `[[` Extracts One Component](#55--extracts-one-component)
- [56. Compare `[` and `[[` Directly](#56-compare--and--directly)
- [57. `[[` Must Select One Component](#57--must-select-one-component)
- [58. `[` and `[[` with Data Frames](#58--and--with-data-frames)
- [59. The `$` Operator](#59-the--operator)
- [60. `$` Versus `[[`](#60--versus-)
- [61. Dynamic Extraction](#61-dynamic-extraction)
- [62. Partial Matching with `$`](#62-partial-matching-with-)
- [63. Lists and Nested Extraction](#63-lists-and-nested-extraction)
- [64. Recursive `[[` Indexing](#64-recursive--indexing)
- [65. Filtering Data-Frame Rows](#65-filtering-data-frame-rows)
- [66. Filter with Multiple
  Conditions](#66-filter-with-multiple-conditions)
- [67. Select Rows and Columns
  Together](#67-select-rows-and-columns-together)
- [68. Filtering Missing Values
  Safely](#68-filtering-missing-values-safely)
- [69. `complete.cases()`](#69-completecases)
- [70. Complete Cases for Selected
  Variables](#70-complete-cases-for-selected-variables)
- [71. `subset()`](#71-subset)
- [72. Why `subset()` Is Not Always the Best Programming
  Tool](#72-why-subset-is-not-always-the-best-programming-tool)
- [73. `which()`](#73-which)
- [74. You Often Do Not Need `which()` for
  Subsetting](#74-you-often-do-not-need-which-for-subsetting)
- [75. `which()` and Missing Logical
  Values](#75-which-and-missing-logical-values)
- [76. `which.min()` and `which.max()`](#76-whichmin-and-whichmax)
- [77. Computational Biology Example: Minimum
  P-Value](#77-computational-biology-example-minimum-p-value)
- [78. Missing Numeric Indices](#78-missing-numeric-indices)
- [79. Duplicate Numeric Indices](#79-duplicate-numeric-indices)
- [80. Empty Indices](#80-empty-indices)
- [81. Row Names Are Not a Substitute for Real
  IDs](#81-row-names-are-not-a-substitute-for-real-ids)
- [82. Avoid Assuming Row Order Is
  Identity](#82-avoid-assuming-row-order-is-identity)
- [83. Safe Identifier Selection with
  `%in%`](#83-safe-identifier-selection-with-in)
- [84. `%in%` Does Not Preserve the Query
  Order](#84-in-does-not-preserve-the-query-order)
- [85. A Complete Data-Frame Filtering
  Example](#85-a-complete-data-frame-filtering-example)
- [86. Computational Biology Example: Variant
  Filtering](#86-computational-biology-example-variant-filtering)
- [87. Genomic Region Extraction](#87-genomic-region-extraction)
- [88. Keep Missing Values Separate Rather Than Silently Dropping
  Them](#88-keep-missing-values-separate-rather-than-silently-dropping-them)
- [89. Introductory Subassignment](#89-introductory-subassignment)
- [90. Logical Subassignment](#90-logical-subassignment)
- [91. Do Not Overwrite Raw Data
  Casually](#91-do-not-overwrite-raw-data-casually)
- [92. Common Mistake: Off-by-One
  Indexing](#92-common-mistake-off-by-one-indexing)
- [93. Common Mistake: Mixing Positive and Negative
  Indices](#93-common-mistake-mixing-positive-and-negative-indices)
- [94. Common Mistake: Using Positions When Names Are
  Safer](#94-common-mistake-using-positions-when-names-are-safer)
- [95. Common Mistake: Forgetting
  `drop = FALSE`](#95-common-mistake-forgetting-drop--false)
- [96. Common Mistake: Confusing `[` and
  `[[`](#96-common-mistake-confusing--and-)
- [97. Common Mistake: Using `$` with a Variable
  Name](#97-common-mistake-using--with-a-variable-name)
- [98. Common Mistake: Using `which()`
  Everywhere](#98-common-mistake-using-which-everywhere)
- [99. Common Mistake: Ignoring `NA` in
  Conditions](#99-common-mistake-ignoring-na-in-conditions)
- [100. Common Mistake: Assuming `%in%` Reorders to the
  Query](#100-common-mistake-assuming-in-reorders-to-the-query)
- [101. Common Mistake: Assuming Equal Row Counts Mean Correct
  Alignment](#101-common-mistake-assuming-equal-row-counts-mean-correct-alignment)
- [102. Debugging Clinic](#102-debugging-clinic)
  - [Problem 1 — The Wrong Element Was
    Selected](#problem-1--the-wrong-element-was-selected)
  - [Problem 2 — Filter Returns an Unexpected `NA`
    Row](#problem-2--filter-returns-an-unexpected-na-row)
  - [Problem 3 — Matrix Became a
    Vector](#problem-3--matrix-became-a-vector)
  - [Problem 4 — Data Frame Became a
    Vector](#problem-4--data-frame-became-a-vector)
  - [Problem 5 — List Function Receives Another List Instead of a
    Value](#problem-5--list-function-receives-another-list-instead-of-a-value)
  - [Problem 6 — Dynamic Column Extraction Returns
    `NULL`](#problem-6--dynamic-column-extraction-returns-null)
  - [Problem 7 — Identifier Matching Produces `NA`
    Indices](#problem-7--identifier-matching-produces-na-indices)
  - [Problem 8 — Rows Duplicated
    Unexpectedly](#problem-8--rows-duplicated-unexpectedly)
- [103. Performance Corner](#103-performance-corner)
  - [Avoid unnecessary full copies](#avoid-unnecessary-full-copies)
  - [Select only needed columns](#select-only-needed-columns)
  - [Filter early when scientifically
    appropriate](#filter-early-when-scientifically-appropriate)
  - [Use specialized tools later](#use-specialized-tools-later)
- [104. Expert Commentary](#104-expert-commentary)
- [105. A Second Expert Habit: Prefer Identity Over
  Position](#105-a-second-expert-habit-prefer-identity-over-position)
- [106. From the Reviewer’s
  Perspective](#106-from-the-reviewers-perspective)
- [107. Complete General Example](#107-complete-general-example)
  - [First row](#first-row)
  - [First two rows](#first-two-rows)
  - [Score column as vector](#score-column-as-vector)
  - [Score column as data frame](#score-column-as-data-frame)
  - [ID and score columns](#id-and-score-columns)
  - [Group B](#group-b)
  - [Group B with score at least 90](#group-b-with-score-at-least-90)
  - [Observed age and score only](#observed-age-and-score-only)
- [108. Complete Computational Biology
  Example](#108-complete-computational-biology-example)
  - [Select chromosome 6](#select-chromosome-6)
  - [Select a region](#select-a-region)
  - [Select observed P-values only](#select-observed-p-values-only)
  - [Select observed P and MAF plus
    thresholds](#select-observed-p-and-maf-plus-thresholds)
  - [Select requested variants by
    membership](#select-requested-variants-by-membership)
  - [Preserve request order with
    `match()`](#preserve-request-order-with-match)
- [109. Practice Questions — Basic
  Level](#109-practice-questions--basic-level)
- [110. Practical Exercises](#110-practical-exercises)
  - [Exercise 1 — Positive Indexing](#exercise-1--positive-indexing)
  - [Exercise 2 — Negative and Zero
    Indices](#exercise-2--negative-and-zero-indices)
  - [Exercise 3 — Duplicate and Out-of-Range
    Indices](#exercise-3--duplicate-and-out-of-range-indices)
  - [Exercise 4 — Logical Filtering](#exercise-4--logical-filtering)
  - [Exercise 5 — Missing Logical
    Values](#exercise-5--missing-logical-values)
  - [Exercise 6 — Named Vector](#exercise-6--named-vector)
  - [Exercise 7 — Membership Versus
    Match](#exercise-7--membership-versus-match)
  - [Exercise 8 — Matrix Subsetting](#exercise-8--matrix-subsetting)
  - [Exercise 9 — Data-Frame
    Extraction](#exercise-9--data-frame-extraction)
  - [Exercise 10 — Dynamic Column
    Name](#exercise-10--dynamic-column-name)
  - [Exercise 11 — List Extraction](#exercise-11--list-extraction)
  - [Exercise 12 — Complete Cases](#exercise-12--complete-cases)
- [111. Computational Biology
  Practice](#111-computational-biology-practice)
  - [Exercise 13 — Variant Selection](#exercise-13--variant-selection)
  - [Exercise 14 — Sample Alignment
    Check](#exercise-14--sample-alignment-check)
  - [Exercise 15 — Gene Selection](#exercise-15--gene-selection)
- [112. Intermediate Thinking
  Exercises](#112-intermediate-thinking-exercises)
  - [Exercise 16 — `[` or `[[`?](#exercise-16---or-)
    - [A](#a)
    - [B](#b)
    - [C](#c)
    - [D](#d)
    - [E](#e)
  - [Exercise 17 — Diagnose Dimension
    Dropping](#exercise-17--diagnose-dimension-dropping)
  - [Exercise 18 — The Missing-Match
    Problem](#exercise-18--the-missing-match-problem)
  - [Exercise 19 — The Wrong Use of
    `%in%`](#exercise-19--the-wrong-use-of-in)
  - [Exercise 20 — Scientific Filtering
    Audit](#exercise-20--scientific-filtering-audit)
- [113. Challenge — Sample and Variant Selection
  Audit](#113-challenge--sample-and-variant-selection-audit)
  - [Part A — General dataset](#part-a--general-dataset)
  - [Part B — Biological dataset](#part-b--biological-dataset)
  - [Part C — Audit Counts](#part-c--audit-counts)
  - [Part D — Alignment Exercise](#part-d--alignment-exercise)
  - [Part E — Structure Audit](#part-e--structure-audit)
- [114. Chapter Competency Check](#114-chapter-competency-check)
  - [Vector](#vector)
  - [Matrix/array](#matrixarray)
  - [List](#list)
  - [Data frame](#data-frame)
  - [Scientific data](#scientific-data)
- [115. Key Takeaways](#115-key-takeaways)
- [116. Repository Output from This
  Chapter](#116-repository-output-from-this-chapter)
- [References and Further Reading](#references-and-further-reading)
  - [Essential Reading](#essential-reading)
  - [Additional Reading](#additional-reading)
  - [Scientific Computing Context](#scientific-computing-context)
  - [Useful R Documentation](#useful-r-documentation)
- [Next Chapter](#next-chapter)
  - [Chapter 5 — Writing Reusable
    Code](#chapter-5--writing-reusable-code)

# Chapter 4 — Indexing, Subsetting and Data Extraction

## Where This Chapter Fits

Chapter 2 taught us how R represents and evaluates values.

Chapter 3 taught us how R organizes those values into structures such
as:

``` text
atomic vectors
matrices
arrays
lists
factors
data frames
```

We now need to learn how to retrieve exactly the part of an object that
we want.

Suppose we have:

``` r
scores <- c(
  82,
  91,
  76,
  88
)
```

How do we obtain:

``` text
the first score?
the last score?
scores 2 and 4?
all scores above 80?
```

Or suppose we have a data frame containing:

``` text
1,000 participants
20 variables
```

How do we retrieve:

``` text
one column?
three selected columns?
participants older than 50?
only case samples?
rows with complete values?
```

In computational biology, the same questions appear constantly:

``` text
Which variants are on chromosome 6?
Which variants have P < 5e-8?
Which samples passed QC?
Which genes belong to a supplied gene list?
Which rows correspond to a genomic region?
Which columns correspond to selected samples?
```

These operations are forms of:

``` text
indexing
subsetting
extraction
filtering
```

They are among the most frequently used operations in R.

This chapter therefore develops a careful mental model of how R selects
data and, equally importantly, **what structure R returns after the
selection**.

------------------------------------------------------------------------

# Learning Objectives

By the end of this chapter, you should be able to:

- explain what an index is;
- explain why R uses 1-based indexing;
- extract elements using positive integer positions;
- exclude elements using negative indices;
- understand the role of zero in numeric indices;
- use sequences and repeated indices;
- subset using logical vectors;
- understand logical-index recycling;
- handle `NA` values safely in logical conditions;
- subset named vectors using names;
- understand what happens when requested names do not exist;
- subset matrices by rows and columns;
- subset arrays by multiple dimensions;
- understand dimension dropping;
- preserve dimensions using `drop = FALSE`;
- subset data frames by rows and columns;
- distinguish `x[i]` from `x[[i]]`;
- understand how `$` differs from `[[`;
- extract list components safely;
- use dynamic names with `[[`;
- use `%in%` for membership testing;
- use `match()` when positions are required;
- understand when `which()` is useful and when it is unnecessary;
- use `which.min()` and `which.max()`;
- identify complete observations using `complete.cases()`;
- understand duplicate, missing, zero, and out-of-range indices;
- avoid row-order assumptions;
- perform safe conditional extraction in scientific datasets;
- use subassignment to modify selected values at an introductory level;
- inspect the result of every important subsetting operation.

------------------------------------------------------------------------

# 1. What Is Indexing?

Consider a vector:

``` r
genes <- c(
  "BRCA1",
  "TP53",
  "APOE",
  "CFTR"
)
```

The vector contains four elements.

Conceptually:

``` text
position:     1        2       3       4
value:      BRCA1     TP53    APOE    CFTR
```

An **index** tells R which position or positions we want.

For example:

``` r
genes[1]
```

means:

> Give me the element of `genes` at position 1.

The result is:

``` text
"BRCA1"
```

The square brackets:

``` r
[
]
```

are R’s fundamental subsetting operator.

------------------------------------------------------------------------

# 2. Why Do We Need Indexing?

Real datasets contain more information than we usually need at one
moment.

Suppose a study contains:

``` text
100,000 variants
```

but we want only:

``` text
variants on chromosome 6
```

Or a clinical table contains:

``` text
2,000 participants
```

but we want only:

``` text
participants with complete age and blood-pressure measurements
```

Indexing lets us select relevant parts of an object without manually
creating separate objects for every possible subset.

The general pattern is:

``` text
original object
      ↓
selection rule
      ↓
subset
```

Examples of selection rules include:

``` text
position
name
TRUE/FALSE condition
row and column coordinates
matching identifiers
```

------------------------------------------------------------------------

# 3. R Uses 1-Based Indexing

R counts positions starting from:

``` text
1
```

not:

``` text
0
```

Example:

``` r
x <- c(
  10,
  20,
  30
)
```

Then:

``` r
x[1]
```

returns:

``` text
10
```

``` r
x[2]
```

returns:

``` text
20
```

``` r
x[3]
```

returns:

``` text
30
```

This is called **1-based indexing**.

Some languages, such as Python, commonly use zero-based indexing.

Do not transfer Python’s indexing rules into R.

------------------------------------------------------------------------

# 4. Positive Integer Indexing

Positive integer indices **select** positions.

Example:

``` r
scores <- c(
  82,
  91,
  76,
  88
)
```

First element:

``` r
scores[1]
```

Second element:

``` r
scores[2]
```

Fourth element:

``` r
scores[4]
```

Select several elements:

``` r
scores[
  c(
    1,
    3
  )
]
```

Result:

``` text
82 76
```

The index itself can be a vector.

That means this:

``` r
c(
  1,
  3
)
```

means:

> select position 1 and position 3.

------------------------------------------------------------------------

# 5. The Order of the Index Controls the Output

Suppose:

``` r
x <- c(
  "A",
  "B",
  "C",
  "D"
)
```

Then:

``` r
x[
  c(
    4,
    2,
    1
  )
]
```

returns:

``` text
"D" "B" "A"
```

R does not automatically sort the index.

The requested order becomes the output order.

This is useful, but it also means that indexing can deliberately or
accidentally reorder data.

------------------------------------------------------------------------

# 6. Repeated Indices Repeat Values

Example:

``` r
x <- c(
  "A",
  "B",
  "C"
)
```

Run:

``` r
x[
  c(
    1,
    1,
    3
  )
]
```

Result:

``` text
"A" "A" "C"
```

The first position was requested twice, so it appears twice.

This is not an error.

It is important later because a vector of matching positions can
intentionally or accidentally duplicate observations.

------------------------------------------------------------------------

# 7. Creating Index Sequences

Instead of writing:

``` r
x[
  c(
    1,
    2,
    3,
    4
  )
]
```

we can write:

``` r
x[1:4]
```

The expression:

``` r
1:4
```

creates:

``` text
1 2 3 4
```

For more flexible sequences:

``` r
seq(
  from = 1,
  to = 7,
  by = 2
)
```

returns:

``` text
1 3 5 7
```

Then:

``` r
x[
  seq(
    from = 1,
    to = length(x),
    by = 2
  )
]
```

can select every second element starting from the first.

------------------------------------------------------------------------

# 8. Why `seq_along()` Is Often Safer

Suppose you want all valid positions of a vector:

``` r
x <- c(
  "A",
  "B",
  "C"
)
```

Use:

``` r
seq_along(x)
```

This returns:

``` text
1 2 3
```

A beginner may use:

``` r
1:length(x)
```

This often works.

But if:

``` r
length(x) == 0
```

then:

``` r
1:0
```

returns:

``` text
1 0
```

which is not what we intended.

`seq_along(x)` behaves safely for empty objects.

This becomes especially useful in loops later.

------------------------------------------------------------------------

# 9. Zero as an Index

Zero does **not** mean “the first element” in R.

Example:

``` r
x <- c(
  10,
  20,
  30
)
```

Run:

``` r
x[0]
```

The result is an empty vector of the same basic type.

Why?

Because index 0 selects no element.

Zero can appear alongside positive or negative indices and is generally
ignored.

Example:

``` r
x[
  c(
    0,
    2,
    3
  )
]
```

returns positions 2 and 3.

Do not interpret zero using Python rules.

------------------------------------------------------------------------

# 10. Out-of-Range Positive Indices

Consider:

``` r
x <- c(
  10,
  20,
  30
)
```

Then:

``` r
x[5]
```

requests a position that does not exist.

For an atomic vector, R returns:

``` text
NA
```

This can be surprising because no error is necessarily produced.

Therefore, if positions come from calculated code rather than obvious
literals, inspect them.

Example:

``` r
index <- 5

length(x)
index
x[index]
```

------------------------------------------------------------------------

# 11. Negative Indexing

Negative indices mean:

> exclude these positions.

Example:

``` r
x <- c(
  "A",
  "B",
  "C",
  "D"
)
```

Remove position 2:

``` r
x[-2]
```

Result:

``` text
"A" "C" "D"
```

Remove positions 1 and 3:

``` r
x[
  -c(
    1,
    3
  )
]
```

Result:

``` text
"B" "D"
```

Positive indexing answers:

> What should I keep?

Negative indexing answers:

> What should I remove?

------------------------------------------------------------------------

# 12. You Cannot Mix Positive and Negative Indices

This is invalid:

``` r
x[
  c(
    1,
    -2
  )
]
```

R cannot interpret this as both:

``` text
select position 1
```

and:

``` text
remove position 2
```

in the same numeric index.

Zero is the main exception because it selects nothing.

Choose one strategy:

``` text
positive = keep
negative = exclude
```

------------------------------------------------------------------------

# 13. Excluding the Last Element

Suppose:

``` r
x <- c(
  10,
  20,
  30,
  40
)
```

Remove the last element:

``` r
x[
  -length(x)
]
```

Why does this work?

``` r
length(x)
```

returns:

``` text
4
```

so R evaluates:

``` r
x[-4]
```

------------------------------------------------------------------------

# 14. General Example: Positional Indexing

Suppose:

``` r
temperatures <- c(
  22.1,
  23.5,
  21.8,
  25.2,
  24.7
)
```

First reading:

``` r
temperatures[1]
```

Last reading:

``` r
temperatures[
  length(temperatures)
]
```

First three:

``` r
temperatures[1:3]
```

Measurements 2 and 5:

``` r
temperatures[
  c(
    2,
    5
  )
]
```

Everything except measurement 3:

``` r
temperatures[-3]
```

Every second position:

``` r
temperatures[
  seq(
    1,
    length(temperatures),
    by = 2
  )
]
```

------------------------------------------------------------------------

# 15. Computational Biology Example: Positional Indexing

Suppose:

``` r
variant_id <- c(
  "rs1001",
  "rs1002",
  "rs1003",
  "rs1004",
  "rs1005"
)
```

First variant:

``` r
variant_id[1]
```

Last variant:

``` r
variant_id[
  length(variant_id)
]
```

Select variants 2 and 4:

``` r
variant_id[
  c(
    2,
    4
  )
]
```

This demonstrates positional indexing.

But in real genomic work, identifiers are often safer than hard-coded
positions because row order may change after filtering, sorting, or
merging.

That is why we will soon learn named and logical indexing.

------------------------------------------------------------------------

# 16. Logical Indexing

Logical indexing is one of the most important R skills.

Instead of saying:

``` text
select positions 2 and 4
```

we provide a logical vector:

``` text
FALSE TRUE FALSE TRUE
```

where:

``` text
TRUE  = keep this element
FALSE = do not keep this element
```

Example:

``` r
x <- c(
  10,
  20,
  30,
  40
)

keep <- c(
  FALSE,
  TRUE,
  FALSE,
  TRUE
)

x[keep]
```

Result:

``` text
20 40
```

------------------------------------------------------------------------

# 17. Logical Conditions Create Logical Indices

We normally do not type `TRUE` and `FALSE` manually.

Instead, comparisons generate them.

Example:

``` r
x <- c(
  10,
  20,
  30,
  40
)
```

Create:

``` r
x >= 25
```

Result:

``` text
FALSE FALSE TRUE TRUE
```

Use it directly:

``` r
x[
  x >= 25
]
```

Result:

``` text
30 40
```

This is the foundation of filtering in R.

------------------------------------------------------------------------

# 18. Build the Condition Separately When Learning

These two are equivalent:

``` r
x[
  x >= 25
]
```

and:

``` r
keep <- x >= 25

x[keep]
```

For beginners and debugging, the second form is often easier because we
can inspect:

``` r
keep
```

A useful learning pattern is:

``` text
1. build the condition
2. inspect TRUE/FALSE values
3. use it as an index
```

------------------------------------------------------------------------

# 19. Combining Conditions with `&`

Suppose:

``` r
x <- c(
  10,
  20,
  30,
  40,
  50
)
```

Select values:

``` text
at least 20
AND
less than 50
```

Create:

``` r
keep <- (
  x >= 20
) & (
  x < 50
)

keep
```

Then:

``` r
x[keep]
```

Result:

``` text
20 30 40
```

The operator:

``` r
&
```

means element-wise logical AND.

------------------------------------------------------------------------

# 20. Combining Conditions with `|`

Suppose we want values:

``` text
less than 20
OR
greater than 40
```

Use:

``` r
keep <- (
  x < 20
) | (
  x > 40
)

x[keep]
```

The operator:

``` r
|
```

means element-wise logical OR.

------------------------------------------------------------------------

# 21. Negating a Condition with `!`

Suppose:

``` r
passed_qc <- c(
  TRUE,
  FALSE,
  TRUE,
  FALSE
)
```

Then:

``` r
!passed_qc
```

returns:

``` text
FALSE TRUE FALSE TRUE
```

The operator:

``` r
!
```

means logical NOT.

Example:

``` r
sample_id <- c(
  "S1",
  "S2",
  "S3",
  "S4"
)

sample_id[
  !passed_qc
]
```

returns samples that failed QC.

------------------------------------------------------------------------

# 22. Missing Values in Logical Indices

This is extremely important.

Suppose:

``` r
x <- c(
  10,
  NA,
  30,
  40
)
```

Create:

``` r
x > 20
```

The result is:

``` text
FALSE NA TRUE TRUE
```

Why is the second result `NA`?

Because R cannot determine whether an unknown value is greater than 20.

Now:

``` r
x[
  x > 20
]
```

can include an `NA` position in the output.

If the intention is to select only known values above 20, use:

``` r
keep <- (
  !is.na(x)
) & (
  x > 20
)

x[keep]
```

Result:

``` text
30 40
```

------------------------------------------------------------------------

# 23. Do Not Hide Missingness Accidentally

Consider:

``` r
p <- c(
  0.01,
  NA,
  0.20,
  5e-8
)
```

If we write:

``` r
p <= 0.05
```

we get:

``` text
TRUE NA FALSE TRUE
```

If our scientific question is:

> Which **observed** P-values are at most 0.05?

then use:

``` r
keep <- (
  !is.na(p)
) & (
  p <= 0.05
)
```

This makes the missingness decision explicit.

Do not treat missing values as automatically false unless that is the
intended logic.

------------------------------------------------------------------------

# 24. Logical Index Recycling

Logical indices can be recycled.

Example:

``` r
x <- c(
  10,
  20,
  30,
  40,
  50,
  60
)
```

Then:

``` r
x[
  c(
    TRUE,
    FALSE
  )
]
```

R conceptually repeats:

``` text
TRUE FALSE TRUE FALSE TRUE FALSE
```

Result:

``` text
10 30 50
```

This can be useful.

But it can also hide mistakes if the logical index has the wrong length.

A strong debugging habit is:

``` r
length(x)
length(keep)
```

when a filter behaves unexpectedly.

------------------------------------------------------------------------

# 25. Named Indexing

Vectors can have names.

Example:

``` r
expression <- c(
  BRCA1 = 12.4,
  TP53 = 9.8,
  APOE = 5.1
)

expression
```

Now we can select by name:

``` r
expression["TP53"]
```

Result:

``` text
TP53
 9.8
```

Select several:

``` r
expression[
  c(
    "APOE",
    "BRCA1"
  )
]
```

This is often safer than remembering positions.

------------------------------------------------------------------------

# 26. Why Named Indexing Is Useful

Suppose:

``` text
BRCA1 is position 1 today
```

but after sorting:

``` text
BRCA1 may be position 3
```

Code such as:

``` r
expression[1]
```

now means something different.

But:

``` r
expression["BRCA1"]
```

still requests the same named element.

This illustrates a general scientific-computing principle:

> Stable identifiers are usually safer than accidental row positions.

------------------------------------------------------------------------

# 27. What Happens If a Name Does Not Exist?

Example:

``` r
expression["NOT_A_GENE"]
```

For a named atomic vector, the result is typically an `NA` value with
the requested name.

This is different from a guaranteed error.

Therefore, when matching identifiers supplied externally, it is useful
to validate that the requested names actually exist.

Example:

``` r
requested <- c(
  "TP53",
  "NOT_A_GENE"
)

requested %in% names(expression)
```

This reveals which requested identifiers are present.

------------------------------------------------------------------------

# 28. Duplicate Names Require Care

Consider:

``` r
x <- c(
  A = 10,
  A = 20,
  B = 30
)
```

Duplicate names are allowed.

But they make name-based extraction ambiguous.

Check:

``` r
names(x)
```

If you need all elements whose name is `"A"`:

``` r
x[
  names(x) == "A"
]
```

Do not assume that duplicate names behave like unique database keys.

Whenever identifiers are supposed to be unique, validate them:

``` r
anyDuplicated(
  names(x)
)
```

------------------------------------------------------------------------

# 29. `%in%` — Membership Testing

Suppose:

``` r
genes <- c(
  "BRCA1",
  "TP53",
  "APOE",
  "CFTR"
)
```

and we want:

``` r
target_genes <- c(
  "TP53",
  "CFTR"
)
```

Test:

``` r
genes %in% target_genes
```

Result conceptually:

``` text
FALSE TRUE FALSE TRUE
```

Then:

``` r
genes[
  genes %in% target_genes
]
```

returns:

``` text
"TP53" "CFTR"
```

`%in%` is extremely useful for identifier filtering.

------------------------------------------------------------------------

# 30. Why `%in%` Is Often Better Than Repeated `==`

A beginner may write:

``` r
genes == "TP53" |
  genes == "CFTR"
```

This works for two values.

But:

``` r
genes %in% c(
  "TP53",
  "CFTR"
)
```

is clearer and scales to long identifier lists.

Use `%in%` when asking:

> Is each value in this allowed/requested set?

------------------------------------------------------------------------

# 31. `match()` — Finding Positions

`%in%` answers a membership question.

Sometimes we need positions.

Use:

``` r
match()
```

Example:

``` r
genes <- c(
  "BRCA1",
  "TP53",
  "APOE",
  "CFTR"
)

requested <- c(
  "CFTR",
  "BRCA1"
)

match(
  requested,
  genes
)
```

Result:

``` text
4 1
```

Interpretation:

``` text
CFTR  is at position 4
BRCA1 is at position 1
```

------------------------------------------------------------------------

# 32. Missing Matches with `match()`

Example:

``` r
requested <- c(
  "TP53",
  "NOT_FOUND"
)

match(
  requested,
  genes
)
```

The missing match is represented by:

``` text
NA
```

This is valuable because we can detect failed identifier alignment.

Example:

``` r
idx <- match(
  requested,
  genes
)

is.na(idx)
```

In real scientific work, missing matches should be explained rather than
silently discarded.

------------------------------------------------------------------------

# 33. Reordering with `match()`

Suppose:

``` r
metadata_id <- c(
  "S1",
  "S2",
  "S3"
)
```

but expression columns are:

``` r
expression_id <- c(
  "S2",
  "S1",
  "S3"
)
```

Find where metadata IDs occur in expression order:

``` r
match(
  metadata_id,
  expression_id
)
```

Result:

``` text
2 1 3
```

This tells us that order differs.

We will learn fuller join/reordering workflows later.

For now, understand the key principle:

> equal lengths do not guarantee correct alignment.

Identifiers must be matched.

------------------------------------------------------------------------

# 34. Matrix Indexing

A matrix has rows and columns.

Recall:

``` r
m <- matrix(
  1:12,
  nrow = 3,
  ncol = 4
)

m
```

A matrix is indexed using:

``` r
m[row, column]
```

This comma is crucial.

The first position refers to rows.

The second refers to columns.

------------------------------------------------------------------------

# 35. Extract One Matrix Element

Example:

``` r
m[
  2,
  3
]
```

means:

> row 2, column 3.

This returns one value.

------------------------------------------------------------------------

# 36. Extract an Entire Row

Use:

``` r
m[
  2,
]
```

The blank position after the comma means:

> all columns.

So:

``` r
m[
  2,
]
```

means:

> row 2, all columns.

------------------------------------------------------------------------

# 37. Extract an Entire Column

Use:

``` r
m[
  ,
  3
]
```

The blank row position means:

> all rows.

So:

``` r
m[
  ,
  3
]
```

means:

> all rows, column 3.

------------------------------------------------------------------------

# 38. Select Multiple Rows and Columns

Example:

``` r
m[
  c(
    1,
    3
  ),
  c(
    2,
    4
  )
]
```

This selects:

``` text
rows 1 and 3
columns 2 and 4
```

Both row and column indices can use:

``` text
positive integers
negative integers
logical vectors
names
```

when those forms are appropriate.

------------------------------------------------------------------------

# 39. Matrix Row and Column Names

Create:

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
```

Now select by names:

``` r
expression[
  "GENE2",
  "SampleB"
]
```

Select two genes:

``` r
expression[
  c(
    "GENE1",
    "GENE3"
  ),
  ,
]
```

Named matrix indexing often makes scientific code easier to interpret
than numeric positions.

------------------------------------------------------------------------

# 40. Matrix Dimension Dropping

This behavior causes many beginner bugs.

Suppose:

``` r
m <- matrix(
  1:12,
  nrow = 3
)
```

Check:

``` r
dim(m)
```

Now select one column:

``` r
one_column <- m[
  ,
  1
]
```

Inspect:

``` r
class(one_column)
dim(one_column)
length(one_column)
```

By default, R often **drops unnecessary dimensions**.

So a one-column matrix subset can become a vector.

------------------------------------------------------------------------

# 41. Preserve Matrix Structure with `drop = FALSE`

If you want the result to remain a matrix:

``` r
one_column_matrix <- m[
  ,
  1,
  drop = FALSE
]
```

Inspect:

``` r
class(
  one_column_matrix
)
```

``` r
dim(
  one_column_matrix
)
```

Now the result keeps:

``` text
rows × 1 column
```

This is especially important inside reusable functions, where downstream
code may require a matrix.

------------------------------------------------------------------------

# 42. Why Dimension Dropping Matters

Suppose a function expects:

``` text
matrix input
```

When several columns are selected:

``` r
m[
  ,
  c(
    1,
    2
  )
]
```

the result is a matrix.

But when only one column remains:

``` r
m[
  ,
  1
]
```

the result may become a vector.

Now downstream code behaves differently depending on how many columns
happened to pass a filter.

Using:

``` r
drop = FALSE
```

can stabilize the return structure.

This is not merely cosmetic.

It is a programming-contract issue.

------------------------------------------------------------------------

# 43. `drop()`

R also provides:

``` r
drop()
```

which explicitly removes dimensions of length 1 from an array-like
object.

Example:

``` r
m1 <- m[
  ,
  1,
  drop = FALSE
]

dim(m1)
```

Then:

``` r
drop(m1)
```

returns a simplified vector.

Use `drop()` when you deliberately want simplification.

------------------------------------------------------------------------

# 44. Matrix Linear Indexing

A matrix is built on an underlying vector.

Therefore:

``` r
m[1]
```

is valid even though we supplied only one index.

R then indexes the matrix’s underlying elements in column-major order.

Example:

``` r
m <- matrix(
  1:6,
  nrow = 2
)

m
```

Because R fills columns first, the internal order follows that
column-major layout.

For beginner analytical code, prefer:

``` r
m[row, column]
```

when row/column meaning matters.

Single-index matrix extraction is useful to understand, but easy to
misuse scientifically.

------------------------------------------------------------------------

# 45. Index Matrices: An Advanced Preview

R can select individual matrix cells using a two-column matrix of:

``` text
row
column
```

coordinates.

Example:

``` r
m <- matrix(
  1:9,
  nrow = 3
)

idx <- matrix(
  c(
    1, 1,
    2, 3,
    3, 2
  ),
  ncol = 2,
  byrow = TRUE
)

m[idx]
```

This selects specific row-column pairs.

You do not need this pattern constantly, but it demonstrates that an
index itself can be a structured object.

------------------------------------------------------------------------

# 46. Array Indexing

Arrays extend matrices to more than two dimensions.

Example:

``` r
a <- array(
  1:24,
  dim = c(
    3,
    2,
    4
  )
)
```

The dimensions might represent:

``` text
gene × sample × time
```

To select:

``` text
gene 2
sample 1
time 3
```

use:

``` r
a[
  2,
  1,
  3
]
```

Each comma separates one dimension.

------------------------------------------------------------------------

# 47. Select an Array Slice

Suppose the third dimension represents time.

Select all genes and samples at time point 2:

``` r
a[
  ,
  ,
  2
]
```

Again, blank index positions mean:

> keep all values in this dimension.

Dimension dropping also applies to arrays.

Use:

``` r
drop = FALSE
```

when preserving dimensions is important.

------------------------------------------------------------------------

# 48. Data-Frame Subsetting

A data frame has:

``` text
rows
columns
```

but unlike a matrix, columns can have different types.

Example:

``` r
students <- data.frame(
  id = c(
    "S1",
    "S2",
    "S3",
    "S4"
  ),
  score = c(
    82,
    91,
    76,
    88
  ),
  group = c(
    "A",
    "B",
    "A",
    "B"
  )
)

students
```

We can subset a data frame in several ways.

This is where understanding:

``` text
[
[[
$
```

becomes essential.

------------------------------------------------------------------------

# 49. Data-Frame Row and Column Indexing

The two-dimensional form is:

``` r
students[
  rows,
  columns
]
```

First two rows:

``` r
students[
  1:2,
  ]
```

Only columns 1 and 3:

``` r
students[
  ,
  c(
    1,
    3
  )
]
```

Rows 2 and 4, columns 1 and 2:

``` r
students[
  c(
    2,
    4
  ),
  c(
    1,
    2
  )
]
```

------------------------------------------------------------------------

# 50. Select Data-Frame Columns by Name

Prefer meaningful names over numeric positions when possible.

Example:

``` r
students[
  ,
  c(
    "id",
    "score"
  )
]
```

This is easier to understand than:

``` r
students[
  ,
  c(
    1,
    2
  )
]
```

and is less fragile if column order changes.

------------------------------------------------------------------------

# 51. One-Column Selection Can Simplify

Consider:

``` r
students[
  ,
  "score"
]
```

This usually returns the underlying column as a vector.

Check:

``` r
class(
  students[
    ,
    "score"
  ]
)
```

If you want a one-column data frame:

``` r
students[
  ,
  "score",
  drop = FALSE
]
```

or simply:

``` r
students[
  "score"
]
```

These return structures are different.

------------------------------------------------------------------------

# 52. `students["score"]`

This uses one-dimensional data-frame indexing.

A data frame is list-like.

So:

``` r
students[
  "score"
]
```

returns a **data frame containing one column**.

Inspect:

``` r
class(
  students[
    "score"
  ]
)
```

It should remain:

``` text
"data.frame"
```

This is different from:

``` r
students[
  [
    "score"
  ]
]
```

which extracts the column itself.

------------------------------------------------------------------------

# 53. `[` Versus `[[`

This is one of the most important distinctions in R.

Consider a list-like object:

``` r
x <- list(
  gene = "TP53",
  p_value = 0.001,
  significant = TRUE
)
```

Run:

``` r
x["gene"]
```

and:

``` r
x[
  [
    "gene"
  ]
]
```

They do not return the same structure.

------------------------------------------------------------------------

# 54. `[` Usually Returns a Subset of the Container

Example:

``` r
x["gene"]
```

returns a list containing one element.

Check:

``` r
class(
  x["gene"]
)
```

The result is still:

``` text
"list"
```

Conceptually:

``` text
original list
      ↓
select one component
      ↓
smaller list
```

------------------------------------------------------------------------

# 55. `[[` Extracts One Component

Example:

``` r
x[
  [
    "gene"
  ]
]
```

returns:

``` text
"TP53"
```

The surrounding list container is removed.

Conceptually:

``` text
list
  |
  +-- gene = "TP53"

[[ "gene" ]]
       ↓
"TP53"
```

A useful beginner rule is:

``` text
[  = subset/container
[[ = extract one component
```

This rule is not the entire formal semantics of R, but it is an
excellent working model.

------------------------------------------------------------------------

# 56. Compare `[` and `[[` Directly

Run:

``` r
one_as_list <- x["p_value"]

one_value <- x[
  [
    "p_value"
  ]
]
```

Inspect:

``` r
class(one_as_list)
```

``` r
class(one_value)
```

``` r
str(one_as_list)
```

``` r
str(one_value)
```

This experiment is worth repeating until the difference feels natural.

------------------------------------------------------------------------

# 57. `[[` Must Select One Component

For a list:

``` r
x[
  [
    1
  ]
]
```

extracts one component.

But:

``` r
x[
  [
    c(
      1,
      2
    )
  ]
]
```

does **not** mean:

> select components 1 and 2 as siblings.

For multiple sibling components, use:

``` r
x[
  c(
    1,
    2
  )
]
```

There is one advanced exception: a vector supplied to `[[` can be used
for recursive indexing through nested objects. We will show that later
in this chapter.

------------------------------------------------------------------------

# 58. `[` and `[[` with Data Frames

Because a data frame is list-like:

``` r
students["score"]
```

returns a one-column data frame.

But:

``` r
students[
  [
    "score"
  ]
]
```

returns the score vector.

Inspect:

``` r
class(
  students["score"]
)
```

versus:

``` r
class(
  students[
    [
      "score"
    ]
  ]
)
```

This is one of the cleanest demonstrations that data frames are built
from column vectors.

------------------------------------------------------------------------

# 59. The `$` Operator

The `$` operator extracts a named component.

Example:

``` r
students$score
```

This returns the `score` column.

For a list:

``` r
x$gene
```

returns:

``` text
"TP53"
```

`$` is convenient and readable when the component name is known directly
in the code.

------------------------------------------------------------------------

# 60. `$` Versus `[[`

These are often similar:

``` r
students$score
```

and:

``` r
students[
  [
    "score"
  ]
]
```

Both usually extract the column vector.

But they differ importantly when the component name is stored in another
object.

Suppose:

``` r
column_name <- "score"
```

Then:

``` r
students[
  [
    column_name
  ]
]
```

uses the value of `column_name`.

It retrieves:

``` text
score
```

But:

``` r
students$column_name
```

looks for a literal column named:

``` text
column_name
```

It does not normally use the value `"score"`.

This is why `[[` is very useful in programming.

------------------------------------------------------------------------

# 61. Dynamic Extraction

Example:

``` r
column_name <- "group"
```

Use:

``` r
students[
  [
    column_name
  ]
]
```

This lets a program choose a column dynamically.

Later, functions will often receive a column or component name as an
argument.

Understanding dynamic extraction early is valuable.

------------------------------------------------------------------------

# 62. Partial Matching with `$`

The `$` operator can perform partial matching in some recursive objects,
including behavior that can surprise users.

Suppose an object has:

``` text
sequencing_depth
```

and someone types a shortened component name.

Depending on the object/method, R may partially match it.

Do not design scripts that depend on partial matching.

Prefer exact names.

For debugging, R can be configured to warn about partial `$` matches:

``` r
options(
  warnPartialMatchDollar = TRUE
)
```

You do not need to set this globally now, but it is useful to know the
issue exists.

------------------------------------------------------------------------

# 63. Lists and Nested Extraction

Recall a nested list:

``` r
study <- list(
  metadata = list(
    name = "Study A",
    build = "GRCh38"
  ),
  settings = list(
    threshold = 0.05,
    chromosome = 6
  )
)
```

Extract:

``` r
study$settings
```

Then:

``` r
study$settings$threshold
```

Or:

``` r
study[
  [
    "settings"
  ]
][
  [
    "threshold"
  ]
]
```

Both retrieve the threshold.

------------------------------------------------------------------------

# 64. Recursive `[[` Indexing

R also permits a compact recursive form:

``` r
study[
  [
    c(
      "settings",
      "threshold"
    )
  ]
]
```

This means:

``` text
enter "settings"
then extract "threshold"
```

This is useful with nested lists, though beginners should first
understand the step-by-step form.

------------------------------------------------------------------------

# 65. Filtering Data-Frame Rows

Suppose:

``` r
students
```

contains:

``` text
id score group
```

Select scores at least 85:

``` r
students[
  students$score >= 85,
  ]
```

Break the logic apart:

``` r
keep <- students$score >= 85
```

Inspect:

``` r
keep
```

Then:

``` r
students[
  keep,
]
```

This makes the filtering logic easier to understand.

------------------------------------------------------------------------

# 66. Filter with Multiple Conditions

Select students:

``` text
score >= 80
AND
group == "B"
```

Use:

``` r
keep <- (
  students$score >= 80
) & (
  students$group == "B"
)

students[
  keep,
]
```

The logical vector must correspond to rows.

------------------------------------------------------------------------

# 67. Select Rows and Columns Together

Suppose we need:

``` text
students with score >= 85
```

and only:

``` text
id
score
```

Use:

``` r
students[
  students$score >= 85,
  c(
    "id",
    "score"
  )
]
```

Read this literally:

``` text
rows:
score >= 85

columns:
id and score
```

------------------------------------------------------------------------

# 68. Filtering Missing Values Safely

Suppose:

``` r
students <- data.frame(
  id = c(
    "S1",
    "S2",
    "S3",
    "S4"
  ),
  score = c(
    82,
    NA,
    76,
    88
  )
)
```

This condition:

``` r
students$score >= 80
```

returns an `NA` for S2.

A safer filter for observed scores is:

``` r
keep <- (
  !is.na(
    students$score
  )
) & (
  students$score >= 80
)

students[
  keep,
]
```

Again, the missingness decision is explicit.

------------------------------------------------------------------------

# 69. `complete.cases()`

`complete.cases()` identifies rows without missing values in the
supplied objects.

Example:

``` r
students <- data.frame(
  id = c(
    "S1",
    "S2",
    "S3"
  ),
  age = c(
    20,
    NA,
    22
  ),
  score = c(
    82,
    91,
    NA
  )
)

complete.cases(
  students
)
```

This returns one logical value per row.

Then:

``` r
students[
  complete.cases(students),
]
```

keeps rows with no missing value anywhere in the data frame.

------------------------------------------------------------------------

# 70. Complete Cases for Selected Variables

Sometimes a row can have missing values in irrelevant columns.

Suppose our analysis needs only:

``` text
age
score
```

Use:

``` r
needed <- students[
  c(
    "age",
    "score"
  )
]

keep <- complete.cases(
  needed
)

students[
  keep,
]
```

This is more explicit than removing every row with any missing field.

Missing-data decisions should follow the analytical question.

------------------------------------------------------------------------

# 71. `subset()`

Base R provides:

``` r
subset()
```

Example:

``` r
subset(
  students,
  score >= 80
)
```

Select columns:

``` r
subset(
  students,
  score >= 80,
  select = c(
    id,
    score
  )
)
```

This can be convenient interactively because column names can be written
directly.

------------------------------------------------------------------------

# 72. Why `subset()` Is Not Always the Best Programming Tool

`subset()` uses non-standard evaluation rules.

That makes interactive code concise, but programmatic code can become
less predictable when column names come from variables.

For beginner learning, understand `subset()`.

For reusable functions and programming, explicit indexing such as:

``` r
students[
  rows,
  columns
]
```

or later `dplyr` workflows may be clearer.

Do not turn this into a rule that `subset()` is “bad.”

It is a convenience function with trade-offs.

------------------------------------------------------------------------

# 73. `which()`

Suppose:

``` r
x <- c(
  10,
  20,
  30,
  40
)
```

Logical condition:

``` r
x > 20
```

returns:

``` text
FALSE FALSE TRUE TRUE
```

Now:

``` r
which(
  x > 20
)
```

returns the positions:

``` text
3 4
```

So:

``` r
which()
```

converts TRUE positions into integer indices.

------------------------------------------------------------------------

# 74. You Often Do Not Need `which()` for Subsetting

These are equivalent for ordinary vector filtering:

``` r
x[
  x > 20
]
```

and:

``` r
x[
  which(
    x > 20
  )
]
```

The first is usually simpler.

Use `which()` when you genuinely need the **positions**, not merely the
selected values.

For example:

``` r
positions <- which(
  x > 20
)
```

may be useful if the indices themselves matter.

------------------------------------------------------------------------

# 75. `which()` and Missing Logical Values

Consider:

``` r
condition <- c(
  TRUE,
  NA,
  FALSE,
  TRUE
)
```

Then:

``` r
which(condition)
```

returns positions of `TRUE` values.

The `NA` position is not returned.

This differs from direct logical indexing, where an `NA` in the index
can produce an `NA` result.

This distinction is useful, but it should not be used to hide
missingness accidentally.

------------------------------------------------------------------------

# 76. `which.min()` and `which.max()`

Suppose:

``` r
x <- c(
  5,
  2,
  8,
  2
)
```

Minimum position:

``` r
which.min(x)
```

returns the position of the first minimum value.

Maximum position:

``` r
which.max(x)
```

returns the position of the first maximum value.

To obtain the value itself:

``` r
x[
  which.min(x)
]
```

These functions are useful when you need both:

``` text
the extreme value
and
where it occurred
```

------------------------------------------------------------------------

# 77. Computational Biology Example: Minimum P-Value

Suppose:

``` r
variant_id <- c(
  "rs1",
  "rs2",
  "rs3",
  "rs4"
)

p_value <- c(
  0.20,
  0.001,
  5e-8,
  0.02
)
```

Find the position of the smallest P-value:

``` r
lead_position <- which.min(
  p_value
)
```

Retrieve the variant:

``` r
variant_id[
  lead_position
]
```

Retrieve the value:

``` r
p_value[
  lead_position
]
```

This is a programming example.

A smallest P-value does not automatically imply that the corresponding
variant is causal.

------------------------------------------------------------------------

# 78. Missing Numeric Indices

An index itself can contain `NA`.

Example:

``` r
x <- c(
  "A",
  "B",
  "C"
)

x[
  c(
    1,
    NA,
    3
  )
]
```

The unknown index produces an unknown result at that position.

This is logically consistent:

> one requested position is unknown.

When indices come from `match()`, missing matches often appear as `NA`,
so check them before subsetting.

------------------------------------------------------------------------

# 79. Duplicate Numeric Indices

Example:

``` r
x <- c(
  "A",
  "B",
  "C"
)

idx <- c(
  2,
  2,
  1
)

x[idx]
```

returns:

``` text
"B" "B" "A"
```

If a matching workflow unexpectedly duplicates rows, inspect the index.

This becomes especially important in joins and repeated identifiers.

------------------------------------------------------------------------

# 80. Empty Indices

Example:

``` r
x[
  integer(0)
]
```

returns an empty object of the appropriate basic structure.

Why is this important?

Suppose a filter finds no matches:

``` r
which(
  x == "NOT_PRESENT"
)
```

may return:

``` text
integer(0)
```

Subsetting with that result returns no elements.

This is not necessarily an error.

Your code should decide whether “no matches” is valid or should trigger
a warning/error.

------------------------------------------------------------------------

# 81. Row Names Are Not a Substitute for Real IDs

Data frames can have row names.

Example:

``` r
rownames(students)
```

But in many analytical projects, stable identifiers should exist as an
explicit column:

``` text
sample_id
variant_id
participant_id
```

Why?

Because row names are easily lost or changed during:

``` text
import
export
joins
reshaping
conversion
```

For important scientific identifiers, explicit columns are usually
safer.

------------------------------------------------------------------------

# 82. Avoid Assuming Row Order Is Identity

Suppose:

``` r
expression_samples <- c(
  "S1",
  "S2",
  "S3"
)
```

and:

``` r
metadata_samples <- c(
  "S2",
  "S1",
  "S3"
)
```

Both have length 3.

But:

``` r
identical(
  expression_samples,
  metadata_samples
)
```

returns:

``` text
FALSE
```

If we combine these datasets only because their row counts match, sample
labels may be assigned incorrectly.

That is a scientific error, not merely a programming inconvenience.

------------------------------------------------------------------------

# 83. Safe Identifier Selection with `%in%`

Suppose a study contains:

``` r
sample_id <- c(
  "S1",
  "S2",
  "S3",
  "S4",
  "S5"
)
```

and selected samples are:

``` r
selected <- c(
  "S2",
  "S5"
)
```

Use:

``` r
keep <- sample_id %in% selected

sample_id[keep]
```

If you require the order of `selected`, use `match()` instead.

This distinction matters:

``` text
%in% asks membership
match asks position/alignment
```

------------------------------------------------------------------------

# 84. `%in%` Does Not Preserve the Query Order

Example:

``` r
sample_id <- c(
  "S1",
  "S2",
  "S3",
  "S4"
)

requested <- c(
  "S4",
  "S1"
)
```

Then:

``` r
sample_id[
  sample_id %in% requested
]
```

returns values in the order they occur in `sample_id`:

``` text
S1 S4
```

not necessarily:

``` text
S4 S1
```

If requested order matters:

``` r
idx <- match(
  requested,
  sample_id
)

sample_id[idx]
```

returns:

``` text
S4 S1
```

This is an important distinction.

------------------------------------------------------------------------

# 85. A Complete Data-Frame Filtering Example

Create:

``` r
students <- data.frame(
  id = c(
    "S1",
    "S2",
    "S3",
    "S4",
    "S5"
  ),
  age = c(
    20,
    22,
    NA,
    25,
    19
  ),
  score = c(
    82,
    91,
    76,
    NA,
    88
  ),
  group = c(
    "A",
    "B",
    "A",
    "B",
    "B"
  )
)
```

Goal:

``` text
group B
score at least 85
score observed
```

Build each condition:

``` r
is_group_b <- students$group == "B"

score_observed <- !is.na(
  students$score
)

high_score <- students$score >= 85
```

Combine:

``` r
keep <- is_group_b &
  score_observed &
  high_score
```

Inspect:

``` r
keep
```

Then:

``` r
selected_students <- students[
  keep,
  c(
    "id",
    "score",
    "group"
  )
]

selected_students
```

This stepwise style is excellent for learning and debugging.

------------------------------------------------------------------------

# 86. Computational Biology Example: Variant Filtering

Create a synthetic variant table:

``` r
variants <- data.frame(
  SNP = c(
    "rs1",
    "rs2",
    "rs3",
    "rs4",
    "rs5"
  ),
  CHR = c(
    6L,
    6L,
    6L,
    6L,
    6L
  ),
  BP = c(
    26000000L,
    27500000L,
    28700000L,
    31300000L,
    32600000L
  ),
  MAF = c(
    0.12,
    0.04,
    NA,
    0.21,
    0.08
  ),
  P = c(
    0.40,
    0.02,
    1e-4,
    5e-8,
    NA
  )
)
```

Suppose we want variants that:

``` text
have observed P
have observed MAF
P <= 0.05
MAF >= 0.05
```

Build:

``` r
has_p <- !is.na(
  variants$P
)

has_maf <- !is.na(
  variants$MAF
)

passes_p <- variants$P <= 0.05

passes_maf <- variants$MAF >= 0.05
```

Combine:

``` r
keep <- has_p &
  has_maf &
  passes_p &
  passes_maf
```

Inspect:

``` r
keep
```

Subset:

``` r
selected_variants <- variants[
  keep,
  c(
    "SNP",
    "BP",
    "MAF",
    "P"
  )
]

selected_variants
```

This is a teaching example.

The thresholds are not presented as a complete GWAS QC protocol.

------------------------------------------------------------------------

# 87. Genomic Region Extraction

Suppose we want variants between:

``` text
31,000,000
and
32,000,000
```

on chromosome 6.

Build:

``` r
in_chr6 <- variants$CHR == 6

in_region <- (
  variants$BP >= 31000000
) & (
  variants$BP <= 32000000
)

keep <- in_chr6 &
  in_region

variants[
  keep,
]
```

This is a direct example of translating a scientific selection rule into
a logical index.

------------------------------------------------------------------------

# 88. Keep Missing Values Separate Rather Than Silently Dropping Them

Suppose P-values include missing data.

Instead of immediately discarding them:

``` r
missing_p <- variants[
  is.na(
    variants$P
  ),
]

observed_p <- variants[
  !is.na(
    variants$P
  ),
]
```

Now both groups remain auditable.

You can report:

``` r
nrow(missing_p)
```

and:

``` r
nrow(observed_p)
```

This is often better scientific practice than silently losing rows.

------------------------------------------------------------------------

# 89. Introductory Subassignment

The same indexing system can be used to replace selected values.

Example:

``` r
x <- c(
  10,
  20,
  30,
  40
)
```

Replace position 2:

``` r
x[2] <- 99

x
```

Replace positions 1 and 4:

``` r
x[
  c(
    1,
    4
  )
] <- 0

x
```

This is called **subassignment**.

------------------------------------------------------------------------

# 90. Logical Subassignment

Example:

``` r
x <- c(
  10,
  20,
  30,
  40
)
```

Replace all values below 25:

``` r
x[
  x < 25
] <- NA

x
```

This is useful for recoding, but it changes the object.

Before altering scientific data, ensure the transformation is justified
and documented.

------------------------------------------------------------------------

# 91. Do Not Overwrite Raw Data Casually

Suppose an impossible measurement should be marked missing.

A weak workflow is:

``` r
raw_data[
  raw_data$value < 0,
  "value"
] <- NA
```

and then saving over the original file.

A better workflow is:

``` text
raw input
    ↓
cleaned object
    ↓
documented rule
    ↓
processed output
```

For example:

``` r
clean_data <- raw_data

clean_data[
  clean_data$value < 0,
  "value"
] <- NA
```

This preserves provenance.

------------------------------------------------------------------------

# 92. Common Mistake: Off-by-One Indexing

R starts at 1.

Wrong mental model:

``` text
first element = position 0
```

Correct:

``` text
first element = position 1
```

If you use Python regularly, consciously switch mental models when
working in R.

------------------------------------------------------------------------

# 93. Common Mistake: Mixing Positive and Negative Indices

Wrong:

``` r
x[
  c(
    1,
    -3
  )
]
```

Choose:

``` text
positions to keep
```

or:

``` text
positions to exclude
```

not both in the same ordinary numeric index.

------------------------------------------------------------------------

# 94. Common Mistake: Using Positions When Names Are Safer

Fragile:

``` r
data[
  ,
  7
]
```

What is column 7?

If column order changes, the code silently selects something else.

Clearer:

``` r
data[
  ,
  "P"
]
```

when the intended column is known by name.

------------------------------------------------------------------------

# 95. Common Mistake: Forgetting `drop = FALSE`

A function may work while two columns are selected but fail when only
one remains because:

``` text
matrix
```

became:

``` text
vector
```

Inspect:

``` r
class()
dim()
```

and preserve dimensions intentionally.

------------------------------------------------------------------------

# 96. Common Mistake: Confusing `[` and `[[`

For a list:

``` r
x["gene"]
```

returns a list.

But:

``` r
x[
  [
    "gene"
  ]
]
```

returns the component itself.

If a function receives the wrong structure, inspect:

``` r
class()
str()
```

before changing unrelated code.

------------------------------------------------------------------------

# 97. Common Mistake: Using `$` with a Variable Name

Suppose:

``` r
column_name <- "score"
```

Wrong for dynamic extraction:

``` r
students$column_name
```

Correct:

``` r
students[
  [
    column_name
  ]
]
```

This becomes especially important when we start writing functions.

------------------------------------------------------------------------

# 98. Common Mistake: Using `which()` Everywhere

This:

``` r
x[
  which(
    x > 10
  )
]
```

is usually unnecessary.

Prefer:

``` r
x[
  x > 10
]
```

Use `which()` when you need integer positions.

------------------------------------------------------------------------

# 99. Common Mistake: Ignoring `NA` in Conditions

Suppose:

``` r
x > 10
```

contains `NA`.

Direct subsetting may propagate missing output.

If the intention is to keep only observed values meeting the condition:

``` r
!is.na(x) &
  x > 10
```

Make the missingness rule explicit.

------------------------------------------------------------------------

# 100. Common Mistake: Assuming `%in%` Reorders to the Query

Membership filtering preserves the order of the source object.

Use:

``` r
match()
```

when requested order matters.

------------------------------------------------------------------------

# 101. Common Mistake: Assuming Equal Row Counts Mean Correct Alignment

Two objects can each have:

``` text
500 rows
```

but represent samples in different orders.

Always use identifiers when biological correspondence matters.

------------------------------------------------------------------------

# 102. Debugging Clinic

## Problem 1 — The Wrong Element Was Selected

Inspect:

``` r
index
length(x)
x
```

Questions:

``` text
Did you assume zero-based indexing?
Did the object order change?
Should you use names instead?
```

------------------------------------------------------------------------

## Problem 2 — Filter Returns an Unexpected `NA` Row

Inspect:

``` r
condition
```

Then:

``` r
is.na(
  condition
)
```

The underlying data likely contain missing values.

Decide explicitly how missing observations should be handled.

------------------------------------------------------------------------

## Problem 3 — Matrix Became a Vector

Inspect:

``` r
class(result)
dim(result)
```

If one row or column was selected, try:

``` r
drop = FALSE
```

------------------------------------------------------------------------

## Problem 4 — Data Frame Became a Vector

Compare:

``` r
df[
  ,
  "score"
]
```

with:

``` r
df[
  ,
  "score",
  drop = FALSE
]
```

and:

``` r
df["score"]
```

Choose the return structure intentionally.

------------------------------------------------------------------------

## Problem 5 — List Function Receives Another List Instead of a Value

Check whether you used:

``` r
[
```

when you needed:

``` r
[[
```

Inspect with:

``` r
str()
```

------------------------------------------------------------------------

## Problem 6 — Dynamic Column Extraction Returns `NULL`

If:

``` r
column_name <- "score"
```

do not use:

``` r
df$column_name
```

Use:

``` r
df[
  [
    column_name
  ]
]
```

------------------------------------------------------------------------

## Problem 7 — Identifier Matching Produces `NA` Indices

Inspect:

``` r
idx <- match(
  requested,
  available
)

requested[
  is.na(idx)
]
```

This tells you which requested identifiers were not found.

Do not simply remove them before understanding why.

------------------------------------------------------------------------

## Problem 8 — Rows Duplicated Unexpectedly

Inspect the index:

``` r
idx
```

Check duplicates:

``` r
duplicated(idx)
```

or:

``` r
anyDuplicated(idx)
```

Repeated positions generate repeated output.

------------------------------------------------------------------------

# 103. Performance Corner

Indexing is normally efficient for moderate in-memory objects, but
several issues become important at scale.

## Avoid unnecessary full copies

Subsetting a very large object can create another large object in
memory.

## Select only needed columns

For a large table, this:

``` r
large_data[
  ,
  c(
    "SNP",
    "P"
  )
]
```

creates a smaller object than carrying dozens of unused columns through
every step.

## Filter early when scientifically appropriate

If a pipeline only needs chromosome 6, it may be wasteful to repeatedly
process all chromosomes.

However:

> never introduce filters solely for speed if they alter the scientific
> question.

## Use specialized tools later

For large tabular and genomic datasets, later chapters introduce:

``` text
data.table
Arrow
DuckDB
Bioconductor range operations
indexed genomic files
```

At this stage, correct selection and alignment matter more than
micro-optimization.

------------------------------------------------------------------------

# 104. Expert Commentary

Indexing looks simple because the syntax is compact.

But expert R programmers ask two questions every time they subset:

``` text
1. Which values will I select?
2. What structure will R return?
```

For example:

``` r
m[
  ,
  1
]
```

and:

``` r
m[
  ,
  1,
  drop = FALSE
]
```

select the same values but return different structures.

Likewise:

``` r
x["gene"]
```

and:

``` r
x[
  [
    "gene"
  ]
]
```

select related information but return different object types.

That difference affects everything downstream.

------------------------------------------------------------------------

# 105. A Second Expert Habit: Prefer Identity Over Position

In scientific work, experts are cautious about code such as:

``` r
phenotype <- phenotype[
  c(
    2,
    1,
    3
  ),
]
```

unless the positional relationship is clearly justified.

They prefer explicit identifiers:

``` text
sample ID
variant ID
gene ID
```

combined with:

``` r
match()
```

or later relational joins.

Why?

Because sorting, filtering, importing, and merging can change order.

Identity should not depend on accidental position.

------------------------------------------------------------------------

# 106. From the Reviewer’s Perspective

Subsetting is a major point at which scientific datasets can change.

A reviewer may ask:

``` text
How many rows were present before filtering?
How many remained?
Which conditions were applied?
How were missing values handled?
Were duplicate IDs present?
Were rows aligned by identifier or by order?
Did one-column extraction change object type?
Were excluded samples/variants recorded?
```

A filtering command can be syntactically correct and still be
scientifically wrong.

For example:

``` r
expression[
  ,
  metadata$group == "case"
]
```

is valid R code.

But it is only scientifically valid if:

``` text
metadata rows correspond exactly to expression columns
```

Code correctness and data alignment are separate questions.

------------------------------------------------------------------------

# 107. Complete General Example

Create:

``` r
students <- data.frame(
  id = c(
    "S1",
    "S2",
    "S3",
    "S4",
    "S5"
  ),
  age = c(
    19,
    21,
    20,
    NA,
    22
  ),
  score = c(
    82,
    91,
    76,
    88,
    93
  ),
  group = c(
    "A",
    "B",
    "A",
    "B",
    "B"
  )
)
```

## First row

``` r
students[
  1,
]
```

## First two rows

``` r
students[
  1:2,
]
```

## Score column as vector

``` r
students[
  [
    "score"
  ]
]
```

## Score column as data frame

``` r
students[
  "score"
]
```

## ID and score columns

``` r
students[
  c(
    "id",
    "score"
  )
]
```

## Group B

``` r
students[
  students$group == "B",
]
```

## Group B with score at least 90

``` r
keep <- (
  students$group == "B"
) & (
  students$score >= 90
)

students[
  keep,
]
```

## Observed age and score only

``` r
keep_complete <- complete.cases(
  students[
    c(
      "age",
      "score"
    )
  ]
)

students[
  keep_complete,
]
```

Each operation should be inspected with:

``` r
str()
```

and when necessary:

``` r
class()
dim()
```

------------------------------------------------------------------------

# 108. Complete Computational Biology Example

Create:

``` r
variants <- data.frame(
  SNP = c(
    "rs1001",
    "rs1002",
    "rs1003",
    "rs1004",
    "rs1005",
    "rs1006"
  ),
  CHR = c(
    6L,
    6L,
    6L,
    6L,
    1L,
    6L
  ),
  BP = c(
    26000000L,
    27500000L,
    28700000L,
    31300000L,
    12000000L,
    32600000L
  ),
  MAF = c(
    0.12,
    0.04,
    NA,
    0.21,
    0.31,
    0.08
  ),
  P = c(
    0.40,
    0.02,
    1e-4,
    5e-8,
    0.50,
    NA
  )
)
```

## Select chromosome 6

``` r
chr6 <- variants[
  variants$CHR == 6,
]
```

## Select a region

``` r
region <- variants[
  (
    variants$CHR == 6
  ) & (
    variants$BP >= 27000000
  ) & (
    variants$BP <= 32000000
  ),
]
```

## Select observed P-values only

``` r
observed <- variants[
  !is.na(
    variants$P
  ),
]
```

## Select observed P and MAF plus thresholds

``` r
keep <- (
  !is.na(
    variants$P
  )
) & (
  !is.na(
    variants$MAF
  )
) & (
  variants$P <= 0.05
) & (
  variants$MAF >= 0.05
)

filtered <- variants[
  keep,
  c(
    "SNP",
    "CHR",
    "BP",
    "MAF",
    "P"
  )
]
```

## Select requested variants by membership

``` r
requested <- c(
  "rs1004",
  "rs1002"
)

variants[
  variants$SNP %in% requested,
]
```

Notice: source-row order is preserved.

## Preserve request order with `match()`

``` r
idx <- match(
  requested,
  variants$SNP
)

idx
```

Check missing matches:

``` r
requested[
  is.na(idx)
]
```

If none are missing:

``` r
variants[
  idx,
]
```

now follows the order:

``` text
rs1004
rs1002
```

This distinction is central to safe biological identifier handling.

------------------------------------------------------------------------

# 109. Practice Questions — Basic Level

1.  What is an index?
2.  What does `x[1]` mean?
3.  Does R begin indexing at 0 or 1?
4.  What does a positive integer index do?
5.  What does a negative integer index do?
6.  What does `x[0]` return?
7.  Can positive and negative indices normally be mixed?
8.  What happens when a positive index is out of range for an atomic
    vector?
9.  What happens when the same index appears twice?
10. Why can index order change output order?
11. What does logical indexing mean?
12. What does `TRUE` mean in a logical index?
13. What does `FALSE` mean?
14. How are logical indices commonly created?
15. What does `&` mean?
16. What does `|` mean?
17. What does `!` mean?
18. What happens when a logical condition evaluates to `NA`?
19. How can you explicitly exclude missing values from a logical filter?
20. What is logical-index recycling?
21. Why should logical-index lengths sometimes be checked?
22. What is named indexing?
23. Why can names be safer than positions?
24. What does `%in%` test?
25. What does `match()` return?
26. What happens when `match()` cannot find a requested value?
27. What is the difference between `%in%` and `match()`?
28. What is the syntax for matrix indexing?
29. What does a blank row or column index mean?
30. What is dimension dropping?
31. What does `drop = FALSE` do?
32. What does `drop()` do?
33. How is an array indexed?
34. What does `df[rows, columns]` mean?
35. What does `df["score"]` return?
36. What does `df[["score"]]` return?
37. What is the basic difference between `[` and `[[`?
38. What does `$` do?
39. Why is `[[column_name]]` useful in programming?
40. Why does `df$column_name` not normally use the value stored in
    `column_name`?
41. What does `complete.cases()` return?
42. What does `which()` return?
43. Why is `which()` often unnecessary for ordinary filtering?
44. What does `which.min()` return?
45. What does `which.max()` return?
46. What does an `NA` numeric index mean?
47. What does `integer(0)` represent?
48. Why can duplicate indices duplicate rows?
49. Why should row order not be treated as biological identity?
50. Why can correct R subsetting still produce scientifically incorrect
    data?

------------------------------------------------------------------------

# 110. Practical Exercises

## Exercise 1 — Positive Indexing

Create:

``` r
x <- c(
  11,
  22,
  33,
  44,
  55
)
```

Extract:

``` text
first element
last element
positions 2 and 4
first three elements
positions 5, 1, and 3 in that order
```

------------------------------------------------------------------------

## Exercise 2 — Negative and Zero Indices

Using the same `x`:

1.  remove position 2;
2.  remove positions 1 and 5;
3.  test `x[0]`;
4.  test a vector containing zero and positive positions;
5.  try mixing positive and negative positions and read the error.

------------------------------------------------------------------------

## Exercise 3 — Duplicate and Out-of-Range Indices

Run:

``` r
x[
  c(
    2,
    2,
    5
  )
]
```

Then:

``` r
x[10]
```

Explain both results.

------------------------------------------------------------------------

## Exercise 4 — Logical Filtering

Create:

``` r
x <- c(
  5,
  10,
  15,
  20,
  25
)
```

Select:

``` text
values >= 15
values between 10 and 20 inclusive
values below 10 OR above 20
```

Build each logical vector separately before subsetting.

------------------------------------------------------------------------

## Exercise 5 — Missing Logical Values

Create:

``` r
x <- c(
  5,
  NA,
  15,
  20
)
```

Compare:

``` r
x[
  x >= 10
]
```

with:

``` r
x[
  !is.na(x) &
    x >= 10
]
```

Explain the difference.

------------------------------------------------------------------------

## Exercise 6 — Named Vector

Create:

``` r
expression <- c(
  BRCA1 = 10.5,
  TP53 = 8.2,
  APOE = 4.1,
  CFTR = 7.9
)
```

Extract:

``` text
TP53
BRCA1 and CFTR
a name that does not exist
```

Then test:

``` r
c(
  "TP53",
  "NOT_FOUND"
) %in% names(expression)
```

------------------------------------------------------------------------

## Exercise 7 — Membership Versus Match

Using:

``` r
available <- c(
  "S1",
  "S2",
  "S3",
  "S4"
)

requested <- c(
  "S4",
  "S1"
)
```

Compare:

``` r
available[
  available %in% requested
]
```

with:

``` r
available[
  match(
    requested,
    available
  )
]
```

Explain the order difference.

------------------------------------------------------------------------

## Exercise 8 — Matrix Subsetting

Create a:

``` text
4 × 3
```

matrix.

Add row names and column names.

Extract:

``` text
row 2
column 3
rows 1 and 4
columns 1 and 2
one specific cell
```

Then repeat one-column selection with:

``` r
drop = FALSE
```

and compare structures.

------------------------------------------------------------------------

## Exercise 9 — Data-Frame Extraction

Create a data frame with:

``` text
id
age
group
score
```

Extract `score` using:

``` r
df["score"]
```

``` r
df[
  [
    "score"
  ]
]
```

``` r
df$score
```

Compare:

``` r
class()
str()
```

for each result.

------------------------------------------------------------------------

## Exercise 10 — Dynamic Column Name

Create:

``` r
column_name <- "score"
```

Use it to extract the score column programmatically.

Demonstrate why:

``` r
df$column_name
```

is not equivalent.

------------------------------------------------------------------------

## Exercise 11 — List Extraction

Create:

``` r
result <- list(
  gene = "TP53",
  p = 0.001,
  settings = list(
    threshold = 0.05,
    method = "demo"
  )
)
```

Compare:

``` r
result["gene"]
```

``` r
result[
  [
    "gene"
  ]
]
```

``` r
result$gene
```

Then retrieve the nested threshold.

------------------------------------------------------------------------

## Exercise 12 — Complete Cases

Create a data frame with missing values in several columns.

Identify:

``` text
rows complete for every column
rows complete for only two selected analysis variables
```

Compare the results.

------------------------------------------------------------------------

# 111. Computational Biology Practice

## Exercise 13 — Variant Selection

Create:

``` r
variants <- data.frame(
  SNP = paste0(
    "rs",
    1:8
  ),
  CHR = c(
    1L,
    6L,
    6L,
    6L,
    2L,
    6L,
    6L,
    3L
  ),
  BP = c(
    100L,
    26000000L,
    28000000L,
    31000000L,
    500L,
    32500000L,
    34000000L,
    900L
  ),
  P = c(
    0.8,
    0.1,
    0.001,
    5e-8,
    0.3,
    NA,
    0.02,
    0.9
  )
)
```

Using base R indexing:

1.  select chromosome 6;
2.  select chromosome 6 variants between 27 and 33 Mb;
3.  separate missing P-values;
4.  select observed P-values below 0.05;
5.  return only `SNP`, `BP`, and `P`.

------------------------------------------------------------------------

## Exercise 14 — Sample Alignment Check

Suppose:

``` r
expression_samples <- c(
  "S1",
  "S2",
  "S3",
  "S4"
)

metadata_samples <- c(
  "S2",
  "S1",
  "S4",
  "S3"
)
```

1.  Check whether the order is identical.
2.  Use `match()` to determine how expression samples occur in metadata.
3.  Verify that all requested IDs are found.
4.  Explain why equal lengths are insufficient.

Do not perform a full join yet; joins are taught later.

------------------------------------------------------------------------

## Exercise 15 — Gene Selection

Suppose:

``` r
all_genes <- c(
  "BRCA1",
  "TP53",
  "APOE",
  "CFTR",
  "MICA"
)

genes_of_interest <- c(
  "MICA",
  "TP53",
  "NOT_PRESENT"
)
```

Use:

``` r
%in%
```

to test membership.

Then use:

``` r
match()
```

to preserve the order of `genes_of_interest`.

Identify which requested gene is absent.

------------------------------------------------------------------------

# 112. Intermediate Thinking Exercises

## Exercise 16 — `[` or `[[`?

For each situation, choose the more appropriate operator and explain
why.

### A

You want a smaller list containing three components.

### B

You want the numeric vector stored in one list component.

### C

You want a one-column data frame.

### D

You want the raw vector stored in one data-frame column.

### E

A function receives a column name as a character string and must extract
that column.

------------------------------------------------------------------------

## Exercise 17 — Diagnose Dimension Dropping

A function expects a matrix.

This works:

``` r
x[
  ,
  c(
    1,
    2
  )
]
```

but fails when:

``` r
x[
  ,
  1
]
```

Explain why.

Show the safer form.

------------------------------------------------------------------------

## Exercise 18 — The Missing-Match Problem

A researcher runs:

``` r
idx <- match(
  requested_ids,
  available_ids
)

data[
  idx,
]
```

Some requested IDs were not found.

What can happen?

What should be checked before subsetting?

Write diagnostic code that reports missing IDs.

------------------------------------------------------------------------

## Exercise 19 — The Wrong Use of `%in%`

The required output order is:

``` text
S4
S1
```

but the source order is:

``` text
S1
S2
S3
S4
```

Explain why:

``` r
source[
  source %in% requested
]
```

does not guarantee requested order.

Show the appropriate `match()` approach.

------------------------------------------------------------------------

## Exercise 20 — Scientific Filtering Audit

A colleague writes:

``` r
variants <- variants[
  variants$P < 0.05 &
    variants$MAF > 0.01,
]
```

Questions:

1.  What happens if `P` contains `NA`?
2.  What happens if `MAF` contains `NA`?
3.  How would you make the missingness rule explicit?
4.  What before/after counts should be recorded?
5.  Why is this still not a complete scientific QC protocol?

------------------------------------------------------------------------

# 113. Challenge — Sample and Variant Selection Audit

Create:

``` text
Chapter_04_Selection_Audit.Rmd
```

The project should demonstrate safe subsetting using both a general
dataset and a biological dataset.

## Part A — General dataset

Create a student or employee data frame containing:

``` text
ID
age
group
numeric measurement
one or more missing values
```

Perform and document:

``` text
positional row extraction
named column extraction
logical filtering
multiple conditions
complete-case selection
dynamic column extraction
```

For every important subset, record:

``` r
nrow()
names()
str()
```

where appropriate.

------------------------------------------------------------------------

## Part B — Biological dataset

Create a synthetic variant table containing:

``` text
SNP
CHR
BP
A1
A2
MAF
P
```

Include:

``` text
at least one missing P
at least one missing MAF
multiple chromosomes
several chromosome-6 variants
```

Perform:

``` text
chromosome selection
regional selection
P-value filtering
MAF filtering
missing-value separation
identifier selection with %in%
ordered extraction with match()
```

------------------------------------------------------------------------

## Part C — Audit Counts

For every filtering stage, record:

``` text
number before
number after
number removed
```

Example:

``` r
n_before <- nrow(variants)

filtered <- variants[
  keep,
]

n_after <- nrow(filtered)

n_removed <- n_before - n_after
```

------------------------------------------------------------------------

## Part D — Alignment Exercise

Create two sample-ID vectors in different orders.

Use:

``` r
identical()
match()
is.na()
```

to demonstrate safe alignment checking.

Do not merge them yet.

------------------------------------------------------------------------

## Part E — Structure Audit

Demonstrate:

``` r
df["column"]
df[["column"]]
df$column
```

and:

``` r
matrix[
  ,
  1
]

matrix[
  ,
  1,
  drop = FALSE
]
```

Explain how the return structures differ.

The project goal is:

> make every selection rule and every returned structure visible and
> auditable.

------------------------------------------------------------------------

# 114. Chapter Competency Check

Before moving to Chapter 5, you should be able to explain:

``` text
index
1-based indexing
positive indexing
negative indexing
zero index
logical indexing
logical recycling
named indexing
membership
matching
dimension dropping
subsetting
extraction
subassignment
```

You should be comfortable using:

``` r
[
[[
$
seq()
seq_along()
length()
names()
rownames()
colnames()
dim()
drop()
%in%
match()
which()
which.min()
which.max()
is.na()
complete.cases()
duplicated()
anyDuplicated()
identical()
```

You should also be able to answer:

### Vector

- How do I select positions?
- How do I exclude positions?
- How do I filter by a condition?
- How do I select by name?

### Matrix/array

- Which index refers to rows?
- Which refers to columns?
- What happens when only one row or column remains?
- When should I use `drop = FALSE`?

### List

- When do I want `[`?
- When do I want `[[`?
- When is `$` convenient?
- How do I extract a component when its name is stored in a variable?

### Data frame

- How do I select rows?
- How do I select columns?
- How do I preserve a one-column data frame?
- How do I safely handle missing values?

### Scientific data

- Are identifiers aligned?
- Are requested IDs missing?
- Did filtering change row counts as expected?
- Did duplicate indices or IDs create duplicate output?
- Is my selection scientifically justified?

------------------------------------------------------------------------

# 115. Key Takeaways

1.  **Indexing selects part of an R object.**

2.  **R uses 1-based indexing.**

3.  **Positive indices select positions; negative indices exclude
    positions.**

4.  **Zero selects no element and is not the first position.**

5.  **Repeated indices repeat output values.**

6.  **Logical vectors are the foundation of filtering.**

7.  **Missing values in logical conditions must be handled
    deliberately.**

8.  **Names and stable identifiers are often safer than hard-coded
    positions.**

9.  **`%in%` tests membership; `match()` finds positions and can
    preserve requested order.**

10. **Matrices and arrays use one index per dimension.**

11. **R may drop dimensions when only one row or column remains.**

12. **Use `drop = FALSE` when return structure must remain stable.**

13. **`[` generally returns a subset of a container.**

14. **`[[` extracts one component from list-like objects.**

15. **`$` is convenient for literal component names, but
    `[[name_variable]]` is better for dynamic programming.**

16. **`which()` is useful when positions are needed; it is usually
    unnecessary for ordinary logical subsetting.**

17. **`complete.cases()` provides an explicit way to identify rows
    complete for selected variables.**

18. **Equal row counts do not guarantee correct scientific alignment.**

19. **Subsetting can be syntactically correct while scientifically
    wrong.**

20. **Always ask both: what values did I select, and what structure did
    R return?**

------------------------------------------------------------------------

# 116. Repository Output from This Chapter

A useful Chapter 4 practice area could contain:

``` text
code/
└── 04_Indexing_Subsetting_and_Data_Extraction/
    ├── 01_vector_indexing.R
    ├── 02_logical_indexing.R
    ├── 03_named_indexing_and_matching.R
    ├── 04_matrix_and_array_indexing.R
    ├── 05_list_extraction.R
    ├── 06_data_frame_subsetting.R
    ├── 07_missing_and_duplicate_indices.R
    └── 08_sample_variant_selection_audit.R

exercises/
└── chapter04/

projects/
└── beginner/
    └── sample_variant_selection_audit/
```

The exact number of scripts is not important.

The important outcome is that the learner can move from:

``` text
"I know that brackets exist"
```

to:

``` text
"I can predict what R will select and what structure R will return."
```

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

5.  Wickham H. *Advanced R*: sections on subsetting and vector
    semantics.

## Scientific Computing Context

6.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

7.  Noble WS. A quick guide to organizing computational biology
    projects. *PLoS Computational Biology*. 2009;5(7):e1000424.

## Useful R Documentation

Explore:

``` r
?Extract
?Subscript
?match
?which
?which.min
?complete.cases
?subset
?drop
?duplicated
```

A particularly useful help topic is:

``` r
?Extract
```

because it documents the behavior of:

``` r
[
[[
$
```

across many R objects.

Do not try to memorize the full help page.

Run small examples and inspect the returned structure.

------------------------------------------------------------------------

# Next Chapter

## Chapter 5 — Writing Reusable Code

We now know how to:

``` text
create R objects
understand their types
organize values into data structures
extract exactly the values we need
```

The next step is to stop repeating the same code manually.

Chapter 5 will teach how to create reusable functions.

It will explain:

- why functions are needed;
- what a function is;
- function syntax;
- arguments;
- required and optional arguments;
- default values;
- return values;
- local objects;
- scope at an introductory level;
- input validation;
- side effects;
- error messages;
- function naming;
- documentation;
- and testing small reusable functions.

The progression is:

``` text
Chapter 2
How R evaluates values
        ↓
Chapter 3
How R organizes values
        ↓
Chapter 4
How R selects values
        ↓
Chapter 5
How we package repeated logic into reusable functions
```
