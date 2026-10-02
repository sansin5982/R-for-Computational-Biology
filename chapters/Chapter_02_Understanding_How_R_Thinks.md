Chapter 2 — Understanding How R Thinks
================
Sandeep Kumar Singh, PhD

- [Chapter 2 — Understanding How R
  Thinks](#chapter-2--understanding-how-r-thinks)
  - [Chapter Purpose](#chapter-purpose)
  - [Learning Outcomes](#learning-outcomes)
  - [Chapter Roadmap](#chapter-roadmap)
  - [Mental Model](#mental-model)
  - [1. Objects, Names and Values](#1-objects-names-and-values)
  - [2. Assignment and Reassignment](#2-assignment-and-reassignment)
  - [3. Atomic Types and `typeof()`](#3-atomic-types-and-typeof)
  - [4. Coercion and Type Hierarchies](#4-coercion-and-type-hierarchies)
  - [5. Vectorized Evaluation](#5-vectorized-evaluation)
  - [6. Recycling Rules](#6-recycling-rules)
  - [7. Missing and Special Values](#7-missing-and-special-values)
  - [8. Attributes and Metadata](#8-attributes-and-metadata)
  - [9. Copy-on-Modify: Conceptual
    Introduction](#9-copy-on-modify-conceptual-introduction)
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

# Chapter 2 — Understanding How R Thinks

## Chapter Purpose

Build the internal mental models needed to reason about R: objects,
assignment, evaluation, types, coercion, vectorization, missing values,
attributes, recycling, and the difference between names and values.

This chapter keeps the course centered on **R programming**. Biological
examples are used to reinforce the same programming ideas after they are
understood on simpler data.

## Learning Outcomes

By the end of the chapter, the learner should be able to:

- explain names, values, and assignment
- inspect type and structure rather than guessing
- predict basic coercion and recycling
- distinguish `NA`, `NaN`, `Inf`, and `NULL`
- reason about vectorized expressions
- recognize attributes as metadata attached to objects

## Chapter Roadmap

1.  **Objects, Names and Values**
2.  **Assignment and Reassignment**
3.  **Atomic Types and `typeof()`**
4.  **Coercion and Type Hierarchies**
5.  **Vectorized Evaluation**
6.  **Recycling Rules**
7.  **Missing and Special Values**
8.  **Attributes and Metadata**
9.  **Copy-on-Modify: Conceptual Introduction**

## Mental Model

R code creates names that refer to values. Operations act on objects
according to their type, class, attributes, and vector length. Many
surprises disappear once you inspect those properties explicitly.

## 1. Objects, Names and Values

Treat **Objects, Names and Values** as a programming concept rather than
a recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 2. Assignment and Reassignment

Treat **Assignment and Reassignment** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 3. Atomic Types and `typeof()`

Treat **Atomic Types and `typeof()`** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 4. Coercion and Type Hierarchies

Treat **Coercion and Type Hierarchies** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 5. Vectorized Evaluation

Treat **Vectorized Evaluation** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 6. Recycling Rules

Treat **Recycling Rules** as a programming concept rather than a recipe.
Start with a small object, inspect its structure, make one controlled
change, and verify what R returns before scaling the pattern to real
data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 7. Missing and Special Values

Treat **Missing and Special Values** as a programming concept rather
than a recipe. Start with a small object, inspect its structure, make
one controlled change, and verify what R returns before scaling the
pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 8. Attributes and Metadata

Treat **Attributes and Metadata** as a programming concept rather than a
recipe. Start with a small object, inspect its structure, make one
controlled change, and verify what R returns before scaling the pattern
to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

## 9. Copy-on-Modify: Conceptual Introduction

Treat **Copy-on-Modify: Conceptual Introduction** as a programming
concept rather than a recipe. Start with a small object, inspect its
structure, make one controlled change, and verify what R returns before
scaling the pattern to real data.

**Professional habit:** use inspection and a minimal example before
adapting the concept to a large workflow.

# Essential Functions and Tools

The following functions or tools should become familiar during this
chapter:

- `<-`
- `=`
- `typeof()`
- `class()`
- `str()`
- `is.*()`
- `as.*()`
- `length()`
- `attributes()`
- `attr()`
- `is.na()`
- `is.nan()`
- `is.infinite()`

Do not memorize the list mechanically. For unfamiliar functions, inspect
documentation with `?`, `args()`, `str()`, `class()`, and small test
objects.

# General Example

Use a small set of measurements to observe type, coercion,
vectorization, and missingness.

``` r
x <- c(10, 20, 30, NA)
typeof(x)
class(x)
x * 2
is.na(x)
mean(x, na.rm = TRUE)

mixed <- c(1, 2, "3")
typeof(mixed)
str(mixed)
```

After running the code, inspect the relevant objects rather than
assuming their structure.

# Computational Biology Example

Use allele-frequency-like values to reinforce the same ideas.

``` r
af <- c(0.12, 0.04, NA, 0.31)
typeof(af)
is.na(af)
af_percent <- af * 100
af_percent

variant_id <- c("rs1", "rs2", "rs3", "rs4")
length(variant_id) == length(af)
```

This is a teaching example. It demonstrates the R concept; it is not
presented as a complete biological analysis.

# Expert Additions Often Missing from Introductory Courses

- Names are not values; reassignment changes bindings, not the
  historical script.
- Implicit coercion can silently change an entire vector’s type.
- Recycling is convenient but can create subtle bugs when lengths are
  unintended.
- `class()` and `typeof()` answer different questions.
- Attributes underpin factors, dates, matrices, and many specialized
  biological classes.
- Copy-on-modify is introduced conceptually now and revisited during
  performance work.

These additions are included because they prevent later misconceptions
or improve real-world transfer.

# Common Mistakes

- **Accidental coercion** — mixing characters with numbers can turn the
  whole atomic vector into character
- **Silent recycling** — short vectors may be recycled in arithmetic
- **Missing-value comparison** — `x == NA` is not the correct
  missingness test
- **Confusing NULL and NA** — they represent different ideas
- **Assuming class equals storage type** — class is a higher-level
  interpretation

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

For this chapter specifically, pay particular attention to: **type,
length, coercion, missing values, and unexpected attributes**.

# Performance and Scalability

Vectorized operations are usually preferable to repeated scalar work,
but vectorization is not magic. Later chapters will distinguish readable
vectorization from memory-heavy intermediate allocations.

Do not optimize code before verifying correctness and understanding the
object model.

# Professional / Reviewer Perspective

A reviewer should be able to understand what data types and
missing-value conventions the analysis expects. Silent coercion or
recycling can invalidate downstream scientific results without causing a
syntax error.

# Practice and Transfer Exercises

1.  Predict the result type of several mixed vectors before running
    them.
2.  Compare `class()` and `typeof()` on numeric, integer, logical,
    factor, and Date objects.
3.  Demonstrate correct and incorrect missing-value tests.
4.  Create two unequal-length vectors and examine recycling.
5.  Inspect attributes on a factor or Date.
6.  Explain why `c(1, TRUE, 'x')` becomes character.

# Chapter Project

**R Object Inspection Notebook**

Create an `.Rmd` that builds several ordinary and genomics-style
objects, records `typeof()`, `class()`, `length()`, `str()`,
missingness, and attributes, and explains each result in plain language.

The project should include a short README, clear inputs/outputs,
reproducible code, and a note explaining which R concepts from this
chapter are being demonstrated.

# Competency Check

Before continuing, the learner should be able to:

- predict basic coercion
- inspect objects systematically
- explain vectorization and recycling
- distinguish special missing values
- recognize attributes

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

**Chapter 3 — Mastering R Data Structures** turns these foundations into
practical work with vectors, matrices, arrays, lists, factors, data
frames, and specialized structures.
