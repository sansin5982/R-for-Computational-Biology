Chapter 4 — Indexing, Subsetting and Data Extraction
================
Sandeep Kumar Singh, PhD

- [Chapter 4 — Indexing, Subsetting and Data
  Extraction](#chapter-4--indexing-subsetting-and-data-extraction)
  - [Chapter Purpose](#chapter-purpose)
  - [Chapter Roadmap](#chapter-roadmap)
  - [Mental Model](#mental-model)
  - [1. Vector Indexing](#1-vector-indexing)
  - [2. Logical Indexing](#2-logical-indexing)
  - [3. Named Indexing](#3-named-indexing)
  - [4. Matrix and Array Indexing](#4-matrix-and-array-indexing)
  - [5. Data-Frame Subsetting](#5-data-frame-subsetting)
  - [6. `[` versus `[[`](#6--versus-)
  - [7. The `$` Operator](#7-the--operator)
  - [8. Dropping Dimensions](#8-dropping-dimensions)
  - [9. Missing and Duplicate Indices](#9-missing-and-duplicate-indices)
  - [10. Safe Conditional Extraction](#10-safe-conditional-extraction)
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

# Chapter 4 — Indexing, Subsetting and Data Extraction

## Chapter Purpose

Teach precise extraction from R objects using positional, logical,
named, and conditional indexing. The chapter emphasizes the behavioral
differences among `[`, `[[`, and `$`, plus safe subsetting habits.

This chapter keeps the course centered on **R programming**. Biological
examples are used to reinforce the same programming ideas after they are
understood on simpler data.

## Chapter Roadmap

1.  **Vector Indexing**
2.  **Logical Indexing**
3.  **Named Indexing**
4.  **Matrix and Array Indexing**
5.  **Data-Frame Subsetting**
6.  **`[` versus `[[`**
7.  **The `$` Operator**
8.  **Dropping Dimensions**
9.  **Missing and Duplicate Indices**
10. **Safe Conditional Extraction**

## Mental Model

Subsetting answers two separate questions: which elements should be
selected, and what structure should the result retain? Many bugs arise
when only the first question is considered.

## 1. Vector Indexing

Treat **Vector Indexing** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 2. Logical Indexing

Treat **Logical Indexing** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 3. Named Indexing

Treat **Named Indexing** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 4. Matrix and Array Indexing

Treat **Matrix and Array Indexing** as a programming concept rather than
a recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 5. Data-Frame Subsetting

Treat **Data-Frame Subsetting** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 6. `[` versus `[[`

Treat **`[` versus `[[`** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 7. The `$` Operator

Treat **The `$` Operator** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 8. Dropping Dimensions

Treat **Dropping Dimensions** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 9. Missing and Duplicate Indices

Treat **Missing and Duplicate Indices** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 10. Safe Conditional Extraction

Treat **Safe Conditional Extraction** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

# Essential Functions and Tools

The following functions or tools should become familiar during this
chapter:

- `[`
- `[[`
- `$`
- `which()`
- `which.min()`
- `which.max()`
- `subset()`
- `drop()`
- `match()`
- `%in%`
- `is.na()`
- `complete.cases()`

Do not memorize the list mechanically. For unfamiliar functions, inspect
documentation with `?`, `args()`, `str()`, `class()`, and small test
objects.

# General Example

Use a small table of students and scores to compare positional and
logical subsetting.

``` r
students <- data.frame(
  id = c("S1", "S2", "S3", "S4"),
  score = c(82, 91, 76, 88),
  group = c("A", "B", "A", "B")
)

students[1:2, ]
students[students$score >= 85, ]
students[students$group %in% "B", c("id", "score")]
```

After running the code, inspect the relevant objects rather than
assuming their structure.

# Computational Biology Example

Filter a synthetic variant table while preserving identifiers and
relevant columns.

``` r
variants <- data.frame(
  SNP = c("rs1", "rs2", "rs3", "rs4"),
  CHR = c(6, 6, 6, 6),
  BP = c(26000000, 27500000, 31300000, 32600000),
  P = c(0.4, 0.02, 5e-8, NA)
)

variants[!is.na(variants$P) & variants$P <= 5e-8, ]
variants[variants$SNP %in% c("rs2", "rs3"), c("SNP", "P")]
```

This is a teaching example. It demonstrates the R concept; it is not
presented as a complete biological analysis.

# Expert Additions Often Missing from Introductory Courses

- `[` usually preserves a container; `[[` extracts one component.
- Dimension dropping can change matrices into vectors unexpectedly.
- Logical indices containing `NA` can propagate missing rows/elements.
- Names are often safer than hard-coded column positions.
- Partial matching with `$` can be surprising and should not be relied
  upon.
- Matching identifiers explicitly is safer than assuming row order.

These additions are included because they prevent later misconceptions
or improve real-world transfer.

# Common Mistakes

- **Off-by-one indices** — R uses 1-based indexing
- **Mixed positive and negative indices** — generally invalid except for
  zeros
- **Dimension drop** — single-column matrix extraction may become a
  vector
- **NA logical indices** — can produce NA output rows
- **Order assumptions** — subsetting two objects independently can
  misalign them

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

For this chapter specifically, pay particular attention to: **index
lengths, names, dimensions, `NA` in logical conditions, and return
structure**.

# Performance and Scalability

For large tables, repeated base indexing can still be efficient, but
later chapters introduce `data.table` and database-style approaches for
scale. Correct alignment remains more important than micro-optimization.

Do not optimize code before verifying correctness and understanding the
object model.

# Professional / Reviewer Perspective

Subsetting code is often where samples or variants are silently lost.
Reviewers should be able to reconstruct inclusion criteria and verify
that identifiers, not accidental order, drive joins and filters.

# Practice and Transfer Exercises

1.  Subset every second element of a vector.
2.  Filter rows using two logical conditions.
3.  Extract one list element with both `[` and `[[` and compare
    structure.
4.  Demonstrate matrix dimension dropping.
5.  Use `%in%` to select identifiers.
6.  Filter a variant table while preserving missing P-values separately.

# Chapter Project

**Sample and Variant Selection Audit**

Create reusable examples showing exactly which samples and variants are
retained under several criteria. Record before/after counts and
identifiers so the selection can be audited.

The project should include a short README, clear inputs/outputs,
reproducible code, and a note explaining which R concepts from this
chapter are being demonstrated.

# Competency Check

Before continuing, the learner should be able to:

- use multiple indexing modes
- distinguish extraction operators
- preserve structure intentionally
- handle missingness in filters
- avoid row-order assumptions

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

**Chapter 5 — Writing Reusable Code** moves repeated operations into
well-designed functions.
