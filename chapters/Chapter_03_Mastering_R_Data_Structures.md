Chapter 3 — Mastering R Data Structures
================
Sandeep Kumar Singh, PhD

- [Chapter 3 — Mastering R Data
  Structures](#chapter-3--mastering-r-data-structures)
  - [Chapter Purpose](#chapter-purpose)
  - [Learning Outcomes](#learning-outcomes)
  - [Chapter Roadmap](#chapter-roadmap)
  - [Mental Model](#mental-model)
  - [1. Atomic Vectors](#1-atomic-vectors)
  - [2. Matrices](#2-matrices)
  - [3. Arrays](#3-arrays)
  - [4. Lists](#4-lists)
  - [5. Factors](#5-factors)
  - [6. Data Frames](#6-data-frames)
  - [7. Names, Dimensions and
    Dimnames](#7-names-dimensions-and-dimnames)
  - [8. Nested Structures](#8-nested-structures)
  - [9. Introduction to Specialized
    Classes](#9-introduction-to-specialized-classes)
- [Essential Functions and Tools](#essential-functions-and-tools)
- [General Example](#general-example)
- [Computational Biology Example](#computational-biology-example)
- [Expert Additions Often Missing from Introductory
  Courses](#expert-additions-often-missing-from-introductory-courses)
- [Common Mistakes](#common-mistakes)
- [Debugging Clinic](#debugging-clinic)
- [Performance and Scalability](#performance-and-scalability)
- [Professional / Reviewer
  Perspective](#professional--reviewer-perspective)
- [Practice and Transfer Exercises](#practice-and-transfer-exercises)
- [Chapter Project](#chapter-project)
- [Competency Check](#competency-check)
- [References and Further Reading](#references-and-further-reading)
- [Next Chapter](#next-chapter)

# Chapter 3 — Mastering R Data Structures

## Chapter Purpose

Develop fluency with the major R data structures and understand when
each structure is appropriate. This chapter emphasizes structure,
dimensions, names, attributes, and nested objects before moving to
manipulation frameworks.

This chapter keeps the course centered on **R programming**. Biological
examples are used to reinforce the same programming ideas after they are
understood on simpler data.

## Learning Outcomes

By the end of the chapter, the learner should be able to:

- construct and inspect vectors, matrices, arrays, lists, factors, and
  data frames
- choose an appropriate structure for a task
- understand dimensions and names
- navigate nested lists
- explain factor levels and common pitfalls
- recognize how biological data often use structured objects

## Chapter Roadmap

1.  **Atomic Vectors**
2.  **Matrices**
3.  **Arrays**
4.  **Lists**
5.  **Factors**
6.  **Data Frames**
7.  **Names, Dimensions and Dimnames**
8.  **Nested Structures**
9.  **Introduction to Specialized Classes**

## Mental Model

A data structure determines how values are organized and what operations
are natural. Ask: is the object homogeneous or heterogeneous,
one-dimensional or multi-dimensional, flat or nested?

## 1. Atomic Vectors

Treat **Atomic Vectors** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 2. Matrices

Treat **Matrices** as a programming concept rather than a recipe. Start
with a small object, inspect its structure, make one controlled change,
and verify what R returns before scaling the pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 3. Arrays

Treat **Arrays** as a programming concept rather than a recipe. Start
with a small object, inspect its structure, make one controlled change,
and verify what R returns before scaling the pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 4. Lists

Treat **Lists** as a programming concept rather than a recipe. Start
with a small object, inspect its structure, make one controlled change,
and verify what R returns before scaling the pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 5. Factors

Treat **Factors** as a programming concept rather than a recipe. Start
with a small object, inspect its structure, make one controlled change,
and verify what R returns before scaling the pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 6. Data Frames

Treat **Data Frames** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 7. Names, Dimensions and Dimnames

Treat **Names, Dimensions and Dimnames** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 8. Nested Structures

Treat **Nested Structures** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 9. Introduction to Specialized Classes

Treat **Introduction to Specialized Classes** as a programming concept
rather than a recipe. Start with a small object, inspect its structure,
make one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

# Essential Functions and Tools

The following functions or tools should become familiar during this
chapter:

- `c()`
- `vector()`
- `matrix()`
- `array()`
- `list()`
- `factor()`
- `data.frame()`
- `names()`
- `dim()`
- `nrow()`
- `ncol()`
- `dimnames()`
- `levels()`
- `unlist()`
- `str()`

Do not memorize the list mechanically. For unfamiliar functions, inspect
documentation with `?`, `args()`, `str()`, `class()`, and small test
objects.

# General Example

Build a small student dataset in multiple structures and compare how
each represents the same information.

``` r
scores <- c(82, 91, 76, 88)
score_matrix <- matrix(scores, nrow = 2)
student <- list(
  id = "S01",
  scores = scores,
  passed = TRUE
)
students <- data.frame(
  id = c("S01", "S02"),
  group = factor(c("A", "B")),
  score = c(82, 91)
)
str(student)
str(students)
```

After running the code, inspect the relevant objects rather than
assuming their structure.

# Computational Biology Example

Represent gene-expression measurements and sample metadata using
structures appropriate to each component.

``` r
expr <- matrix(
  c(10, 12, 8, 15, 20, 18),
  nrow = 3,
  dimnames = list(
    c("GENE1", "GENE2", "GENE3"),
    c("SampleA", "SampleB")
  )
)

metadata <- data.frame(
  sample = c("SampleA", "SampleB"),
  tissue = factor(c("Blood", "Brain"))
)

str(expr)
str(metadata)
```

This is a teaching example. It demonstrates the R concept; it is not
presented as a complete biological analysis.

# Expert Additions Often Missing from Introductory Courses

- Factors encode categorical levels and can retain unused levels.
- A matrix is homogeneous; mixing types can coerce every element.
- Lists are the backbone of many model and package return objects.
- Data frames are lists of equal-length columns, not matrices.
- Dimnames are not decorative; they can protect against sample/order
  mistakes.
- Specialized Bioconductor classes build on core R object concepts.

These additions are included because they prevent later misconceptions
or improve real-world transfer.

# Common Mistakes

- **Matrix coercion** — adding one character value can coerce all cells
- **Factor confusion** — levels and displayed labels are not
  interchangeable with integer codes
- **List flattening** — `unlist()` can destroy useful structure
- **Row-order assumptions** — unnamed dimensions make alignment errors
  easier
- **Data-frame/matrix confusion** — operations may return different
  object classes

# Debugging Clinic

When something fails, use the smallest useful diagnostic sequence:

``` text
1. Read the exact error or warning.
2. Inspect the object with class(), typeof(), str(), names(), dim(), or length().
3. Check the function signature and documentation.
4. Reproduce the issue on a smaller object.
5. Verify assumptions about missingness, types, dimensions, paths, or packages.
6. Only then modify the code.
```

For this chapter specifically, pay particular attention to: **class,
dimensions, names, nested structure, factor levels, and coercion**.

# Performance and Scalability

Choose structures that match the computation. Matrices are efficient for
homogeneous numeric work; lists offer flexibility but may require
different iteration patterns. Specialized structures can reduce errors
by encoding domain semantics.

Do not optimize code before verifying correctness and understanding the
object model.

# Professional / Reviewer Perspective

Scientific code should make sample and feature identities explicit.
Unnamed matrices or implicit row-order assumptions are frequent sources
of irreproducible biological analyses.

# Practice and Transfer Exercises

1.  Create equivalent information as a vector, list, and data frame.
2.  Add row and column names to a matrix and retrieve them.
3.  Create a factor with an unused level and inspect `levels()`.
4.  Construct and inspect a nested list.
5.  Show why a matrix cannot safely mix numeric and character values.
6.  Create a small expression matrix with sample metadata.

# Chapter Project

**Structured Study Dataset**

Build a small study object containing a numeric matrix, sample metadata
data frame, analysis settings list, and factor variables. Document why
each structure was chosen.

The project should include a short README, clear inputs/outputs,
reproducible code, and a note explaining which R concepts from this
chapter are being demonstrated.

# Competency Check

Before continuing, the learner should be able to:

- select suitable data structures
- inspect nested objects
- manage names and dimensions
- explain factors
- distinguish matrices, lists, and data frames

# References and Further Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.
2.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.
3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

For package APIs and software behavior that can change over time,
consult the current official R, CRAN, Posit, or Bioconductor
documentation.

# Next Chapter

**Chapter 4 — Indexing, Subsetting and Data Extraction** teaches how to
retrieve exactly the elements, rows, columns, and nested components you
need.
