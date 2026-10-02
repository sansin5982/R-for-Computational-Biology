Chapter 1 — Building a Professional R Environment
================
Sandeep Kumar Singh, PhD

- [Chapter 1 — Building a Professional R
  Environment](#chapter-1--building-a-professional-r-environment)
  - [Lesson 1.1 — R as a Programming
    Environment](#lesson-11--r-as-a-programming-environment)
    - [Where This Lesson Fits](#where-this-lesson-fits)
    - [1. What Is R?](#1-what-is-r)
    - [2. R Is the Language; RStudio Is Not
      R](#2-r-is-the-language-rstudio-is-not-r)
    - [3. What Is an IDE?](#3-what-is-an-ide)
    - [4. R Can Run Without RStudio](#4-r-can-run-without-rstudio)
    - [5. Base R](#5-base-r)
    - [6. What Is an R Package?](#6-what-is-an-r-package)
    - [7. Installing a Package Is Different from Loading
      It](#7-installing-a-package-is-different-from-loading-it)
    - [8. What Is CRAN?](#8-what-is-cran)
    - [9. What Is Bioconductor?](#9-what-is-bioconductor)
    - [10. The R Ecosystem](#10-the-r-ecosystem)
    - [11. Your First Environment
      Inspection](#11-your-first-environment-inspection)
    - [12. Understanding an R Session](#12-understanding-an-r-session)
    - [13. Interactive Work Versus Script-Based
      Work](#13-interactive-work-versus-script-based-work)
    - [14. General Example: A Small Numerical
      Dataset](#14-general-example-a-small-numerical-dataset)
    - [15. Computational Biology Example: Variant
      P-values](#15-computational-biology-example-variant-p-values)
    - [16. Why R Is Important in Computational
      Biology](#16-why-r-is-important-in-computational-biology)
    - [17. Common Misconceptions](#17-common-misconceptions)
    - [18. Debugging Clinic](#18-debugging-clinic)
    - [19. Expert Commentary](#19-expert-commentary)
    - [20. From the Reviewer’s
      Perspective](#20-from-the-reviewers-perspective)
  - [Practice Questions — Basic Level](#practice-questions--basic-level)
    - [Concept Questions](#concept-questions)
    - [Practical Questions](#practical-questions)
  - [Lesson Competency Check](#lesson-competency-check)
  - [Key Takeaways](#key-takeaways)
  - [References and Further Reading](#references-and-further-reading)
    - [Essential Reading](#essential-reading)
    - [Additional Reading](#additional-reading)
    - [Official Documentation](#official-documentation)
  - [Next Lesson](#next-lesson)
    - [Lesson 1.2 — Installing R and Verifying the
      Installation](#lesson-12--installing-r-and-verifying-the-installation)
  - [Lesson 1.2 — Installing R and Verifying the
    Installation](#lesson-12--installing-r-and-verifying-the-installation-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-1)
    - [Learning Objectives](#learning-objectives)
  - [1. Before Installing Anything: Know What You Are
    Installing](#1-before-installing-anything-know-what-you-are-installing)
  - [2. Where Should R Come From?](#2-where-should-r-come-from)
  - [3. Understanding R Version
    Numbers](#3-understanding-r-version-numbers)
  - [4. Windows Installation](#4-windows-installation)
  - [5. macOS Installation](#5-macos-installation)
  - [6. Linux Installation](#6-linux-installation)
  - [7. Verifying R from Inside R](#7-verifying-r-from-inside-r)
    - [7.1 R version](#71-r-version)
    - [7.2 Detailed version object](#72-detailed-version-object)
    - [7.3 R home directory](#73-r-home-directory)
    - [7.4 Platform information](#74-platform-information)
    - [7.5 Operating-system
      information](#75-operating-system-information)
  - [8. R Installation Directory, Package Library and Project Directory
    Are
    Different](#8-r-installation-directory-package-library-and-project-directory-are-different)
  - [9. Verifying R from the Terminal](#9-verifying-r-from-the-terminal)
  - [10. What Is PATH?](#10-what-is-path)
  - [11. Inspecting PATH from R](#11-inspecting-path-from-r)
  - [12. Multiple Versions of R](#12-multiple-versions-of-r)
  - [13. Why Packages May Seem to Disappear After an R
    Upgrade](#13-why-packages-may-seem-to-disappear-after-an-r-upgrade)
  - [14. A Small Installation Diagnostic
    Script](#14-a-small-installation-diagnostic-script)
  - [15. General Practical Example](#15-general-practical-example)
  - [16. Computational Biology Practical
    Example](#16-computational-biology-practical-example)
  - [17. R and WSL: An Important
    Distinction](#17-r-and-wsl-an-important-distinction)
  - [18. Do You Need the Newest R Version
    Immediately?](#18-do-you-need-the-newest-r-version-immediately)
  - [19. 64-bit Computing and
    Architecture](#19-64-bit-computing-and-architecture)
  - [20. Common Mistakes](#20-common-mistakes)
    - [Mistake 1 — Installing RStudio but not
      R](#mistake-1--installing-rstudio-but-not-r)
    - [Mistake 2 — Assuming the installed
      version](#mistake-2--assuming-the-installed-version)
    - [Mistake 3 — Confusing R’s installation folder with the project
      folder](#mistake-3--confusing-rs-installation-folder-with-the-project-folder)
    - [Mistake 4 — Assuming missing packages were deleted after an
      upgrade](#mistake-4--assuming-missing-packages-were-deleted-after-an-upgrade)
    - [Mistake 5 — Randomly modifying
      PATH](#mistake-5--randomly-modifying-path)
    - [Mistake 6 — Using unofficial
      installers](#mistake-6--using-unofficial-installers)
  - [21. Debugging Clinic](#21-debugging-clinic)
    - [Scenario 1 — RStudio opens, but the terminal says R is not
      recognized](#scenario-1--rstudio-opens-but-the-terminal-says-r-is-not-recognized)
    - [Scenario 2 — RStudio reports a different version from the
      terminal](#scenario-2--rstudio-reports-a-different-version-from-the-terminal)
    - [Scenario 3 — A package worked before the R
      upgrade](#scenario-3--a-package-worked-before-the-r-upgrade)
    - [Scenario 4 — A collaborator cannot reproduce your
      analysis](#scenario-4--a-collaborator-cannot-reproduce-your-analysis)
  - [22. Expert Commentary](#22-expert-commentary)
  - [23. From the Reviewer’s
    Perspective](#23-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-1)
    - [Concept Questions](#concept-questions-1)
  - [Practical Exercises](#practical-exercises)
    - [Exercise 1 — Identify Your R
      Version](#exercise-1--identify-your-r-version)
    - [Exercise 2 — Locate R](#exercise-2--locate-r)
    - [Exercise 3 — Inspect Package
      Libraries](#exercise-3--inspect-package-libraries)
    - [Exercise 4 — Inspect the System](#exercise-4--inspect-the-system)
    - [Exercise 5 — Inspect the Working
      Directory](#exercise-5--inspect-the-working-directory)
    - [Exercise 6 — Terminal
      Verification](#exercise-6--terminal-verification)
  - [Small Challenge](#small-challenge)
  - [Lesson Competency Check](#lesson-competency-check-1)
  - [Key Takeaways](#key-takeaways-1)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson)
  - [References and Further Reading](#references-and-further-reading-1)
    - [Essential Reading](#essential-reading-1)
    - [Additional Reading](#additional-reading-1)
    - [Official Documentation](#official-documentation-1)
  - [Next Lesson](#next-lesson-1)
    - [Lesson 1.3 — RStudio and the
      IDE](#lesson-13--rstudio-and-the-ide)
  - [Lesson 1.3 — RStudio and the
    IDE](#lesson-13--rstudio-and-the-ide-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-2)
    - [Learning Objectives](#learning-objectives-1)
  - [1. RStudio Is a Workspace for
    Programming](#1-rstudio-is-a-workspace-for-programming)
  - [2. The Four-Pane Layout](#2-the-four-pane-layout)
  - [3. The Source Editor](#3-the-source-editor)
  - [4. The Console](#4-the-console)
  - [5. Source Versus Console](#5-source-versus-console)
  - [6. Running Code from Source](#6-running-code-from-source)
  - [7. Running a Complete Script](#7-running-a-complete-script)
  - [8. The Environment Pane](#8-the-environment-pane)
  - [9. Hidden Session State](#9-hidden-session-state)
  - [10. History](#10-history)
  - [11. Files](#11-files)
  - [12. Plots](#12-plots)
  - [13. Packages](#13-packages)
  - [14. Help](#14-help)
  - [15. Viewer](#15-viewer)
  - [16. Terminal](#16-terminal)
  - [17. Jobs](#17-jobs)
  - [18. High-Value Keyboard
    Shortcuts](#18-high-value-keyboard-shortcuts)
  - [19. Code Completion and Function
    Information](#19-code-completion-and-function-information)
  - [20. Create the Lesson Script](#20-create-the-lesson-script)
  - [21. General Example](#21-general-example)
  - [22. Computational Biology
    Example](#22-computational-biology-example)
  - [23. Workspace Restoration](#23-workspace-restoration)
  - [24. Restarting R](#24-restarting-r)
  - [25. RStudio Is Not Your Project](#25-rstudio-is-not-your-project)
  - [26. Common Mistakes](#26-common-mistakes)
  - [27. Debugging Clinic](#27-debugging-clinic)
    - [Scenario 1 — Object not found](#scenario-1--object-not-found)
    - [Scenario 2 — Code works only after running lines out of
      order](#scenario-2--code-works-only-after-running-lines-out-of-order)
    - [Scenario 3 — Plot appears but is not
      saved](#scenario-3--plot-appears-but-is-not-saved)
    - [Scenario 4 — Package works only after clicking its
      checkbox](#scenario-4--package-works-only-after-clicking-its-checkbox)
  - [28. Expert Commentary](#28-expert-commentary)
  - [29. From the Reviewer’s
    Perspective](#29-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-2)
    - [Concept Questions](#concept-questions-2)
  - [Practical Exercises](#practical-exercises-1)
    - [Exercise 1 — Create a Script](#exercise-1--create-a-script)
    - [Exercise 2 — Run Code in Different
      Ways](#exercise-2--run-code-in-different-ways)
    - [Exercise 3 — Inspect
      Environment](#exercise-3--inspect-environment)
    - [Exercise 4 — Expose Hidden
      State](#exercise-4--expose-hidden-state)
    - [Exercise 5 — General Example](#exercise-5--general-example)
    - [Exercise 6 — Computational Biology
      Example](#exercise-6--computational-biology-example)
  - [Small Challenge](#small-challenge-1)
  - [Lesson Competency Check](#lesson-competency-check-2)
  - [Key Takeaways](#key-takeaways-2)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-1)
  - [References and Further Reading](#references-and-further-reading-2)
    - [Essential Reading](#essential-reading-2)
    - [Additional Reading](#additional-reading-2)
  - [Next Lesson](#next-lesson-2)
    - [Lesson 1.4 — Your First R
      Project](#lesson-14--your-first-r-project)
  - [Lesson 1.4 — Your First R
    Project](#lesson-14--your-first-r-project-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-3)
    - [Learning Objectives](#learning-objectives-2)
  - [1. The Problem with Loose
    Scripts](#1-the-problem-with-loose-scripts)
  - [2. What Is a Project?](#2-what-is-a-project)
  - [3. A Script Is Not a Project](#3-a-script-is-not-a-project)
  - [4. What Is an RStudio Project?](#4-what-is-an-rstudio-project)
  - [5. What Is the Project Root?](#5-what-is-the-project-root)
  - [6. Why Project Roots Matter](#6-why-project-roots-matter)
  - [7. Creating an RStudio Project](#7-creating-an-rstudio-project)
  - [8. Confirming the Project
    Location](#8-confirming-the-project-location)
  - [9. Create the Basic Directory
    Structure](#9-create-the-basic-directory-structure)
  - [10. Avoiding Errors When Creating Existing
    Directories](#10-avoiding-errors-when-creating-existing-directories)
  - [11. Create Several Directories
    Efficiently](#11-create-several-directories-efficiently)
  - [12. What Belongs in Each
    Directory?](#12-what-belongs-in-each-directory)
    - [`data/`](#data)
    - [`scripts/`](#scripts)
    - [`figures/`](#figures)
    - [`tables/`](#tables)
    - [`reports/`](#reports)
    - [`outputs/`](#outputs)
  - [13. Why Number Scripts?](#13-why-number-scripts)
  - [14. Raw Data and Processed Data](#14-raw-data-and-processed-data)
  - [15. A More Mature Analytical
    Structure](#15-a-more-mature-analytical-structure)
  - [16. The README Is Part of the
    Project](#16-the-readme-is-part-of-the-project)
  - [17. General Example — A Simple Sales
    Project](#17-general-example--a-simple-sales-project)
  - [18. Computational Biology Example — GWAS Summary Statistics
    Project](#18-computational-biology-example--gwas-summary-statistics-project)
  - [19. Computational Biology Projects Often Need Special
    Care](#19-computational-biology-projects-often-need-special-care)
  - [20. Data Should Not Be Mixed with
    Results](#20-data-should-not-be-mixed-with-results)
  - [21. Scripts Should Not Be Mixed with Generated
    Outputs](#21-scripts-should-not-be-mixed-with-generated-outputs)
  - [22. Project Naming](#22-project-naming)
  - [23. File and Folder Naming](#23-file-and-folder-naming)
  - [24. Do Not Use the Desktop as Project
    Architecture](#24-do-not-use-the-desktop-as-project-architecture)
  - [25. Opening a Project Correctly](#25-opening-a-project-correctly)
  - [26. One Project, One Purpose](#26-one-project-one-purpose)
  - [27. Project Structure Is Not
    Universal](#27-project-structure-is-not-universal)
  - [28. Build the Chapter 1 Practice
    Project](#28-build-the-chapter-1-practice-project)
  - [29. Create the Structure with R](#29-create-the-structure-with-r)
  - [30. Inspect the Project
    Programmatically](#30-inspect-the-project-programmatically)
  - [31. Common Mistakes](#31-common-mistakes)
    - [Mistake 1 — One folder for
      everything](#mistake-1--one-folder-for-everything)
    - [Mistake 2 — One giant project for unrelated
      analyses](#mistake-2--one-giant-project-for-unrelated-analyses)
    - [Mistake 3 — Using absolute paths
      everywhere](#mistake-3--using-absolute-paths-everywhere)
    - [Mistake 4 — Overwriting raw
      data](#mistake-4--overwriting-raw-data)
    - [Mistake 5 — Creating dozens of empty
      folders](#mistake-5--creating-dozens-of-empty-folders)
    - [Mistake 6 — Treating `.Rproj` as the project
      itself](#mistake-6--treating-rproj-as-the-project-itself)
    - [Mistake 7 — Using `setwd()` repeatedly to repair a disorganized
      workflow](#mistake-7--using-setwd-repeatedly-to-repair-a-disorganized-workflow)
  - [32. Debugging Clinic](#32-debugging-clinic)
    - [Scenario 1 — `file not found`](#scenario-1--file-not-found)
    - [Scenario 2 — Script works only when opened from one particular
      directory](#scenario-2--script-works-only-when-opened-from-one-particular-directory)
    - [Scenario 3 — Output files appear in unexpected
      places](#scenario-3--output-files-appear-in-unexpected-places)
    - [Scenario 4 — Project works on your machine but not your
      collaborator’s](#scenario-4--project-works-on-your-machine-but-not-your-collaborators)
  - [33. Performance Corner](#33-performance-corner)
  - [34. Expert Commentary](#34-expert-commentary)
  - [35. From the Reviewer’s
    Perspective](#35-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-3)
    - [Concept Questions](#concept-questions-3)
  - [Practical Exercises](#practical-exercises-2)
    - [Exercise 1 — Create an RStudio
      Project](#exercise-1--create-an-rstudio-project)
    - [Exercise 2 — Confirm the Root](#exercise-2--confirm-the-root)
    - [Exercise 3 — Create Directories](#exercise-3--create-directories)
    - [Exercise 4 — Create Nested Data
      Directories](#exercise-4--create-nested-data-directories)
    - [Exercise 5 — Inspect
      Recursively](#exercise-5--inspect-recursively)
    - [Exercise 6 — General Project
      Design](#exercise-6--general-project-design)
    - [Exercise 7 — Computational Biology Project
      Design](#exercise-7--computational-biology-project-design)
  - [Intermediate Thinking Exercise](#intermediate-thinking-exercise)
  - [Mini Task — Build the Chapter 1 Project
    Skeleton](#mini-task--build-the-chapter-1-project-skeleton)
  - [Lesson Competency Check](#lesson-competency-check-3)
  - [Key Takeaways](#key-takeaways-3)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-2)
  - [References and Further Reading](#references-and-further-reading-3)
    - [Essential Reading](#essential-reading-3)
    - [Additional Reading](#additional-reading-3)
    - [Documentation Practice](#documentation-practice)
  - [Next Lesson](#next-lesson-3)
    - [Lesson 1.5 — Files, Folders and
      Paths](#lesson-15--files-folders-and-paths)
  - [Lesson 1.5 — Files, Folders and
    Paths](#lesson-15--files-folders-and-paths-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-4)
    - [Learning Objectives](#learning-objectives-3)
  - [1. What Is a Path?](#1-what-is-a-path)
  - [2. Files and Directories](#2-files-and-directories)
  - [3. Absolute Paths](#3-absolute-paths)
  - [4. Relative Paths](#4-relative-paths)
  - [5. Relative to What?](#5-relative-to-what)
  - [6. The Current Working Directory](#6-the-current-working-directory)
  - [7. What Does `setwd()` Do?](#7-what-does-setwd-do)
  - [8. Why Hard-Coded `setwd()` Is
    Fragile](#8-why-hard-coded-setwd-is-fragile)
  - [9. When `setwd()` Can Still Be
    Useful](#9-when-setwd-can-still-be-useful)
  - [10. Inspecting Whether a File
    Exists](#10-inspecting-whether-a-file-exists)
  - [11. Inspecting Whether a Directory
    Exists](#11-inspecting-whether-a-directory-exists)
  - [12. Listing Files](#12-listing-files)
  - [13. Filtering Listed Files](#13-filtering-listed-files)
  - [14. Creating Directories](#14-creating-directories)
  - [15. Building Paths with
    `file.path()`](#15-building-paths-with-filepath)
  - [16. Why `file.path()` Becomes
    Important](#16-why-filepath-becomes-important)
  - [17. `normalizePath()`](#17-normalizepath)
  - [18. Special Path Symbols: `.` and
    `..`](#18-special-path-symbols--and-)
    - [Current directory](#current-directory)
    - [Parent directory](#parent-directory)
  - [19. Windows Backslashes](#19-windows-backslashes)
  - [20. Why Backslashes Cause Strange
    Errors](#20-why-backslashes-cause-strange-errors)
  - [21. Spaces in Filenames](#21-spaces-in-filenames)
  - [22. Case Sensitivity](#22-case-sensitivity)
  - [23. File Extensions Matter](#23-file-extensions-matter)
  - [24. The Home Directory](#24-the-home-directory)
  - [25. Windows and WSL Paths Are
    Different](#25-windows-and-wsl-paths-are-different)
  - [26. Network Drives and Mounted
    Filesystems](#26-network-drives-and-mounted-filesystems)
  - [27. Introducing the `here`
    Package](#27-introducing-the-here-package)
  - [28. Building a Path with `here()`](#28-building-a-path-with-here)
  - [29. Why `here()` Is Useful](#29-why-here-is-useful)
  - [30. `here()` Is Not Magic](#30-here-is-not-magic)
  - [31. Inspecting the `here` Root](#31-inspecting-the-here-root)
  - [32. General Practical Example](#32-general-practical-example)
  - [33. Computational Biology Practical
    Example](#33-computational-biology-practical-example)
  - [34. A Larger Genomics Example](#34-a-larger-genomics-example)
  - [35. Input Paths and Output Paths](#35-input-paths-and-output-paths)
  - [36. Check Output Directories Before
    Writing](#36-check-output-directories-before-writing)
  - [37. Do Not Construct Paths with `paste()` Unless
    Necessary](#37-do-not-construct-paths-with-paste-unless-necessary)
  - [38. Avoid Embedding File Locations
    Everywhere](#38-avoid-embedding-file-locations-everywhere)
  - [39. A Path Debugging Workflow](#39-a-path-debugging-workflow)
    - [Step 1 — Inspect the working
      directory](#step-1--inspect-the-working-directory)
    - [Step 2 — Inspect the project/root
      context](#step-2--inspect-the-projectroot-context)
    - [Step 3 — Inspect the directory](#step-3--inspect-the-directory)
    - [Step 4 — Construct the expected
      path](#step-4--construct-the-expected-path)
    - [Step 5 — Test it](#step-5--test-it)
    - [Step 6 — Check spelling and
      capitalization](#step-6--check-spelling-and-capitalization)
  - [40. Common Mistakes](#40-common-mistakes)
    - [Mistake 1 — Hard-coding a personal absolute
      path](#mistake-1--hard-coding-a-personal-absolute-path)
    - [Mistake 2 — Repeatedly using `setwd()` throughout a
      script](#mistake-2--repeatedly-using-setwd-throughout-a-script)
    - [Mistake 3 — Confusing the script location with the working
      directory](#mistake-3--confusing-the-script-location-with-the-working-directory)
    - [Mistake 4 — Using unescaped Windows
      backslashes](#mistake-4--using-unescaped-windows-backslashes)
    - [Mistake 5 — Ignoring
      capitalization](#mistake-5--ignoring-capitalization)
    - [Mistake 6 — Guessing filenames](#mistake-6--guessing-filenames)
    - [Mistake 7 — Assuming `here()` repairs a disorganized
      project](#mistake-7--assuming-here-repairs-a-disorganized-project)
    - [Mistake 8 — Saving outputs without specifying a
      directory](#mistake-8--saving-outputs-without-specifying-a-directory)
  - [41. Debugging Clinic](#41-debugging-clinic)
    - [Scenario 1 — File exists, but R says it does
      not](#scenario-1--file-exists-but-r-says-it-does-not)
    - [Scenario 2 — Windows path produces strange
      output](#scenario-2--windows-path-produces-strange-output)
    - [Scenario 3 — Script works only after
      `setwd()`](#scenario-3--script-works-only-after-setwd)
    - [Scenario 4 — RStudio sees the file but WSL tool does
      not](#scenario-4--rstudio-sees-the-file-but-wsl-tool-does-not)
    - [Scenario 5 — Output directory does not
      exist](#scenario-5--output-directory-does-not-exist)
    - [Scenario 6 — `here()` points somewhere
      unexpected](#scenario-6--here-points-somewhere-unexpected)
  - [42. Performance Corner](#42-performance-corner)
  - [43. Expert Commentary](#43-expert-commentary)
  - [44. From the Reviewer’s
    Perspective](#44-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-4)
    - [Concept Questions](#concept-questions-4)
  - [Practical Exercises](#practical-exercises-3)
    - [Exercise 1 — Inspect the Working
      Directory](#exercise-1--inspect-the-working-directory)
    - [Exercise 2 — Check Directories](#exercise-2--check-directories)
    - [Exercise 3 — Inspect Project
      Files](#exercise-3--inspect-project-files)
    - [Exercise 4 — Build a Path](#exercise-4--build-a-path)
    - [Exercise 5 — Check Before
      Reading](#exercise-5--check-before-reading)
    - [Exercise 6 — Use `here`](#exercise-6--use-here)
    - [Exercise 7 — Genomics Path](#exercise-7--genomics-path)
    - [Exercise 8 — Create an Output
      Directory](#exercise-8--create-an-output-directory)
  - [Intermediate Exercises](#intermediate-exercises)
    - [Exercise 9 — Diagnose the Broken
      Path](#exercise-9--diagnose-the-broken-path)
    - [Exercise 10 — Cross-Platform
      Failure](#exercise-10--cross-platform-failure)
    - [Exercise 11 — Windows and WSL](#exercise-11--windows-and-wsl)
  - [Challenge — Build a Path Diagnostic
    Script](#challenge--build-a-path-diagnostic-script)
  - [Lesson Competency Check](#lesson-competency-check-4)
  - [Key Takeaways](#key-takeaways-4)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-3)
  - [References and Further Reading](#references-and-further-reading-4)
    - [Essential Reading](#essential-reading-4)
    - [Scientific Computing and
      Reproducibility](#scientific-computing-and-reproducibility)
    - [Documentation Practice](#documentation-practice-1)
  - [Next Lesson](#next-lesson-4)
    - [Lesson 1.6 — Scripts, Console and
      Execution](#lesson-16--scripts-console-and-execution)
  - [Lesson 1.6 — Scripts, Console and
    Execution](#lesson-16--scripts-console-and-execution-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-5)
    - [Learning Objectives](#learning-objectives-4)
  - [1. Interactive R Versus Scripted
    R](#1-interactive-r-versus-scripted-r)
  - [2. What Is an R Script?](#2-what-is-an-r-script)
  - [3. Scripts Are Instructions, Not Stored
    Results](#3-scripts-are-instructions-not-stored-results)
  - [4. Execution Order Matters](#4-execution-order-matters)
  - [5. Hidden Session State Can Mask Bad Execution
    Order](#5-hidden-session-state-can-mask-bad-execution-order)
  - [6. Running One Line](#6-running-one-line)
  - [7. Running a Selection](#7-running-a-selection)
  - [8. Running the Complete Script](#8-running-the-complete-script)
  - [9. Comments in R Scripts](#9-comments-in-r-scripts)
  - [10. Blank Lines and Readability](#10-blank-lines-and-readability)
  - [11. Script Sections](#11-script-sections)
  - [12. What Does `source()` Do?](#12-what-does-source-do)
  - [13. A Simple `source()` Example](#13-a-simple-source-example)
  - [14. Sourcing One Script from
    Another](#14-sourcing-one-script-from-another)
  - [15. Avoid Deep Chains of
    Sourcing](#15-avoid-deep-chains-of-sourcing)
  - [16. `source()` and Project Paths](#16-source-and-project-paths)
  - [17. What Is `Rscript`?](#17-what-is-rscript)
  - [18. Why `Rscript` Matters](#18-why-rscript-matters)
  - [19. First Command-Line Script](#19-first-command-line-script)
  - [20. `print()` Versus `cat()`](#20-print-versus-cat)
  - [21. Interactive Versus Non-Interactive
    Sessions](#21-interactive-versus-non-interactive-sessions)
  - [22. Why `readline()` Can Break
    Automation](#22-why-readline-can-break-automation)
  - [23. Clean-Session Execution](#23-clean-session-execution)
  - [24. A Clean-Session Example](#24-a-clean-session-example)
  - [25. General Example — Complete
    Script](#25-general-example--complete-script)
  - [26. Computational Biology Example — Sequencing
    Depth](#26-computational-biology-example--sequencing-depth)
  - [27. Reading an Input File in a Complete
    Script](#27-reading-an-input-file-in-a-complete-script)
  - [28. Why Stopping Early Can Be
    Better](#28-why-stopping-early-can-be-better)
  - [29. Script Dependencies](#29-script-dependencies)
  - [30. Package Dependencies](#30-package-dependencies)
  - [31. Introductory Command-Line
    Arguments](#31-introductory-command-line-arguments)
  - [32. A Small Argument Example](#32-a-small-argument-example)
  - [33. Why Arguments Matter in
    Bioinformatics](#33-why-arguments-matter-in-bioinformatics)
  - [34. Standard Output, Errors and Exit
    Status](#34-standard-output-errors-and-exit-status)
  - [35. Do Not Hide Errors Just to Keep a Script
    Running](#35-do-not-hide-errors-just-to-keep-a-script-running)
  - [36. One Script Versus Many
    Scripts](#36-one-script-versus-many-scripts)
  - [37. Script Naming](#37-script-naming)
  - [38. Script Headers](#38-script-headers)
  - [39. Reproducible Script
    Checklist](#39-reproducible-script-checklist)
  - [40. Common Mistakes](#40-common-mistakes-1)
    - [Mistake 1 — Running lines manually in a special
      order](#mistake-1--running-lines-manually-in-a-special-order)
    - [Mistake 2 — Depending on objects already in
      Environment](#mistake-2--depending-on-objects-already-in-environment)
    - [Mistake 3 — Sourcing scripts with personal absolute
      paths](#mistake-3--sourcing-scripts-with-personal-absolute-paths)
    - [Mistake 4 — Creating deep chains of sourced
      scripts](#mistake-4--creating-deep-chains-of-sourced-scripts)
    - [Mistake 5 — Assuming RStudio and `Rscript` execution are
      identical in every
      detail](#mistake-5--assuming-rstudio-and-rscript-execution-are-identical-in-every-detail)
    - [Mistake 6 — Using interactive prompts in automated
      scripts](#mistake-6--using-interactive-prompts-in-automated-scripts)
    - [Mistake 7 — Ignoring missing input files until
      later](#mistake-7--ignoring-missing-input-files-until-later)
    - [Mistake 8 — Suppressing meaningful
      errors](#mistake-8--suppressing-meaningful-errors)
  - [41. Debugging Clinic](#41-debugging-clinic-1)
    - [Scenario 1 — Script works in RStudio but fails with
      `Rscript`](#scenario-1--script-works-in-rstudio-but-fails-with-rscript)
    - [Scenario 2 — `source()` reports file not
      found](#scenario-2--source-reports-file-not-found)
    - [Scenario 3 — Script fails after restarting
      R](#scenario-3--script-fails-after-restarting-r)
    - [Scenario 4 — Script writes output somewhere
      unexpected](#scenario-4--script-writes-output-somewhere-unexpected)
    - [Scenario 5 — Argument script is run without
      arguments](#scenario-5--argument-script-is-run-without-arguments)
  - [42. Performance Corner](#42-performance-corner-1)
  - [43. Expert Commentary](#43-expert-commentary-1)
  - [44. From the Reviewer’s
    Perspective](#44-from-the-reviewers-perspective-1)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-5)
    - [Concept Questions](#concept-questions-5)
  - [Practical Exercises](#practical-exercises-4)
    - [Exercise 1 — Run a Complete
      Script](#exercise-1--run-a-complete-script)
    - [Exercise 2 — Expose Hidden
      State](#exercise-2--expose-hidden-state)
    - [Exercise 3 — Source Another
      Script](#exercise-3--source-another-script)
    - [Exercise 4 — Input Validation](#exercise-4--input-validation)
    - [Exercise 5 — General Script](#exercise-5--general-script)
    - [Exercise 6 — Computational Biology
      Script](#exercise-6--computational-biology-script)
  - [Intermediate Exercises](#intermediate-exercises-1)
    - [Exercise 7 — Diagnose Script
      Dependencies](#exercise-7--diagnose-script-dependencies)
    - [Exercise 8 — Convert an Interactive
      Workflow](#exercise-8--convert-an-interactive-workflow)
    - [Exercise 9 — Run with an
      Argument](#exercise-9--run-with-an-argument)
  - [Challenge — Build a Reproducible Execution
    Check](#challenge--build-a-reproducible-execution-check)
  - [Lesson Competency Check](#lesson-competency-check-5)
  - [Key Takeaways](#key-takeaways-5)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-4)
  - [References and Further Reading](#references-and-further-reading-5)
    - [Essential Reading](#essential-reading-5)
    - [Additional Reading](#additional-reading-4)
    - [Documentation Practice](#documentation-practice-2)
  - [Next Lesson](#next-lesson-5)
    - [Lesson 1.7 — Packages and
      Libraries](#lesson-17--packages-and-libraries)
  - [Lesson 1.7 — Packages and
    Libraries](#lesson-17--packages-and-libraries-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-6)
    - [Learning Objectives](#learning-objectives-5)
  - [1. Why Packages Exist](#1-why-packages-exist)
  - [2. What Is an R Package?](#2-what-is-an-r-package)
  - [3. Package Versus Function](#3-package-versus-function)
  - [4. Package Versus Library](#4-package-versus-library)
  - [5. Why `library()` Has That Name](#5-why-library-has-that-name)
  - [6. Installing Versus Loading](#6-installing-versus-loading)
    - [Installing](#installing)
    - [Loading/attaching for the current
      session](#loadingattaching-for-the-current-session)
  - [7. Installation Usually Persists Across
    Sessions](#7-installation-usually-persists-across-sessions)
  - [8. Do Not Put `install.packages()` in Every Analysis
    Script](#8-do-not-put-installpackages-in-every-analysis-script)
  - [9. Installing a CRAN Package](#9-installing-a-cran-package)
  - [10. Loading a Package](#10-loading-a-package)
  - [11. The `::` Operator](#11-the--operator)
  - [12. Why `package::function` Is
    Useful](#12-why-packagefunction-is-useful)
  - [13. Does `package::function` Require
    `library()`?](#13-does-packagefunction-require-library)
  - [14. What Is a Namespace?](#14-what-is-a-namespace)
  - [15. `::` Versus `:::`](#15--versus-)
  - [16. Inspecting Package Libraries with
    `.libPaths()`](#16-inspecting-package-libraries-with-libpaths)
  - [17. Why Multiple Libraries Exist](#17-why-multiple-libraries-exist)
  - [18. Inspecting Installed
    Packages](#18-inspecting-installed-packages)
  - [19. `find.package()`](#19-findpackage)
  - [20. Checking a Package Version](#20-checking-a-package-version)
  - [21. Inspecting Loaded and Attached
    Packages](#21-inspecting-loaded-and-attached-packages)
  - [22. `sessionInfo()` Revisited](#22-sessioninfo-revisited)
  - [23. `library()` Versus `require()`](#23-library-versus-require)
  - [24. `requireNamespace()`](#24-requirenamespace)
  - [25. `library()` or
    `package::function()`?](#25-library-or-packagefunction)
    - [Style A — Attach the package](#style-a--attach-the-package)
    - [Style B — Explicit namespace](#style-b--explicit-namespace)
  - [26. What Is CRAN?](#26-what-is-cran)
  - [27. What Is Bioconductor?](#27-what-is-bioconductor)
  - [28. Installing Bioconductor
    Packages](#28-installing-bioconductor-packages)
  - [29. Why Bioconductor Uses
    `BiocManager`](#29-why-bioconductor-uses-biocmanager)
  - [30. Checking the Bioconductor
    Environment](#30-checking-the-bioconductor-environment)
  - [31. A Computational Biology
    Example](#31-a-computational-biology-example)
  - [32. Package Dependencies](#32-package-dependencies)
  - [33. System Dependencies](#33-system-dependencies)
  - [34. Binary Versus Source
    Packages](#34-binary-versus-source-packages)
  - [35. Updating Packages](#35-updating-packages)
  - [36. Removing a Package](#36-removing-a-package)
  - [37. Detaching a Package Is Not the Same as Removing
    It](#37-detaching-a-package-is-not-the-same-as-removing-it)
  - [38. Package Conflicts](#38-package-conflicts)
  - [39. What Does “Masked” Mean?](#39-what-does-masked-mean)
  - [40. Inspecting Where a Function Comes
    From](#40-inspecting-where-a-function-comes-from)
  - [41. Package Startup Messages](#41-package-startup-messages)
  - [42. Common Installation Error: Package Not
    Available](#42-common-installation-error-package-not-available)
  - [43. Common Loading Error: There Is No Package
    Called…](#43-common-loading-error-there-is-no-package-called)
  - [44. Common Error: Package Installed but Not
    Found](#44-common-error-package-installed-but-not-found)
  - [45. Different R Versions Can Have Different Package
    Libraries](#45-different-r-versions-can-have-different-package-libraries)
  - [46. Package Installation Should Be Reproducible
    Too](#46-package-installation-should-be-reproducible-too)
  - [47. General Example — Inspecting a
    Package](#47-general-example--inspecting-a-package)
  - [48. General Example — `here`](#48-general-example--here)
  - [49. Computational Biology Example — Bioconductor
    Availability](#49-computational-biology-example--bioconductor-availability)
  - [50. Making Dependencies Explicit at the Top of a
    Script](#50-making-dependencies-explicit-at-the-top-of-a-script)
  - [51. Should a Script Automatically Install Missing
    Packages?](#51-should-a-script-automatically-install-missing-packages)
  - [52. Setup Script Versus Analysis
    Script](#52-setup-script-versus-analysis-script)
  - [53. Common Mistakes](#53-common-mistakes)
    - [Mistake 1 — Confusing installation with
      loading](#mistake-1--confusing-installation-with-loading)
    - [Mistake 2 — Installing packages every time a script
      runs](#mistake-2--installing-packages-every-time-a-script-runs)
    - [Mistake 3 — Calling `library()` before installation and assuming
      R will install
      automatically](#mistake-3--calling-library-before-installation-and-assuming-r-will-install-automatically)
    - [Mistake 4 — Assuming every package is on
      CRAN](#mistake-4--assuming-every-package-is-on-cran)
    - [Mistake 5 — Ignoring the R
      version](#mistake-5--ignoring-the-r-version)
    - [Mistake 6 — Treating every package startup message as an
      error](#mistake-6--treating-every-package-startup-message-as-an-error)
    - [Mistake 7 — Ignoring function
      conflicts](#mistake-7--ignoring-function-conflicts)
    - [Mistake 8 — Using `:::` routinely](#mistake-8--using--routinely)
    - [Mistake 9 — Updating packages during an important analysis
      without considering
      reproducibility](#mistake-9--updating-packages-during-an-important-analysis-without-considering-reproducibility)
    - [Mistake 10 — Assuming an installation error always means the R
      package is
      broken](#mistake-10--assuming-an-installation-error-always-means-the-r-package-is-broken)
  - [54. Debugging Clinic](#54-debugging-clinic)
    - [Scenario 1 — `library()` says package is
      missing](#scenario-1--library-says-package-is-missing)
    - [Scenario 2 — Package worked before an R
      upgrade](#scenario-2--package-worked-before-an-r-upgrade)
    - [Scenario 3 — A Bioconductor package fails with
      `install.packages()`](#scenario-3--a-bioconductor-package-fails-with-installpackages)
    - [Scenario 4 — Function behaves differently after loading another
      package](#scenario-4--function-behaves-differently-after-loading-another-package)
    - [Scenario 5 — Package installation requests compilation
      tools](#scenario-5--package-installation-requests-compilation-tools)
    - [Scenario 6 — Script works on one machine but package versions
      differ](#scenario-6--script-works-on-one-machine-but-package-versions-differ)
  - [55. Performance Corner](#55-performance-corner)
  - [56. Expert Commentary](#56-expert-commentary)
  - [57. From the Reviewer’s
    Perspective](#57-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-6)
    - [Concept Questions](#concept-questions-6)
  - [Practical Exercises](#practical-exercises-5)
    - [Exercise 1 — Inspect Your
      Libraries](#exercise-1--inspect-your-libraries)
    - [Exercise 2 — Inspect Installed
      Packages](#exercise-2--inspect-installed-packages)
    - [Exercise 3 — Check Package
      Availability](#exercise-3--check-package-availability)
    - [Exercise 4 — Inspect a Package](#exercise-4--inspect-a-package)
    - [Exercise 5 — Namespace Use](#exercise-5--namespace-use)
    - [Exercise 6 — Search Path](#exercise-6--search-path)
    - [Exercise 7 — Session
      Information](#exercise-7--session-information)
    - [Exercise 8 — Bioconductor Check](#exercise-8--bioconductor-check)
  - [Intermediate Exercises](#intermediate-exercises-2)
    - [Exercise 9 — Diagnose the
      Script](#exercise-9--diagnose-the-script)
    - [Exercise 10 — Package Conflict](#exercise-10--package-conflict)
    - [Exercise 11 — Different Computer, Different
      Result](#exercise-11--different-computer-different-result)
  - [Challenge — Build a Package Environment Diagnostic
    Script](#challenge--build-a-package-environment-diagnostic-script)
  - [Lesson Competency Check](#lesson-competency-check-6)
  - [Key Takeaways](#key-takeaways-6)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-5)
  - [References and Further Reading](#references-and-further-reading-6)
    - [Essential Reading](#essential-reading-6)
    - [Computational Biology and
      Bioconductor](#computational-biology-and-bioconductor)
    - [Official Documentation](#official-documentation-2)
  - [Next Lesson](#next-lesson-6)
    - [Lesson 1.8 — Getting Help and Reading
      Documentation](#lesson-18--getting-help-and-reading-documentation)
  - [Lesson 1.8 — Getting Help and Reading
    Documentation](#lesson-18--getting-help-and-reading-documentation-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-7)
    - [Learning Objectives](#learning-objectives-6)
  - [1. You Are Not Expected to Memorize
    R](#1-you-are-not-expected-to-memorize-r)
  - [2. Help for a Known Function: `?`](#2-help-for-a-known-function-)
  - [3. `help()`](#3-help)
  - [4. When You Do Not Know the Function
    Name](#4-when-you-do-not-know-the-function-name)
  - [5. `?` Versus `??`](#5--versus-)
  - [6. Anatomy of an R Help Page](#6-anatomy-of-an-r-help-page)
  - [7. Read the Description First](#7-read-the-description-first)
  - [8. Read the Usage Section](#8-read-the-usage-section)
  - [9. Read the Arguments Section](#9-read-the-arguments-section)
  - [10. Required and Optional
    Arguments](#10-required-and-optional-arguments)
  - [11. Defaults Are Analytical
    Decisions](#11-defaults-are-analytical-decisions)
  - [12. Inspect Arguments Quickly with
    `args()`](#12-inspect-arguments-quickly-with-args)
  - [13. What Does `...` Mean?](#13-what-does--mean)
  - [14. The Value Section](#14-the-value-section)
  - [15. Inspect What You Actually
    Received](#15-inspect-what-you-actually-received)
  - [16. The Examples Section](#16-the-examples-section)
  - [17. Run Packaged Examples with
    `example()`](#17-run-packaged-examples-with-example)
  - [18. Minimal Reproducible
    Examples](#18-minimal-reproducible-examples)
  - [19. General Example — Learning
    `median()`](#19-general-example--learning-median)
  - [20. Search by Concept with
    `help.search()`](#20-search-by-concept-with-helpsearch)
  - [21. Package-Level Help](#21-package-level-help)
  - [22. What Is a Vignette?](#22-what-is-a-vignette)
  - [23. Finding Vignettes](#23-finding-vignettes)
  - [24. `browseVignettes()`](#24-browsevignettes)
  - [25. Why Vignettes Matter in Computational
    Biology](#25-why-vignettes-matter-in-computational-biology)
  - [26. Reference Documentation Versus
    Tutorials](#26-reference-documentation-versus-tutorials)
    - [Reference documentation](#reference-documentation)
    - [Official vignettes/tutorials](#official-vignettestutorials)
    - [Books and teaching resources](#books-and-teaching-resources)
  - [27. CRAN Documentation](#27-cran-documentation)
  - [28. Bioconductor Documentation](#28-bioconductor-documentation)
  - [29. Package Versions and
    Documentation](#29-package-versions-and-documentation)
  - [30. Find Where a Function Comes
    From](#30-find-where-a-function-comes-from)
  - [31. `methods()` — A First Look](#31-methods--a-first-look)
  - [32. Documentation Can Look More Advanced Than Your Current
    Level](#32-documentation-can-look-more-advanced-than-your-current-level)
  - [33. Read Error Messages Before
    Searching](#33-read-error-messages-before-searching)
  - [34. Message, Warning and Error Are
    Different](#34-message-warning-and-error-are-different)
    - [Message](#message)
    - [Warning](#warning)
    - [Error](#error)
  - [35. Search Exact Error Phrases
    Carefully](#35-search-exact-error-phrases-carefully)
  - [36. A Practical Source Hierarchy](#36-a-practical-source-hierarchy)
  - [37. Community Discussions](#37-community-discussions)
  - [38. GitHub Issues and Release
    Notes](#38-github-issues-and-release-notes)
  - [39. Documentation and
    Reproducibility](#39-documentation-and-reproducibility)
  - [40. General Practical Example —
    `quantile()`](#40-general-practical-example--quantile)
  - [41. Computational Biology Example — Learn a Package Before Using
    It](#41-computational-biology-example--learn-a-package-before-using-it)
  - [42. Computational Biology Example — Documentation Before VCF
    Analysis](#42-computational-biology-example--documentation-before-vcf-analysis)
  - [43. Statistical Documentation Requires Extra
    Care](#43-statistical-documentation-requires-extra-care)
  - [44. Using AI for R Help](#44-using-ai-for-r-help)
  - [45. Asking Better Technical
    Questions](#45-asking-better-technical-questions)
  - [46. A Systematic Help Workflow](#46-a-systematic-help-workflow)
    - [Step 1 — Classify the problem](#step-1--classify-the-problem)
    - [Step 2 — Inspect the relevant
      object/environment](#step-2--inspect-the-relevant-objectenvironment)
    - [Step 3 — Use local function
      help](#step-3--use-local-function-help)
    - [Step 4 — Search installed
      documentation](#step-4--search-installed-documentation)
    - [Step 5 — Inspect package
      documentation](#step-5--inspect-package-documentation)
    - [Step 6 — Build a minimal
      example](#step-6--build-a-minimal-example)
    - [Step 7 — Consult authoritative online
      resources](#step-7--consult-authoritative-online-resources)
    - [Step 8 — Search community discussions when
      necessary](#step-8--search-community-discussions-when-necessary)
    - [Step 9 — Use AI assistance if
      useful](#step-9--use-ai-assistance-if-useful)
    - [Step 10 — Verify](#step-10--verify)
  - [47. Do Not Debug Everything at
    Once](#47-do-not-debug-everything-at-once)
  - [48. Common Mistakes](#48-common-mistakes)
    - [Mistake 1 — Trying to memorize every
      function](#mistake-1--trying-to-memorize-every-function)
    - [Mistake 2 — Choosing a function from its name
      alone](#mistake-2--choosing-a-function-from-its-name-alone)
    - [Mistake 3 — Ignoring Arguments](#mistake-3--ignoring-arguments)
    - [Mistake 4 — Ignoring Value](#mistake-4--ignoring-value)
    - [Mistake 5 — Copying examples without checking object
      classes](#mistake-5--copying-examples-without-checking-object-classes)
    - [Mistake 6 — Assuming online documentation matches your installed
      version](#mistake-6--assuming-online-documentation-matches-your-installed-version)
    - [Mistake 7 — Ignoring warnings](#mistake-7--ignoring-warnings)
    - [Mistake 8 — Searching vague error
      phrases](#mistake-8--searching-vague-error-phrases)
    - [Mistake 9 — Trusting old community answers without
      verification](#mistake-9--trusting-old-community-answers-without-verification)
    - [Mistake 10 — Treating AI output as authoritative
      documentation](#mistake-10--treating-ai-output-as-authoritative-documentation)
  - [49. Debugging Clinic](#49-debugging-clinic)
    - [Scenario 1 — Unused Argument](#scenario-1--unused-argument)
    - [Scenario 2 — Function Not Found](#scenario-2--function-not-found)
    - [Scenario 3 — Documentation Example Works but Your Data
      Fail](#scenario-3--documentation-example-works-but-your-data-fail)
    - [Scenario 4 — Online Code Uses an Argument Missing
      Locally](#scenario-4--online-code-uses-an-argument-missing-locally)
    - [Scenario 5 — Same Function Name in Multiple
      Packages](#scenario-5--same-function-name-in-multiple-packages)
    - [Scenario 6 — Old Bioconductor Workflow
      Fails](#scenario-6--old-bioconductor-workflow-fails)
  - [50. Performance Corner](#50-performance-corner)
  - [51. Expert Commentary](#51-expert-commentary)
  - [52. From the Reviewer’s
    Perspective](#52-from-the-reviewers-perspective)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-7)
  - [Practical Exercises](#practical-exercises-6)
    - [Exercise 1 — Read a Help Page](#exercise-1--read-a-help-page)
    - [Exercise 2 — Inspect Signatures](#exercise-2--inspect-signatures)
    - [Exercise 3 — Run an Example](#exercise-3--run-an-example)
    - [Exercise 4 — Search by Concept](#exercise-4--search-by-concept)
    - [Exercise 5 — Package
      Documentation](#exercise-5--package-documentation)
    - [Exercise 6 — Inspect Output](#exercise-6--inspect-output)
    - [Exercise 7 — Package Version](#exercise-7--package-version)
    - [Exercise 8 — Vignettes](#exercise-8--vignettes)
  - [Intermediate Exercises](#intermediate-exercises-3)
    - [Exercise 9 — Diagnose an Unused
      Argument](#exercise-9--diagnose-an-unused-argument)
    - [Exercise 10 — Documentation Version
      Mismatch](#exercise-10--documentation-version-mismatch)
    - [Exercise 11 — Bioconductor Documentation
      Audit](#exercise-11--bioconductor-documentation-audit)
  - [Challenge — Build an R Help Toolkit
    Script](#challenge--build-an-r-help-toolkit-script)
  - [Mini-Project — Learn One Function Without a
    Tutorial](#mini-project--learn-one-function-without-a-tutorial)
  - [Lesson Competency Check](#lesson-competency-check-7)
  - [Key Takeaways](#key-takeaways-7)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-6)
  - [References and Further Reading](#references-and-further-reading-7)
    - [Essential Reading](#essential-reading-7)
    - [R Packages and Documentation](#r-packages-and-documentation)
    - [Computational Biology](#computational-biology)
    - [Scientific Computing Practice](#scientific-computing-practice)
    - [Documentation Practice](#documentation-practice-3)
  - [Next Lesson](#next-lesson-7)
    - [Lesson 1.9 — Understanding the R
      Session](#lesson-19--understanding-the-r-session)
  - [Lesson 1.9 — Understanding the R
    Session](#lesson-19--understanding-the-r-session-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-8)
    - [Learning Objectives](#learning-objectives-7)
  - [1. What Is an R Session?](#1-what-is-an-r-session)
  - [2. Code on Disk Is Not Session
    State](#2-code-on-disk-is-not-session-state)
  - [3. The Global Environment](#3-the-global-environment)
  - [4. Inspecting `.GlobalEnv`](#4-inspecting-globalenv)
  - [5. `objects()`](#5-objects)
  - [6. Inspection Before Assumption](#6-inspection-before-assumption)
  - [7. Testing Whether an Object
    Exists](#7-testing-whether-an-object-exists)
  - [8. Removing Objects with `rm()`](#8-removing-objects-with-rm)
  - [9. Removing Multiple Objects](#9-removing-multiple-objects)
  - [10. The Famous `rm(list = ls())`](#10-the-famous-rmlist--ls)
  - [11. Restarting R Versus Clearing
    Objects](#11-restarting-r-versus-clearing-objects)
  - [12. The Search Path](#12-the-search-path)
  - [13. Search-Path Mental Model](#13-search-path-mental-model)
  - [14. Why the Search Path Matters](#14-why-the-search-path-matters)
  - [15. Avoid Reusing Important Function
    Names](#15-avoid-reusing-important-function-names)
  - [16. Attached Packages](#16-attached-packages)
  - [17. Loaded Namespaces Are
    Different](#17-loaded-namespaces-are-different)
  - [18. Inspecting Loaded Namespaces](#18-inspecting-loaded-namespaces)
  - [19. Why “Attached” and “Loaded” Must Not Be Treated as
    Synonyms](#19-why-attached-and-loaded-must-not-be-treated-as-synonyms)
  - [20. Finding Where a Name Comes
    From](#20-finding-where-a-name-comes-from)
  - [21. `sessionInfo()`](#21-sessioninfo)
  - [22. Why `sessionInfo()` Matters](#22-why-sessioninfo-matters)
  - [23. Saving Session Information](#23-saving-session-information)
  - [24. Quick R-Version Inspection](#24-quick-r-version-inspection)
  - [25. Environment Variables](#25-environment-variables)
  - [26. R Environment Versus Environment
    Variable](#26-r-environment-versus-environment-variable)
  - [27. Inspecting Environment Variables
    Safely](#27-inspecting-environment-variables-safely)
  - [28. Setting an Environment Variable for the Current
    Process](#28-setting-an-environment-variable-for-the-current-process)
  - [29. Do Not Hard-Code Secrets](#29-do-not-hard-code-secrets)
  - [30. Startup Behavior](#30-startup-behavior)
  - [31. `.Rprofile`](#31-rprofile)
  - [32. `.Renviron`](#32-renviron)
  - [33. Startup Files and “Works on My
    Machine”](#33-startup-files-and-works-on-my-machine)
  - [34. `.RData`](#34-rdata)
  - [35. Why Automatic `.RData` Restoration Can Be
    Risky](#35-why-automatic-rdata-restoration-can-be-risky)
  - [36. Saving One Object Versus Saving a Whole
    Workspace](#36-saving-one-object-versus-saving-a-whole-workspace)
  - [37. `.Rhistory`](#37-rhistory)
  - [38. History Versus Script](#38-history-versus-script)
  - [39. Workspace Settings in
    RStudio](#39-workspace-settings-in-rstudio)
  - [40. Clean-Session Discipline](#40-clean-session-discipline)
  - [41. Restarting R Does Not Delete Your
    Project](#41-restarting-r-does-not-delete-your-project)
  - [42. Session State Versus Project
    State](#42-session-state-versus-project-state)
  - [43. Working Directory Is Session
    State](#43-working-directory-is-session-state)
  - [44. Package Attachment Is Session
    State](#44-package-attachment-is-session-state)
  - [45. Options Are Session State](#45-options-are-session-state)
  - [46. Random-Number State — An Important
    Preview](#46-random-number-state--an-important-preview)
  - [47. Temporary Files and
    `tempdir()`](#47-temporary-files-and-tempdir)
  - [48. General Example — Hidden
    Dependency](#48-general-example--hidden-dependency)
  - [49. Computational Biology Example — Hidden
    Threshold](#49-computational-biology-example--hidden-threshold)
  - [50. Computational Biology Example — Package
    State](#50-computational-biology-example--package-state)
  - [51. Why Beginner Courses Often Skip Session
    State](#51-why-beginner-courses-often-skip-session-state)
  - [52. Professional Workflow — Session
    Hygiene](#52-professional-workflow--session-hygiene)
  - [53. Common Mistakes](#53-common-mistakes-1)
    - [Mistake 1 — Treating Environment objects as permanent
      data](#mistake-1--treating-environment-objects-as-permanent-data)
    - [Mistake 2 — Assuming `rm(list = ls())` fully resets
      R](#mistake-2--assuming-rmlist--ls-fully-resets-r)
    - [Mistake 3 — Depending on automatically restored
      `.RData`](#mistake-3--depending-on-automatically-restored-rdata)
    - [Mistake 4 — Using History instead of
      scripts](#mistake-4--using-history-instead-of-scripts)
    - [Mistake 5 — Ignoring the search
      path](#mistake-5--ignoring-the-search-path)
    - [Mistake 6 — Confusing attached packages and loaded
      namespaces](#mistake-6--confusing-attached-packages-and-loaded-namespaces)
    - [Mistake 7 — Assuming every fresh session is identical across
      machines](#mistake-7--assuming-every-fresh-session-is-identical-across-machines)
    - [Mistake 8 — Sharing every environment
      variable](#mistake-8--sharing-every-environment-variable)
  - [54. Debugging Clinic](#54-debugging-clinic-1)
    - [Scenario 1 — Object Exists Today but Not
      Tomorrow](#scenario-1--object-exists-today-but-not-tomorrow)
    - [Scenario 2 — Wrong `filter()`
      Function](#scenario-2--wrong-filter-function)
    - [Scenario 3 — Script Works Only After Opening an Old RStudio
      Project](#scenario-3--script-works-only-after-opening-an-old-rstudio-project)
    - [Scenario 4 — Collaborator Gets Different Package
      Behavior](#scenario-4--collaborator-gets-different-package-behavior)
    - [Scenario 5 — `rm(list = ls())` Does Not Fix the
      Problem](#scenario-5--rmlist--ls-does-not-fix-the-problem)
    - [Scenario 6 — API Code Works Only on One
      Machine](#scenario-6--api-code-works-only-on-one-machine)
  - [55. Performance Corner](#55-performance-corner-1)
  - [56. Expert Commentary](#56-expert-commentary-1)
  - [57. From the Reviewer’s
    Perspective](#57-from-the-reviewers-perspective-1)
  - [58. General Practical Example — Session
    Inspection](#58-general-practical-example--session-inspection)
  - [59. Computational Biology Practical Example — Session
    Audit](#59-computational-biology-practical-example--session-audit)
  - [Practice Questions — Basic
    Level](#practice-questions--basic-level-8)
  - [Practical Exercises](#practical-exercises-7)
    - [Exercise 1 — Inspect the Global
      Environment](#exercise-1--inspect-the-global-environment)
    - [Exercise 2 — Remove and Verify](#exercise-2--remove-and-verify)
    - [Exercise 3 — Inspect the Search
      Path](#exercise-3--inspect-the-search-path)
    - [Exercise 4 — Loaded Namespace
      Check](#exercise-4--loaded-namespace-check)
    - [Exercise 5 — Capture Session
      Information](#exercise-5--capture-session-information)
    - [Exercise 6 — Environment
      Variables](#exercise-6--environment-variables)
    - [Exercise 7 — Clean-Session Test](#exercise-7--clean-session-test)
    - [Exercise 8 — Workspace Risk](#exercise-8--workspace-risk)
  - [Intermediate Thinking Exercises](#intermediate-thinking-exercises)
    - [Exercise 9 — Diagnose a Hidden-State
      Workflow](#exercise-9--diagnose-a-hidden-state-workflow)
    - [Exercise 10 — Attached Versus
      Loaded](#exercise-10--attached-versus-loaded)
    - [Exercise 11 — Clean Session Across
      Machines](#exercise-11--clean-session-across-machines)
  - [Challenge — Build a Session Diagnostic
    Script](#challenge--build-a-session-diagnostic-script)
  - [Mini-Project — Reproduce from a Clean
    Session](#mini-project--reproduce-from-a-clean-session)
  - [Lesson Competency Check](#lesson-competency-check-8)
  - [Key Takeaways](#key-takeaways-8)
  - [Repository Output from This
    Lesson](#repository-output-from-this-lesson-7)
  - [References and Further Reading](#references-and-further-reading-8)
    - [Essential Reading](#essential-reading-8)
    - [Reproducible Research and R
      Environments](#reproducible-research-and-r-environments)
    - [Computational Biology](#computational-biology-1)
    - [Official Documentation](#official-documentation-3)
  - [Next Lesson](#next-lesson-8)
    - [Lesson 1.10 — Reproducible Package Environments with
      `renv`](#lesson-110--reproducible-package-environments-with-renv)
  - [Lesson 1.10 — Reproducible Package Environments with
    `renv`](#lesson-110--reproducible-package-environments-with-renv-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-9)
    - [Learning Objectives](#learning-objectives-8)
  - [1. The Problem: Same Script, Different
    Packages](#1-the-problem-same-script-different-packages)
  - [2. What `renv` Does](#2-what-renv-does)
  - [3. Install `renv`](#3-install-renv)
  - [4. What `renv::init()` Changes](#4-what-renvinit-changes)
  - [5. The Lockfile](#5-the-lockfile)
  - [6. `renv::snapshot()`](#6-renvsnapshot)
  - [7. `renv::restore()`](#7-renvrestore)
  - [8. `renv::status()`](#8-renvstatus)
  - [9. Project Library Versus Global
    Library](#9-project-library-versus-global-library)
  - [10. Package Discovery](#10-package-discovery)
  - [11. Git and `renv`](#11-git-and-renv)
  - [12. Bioconductor Considerations](#12-bioconductor-considerations)
  - [13. General Example](#13-general-example)
  - [14. Computational Biology
    Example](#14-computational-biology-example)
  - [15. Common Mistakes](#15-common-mistakes)
  - [16. Debugging Clinic](#16-debugging-clinic)
  - [17. Expert Commentary](#17-expert-commentary)
  - [Practice Questions](#practice-questions)
  - [Practical Exercises](#practical-exercises-8)
  - [Challenge — Reproducible Chapter 1
    Environment](#challenge--reproducible-chapter-1-environment)
  - [Lesson Competency Check](#lesson-competency-check-9)
  - [References and Further Reading](#references-and-further-reading-9)
    - [Essential Reading](#essential-reading-9)
  - [Next Lesson](#next-lesson-9)
    - [Lesson 1.11 — Introduction to Reproducible
      Documents](#lesson-111--introduction-to-reproducible-documents)
  - [Lesson 1.11 — Introduction to Reproducible
    Documents](#lesson-111--introduction-to-reproducible-documents-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-10)
    - [Learning Objectives](#learning-objectives-9)
  - [1. The Reproducibility Problem in Manual
    Reporting](#1-the-reproducibility-problem-in-manual-reporting)
  - [2. What Is R Markdown?](#2-what-is-r-markdown)
  - [3. Source Versus Output](#3-source-versus-output)
  - [4. YAML](#4-yaml)
  - [5. Code Chunks](#5-code-chunks)
  - [6. Chunk Options](#6-chunk-options)
  - [7. Inline R](#7-inline-r)
  - [8. Why This Matters
    Scientifically](#8-why-this-matters-scientifically)
  - [9. Quarto Relationship](#9-quarto-relationship)
  - [10. General Example](#10-general-example)
  - [11. Computational Biology
    Example](#11-computational-biology-example)
  - [12. Common Mistakes](#12-common-mistakes)
  - [13. Clean Rendering](#13-clean-rendering)
  - [14. GitHub Workflow](#14-github-workflow)
  - [Practice Questions](#practice-questions-1)
  - [Practical Exercises](#practical-exercises-9)
  - [Challenge — Chapter 1 Reproducibility
    Report](#challenge--chapter-1-reproducibility-report)
  - [References](#references)
  - [Next Lesson](#next-lesson-10)
    - [Lesson 1.12 — Git and GitHub in an R
      Workflow](#lesson-112--git-and-github-in-an-r-workflow)
  - [Lesson 1.12 — Git and GitHub in an R
    Workflow](#lesson-112--git-and-github-in-an-r-workflow-1)
    - [Where This Lesson Fits](#where-this-lesson-fits-11)
    - [Learning Objectives](#learning-objectives-10)
  - [1. Git Is Not GitHub](#1-git-is-not-github)
  - [2. Why Version Control Matters](#2-why-version-control-matters)
  - [3. Repository](#3-repository)
  - [4. Working Tree, Staging Area,
    Commit](#4-working-tree-staging-area-commit)
  - [5. `git status`](#5-git-status)
  - [6. `git add`](#6-git-add)
  - [7. `git commit`](#7-git-commit)
  - [8. `.gitignore`](#8-gitignore)
  - [9. R Project Files and Git](#9-r-project-files-and-git)
  - [10. GitHub Remote](#10-github-remote)
  - [11. Clone](#11-clone)
  - [12. Pull and Push](#12-pull-and-push)
  - [13. RStudio Integration](#13-rstudio-integration)
  - [14. Branches — Introductory View](#14-branches--introductory-view)
  - [15. Merge Conflicts](#15-merge-conflicts)
  - [16. Computational Biology
    Considerations](#16-computational-biology-considerations)
  - [17. General Workflow](#17-general-workflow)
  - [18. Common Mistakes](#18-common-mistakes)
  - [19. Reviewer Perspective](#19-reviewer-perspective)
  - [Practice Questions](#practice-questions-2)
  - [Practical Exercises](#practical-exercises-10)
  - [Challenge — Version-Control Chapter
    1](#challenge--version-control-chapter-1)
  - [References](#references-1)
  - [Next Lesson](#next-lesson-11)
    - [Lesson 1.13 — Chapter Project](#lesson-113--chapter-project)
  - [Lesson 1.13 — Chapter Project: A Professional Reproducible R
    Project](#lesson-113--chapter-project-a-professional-reproducible-r-project)
    - [Project Goal](#project-goal)
    - [Required Structure](#required-structure)
  - [Part 1 — Create the Project](#part-1--create-the-project)
  - [Part 2 — Create Data](#part-2--create-data)
  - [Part 3 — Use Portable Paths](#part-3--use-portable-paths)
  - [Part 4 — Run from a Clean
    Session](#part-4--run-from-a-clean-session)
  - [Part 5 — Inspect Dependencies](#part-5--inspect-dependencies)
  - [Part 6 — Reproducible Report](#part-6--reproducible-report)
  - [Part 7 — Git](#part-7--git)
  - [Part 8 — README](#part-8--readme)
  - [Part 9 — Reproducibility Test](#part-9--reproducibility-test)
  - [Part 10 — Competency Audit](#part-10--competency-audit)
  - [Reviewer Checklist](#reviewer-checklist)
  - [Chapter 1 Completion Criteria](#chapter-1-completion-criteria)
  - [Next Chapter](#next-chapter)
    - [Chapter 2 — Understanding How R
      Thinks](#chapter-2--understanding-how-r-thinks)

# Chapter 1 — Building a Professional R Environment

This chapter establishes the professional R environment and workflow
used throughout the course. It progresses from understanding R and
RStudio through projects, paths, execution, packages, documentation,
session state, reproducible environments, reproducible documents,
Git/GitHub, and an integrated chapter project.

## Lesson 1.1 — R as a Programming Environment

### Where This Lesson Fits

This is the first lesson of **Chapter 1: Building a Professional R
Environment** in the *R-for-Computational-Biology* course.

At this stage, the objective is not to perform statistical analysis or
bioinformatics. Before learning the language itself, we need to
understand the environment in which R code is written, executed,
extended, and maintained.

A common source of confusion for new R users is treating R, RStudio,
packages, CRAN, and Bioconductor as if they were the same thing. They
are related, but each has a different role. Understanding those roles
now will make later chapters much easier.

------------------------------------------------------------------------

### 1. What Is R?

R is an open-source programming language and software environment
designed primarily for statistical computing, data analysis, and
graphics.

That description is correct, but it is incomplete.

Modern R is also used for:

- data cleaning and transformation;
- statistical modelling;
- scientific visualization;
- machine learning;
- reproducible reports;
- automated analytical pipelines;
- interactive web applications;
- package development;
- database interaction;
- high-performance and parallel computing;
- computational biology and bioinformatics.

R is therefore better thought of as both a **programming language** and
a **computing environment for data-oriented work**.

When you write:

``` r
x <- c(10, 20, 30, 40)
mean(x)
```

you are writing instructions in the R language.

R reads those instructions, evaluates them, stores objects in memory,
calls functions, and returns results.

------------------------------------------------------------------------

### 2. R Is the Language; RStudio Is Not R

This distinction is fundamental.

**R** is the programming language and the software that executes R code.

**RStudio** is an Integrated Development Environment, or IDE, that
provides a convenient interface for working with R.

A useful analogy is:

> R is the engine; RStudio is the dashboard and controls that make the
> engine easier to operate.

Installing RStudio without R does not give you a complete R programming
environment. RStudio normally uses an installed version of R to execute
the code you write.

Conceptually:

``` text
You
 |
 | write code
 v
RStudio / another editor / terminal
 |
 | sends instructions
 v
R
 |
 | executes code
 v
Objects, results, figures, files and reports
```

You can use R without RStudio. For example, R can be started from a
terminal or used through another editor such as Visual Studio Code.

RStudio simply makes the development process more convenient.

------------------------------------------------------------------------

### 3. What Is an IDE?

An **Integrated Development Environment (IDE)** is software that brings
common programming tools into one interface.

Instead of separately opening:

- a text editor;
- an R console;
- a terminal;
- documentation;
- plots;
- files;
- environment information;

an IDE places these tools together.

RStudio is currently one of the most widely used IDEs for R.

Later in this chapter we will examine its interface properly. For now,
remember:

``` text
R       = programming language and runtime
RStudio = development environment used to work with R
```

------------------------------------------------------------------------

### 4. R Can Run Without RStudio

This is worth demonstrating.

If R is installed correctly, it can be invoked independently of RStudio.

For example, from a system terminal:

``` text
R
```

or an R script can be executed with:

``` text
Rscript analysis.R
```

This becomes important in computational biology because many analyses
eventually run on:

- Linux servers;
- high-performance computing clusters;
- cloud systems;
- automated pipelines;
- scheduled jobs.

Those environments may not use the familiar RStudio desktop interface.

Learning R rather than learning only “how to click around RStudio” is
therefore an important distinction.

------------------------------------------------------------------------

### 5. Base R

When R is installed, many functions are already available.

For example:

``` r
numbers <- c(2, 4, 6, 8, 10)

mean(numbers)
```

    ## [1] 6

``` r
median(numbers)
```

    ## [1] 6

``` r
sum(numbers)
```

    ## [1] 30

``` r
length(numbers)
```

    ## [1] 5

We did not install an additional package to use these functions.

Functions and capabilities supplied with the standard R distribution are
commonly referred to as **base R**, although the standard R installation
technically contains several base and recommended packages.

You will use base R throughout this course.

We will not treat base R and modern packages as competing philosophies.
A professional R programmer should understand both and choose tools
according to the problem.

------------------------------------------------------------------------

### 6. What Is an R Package?

R itself cannot contain every tool required by every scientific
discipline.

Its functionality is extended through **packages**.

An R package is a structured collection that can contain:

- R functions;
- datasets;
- documentation;
- compiled code;
- tests;
- examples;
- vignettes.

For example, the `ggplot2` package provides a powerful system for data
visualization.

The `data.table` package provides tools for efficient manipulation of
large tabular datasets.

Bioconductor packages such as `GenomicRanges` provide specialized data
structures and methods for genomic intervals.

This extensibility is one of R’s major strengths.

------------------------------------------------------------------------

### 7. Installing a Package Is Different from Loading It

This distinction causes considerable confusion when learning R.

Installation normally happens once:

``` r
install.packages("ggplot2")
```

Loading normally happens whenever a new R session needs the package:

``` r
library(ggplot2)
```

Think of installation as placing a book in your library.

Loading the package is like taking that book from the shelf so that you
can use it during the current session.

We will examine package management properly in Lesson 1.7.

------------------------------------------------------------------------

### 8. What Is CRAN?

**CRAN** stands for the **Comprehensive R Archive Network**.

CRAN provides:

- the R software distribution;
- thousands of contributed R packages;
- package documentation;
- package source code;
- archived package versions;
- infrastructure for package checking.

When you run:

``` r
install.packages("data.table")
```

R normally obtains the package from a CRAN mirror.

CRAN is not simply a website containing random R scripts. Packages
submitted to CRAN must follow defined package structures and undergo
automated checks.

------------------------------------------------------------------------

### 9. What Is Bioconductor?

Computational biology requires specialized software and data structures
that are not part of base R.

**Bioconductor** is an open-source software project built around R for
the analysis and comprehension of biological data.

It provides packages for areas such as:

- genomic intervals;
- sequence analysis;
- variant annotation;
- gene expression;
- transcriptomics;
- single-cell analysis;
- biological annotation;
- genomic databases.

Examples include:

``` r
library(GenomicRanges)
library(VariantAnnotation)
library(DESeq2)
```

Do not worry about what these packages do yet.

They appear here only to demonstrate that specialized biological
functionality can be added to the same R environment in which we use
general-purpose packages.

A major principle of this course is:

> We will learn R first and use computational biology as an increasingly
> realistic application domain.

Bioconductor receives dedicated treatment later in the course.

------------------------------------------------------------------------

### 10. The R Ecosystem

At this point, the relationship among the major components can be
represented as:

``` text
                         R
                         |
          +--------------+--------------+
          |                             |
       Base R                     R packages
                                        |
                         +--------------+--------------+
                         |                             |
                       CRAN                       Bioconductor
                         |                             |
                  General-purpose              Biological and
                     packages                  genomic packages
```

RStudio sits around this environment as one possible interface for
writing and executing the code.

------------------------------------------------------------------------

### 11. Your First Environment Inspection

Let us now ask R about itself.

#### Check the R version

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

A result may look similar to:

``` text
[1] "R version 4.x.x (...)"
```

Your exact version may be different.

#### Inspect detailed version information

``` r
version
```

    ##                _                                
    ## platform       x86_64-w64-mingw32               
    ## arch           x86_64                           
    ## os             mingw32                          
    ## crt            ucrt                             
    ## system         x86_64, mingw32                  
    ## status                                          
    ## major          4                                
    ## minor          5.3                              
    ## year           2026                             
    ## month          03                               
    ## day            11                               
    ## svn rev        89597                            
    ## language       R                                
    ## version.string R version 4.5.3 (2026-03-11 ucrt)
    ## nickname       Reassured Reassurer

This returns more information than `R.version.string`.

#### Find where R is installed

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

#### Inspect the operating system

``` r
Sys.info()
```

    ##           sysname           release           version          nodename 
    ##         "Windows"          "10 x64"     "build 26200" "DESKTOP-00HU22H" 
    ##           machine             login              user    effective_user 
    ##          "x86-64"              "hp"              "hp"              "hp" 
    ##           udomain 
    ## "DESKTOP-00HU22H"

These functions are useful when troubleshooting differences between
computers or computational environments.

------------------------------------------------------------------------

### 12. Understanding an R Session

Each time R starts, it creates an **R session**.

During that session you may:

- create objects;
- load packages;
- define functions;
- generate plots;
- read files;
- change options;
- perform analyses.

You can inspect the current session using:

``` r
sessionInfo()
```

    ## R version 4.5.3 (2026-03-11 ucrt)
    ## Platform: x86_64-w64-mingw32/x64
    ## Running under: Windows 11 x64 (build 26200)
    ## 
    ## Matrix products: default
    ##   LAPACK version 3.12.1
    ## 
    ## locale:
    ## [1] LC_COLLATE=English_United States.utf8 
    ## [2] LC_CTYPE=English_United States.utf8   
    ## [3] LC_MONETARY=English_United States.utf8
    ## [4] LC_NUMERIC=C                          
    ## [5] LC_TIME=English_United States.utf8    
    ## 
    ## time zone: Asia/Calcutta
    ## tzcode source: internal
    ## 
    ## attached base packages:
    ## [1] stats     graphics  grDevices utils     datasets  methods   base     
    ## 
    ## loaded via a namespace (and not attached):
    ##  [1] compiler_4.5.3    fastmap_1.2.0     cli_3.6.6         tools_4.5.3      
    ##  [5] htmltools_0.5.9   rstudioapi_0.19.0 yaml_2.3.12       rmarkdown_2.31   
    ##  [9] knitr_1.51        xfun_0.57         digest_0.6.39     rlang_1.2.0      
    ## [13] evaluate_1.0.5

The output contains information such as:

- R version;
- operating system/platform;
- locale;
- attached packages;
- loaded namespaces.

Later, this information becomes important for reproducibility.

If an analysis behaves differently on another computer, one of the first
questions should be:

> Are both analyses actually running in the same software environment?

------------------------------------------------------------------------

### 13. Interactive Work Versus Script-Based Work

R is often used interactively.

You type:

``` r
2 + 2
```

    ## [1] 4

and immediately receive a result.

Interactive work is useful for:

- exploring data;
- testing an idea;
- checking a function;
- debugging;
- learning.

However, scientific analysis should not exist only as commands typed
manually into the console.

Suppose you perform 70 commands interactively and obtain an important
result.

A month later, could you reconstruct exactly what you did?

Probably not.

A script records the analysis:

``` r
# analysis.R

data <- read.csv("data/example.csv")

clean_data <- na.omit(data)

summary(clean_data)
```

The script becomes a reproducible record of the computational procedure.

Throughout this course, we will use interactive exploration when useful,
but important analytical steps will be preserved in scripts.

------------------------------------------------------------------------

### 14. General Example: A Small Numerical Dataset

For now, we will deliberately keep the example simple.

``` r
temperatures <- c(22.1, 23.5, 21.8, 25.2, 24.7)

mean(temperatures)
```

    ## [1] 23.46

``` r
range(temperatures)
```

    ## [1] 21.8 25.2

The important point is not the calculation.

Notice what happened:

1.  R created an object called `temperatures`.
2.  The object contained several values.
3.  We passed that object to functions.
4.  R returned results.

Objects and data structures will be taught properly in later chapters.

------------------------------------------------------------------------

### 15. Computational Biology Example: Variant P-values

Now use exactly the same R concepts with a genomics-flavoured example.

``` r
gwas_p_values <- c(
  0.81,
  0.043,
  0.00012,
  0.72,
  5.2e-08
)

length(gwas_p_values)
```

    ## [1] 5

``` r
min(gwas_p_values)
```

    ## [1] 5.2e-08

Nothing fundamentally different happened.

R does not need a special programming language for GWAS data.

The values happen to represent GWAS P-values, but the underlying R
operations are the same.

This illustrates an important principle for the entire course:

> Learn the programming concept with a simple example, then apply the
> same concept to realistic computational biology data.

We are **not performing GWAS analysis here**. The genomics example
simply gives the R operation scientific context.

------------------------------------------------------------------------

### 16. Why R Is Important in Computational Biology

Modern biological research generates large and heterogeneous datasets.

Examples include:

- genomic variants;
- gene-expression matrices;
- GWAS summary statistics;
- phenotype tables;
- genomic annotations;
- sequencing metadata;
- pathway results;
- single-cell measurements.

R is particularly useful because statistical computing, data
manipulation, visualization, reporting, and biological software can
coexist within the same environment.

A future workflow might conceptually look like:

``` text
GWAS summary statistics
        |
        v
Read into R
        |
        v
Quality checks
        |
        v
Data manipulation
        |
        v
Statistical analysis
        |
        v
Visualization
        |
        v
Reproducible report
```

Do not worry about implementing this workflow yet. By the later stages
of this course, we will build workflows of this kind systematically.

------------------------------------------------------------------------

### 17. Common Misconceptions

#### “R and RStudio are the same thing.”

They are not. R executes R code. RStudio is an IDE used to work with R.

#### “I need RStudio to run R.”

No. R can run independently, including from a terminal.

#### “Every useful R function comes with R.”

No. R is extended extensively through packages.

#### “CRAN and Bioconductor are packages.”

No. They are software/package ecosystems and repositories. They
distribute many individual packages.

#### “Bioinformatics requires a different version of R.”

No. Computational biology typically extends R through appropriate
packages, especially those available through Bioconductor and CRAN.

#### “If code works in the console, my analysis is reproducible.”

Not necessarily. Important analytical steps should be captured in
scripts or reproducible documents.

------------------------------------------------------------------------

### 18. Debugging Clinic

#### Problem 1: Function not found

You run:

``` r
ggplot(data)
```

and receive an error indicating that `ggplot` cannot be found.

One possible explanation is that the package providing the function has
not been loaded.

Do not immediately start changing random parts of the code.

First ask:

1.  Which package provides this function?
2.  Is the package installed?
3.  Is it loaded in this session?
4.  Is the function name spelled correctly?

Systematic debugging is a skill we will develop throughout the course.

#### Problem 2: Code worked yesterday but not today

One possibility is that yesterday’s R session contained objects or
loaded packages that are not present in today’s clean session.

This is one reason we should avoid depending on hidden session state.

------------------------------------------------------------------------

### 19. Expert Commentary

A surprisingly important transition in learning R is moving from **“I
can make this code run”** to **“I understand the environment in which
this code runs.”**

The second mindset matters when analyses become larger, are moved to
another computer, are shared with collaborators, or need to be
reproduced months later.

Do not try to memorize every command introduced in this lesson. The
important outcome is understanding the architecture:

``` text
R
+ IDE
+ packages
+ project
+ scripts
+ reproducible environment
```

We will build each component carefully.

------------------------------------------------------------------------

### 20. From the Reviewer’s Perspective

Imagine receiving supplementary R code for a scientific paper.

If the analysis depends on undocumented packages, unexplained software
versions, manually executed console commands, or objects that are not
created by the supplied scripts, reproducing the work becomes difficult.

Good computational research therefore begins before the statistical
analysis itself.

A clearly defined computing environment is part of reproducible science.

Later chapters will turn this principle into concrete practices using
projects, dependency management, version control, testing, and automated
workflows.

------------------------------------------------------------------------

## Practice Questions — Basic Level

Do these questions after completing the lesson. Answers are
intentionally not included here.

### Concept Questions

1.  What is R?

2.  Is R primarily a programming language, a statistical environment, or
    both? Explain briefly.

3.  What is RStudio?

4.  What is the difference between R and RStudio?

5.  What does IDE stand for?

6.  Can R run without RStudio?

7.  What is meant by base R?

8.  What is an R package?

9.  What is the difference between installing and loading an R package?

10. What does CRAN stand for?

11. What is the main purpose of Bioconductor?

12. Why is Bioconductor particularly important for computational
    biology?

13. What is an R session?

14. What information does `sessionInfo()` provide?

15. Why is repeatedly typing an entire scientific analysis into the
    console a poor reproducibility practice?

### Practical Questions

16. Run R and display its version.

17. Find the location of the R installation on your computer.

18. Use R to inspect information about your operating system.

19. Display information about your current R session.

20. Create the following vector:

``` r
sample_depth <- c(32, 45, 28, 51, 39)
```

Then determine:

- how many values it contains;
- the minimum value;
- the maximum value;
- the mean value.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.2, you should be able to explain, without
looking at the notes:

- what R is;
- what RStudio is;
- why R and RStudio are different;
- what an R package is;
- what CRAN provides;
- what Bioconductor provides;
- what an R session represents;
- why scripts are preferable to console-only analyses for reproducible
  work.

You should also be able to run:

``` r
R.version.string
R.home()
Sys.info()
sessionInfo()
```

and explain broadly what each command tells you.

------------------------------------------------------------------------

## Key Takeaways

You can now:

- distinguish R from the software used to interact with it;
- describe the major components of the R ecosystem;
- distinguish base R from additional packages;
- explain the roles of CRAN and Bioconductor;
- inspect basic information about your R installation and session;
- distinguish exploratory console work from reproducible script-based
  analysis;
- explain why the computing environment matters in computational
  biology.

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  R Core Team. *R: A Language and Environment for Statistical
    Computing*. R Foundation for Statistical Computing, Vienna, Austria.

2.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

3.  Grolemund G. *Hands-On Programming with R*. O’Reilly Media.

### Additional Reading

4.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

5.  Gentleman RC, Carey VJ, Bates DM, et al. Bioconductor: open software
    development for computational biology and bioinformatics. *Genome
    Biology*. 2004;5:R80.

### Official Documentation

- The R Project for Statistical Computing
- CRAN documentation and R manuals
- Posit RStudio documentation
- Bioconductor documentation

For software documentation, prefer the current official documentation
because installation procedures and software interfaces can change over
time.

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.2 — Installing R and Verifying the Installation

In the next lesson we will move from understanding the R ecosystem to
establishing and verifying a working R installation.

We will cover:

- selecting the correct R distribution;
- understanding R versions;
- verifying the installation;
- locating R on the system;
- checking R from the terminal;
- understanding common installation problems;
- and confirming that the environment is ready for the rest of the
  course.

------------------------------------------------------------------------

## Lesson 1.2 — Installing R and Verifying the Installation

### Where This Lesson Fits

In Lesson 1.1, we separated **R**, **RStudio**, **packages**, **CRAN**,
and **Bioconductor** and established that R is the language and runtime
that actually executes R code.

This lesson turns that conceptual understanding into a working
installation.

Installing R is easy. Knowing **which R installation is actually being
used**, whether it is working correctly, where it is located, and how to
diagnose version or PATH problems is a more useful professional skill.

The aim is therefore not simply to click through an installer. By the
end of the lesson, you should be able to verify your R installation from
both R itself and, where appropriate, the operating-system terminal.

------------------------------------------------------------------------

### Learning Objectives

After completing this lesson, you should be able to:

- identify the official source for installing R;
- understand the basic structure of R version numbers;
- install or update R appropriately for Windows, macOS, or Linux;
- distinguish the R installation directory from your project directories
  and package libraries;
- verify the installed R version from within R;
- locate the active R installation;
- inspect the operating-system and platform information visible to R;
- check whether R is available from a terminal;
- understand what the system `PATH` is at a practical level;
- recognize common causes of multiple-R-version confusion;
- collect useful diagnostic information before troubleshooting an R
  installation.

------------------------------------------------------------------------

## 1. Before Installing Anything: Know What You Are Installing

A professional R setup usually contains several separate components:

``` text
R
│
├── R installation
│
├── R packages
│
├── IDE/editor
│   └── RStudio, VS Code, etc.
│
└── Your projects
    ├── scripts
    ├── data
    ├── figures
    └── reports
```

These should not be mentally treated as one installation.

For example, installing a new version of R does not mean that your
research project has moved. Similarly, an R package library is not the
same thing as the directory in which R itself is installed.

This distinction becomes important when you upgrade R or work with
multiple versions.

------------------------------------------------------------------------

## 2. Where Should R Come From?

R should normally be obtained through the official **R Project / CRAN
infrastructure** or through the package-management system recommended
for your operating system.

For a typical desktop installation, begin from the official R Project
website and follow the CRAN download link appropriate for your operating
system.

Avoid downloading R installers from unofficial software-download
websites.

Why?

Because scientific computing depends on knowing what software you
actually installed. Using authoritative distribution channels reduces
uncertainty about version, integrity, and documentation.

> **Professional habit:** For R, RStudio, Bioconductor, packages, and
> other research software, prefer the official project or vendor
> documentation over third-party installation tutorials whenever
> possible.

------------------------------------------------------------------------

## 3. Understanding R Version Numbers

Run:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

You may see output similar to:

``` text
[1] "R version 4.x.x (...)"
```

R versions contain several numeric components.

Conceptually:

``` text
major.minor.patch
```

For example:

``` text
4.x.x
```

The exact current release is not hard-coded into this course because R
continues to evolve. Always verify the current release from the official
R Project documentation when installing or updating R.

Why do versions matter?

Because:

- packages may require a minimum R version;
- compiled packages may need rebuilding after an R upgrade;
- behavior can occasionally change across releases;
- collaborators may be using different versions;
- reproducibility requires knowing the software environment used for an
  analysis.

Version information is therefore part of the analytical record, not
merely an installation detail.

------------------------------------------------------------------------

## 4. Windows Installation

For most Windows learners, installation follows this general workflow:

``` text
R Project
   ↓
CRAN
   ↓
Download R for Windows
   ↓
Base distribution
   ↓
Run installer
   ↓
Verify installation
```

The exact wording of download pages can change, so follow the current
official instructions rather than memorizing screenshots from a course.

During a standard installation, the default choices are generally
appropriate for most users.

After installation, do not assume everything is correct simply because
an icon appears in the Start menu.

Open R and verify it.

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

Then:

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

The second command tells you where the currently running R installation
considers its home directory to be.

------------------------------------------------------------------------

## 5. macOS Installation

On macOS, the appropriate R distribution depends partly on the hardware
architecture and operating-system version.

The general workflow is:

``` text
R Project
   ↓
CRAN
   ↓
Download R for macOS
   ↓
Select the appropriate installer
   ↓
Install
   ↓
Verify
```

Modern Macs may use Apple silicon, while older systems may use Intel
processors. Follow the current CRAN guidance for the machine being used.

After installation:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

``` r
Sys.info()
```

    ##           sysname           release           version          nodename 
    ##         "Windows"          "10 x64"     "build 26200" "DESKTOP-00HU22H" 
    ##           machine             login              user    effective_user 
    ##          "x86-64"              "hp"              "hp"              "hp" 
    ##           udomain 
    ## "DESKTOP-00HU22H"

Do not guess the architecture from the appearance of the computer. Ask R
what environment it sees.

------------------------------------------------------------------------

## 6. Linux Installation

Linux installation differs from Windows and macOS because R is commonly
installed through the operating system’s package-management
infrastructure.

The exact commands depend on the distribution.

Examples of Linux families include:

``` text
Ubuntu / Debian
Fedora / Red Hat
openSUSE
Arch-based distributions
```

For Ubuntu or another distribution, follow the current CRAN instructions
for that specific distribution.

This is particularly important because the R version supplied by a
distribution’s default repositories may differ from the current R
release available through CRAN.

After installation, verification from a terminal becomes especially
useful:

``` text
R --version
```

and, if available:

``` text
Rscript --version
```

We will discuss `Rscript` more fully later in Chapter 1.

------------------------------------------------------------------------

## 7. Verifying R from Inside R

Once R starts successfully, collect a small set of diagnostic
information.

### 7.1 R version

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

### 7.2 Detailed version object

``` r
version
```

    ##                _                                
    ## platform       x86_64-w64-mingw32               
    ## arch           x86_64                           
    ## os             mingw32                          
    ## crt            ucrt                             
    ## system         x86_64, mingw32                  
    ## status                                          
    ## major          4                                
    ## minor          5.3                              
    ## year           2026                             
    ## month          03                               
    ## day            11                               
    ## svn rev        89597                            
    ## language       R                                
    ## version.string R version 4.5.3 (2026-03-11 ucrt)
    ## nickname       Reassured Reassurer

`version` contains several components describing the running R
installation.

You can inspect its structure:

``` r
str(version)
```

    ## List of 15
    ##  $ platform      : chr "x86_64-w64-mingw32"
    ##  $ arch          : chr "x86_64"
    ##  $ os            : chr "mingw32"
    ##  $ crt           : chr "ucrt"
    ##  $ system        : chr "x86_64, mingw32"
    ##  $ status        : chr ""
    ##  $ major         : chr "4"
    ##  $ minor         : chr "5.3"
    ##  $ year          : chr "2026"
    ##  $ month         : chr "03"
    ##  $ day           : chr "11"
    ##  $ svn rev       : chr "89597"
    ##  $ language      : chr "R"
    ##  $ version.string: chr "R version 4.5.3 (2026-03-11 ucrt)"
    ##  $ nickname      : chr "Reassured Reassurer"
    ##  - attr(*, "class")= chr "simple.list"

Do not worry about understanding `str()` deeply yet. We will return to
object structures later.

### 7.3 R home directory

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

This is useful when diagnosing which R installation is active.

### 7.4 Platform information

``` r
R.version$platform
```

    ## [1] "x86_64-w64-mingw32"

and:

``` r
R.version$arch
```

    ## [1] "x86_64"

Depending on the operating system and R build, these provide useful
information about the platform and architecture.

### 7.5 Operating-system information

``` r
Sys.info()
```

    ##           sysname           release           version          nodename 
    ##         "Windows"          "10 x64"     "build 26200" "DESKTOP-00HU22H" 
    ##           machine             login              user    effective_user 
    ##          "x86-64"              "hp"              "hp"              "hp" 
    ##           udomain 
    ## "DESKTOP-00HU22H"

Together, these commands provide a much better picture than simply
saying:

> “R is installed.”

------------------------------------------------------------------------

## 8. R Installation Directory, Package Library and Project Directory Are Different

This distinction is important enough to state explicitly.

Suppose:

``` r
R.home()
```

returns an R installation directory.

That directory is **not** where you should save all your scripts and
biological datasets.

Similarly, package libraries have their own locations.

You can inspect package-library paths using:

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

Your current working directory is obtained with:

``` r
getwd()
```

    ## [1] "E:/Github_Classes/R-for-Computational-Biology/R-for-Computational-Biology/chapters"

These three concepts are different:

``` text
R.home()
    ↓
Where the R software installation lives

.libPaths()
    ↓
Where R looks for installed packages

getwd()
    ↓
The current working directory for this R session
```

Later, we will replace casual working-directory management with
project-based workflows.

For now, learn the distinction.

------------------------------------------------------------------------

## 9. Verifying R from the Terminal

R can also be inspected outside RStudio.

Open a terminal or command prompt and try:

``` text
R --version
```

If configured appropriately, the terminal should report the R version.

You may also try:

``` text
Rscript --version
```

Why does this matter if you plan to use RStudio?

Because later you may:

- execute scripts automatically;
- use GitHub Actions;
- work on Linux servers;
- run jobs on an HPC cluster;
- build pipelines;
- schedule analyses;
- work inside containers.

Those workflows often invoke R from the command line rather than through
an IDE.

------------------------------------------------------------------------

## 10. What Is PATH?

You may encounter an error similar to:

``` text
'R' is not recognized as an internal or external command
```

or on another system:

``` text
command not found: R
```

This does **not necessarily mean that R is not installed**.

It may mean that the operating system cannot find the R executable when
you type `R` in the terminal.

One mechanism used by operating systems to locate executable programs is
the **PATH environment variable**.

Conceptually:

``` text
You type:

R --version

        ↓

Operating system searches directories listed in PATH

        ↓

R executable found?

       / \
     yes  no
      |    |
    run   command-not-found error
```

At this stage, you do not need to become an expert in environment
variables.

The important lesson is:

> “R works in RStudio” and “the terminal can find R” are related but not
> identical checks.

------------------------------------------------------------------------

## 11. Inspecting PATH from R

R can inspect environment variables.

For example:

``` r
Sys.getenv("PATH")
```

    ## [1] "D:\\R_installation\\R-4.5.2\\rtools45/x86_64-w64-mingw32.static.posix/bin;D:\\R_installation\\R-4.5.2\\rtools45/usr/bin;D:\\R_installation\\R-4.5.2\\rtools45\\x86_64-w64-mingw32.static.posix\\bin;D:\\R_installation\\R-4.5.2\\rtools45\\usr\\bin;C:\\Program Files\\R\\R-4.5.3\\bin\\x64;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Program Files\\Git\\cmd;C:\\Program Files\\nodejs\\;C:\\Program Files\\Docker\\Docker\\resources\\bin;C:\\Users\\hp\\AppData\\Local\\Programs\\Quarto\\bin;C:\\Users\\hp\\AppData\\Local\\Microsoft\\WindowsApps;C:\\Users\\hp\\AppData\\Local\\Programs\\Microsoft VS Code\\bin;C:\\Users\\hp\\AppData\\Roaming\\npm;C:\\Users\\hp\\AppData\\Local\\Programs\\Ollama;C:\\Users\\hp\\AppData\\Local\\Programs\\Quarto\\bin;C:\\Program Files\\RStudio\\resources\\app\\bin\\postback"

The output can be long.

Do not edit your system PATH simply because this lesson mentions it.

Changing PATH incorrectly can affect other software. We introduce it
here so that command-line errors make conceptual sense.

When a PATH change is genuinely needed, follow operating-system-specific
official guidance.

------------------------------------------------------------------------

## 12. Multiple Versions of R

It is possible to have more than one R version installed.

For example:

``` text
R 4.x
R 4.y
```

This is not automatically a problem.

It becomes a problem when you do not know which version is being used.

Potential symptoms include:

- RStudio opens a different R version than expected;
- packages appear to have disappeared after an upgrade;
- a package works in one environment but not another;
- terminal R and RStudio report different versions;
- package compilation warnings appear after an upgrade.

The first diagnostic step is simple.

Inside the environment that is giving the problem, run:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

Do not troubleshoot based on assumptions.

Inspect the active environment.

------------------------------------------------------------------------

## 13. Why Packages May Seem to Disappear After an R Upgrade

A learner upgrades R and then says:

> “All my packages are gone.”

Often the packages have not literally vanished.

A new R version may use a different package-library location.

Inspect:

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

The old R installation may have used one library directory while the new
version uses another.

This is one reason dependency management becomes important for serious
projects.

Later we will introduce `renv`, which helps record and restore
project-specific package environments.

------------------------------------------------------------------------

## 14. A Small Installation Diagnostic Script

Create a new R script containing:

``` r
# Basic R installation diagnostics

cat("R version:\n")
```

    ## R version:

``` r
print(R.version.string)
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
cat("\nR home:\n")
```

    ## 
    ## R home:

``` r
print(R.home())
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

``` r
cat("\nPlatform:\n")
```

    ## 
    ## Platform:

``` r
print(R.version$platform)
```

    ## [1] "x86_64-w64-mingw32"

``` r
cat("\nArchitecture:\n")
```

    ## 
    ## Architecture:

``` r
print(R.version$arch)
```

    ## [1] "x86_64"

``` r
cat("\nPackage libraries:\n")
```

    ## 
    ## Package libraries:

``` r
print(.libPaths())
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

``` r
cat("\nWorking directory:\n")
```

    ## 
    ## Working directory:

``` r
print(getwd())
```

    ## [1] "E:/Github_Classes/R-for-Computational-Biology/R-for-Computational-Biology/chapters"

``` r
cat("\nSystem information:\n")
```

    ## 
    ## System information:

``` r
print(Sys.info())
```

    ##           sysname           release           version          nodename 
    ##         "Windows"          "10 x64"     "build 26200" "DESKTOP-00HU22H" 
    ##           machine             login              user    effective_user 
    ##          "x86-64"              "hp"              "hp"              "hp" 
    ##           udomain 
    ## "DESKTOP-00HU22H"

You do not need to understand every function in this script yet.

Its purpose is to demonstrate that a software environment can be
inspected programmatically.

Save the script as:

``` text
01_check_r_installation.R
```

This becomes one of the first reusable files in Chapter 1.

------------------------------------------------------------------------

## 15. General Practical Example

Imagine you are preparing to analyse a small teaching dataset.

Before beginning, record:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

``` r
getwd()
```

    ## [1] "E:/Github_Classes/R-for-Computational-Biology/R-for-Computational-Biology/chapters"

Why would this help?

If the exercise fails on another computer, you immediately have useful
information about:

- R version;
- R installation;
- package-library locations;
- working directory.

The data analysis itself may be simple, but the environment still
matters.

------------------------------------------------------------------------

## 16. Computational Biology Practical Example

Now imagine a collaborator sends you an R script used for genomic
analysis.

Their message says:

> “It works on my computer.”

Before changing the statistical code, you might first ask them to
provide:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
sessionInfo()
```

    ## R version 4.5.3 (2026-03-11 ucrt)
    ## Platform: x86_64-w64-mingw32/x64
    ## Running under: Windows 11 x64 (build 26200)
    ## 
    ## Matrix products: default
    ##   LAPACK version 3.12.1
    ## 
    ## locale:
    ## [1] LC_COLLATE=English_United States.utf8 
    ## [2] LC_CTYPE=English_United States.utf8   
    ## [3] LC_MONETARY=English_United States.utf8
    ## [4] LC_NUMERIC=C                          
    ## [5] LC_TIME=English_United States.utf8    
    ## 
    ## time zone: Asia/Calcutta
    ## tzcode source: internal
    ## 
    ## attached base packages:
    ## [1] stats     graphics  grDevices utils     datasets  methods   base     
    ## 
    ## loaded via a namespace (and not attached):
    ##  [1] compiler_4.5.3    fastmap_1.2.0     cli_3.6.6         tools_4.5.3      
    ##  [5] htmltools_0.5.9   rstudioapi_0.19.0 yaml_2.3.12       rmarkdown_2.31   
    ##  [9] knitr_1.51        xfun_0.57         digest_0.6.39     rlang_1.2.0      
    ## [13] evaluate_1.0.5

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

Why?

A computational biology workflow may depend on many packages, including
packages from Bioconductor.

A difference in:

- R version;
- Bioconductor release;
- package version;
- operating system;

can sometimes explain why code behaves differently across systems.

The biological problem may be complex, but the first troubleshooting
step can still be basic environment inspection.

------------------------------------------------------------------------

## 17. R and WSL: An Important Distinction

Windows users working in bioinformatics frequently encounter **Windows
Subsystem for Linux (WSL)**.

If you install R in Windows and separately install R inside WSL, these
are normally **different R installations**.

Conceptually:

``` text
Windows
├── Windows R
└── RStudio Desktop

WSL / Linux
└── Linux R
```

Installing a package in Windows R does not automatically install that
package in Linux R.

Similarly, their paths, package libraries, and system dependencies can
differ.

This becomes highly relevant when combining R with command-line
bioinformatics software.

We will not configure WSL in this lesson. The important point is simply
to recognize that “R on Windows” and “R inside WSL” may represent
separate computing environments.

------------------------------------------------------------------------

## 18. Do You Need the Newest R Version Immediately?

Not always.

For a new learner starting a fresh course, using a current stable R
release is generally sensible.

For an established research project, upgrading software in the middle of
an analysis deserves more care.

Ask:

- Is the current environment working?
- Does a required package need a newer R version?
- Will upgrading affect reproducibility?
- Is the project environment recorded?
- Can the old environment be restored if needed?

The professional principle is:

> Upgrade deliberately, not automatically in the middle of an important
> analysis.

Software currency matters, but so does analytical stability.

------------------------------------------------------------------------

## 19. 64-bit Computing and Architecture

Modern scientific datasets can require substantial memory.

Most current desktop scientific workflows use 64-bit operating systems
and 64-bit R builds.

You can inspect architecture-related information with:

``` r
R.version$arch
```

    ## [1] "x86_64"

``` r
R.version$platform
```

    ## [1] "x86_64-w64-mingw32"

However, architecture is only one part of computational capacity.

A 64-bit R installation does not magically provide unlimited memory.
Available RAM, operating-system limits, data representation, package
implementation, and algorithm design all matter.

Efficient R programming receives dedicated treatment later in the
course.

------------------------------------------------------------------------

## 20. Common Mistakes

### Mistake 1 — Installing RStudio but not R

RStudio is an IDE. It still needs an R installation to execute R code.

------------------------------------------------------------------------

### Mistake 2 — Assuming the installed version

Do not say:

> “I think I’m using R 4.x.”

Run:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

------------------------------------------------------------------------

### Mistake 3 — Confusing R’s installation folder with the project folder

Do not store research projects inside the R installation directory.

Keep software installation and research projects conceptually separate.

------------------------------------------------------------------------

### Mistake 4 — Assuming missing packages were deleted after an upgrade

First inspect:

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

The new R version may simply be looking at a different package library.

------------------------------------------------------------------------

### Mistake 5 — Randomly modifying PATH

Understand the error first.

Changing environment variables without understanding the system
configuration can create additional problems.

------------------------------------------------------------------------

### Mistake 6 — Using unofficial installers

Prefer official software distribution channels and documentation.

------------------------------------------------------------------------

## 21. Debugging Clinic

### Scenario 1 — RStudio opens, but the terminal says R is not recognized

Possible interpretation:

``` text
R exists
+
RStudio knows where it is
+
terminal PATH may not contain the R executable
```

Do not reinstall everything immediately.

Check the R installation and terminal configuration separately.

------------------------------------------------------------------------

### Scenario 2 — RStudio reports a different version from the terminal

Inside RStudio:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
R.home()
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3"

In the terminal:

``` text
R --version
```

If the versions differ, more than one R installation may be present or
the two environments may resolve R differently.

------------------------------------------------------------------------

### Scenario 3 — A package worked before the R upgrade

Check:

``` r
R.version.string
```

    ## [1] "R version 4.5.3 (2026-03-11 ucrt)"

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

Then determine whether the package is installed in the library used by
the current R version.

------------------------------------------------------------------------

### Scenario 4 — A collaborator cannot reproduce your analysis

Before rewriting the analysis, compare:

``` r
sessionInfo()
```

    ## R version 4.5.3 (2026-03-11 ucrt)
    ## Platform: x86_64-w64-mingw32/x64
    ## Running under: Windows 11 x64 (build 26200)
    ## 
    ## Matrix products: default
    ##   LAPACK version 3.12.1
    ## 
    ## locale:
    ## [1] LC_COLLATE=English_United States.utf8 
    ## [2] LC_CTYPE=English_United States.utf8   
    ## [3] LC_MONETARY=English_United States.utf8
    ## [4] LC_NUMERIC=C                          
    ## [5] LC_TIME=English_United States.utf8    
    ## 
    ## time zone: Asia/Calcutta
    ## tzcode source: internal
    ## 
    ## attached base packages:
    ## [1] stats     graphics  grDevices utils     datasets  methods   base     
    ## 
    ## loaded via a namespace (and not attached):
    ##  [1] compiler_4.5.3    fastmap_1.2.0     cli_3.6.6         tools_4.5.3      
    ##  [5] htmltools_0.5.9   rstudioapi_0.19.0 yaml_2.3.12       rmarkdown_2.31   
    ##  [9] knitr_1.51        xfun_0.57         digest_0.6.39     rlang_1.2.0      
    ## [13] evaluate_1.0.5

from both systems.

Environment differences may not be the cause, but they should be ruled
out systematically.

------------------------------------------------------------------------

## 22. Expert Commentary

One of the easiest ways to waste time in scientific computing is to
troubleshoot the wrong layer.

Suppose a script fails.

The cause might be:

``` text
biology
statistics
R code
package
R version
system library
file path
operating system
```

A good computational researcher learns to separate these layers.

Installation diagnostics are therefore not “beginner housekeeping.” They
are part of systematic problem solving.

When something behaves unexpectedly, collect evidence before changing
the code.

------------------------------------------------------------------------

## 23. From the Reviewer’s Perspective

A manuscript may describe a sophisticated analysis but provide only:

> “All analyses were performed in R.”

That is often insufficient for reproducibility.

At minimum, the computational record may need information about:

- R version;
- important package versions;
- operating environment where relevant;
- analysis scripts;
- dependency-management strategy.

The exact reporting requirements depend on the project and journal, but
the principle is stable:

> Software versions are part of the computational methods.

Later in the course, we will automate much of this information rather
than recording it manually.

------------------------------------------------------------------------

## Practice Questions — Basic Level

### Concept Questions

1.  Why should R normally be downloaded from an official R/CRAN source?

2.  Why is the exact R version relevant to reproducible research?

3.  What does `R.version.string` report?

4.  What does `R.home()` tell you?

5.  What is the purpose of `.libPaths()`?

6.  What does `getwd()` return?

7.  Are the R installation directory and project directory the same
    thing?

8.  What does `Sys.info()` provide?

9.  What is the practical purpose of the system `PATH`?

10. If `R --version` fails in a terminal, does that prove that R is not
    installed? Explain.

11. Can more than one R version exist on the same computer?

12. Why might packages appear to be missing after an R upgrade?

13. Why can Windows R and R inside WSL behave as separate installations?

14. Why should software upgrades be approached carefully during an
    active research project?

15. What is the purpose of `sessionInfo()` when troubleshooting
    reproducibility?

------------------------------------------------------------------------

## Practical Exercises

### Exercise 1 — Identify Your R Version

Run:

``` r
R.version.string
```

Record the output.

------------------------------------------------------------------------

### Exercise 2 — Locate R

Run:

``` r
R.home()
```

Identify where R is installed.

------------------------------------------------------------------------

### Exercise 3 — Inspect Package Libraries

Run:

``` r
.libPaths()
```

How many package-library locations are listed?

------------------------------------------------------------------------

### Exercise 4 — Inspect the System

Run:

``` r
Sys.info()
```

Identify:

- operating system;
- machine/node information;
- architecture information where available.

------------------------------------------------------------------------

### Exercise 5 — Inspect the Working Directory

Run:

``` r
getwd()
```

Is this location the same as `R.home()`?

It normally should not be.

Explain the difference.

------------------------------------------------------------------------

### Exercise 6 — Terminal Verification

Outside RStudio, open a terminal and try:

``` text
R --version
```

Then:

``` text
Rscript --version
```

Record what happens.

If either command fails, do not make system changes yet. Simply record
the error. We will learn to diagnose environments systematically.

------------------------------------------------------------------------

## Small Challenge

Create a script called:

``` text
01_check_r_installation.R
```

The script should display:

1.  R version;
2.  R home directory;
3.  platform;
4.  architecture;
5.  package-library paths;
6.  working directory;
7.  system information.

Run the script from a fresh R session.

The objective is not merely to obtain the information. The objective is
to begin recording computational environments through code rather than
memory.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.3, you should be able to explain the
difference between:

``` text
R installation
R package library
R project directory
```

You should also be able to run and broadly interpret:

``` r
R.version.string
R.home()
R.version$platform
R.version$arch
.libPaths()
getwd()
Sys.info()
sessionInfo()
```

Finally, you should understand why:

``` text
R works in RStudio
```

does not necessarily imply:

``` text
R is available from every terminal environment
```

------------------------------------------------------------------------

## Key Takeaways

You can now:

- identify the appropriate source for installing R;
- verify which R version is actually running;
- locate the active R installation;
- distinguish software, package-library and project locations;
- inspect operating-system information from R;
- understand the basic role of PATH;
- recognize problems caused by multiple R installations;
- understand why packages may appear to change after R upgrades;
- distinguish Windows R from R installed inside WSL;
- collect useful diagnostic information before troubleshooting.

------------------------------------------------------------------------

## Repository Output from This Lesson

After completing Lesson 1.2, your Chapter 1 directory should contain:

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    └── ...
```

Do not worry if the remaining files do not exist yet. We will create
them lesson by lesson.

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  R Core Team. *R: A Language and Environment for Statistical
    Computing*. R Foundation for Statistical Computing, Vienna, Austria.

2.  R Core Team. *R Installation and Administration*. R Foundation for
    Statistical Computing.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

### Additional Reading

4.  Grolemund G. *Hands-On Programming with R*. O’Reilly Media.

5.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

### Official Documentation

For installation instructions, always consult the current official
documentation for:

- The R Project for Statistical Computing;
- CRAN;
- your operating system;
- Posit/RStudio when configuring the IDE.

Installation interfaces, supported operating systems, and current R
versions change over time, so official documentation should take
precedence over screenshots or version-specific instructions in static
course material.

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.3 — RStudio and the IDE

Now that R itself is installed and verified, the next lesson will
examine the environment in which we will do most of our interactive
development.

We will cover:

- the RStudio interface;
- Source versus Console;
- Environment and History;
- Files, Plots, Packages, Help and Viewer;
- Terminal and Jobs;
- useful keyboard shortcuts;
- executing individual lines and code selections;
- and configuring RStudio for a clean, reproducible workflow.

The goal will not be to memorize every RStudio button. It will be to
understand which part of the IDE should be used for which task.

------------------------------------------------------------------------

## Lesson 1.3 — RStudio and the IDE

### Where This Lesson Fits

In Lesson 1.1, we established that **R and RStudio are different
things**. R is the language and runtime; RStudio is an Integrated
Development Environment (IDE) that makes it easier to write, run,
inspect, and organize R code.

In Lesson 1.2, we installed and verified R itself. We can now examine
the environment in which much of this course will be developed.

This is not intended to be a tour of every button in RStudio. Instead,
we will learn the parts of the IDE that matter in everyday R programming
and establish a clean workflow from the beginning.

### Learning Objectives

After completing this lesson, you should be able to:

- explain the role of RStudio as an IDE;
- identify the major RStudio panes and their purposes;
- distinguish the Source editor from the Console;
- create, save, and execute an R script;
- run individual lines and selected blocks of code;
- understand Environment and History;
- use Files, Plots, Packages, Help, Viewer, and Terminal appropriately;
- use a small set of high-value keyboard shortcuts;
- recognize hidden session state;
- understand why important code belongs in scripts rather than only in
  the Console.

## 1. RStudio Is a Workspace for Programming

RStudio provides an interface around R. R still performs the
computation.

``` text
                    RStudio
                       |
       +---------------+---------------+
       |               |               |
   Source editor     Console       Supporting tools
       |               |               |
       +---------------+---------------+
                       |
                       v
                       R
                       |
                       v
              Results / objects / files
```

This distinction becomes important when the same R scripts are later
executed outside RStudio on servers, automated pipelines, or
high-performance computing systems.

## 2. The Four-Pane Layout

A standard RStudio Desktop layout commonly contains four main regions:

``` text
+--------------------------------+--------------------------------+
|           SOURCE               |       ENVIRONMENT/HISTORY      |
+--------------------------------+--------------------------------+
|           CONSOLE              | FILES/PLOTS/PACKAGES/HELP/...  |
+--------------------------------+--------------------------------+
```

The exact appearance can vary with RStudio version and configuration. Do
not memorize positions; understand responsibilities.

## 3. The Source Editor

The **Source** pane is where we write and save code.

Create a new R script:

``` r
x <- 10
y <- 20

total <- x + y

print(total)
```

Save it as:

``` text
02_explore_rstudio.R
```

The important feature of Source is persistence. Your instructions remain
available after the session ends.

## 4. The Console

The **Console** is where R evaluates commands interactively.

``` r
2 + 3
```

Interactive Console work is useful for testing expressions, inspecting
objects, experimenting with functions, and debugging. It should not be
the permanent home of a scientific analysis.

## 5. Source Versus Console

A useful mental model is:

``` text
Source
  |
  | saved instructions
  v
Console
  |
  | sends instructions
  v
R session
  |
  v
Objects and results
```

**Practical rule:** use Source to write important code; use Console to
interact with the running R session.

## 6. Running Code from Source

Place the cursor on:

``` r
x <- 10
```

and run the line. A common shortcut on Windows/Linux is:

``` text
Ctrl + Enter
```

On macOS it is commonly:

``` text
Command + Enter
```

Try:

``` r
gene_count <- 20500
sample_count <- 500

gene_count / sample_count
```

Run individual lines and then a selected block.

## 7. Running a Complete Script

Suppose `02_explore_rstudio.R` contains:

``` r
sample_a <- 15
sample_b <- 27

difference <- sample_b - sample_a

print(difference)
```

A good script should eventually run from beginning to end rather than
depend on a particular sequence of manual Console actions. Later we will
study `source()` and command-line execution more carefully.

## 8. The Environment Pane

Create:

``` r
study_name <- "Example Study"
n_samples <- 300
```

RStudio’s **Environment** pane provides a visual representation of
objects in the current environment.

R itself can also inspect objects:

``` r
ls()
```

The Environment pane is a convenience; it is not the R language.

## 9. Hidden Session State

Suppose yesterday you created:

``` r
threshold <- 0.05
```

Today a script contains only:

``` r
significant <- p_value < threshold
```

If `threshold` happens to remain in a restored workspace, the code may
appear to work. Another person running the script from a clean session
may receive:

``` text
Error: object 'threshold' not found
```

The script failed to define everything it required.

A reproducible script should not depend on objects that mysteriously
happen to exist in the workspace.

## 10. History

RStudio can maintain a history of commands sent to the Console. History
can help recover a useful command, but it should not become the analysis
record.

A better workflow is:

``` text
Useful experimental command
          ↓
Understand it
          ↓
Move/refine it in the appropriate script
```

## 11. Files

The **Files** pane is convenient for locating scripts and outputs, but
clicking through folders is not a substitute for understanding paths.
Lesson 1.5 will cover project-relative paths systematically.

## 12. Plots

Try:

``` r
x <- 1:10
y <- x^2

plot(x, y)
```

An interactive plot may appear in the **Plots** pane. Seeing a plot
there does not mean it has been saved reproducibly. Later we will save
figures deliberately from code.

## 13. Packages

The **Packages** pane provides a graphical view of packages. For
reproducible scripts, package requirements should normally be visible in
code:

``` r
library(ggplot2)
```

Prefer code for actions that affect reproducibility.

## 14. Help

RStudio’s **Help** pane displays R documentation:

``` r
?mean
help(mean)
```

Reading documentation is normal programming practice, not merely an
emergency response to errors.

## 15. Viewer

The **Viewer** pane is used for certain HTML-based and interactive
content. Later it may display HTML widgets and web-oriented outputs. It
is conceptually different from the ordinary Plots pane.

## 16. Terminal

RStudio also provides access to a system terminal.

Examples:

``` text
R --version
git status
```

Later, computational biology workflows may also use command-line tools
such as `bcftools`, `samtools`, or `plink`. These are not R functions.

``` text
RStudio
├── Source
├── Console
└── Terminal
      |
      v
Operating-system shell
```

## 17. Jobs

RStudio can run certain tasks as background or local jobs. We only
introduce the idea here. Long-running analyses, parallel computing, and
pipeline execution are covered later.

## 18. High-Value Keyboard Shortcuts

Start with a few useful shortcuts rather than memorizing dozens.

| Task               | Windows/Linux      | macOS                 |
|--------------------|--------------------|-----------------------|
| Run line/selection | `Ctrl + Enter`     | `Command + Enter`     |
| Save               | `Ctrl + S`         | `Command + S`         |
| Comment/uncomment  | `Ctrl + Shift + C` | `Command + Shift + C` |

A commonly used shortcut:

``` text
Alt + -
```

inserts:

``` r
<-
```

## 19. Code Completion and Function Information

RStudio can suggest functions and provide argument information while
typing. These features support understanding but do not replace
documentation.

``` r
?mean
args(mean)
```

## 20. Create the Lesson Script

Create:

``` text
02_explore_rstudio.R
```

Add:

``` r
# ============================================================
# Script: 02_explore_rstudio.R
# Project: R-for-Computational-Biology
# Purpose: Practice the basic RStudio development workflow
# Author: Sandeep Kumar Singh
# ============================================================

study_name <- "RStudio Practice"
n_samples <- 120
n_variables <- 8

total_measurements <- n_samples * n_variables

print(study_name)
print(total_measurements)
```

Save the script, run individual lines, run a selected block, inspect
Environment, and observe Console output.

## 21. General Example

``` r
sample_measurements <- c(12.4, 15.1, 11.8, 16.3, 14.7)

mean_measurement <- mean(sample_measurements)

print(mean_measurement)
```

The lesson is about the development environment, not data analysis.

## 22. Computational Biology Example

Use the same workflow with a genomics-flavoured object:

``` r
sequencing_depth <- c(31, 42, 28, 55, 37)

mean_depth <- mean(sequencing_depth)
minimum_depth <- min(sequencing_depth)

print(mean_depth)
print(minimum_depth)
```

The programming operation is unchanged. The variable happens to
represent sequencing depth; we are not teaching sequencing analysis.

## 23. Workspace Restoration

RStudio can restore previously saved workspace data. This may create
hidden state.

Understand settings concerning:

- restoring `.RData` at startup;
- saving the workspace on exit.

The exact interface can change. The durable principle is:

> A new R session should reveal whether your scripts are genuinely
> self-contained.

## 24. Restarting R

Restarting R is a useful debugging technique because it removes much of
the current session state.

Ask periodically:

> Will this script run after restarting R?

A script that works only after hours of interactive experimentation may
contain hidden dependencies.

## 25. RStudio Is Not Your Project

Your analysis should exist as files and directories:

``` text
project/
├── README.md
├── data/
├── scripts/
├── figures/
└── outputs/
```

RStudio helps you work with them. It should not be the only place where
the project’s logic exists.

## 26. Common Mistakes

#### Writing everything in the Console

The work may succeed today but leaves no structured computational
record.

#### Assuming Environment objects are part of the script

An object can exist in memory without the script containing instructions
to recreate it.

#### Using History as permanent documentation

History is a convenience, not project architecture.

#### Loading packages only through the GUI

A collaborator cannot see which checkbox you clicked.

#### Treating RStudio as R

RStudio is an interface; R executes the code.

#### Memorizing the entire interface

Interfaces evolve. Learn responsibilities rather than button positions.

## 27. Debugging Clinic

### Scenario 1 — Object not found

``` r
result <- value * 2
```

If `value` is missing, ask where the script is supposed to create it. Do
not automatically create it manually in the Console.

### Scenario 2 — Code works only after running lines out of order

``` r
result <- x + y
```

appears before:

``` r
x <- 10
y <- 20
```

Existing session objects can hide this error. Restarting R exposes the
dependency.

### Scenario 3 — Plot appears but is not saved

The Plots pane is an interactive display. Reproducible figure export
must be coded deliberately.

### Scenario 4 — Package works only after clicking its checkbox

The loading step is not recorded in the script.

## 28. Expert Commentary

Beginners often judge progress by how much code they can make run. A
better early measure is:

> Can I explain where my code lives, where it runs, what objects it
> creates, and whether I can reproduce the result after restarting R?

Use RStudio aggressively as a productivity tool, but do not let the IDE
hide how R actually works.

## 29. From the Reviewer’s Perspective

A supplementary workflow requiring a reviewer to manually load packages,
create Console objects, and execute lines in a special undocumented
order is fragile.

The principle is simple:

> IDE convenience should not become an undocumented analytical
> dependency.

Later we will strengthen this with projects, dependency management,
functions, pipelines, testing, and version control.

## Practice Questions — Basic Level

### Concept Questions

1.  What does IDE stand for?
2.  What role does RStudio play when working with R?
3.  What is the primary purpose of Source?
4.  What is the primary purpose of Console?
5.  Why should important code normally be stored in scripts?
6.  What does Environment show?
7.  How can Environment hide reproducibility problems?
8.  What is History useful for?
9.  Why should History not replace scripts?
10. What is the purpose of Files?
11. Where are ordinary interactive plots commonly displayed?
12. What is Help used for?
13. How do Plots and Viewer differ conceptually?
14. What is Terminal used for?
15. Why might computational biologists need a terminal?
16. What does `Ctrl + Enter` commonly do on Windows/Linux?
17. Why is restarting R useful?
18. Why is clicking a package checkbox less reproducible than recording
    the dependency in code?
19. Does an Environment object guarantee that the script created it?
20. Why is learning RStudio alone insufficient for becoming a strong R
    programmer?

## Practical Exercises

### Exercise 1 — Create a Script

Create `02_explore_rstudio.R`:

``` r
course <- "R-for-Computational-Biology"
lesson <- "RStudio and the IDE"

print(course)
print(lesson)
```

### Exercise 2 — Run Code in Different Ways

``` r
x <- 25
y <- 40
z <- x + y

print(z)
```

Practice running one line, a selected block, and the complete script.

### Exercise 3 — Inspect Environment

``` r
sample_name <- "S001"
sample_count <- 150
ls()
```

Compare `ls()` with the Environment pane.

### Exercise 4 — Expose Hidden State

Create a script:

``` r
result <- starting_value * 10
print(result)
```

Create `starting_value <- 5` manually in Console and run the script.
Restart R and run it again. Explain what changed.

### Exercise 5 — General Example

``` r
temperatures <- c(21.2, 22.5, 24.1, 20.8, 23.7)
average_temperature <- mean(temperatures)
print(average_temperature)
```

### Exercise 6 — Computational Biology Example

``` r
sequencing_depth <- c(31, 42, 28, 55, 37)
average_depth <- mean(sequencing_depth)
minimum_depth <- min(sequencing_depth)

print(average_depth)
print(minimum_depth)
```

## Small Challenge

Create `02_explore_rstudio.R` that:

1.  defines a project name;
2.  defines five numeric sample measurements;
3.  calculates their mean;
4.  prints the project name;
5.  prints the mean;
6.  displays the current R version;
7.  displays the current working directory.

Restart R and run the script from beginning to end. Confirm that it does
not depend on manually created Console objects.

## Lesson Competency Check

Before moving on, you should be able to explain:

``` text
Source
Console
Environment
History
Files
Plots
Packages
Help
Viewer
Terminal
```

You should also be able to create and save an `.R` script, run lines and
selections, execute a complete script, inspect session objects, restart
R, and recognize hidden-state problems.

## Key Takeaways

You can now:

- use RStudio as a development environment rather than treating it as R
  itself;
- distinguish Source from Console;
- understand how code reaches the R session;
- inspect session objects;
- use supporting panes appropriately;
- use a small set of useful shortcuts;
- create and save an R script;
- recognize hidden-state problems;
- test code from a cleaner session;
- understand why reproducible analysis should be recorded in code.

## Repository Output from This Lesson

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    └── ...
```

## References and Further Reading

### Essential Reading

1.  Posit. *RStudio IDE User Guide*. Current official documentation.
2.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.
3.  Grolemund G. *Hands-On Programming with R*. O’Reilly Media.

### Additional Reading

4.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.
5.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

For IDE-specific behavior, prefer current official documentation because
menus, pane names, shortcuts, and interfaces can evolve.

## Next Lesson

### Lesson 1.4 — Your First R Project

The next lesson introduces one of the most important changes in
professional R practice:

> Stop thinking of analyses as loose scripts scattered across the
> computer and start thinking in **projects**.

We will cover project roots, `.Rproj` files, clean directory structure,
separating data/scripts/figures/outputs, and building the first
organized project that will continue to grow throughout Chapter 1.

------------------------------------------------------------------------

## Lesson 1.4 — Your First R Project

### Where This Lesson Fits

So far, we have established three foundations:

- **Lesson 1.1:** what R is and how the R ecosystem is organized;
- **Lesson 1.2:** how to install and verify R;
- **Lesson 1.3:** how RStudio supports the development workflow.

We now make an important transition.

Instead of thinking about R work as individual scripts saved wherever
convenient, we begin organizing work as **projects**.

This is one of the simplest changes you can make to an R workflow, but
it has consequences for almost everything that follows: file paths,
reproducibility, Git, `renv`, Quarto, testing, package development,
Shiny applications, and computational pipelines.

A professional R workflow should make it easy to answer:

> Where does this analysis begin, where are its inputs, where does its
> code live, and where are its outputs written?

A project provides that boundary.

------------------------------------------------------------------------

### Learning Objectives

After completing this lesson, you should be able to:

- explain what an R project is;
- distinguish an analytical project from an individual R script;
- understand the concept of a **project root**;
- explain the purpose of an `.Rproj` file;
- create a new RStudio Project;
- open and close projects correctly;
- organize scripts, data, figures, tables, reports, and outputs into
  meaningful directories;
- distinguish source data from derived outputs;
- understand why project-relative organization improves portability;
- avoid common project-organization mistakes;
- create both a simple general-purpose project and a
  computational-biology project skeleton;
- recognize which project decisions should be made before analysis
  begins.

------------------------------------------------------------------------

## 1. The Problem with Loose Scripts

A common early workflow looks like this:

``` text
Desktop/
├── analysis.R
├── analysis2.R
├── final_analysis.R
├── final_analysis_new.R
├── final_analysis_really_final.R
├── data.csv
├── plot1.png
├── results.csv
└── notes.txt
```

This may work for a small exercise.

It becomes difficult to manage when an analysis contains:

- several datasets;
- multiple scripts;
- intermediate files;
- dozens of figures;
- tables;
- reports;
- package dependencies;
- collaborators;
- different analysis stages.

The problem is not R syntax.

The problem is **project architecture**.

------------------------------------------------------------------------

## 2. What Is a Project?

A project is a self-contained directory that represents one coherent
body of work.

For example:

``` text
customer_analysis/
```

or:

``` text
gwas_qc_project/
```

Inside the project are the files required to perform, understand, and
reproduce the work.

A project might contain:

``` text
project/
├── README.md
├── data/
├── scripts/
├── figures/
├── tables/
└── reports/
```

The project directory gives the work a clear boundary.

Conceptually:

``` text
Outside world
     |
     v
+-----------------------------+
|           PROJECT           |
|                             |
| data -> code -> outputs     |
|          |                  |
|          v                  |
|       reports               |
+-----------------------------+
```

The exact folder structure depends on the work. The principle is more
important than any single template.

------------------------------------------------------------------------

## 3. A Script Is Not a Project

Consider:

``` text
analysis.R
```

This is an R script.

It may contain instructions such as:

``` r
data <- read.csv("data/input.csv")
summary(data)
```

But the script alone does not tell us everything about the work.

Where is:

``` text
data/input.csv
```

stored?

Where should figures go?

Where are the final tables?

Which README explains the project?

A project provides the context in which scripts operate.

Think of the relationship as:

``` text
Project
│
├── data
├── scripts
│   ├── 01_import.R
│   ├── 02_clean.R
│   └── 03_analyse.R
├── figures
├── tables
└── reports
```

The scripts are components of the project.

------------------------------------------------------------------------

## 4. What Is an RStudio Project?

RStudio provides a project mechanism that associates an RStudio session
with a particular project directory.

An RStudio Project typically contains a file ending in:

``` text
.Rproj
```

For example:

``` text
my_first_r_project.Rproj
```

A directory might therefore look like:

``` text
my_first_r_project/
├── my_first_r_project.Rproj
├── README.md
├── data/
├── scripts/
└── outputs/
```

The `.Rproj` file contains project-related RStudio configuration.

It is **not** your analysis.

It does not contain all your data or R code.

It helps RStudio recognize and work with the directory as a project.

------------------------------------------------------------------------

## 5. What Is the Project Root?

The **project root** is the top-level directory of the project.

Suppose:

``` text
my_first_r_project/
├── my_first_r_project.Rproj
├── README.md
├── data/
│   └── observations.csv
└── scripts/
    └── analysis.R
```

Then:

``` text
my_first_r_project/
```

is the project root.

From the root, important locations can be described as:

``` text
data/observations.csv
scripts/analysis.R
README.md
```

This way of thinking becomes central to reproducible file paths.

Instead of asking:

> Where is this file on Sandeep’s computer?

we want to ask:

> Where is this file relative to the project root?

That is a much more portable question.

------------------------------------------------------------------------

## 6. Why Project Roots Matter

Imagine that your script contains:

``` r
read.csv(
  "C:/Users/Student/Desktop/my_project/data/observations.csv"
)
```

This path contains information about one specific computer.

If the project is moved to:

``` text
D:/Research/
```

the path breaks.

If a collaborator clones the project on Linux:

``` text
/home/researcher/projects/
```

the path breaks.

If the project instead refers to:

``` r
read.csv("data/observations.csv")
```

the code describes the file’s location **inside the project**.

Conceptually:

``` text
Computer A
C:/Users/Alice/projects/my_project/
                          |
                          +-- data/observations.csv

Computer B
/home/bob/work/my_project/
                    |
                    +-- data/observations.csv
```

The absolute location changed.

The internal project relationship did not.

We will study paths properly in Lesson 1.5.

------------------------------------------------------------------------

## 7. Creating an RStudio Project

The exact RStudio interface may evolve, but the general workflow is:

``` text
File
  ↓
New Project
  ↓
Choose project location/type
  ↓
Create Project
```

RStudio commonly allows projects to be created from:

- a new directory;
- an existing directory;
- version-control sources such as Git.

At this stage, create a project in a **new directory**.

Call it:

``` text
chapter01_project
```

After creation, you should have something similar to:

``` text
chapter01_project/
└── chapter01_project.Rproj
```

Do not add everything immediately.

We will build the structure deliberately.

------------------------------------------------------------------------

## 8. Confirming the Project Location

Inside the newly created project, run:

``` r
getwd()
```

The working directory should correspond to the project directory in a
normal RStudio Project workflow.

You can also inspect the files:

``` r
list.files()
```

At this point, you may see the `.Rproj` file and any other files already
created.

The important idea is:

``` text
Open project
     ↓
R session starts in project context
     ↓
Project-relative work becomes natural
```

------------------------------------------------------------------------

## 9. Create the Basic Directory Structure

We now create a small but meaningful structure:

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
├── data/
├── scripts/
├── figures/
├── tables/
├── reports/
└── outputs/
```

You can create these directories manually.

But because this is an R course, we should also know that R can create
directories.

For example:

``` r
dir.create("data")
dir.create("scripts")
dir.create("figures")
dir.create("tables")
dir.create("reports")
dir.create("outputs")
```

This introduces an important idea:

> Project setup itself can be automated.

Later in the course we will build more sophisticated project-generation
tools.

------------------------------------------------------------------------

## 10. Avoiding Errors When Creating Existing Directories

If you run:

``` r
dir.create("data")
```

when `data` already exists, R may produce a warning.

A safer pattern is:

``` r
if (!dir.exists("data")) {
  dir.create("data")
}
```

Do not worry about `if` syntax yet.

Control flow is taught properly later.

For now, understand the intention:

``` text
Does directory exist?
       |
    +--+--+
    |     |
   yes    no
    |     |
 do     create
nothing directory
```

------------------------------------------------------------------------

## 11. Create Several Directories Efficiently

Instead of repeating:

``` r
dir.create(...)
```

many times, we can store directory names:

``` r
project_dirs <- c(
  "data",
  "scripts",
  "figures",
  "tables",
  "reports",
  "outputs"
)
```

Then:

``` r
for (dir in project_dirs) {
  if (!dir.exists(dir)) {
    dir.create(dir)
  }
}
```

Loops are not taught yet, so you are **not expected to master this
code**.

It is included because the code performs a useful real task.

Later, when loops and functions are formally introduced, this example
will become much easier to understand.

------------------------------------------------------------------------

## 12. What Belongs in Each Directory?

Folder names should communicate responsibility.

### `data/`

Input datasets used by the analysis.

Example:

``` text
data/
└── observations.csv
```

### `scripts/`

R scripts containing computational instructions.

``` text
scripts/
├── 01_import.R
├── 02_clean.R
└── 03_analysis.R
```

### `figures/`

Generated graphical outputs.

``` text
figures/
├── distribution.png
└── summary_plot.pdf
```

### `tables/`

Generated analytical tables.

``` text
tables/
└── summary_statistics.tsv
```

### `reports/`

R Markdown or Quarto reports.

``` text
reports/
└── analysis_report.qmd
```

### `outputs/`

Other derived analytical outputs that do not naturally belong in figures
or tables.

The exact structure can change according to project complexity.

------------------------------------------------------------------------

## 13. Why Number Scripts?

Consider:

``` text
scripts/
├── import.R
├── clean.R
├── analyse.R
└── plot.R
```

This is already reasonable.

But:

``` text
scripts/
├── 01_import.R
├── 02_clean.R
├── 03_analyse.R
└── 04_plot.R
```

communicates intended execution order.

For many analytical projects, numbered scripts provide a simple workflow
map:

``` text
01_import
    ↓
02_clean
    ↓
03_analyse
    ↓
04_visualize
```

This is not the only possible architecture.

Later, functions and pipeline tools such as `targets` will provide more
sophisticated dependency management.

For now, numbering is a useful organizational convention.

------------------------------------------------------------------------

## 14. Raw Data and Processed Data

Larger projects often benefit from distinguishing source data from
derived data.

For example:

``` text
data/
├── raw/
└── processed/
```

Conceptually:

``` text
Raw data
   |
   | cleaning / transformation
   v
Processed data
   |
   | analysis
   v
Results
```

A useful principle is:

> Raw source data should generally not be silently overwritten by an
> analysis script.

If possible, preserve the original input and write transformed data
separately.

This makes it easier to understand what changed.

------------------------------------------------------------------------

## 15. A More Mature Analytical Structure

As projects grow, we may use:

``` text
project/
├── README.md
├── data/
│   ├── raw/
│   └── processed/
├── scripts/
├── figures/
├── tables/
├── reports/
├── outputs/
└── docs/
```

However, more folders do not automatically make a project better.

Avoid creating complexity merely because a professional-looking template
contains many directories.

The structure should reflect actual responsibilities.

> Start simple. Add structure when the project needs it.

------------------------------------------------------------------------

## 16. The README Is Part of the Project

Every serious project should have a `README.md`.

At minimum, it should answer:

``` text
What is this project?
What does it contain?
How is it organized?
How can someone begin?
```

For our practice project:

``` markdown
# Chapter 1 Practice Project

This project is used to practice professional R project organization.

## Structure

- `data/` — input data
- `scripts/` — R scripts
- `figures/` — generated figures
- `tables/` — generated tables
- `reports/` — reproducible reports
- `outputs/` — other generated outputs
```

The README becomes increasingly important when the project is placed on
GitHub.

------------------------------------------------------------------------

## 17. General Example — A Simple Sales Project

Suppose we want to analyse a small sales dataset.

A sensible structure might be:

``` text
sales_analysis/
├── sales_analysis.Rproj
├── README.md
├── data/
│   ├── raw/
│   │   └── sales.csv
│   └── processed/
├── scripts/
│   ├── 01_import.R
│   ├── 02_clean.R
│   └── 03_summary.R
├── figures/
├── tables/
└── reports/
```

Notice that the structure does not depend on sophisticated statistics.

Project organization is useful even for simple work.

------------------------------------------------------------------------

## 18. Computational Biology Example — GWAS Summary Statistics Project

Now consider a genomics project.

``` text
gwas_summary_project/
├── gwas_summary_project.Rproj
├── README.md
├── data/
│   ├── raw/
│   │   └── example_gwas.tsv
│   └── processed/
├── scripts/
│   ├── 01_import.R
│   ├── 02_qc.R
│   ├── 03_annotation.R
│   └── 04_visualization.R
├── figures/
├── tables/
├── reports/
└── outputs/
```

This is only a structural example.

We are **not teaching GWAS analysis here**.

The important point is that the same project-design principles used for
sales data also apply to genomics data.

The domain changes.

The programming discipline does not.

------------------------------------------------------------------------

## 19. Computational Biology Projects Often Need Special Care

Bioinformatics projects frequently contain very large files:

``` text
FASTQ
BAM
CRAM
VCF
BGEN
large expression matrices
GWAS summary statistics
```

A project structure does **not** imply that every raw file should be
copied into GitHub.

For example:

``` text
data/raw/
```

may contain local data that is:

- too large for GitHub;
- controlled-access;
- confidential;
- licensed;
- generated elsewhere.

Later we will use `.gitignore`, download scripts, metadata files, and
documentation to manage these cases properly.

For now, remember:

> A reproducible project describes where its data come from. It does not
> necessarily redistribute every dataset.

------------------------------------------------------------------------

## 20. Data Should Not Be Mixed with Results

Avoid:

``` text
data/
├── original_data.csv
├── cleaned_data.csv
├── plot.png
├── final_table.csv
├── report.html
└── random_notes.txt
```

A clearer structure is:

``` text
data/
├── raw/
│   └── original_data.csv
└── processed/
    └── cleaned_data.csv

figures/
└── plot.png

tables/
└── final_table.csv

reports/
└── report.html
```

The goal is not aesthetic perfection.

The goal is reducing ambiguity.

------------------------------------------------------------------------

## 21. Scripts Should Not Be Mixed with Generated Outputs

Avoid:

``` text
scripts/
├── analysis.R
├── plot.png
├── summary.csv
└── report.html
```

The `scripts/` directory should primarily contain source code.

Generated outputs should have deliberate destinations.

This distinction later makes:

- Git tracking;
- pipeline design;
- debugging;
- automated cleanup;
- publication preparation;

much easier.

------------------------------------------------------------------------

## 22. Project Naming

Good project names are:

- descriptive;
- concise;
- stable;
- filesystem-friendly.

Examples:

``` text
gwas_qc
variant_annotation
expression_qc
hla_variant_atlas
```

Avoid names such as:

``` text
new_project
test2
final_work
project_latest
analysis_final_final
```

A project name should still make sense six months later.

------------------------------------------------------------------------

## 23. File and Folder Naming

Consistency matters.

For this course, prefer names such as:

``` text
01_import_data.R
02_clean_data.R
03_create_summary.R
```

and:

``` text
data/
figures/
reports/
scripts/
```

Avoid inconsistent combinations such as:

``` text
Raw Data/
R_scripts/
FinalFigures/
new results/
```

Spaces are technically supported in many environments, but simple
predictable names reduce friction across command-line tools and
operating systems.

------------------------------------------------------------------------

## 24. Do Not Use the Desktop as Project Architecture

There is nothing inherently wrong with storing a project under the
Desktop.

The problem arises when the Desktop itself becomes the organizational
system.

For example:

``` text
Desktop/
├── data.csv
├── script.R
├── plot.png
├── revised_script.R
├── new_data.csv
├── final.csv
└── paper_plot_final2.png
```

Instead:

``` text
Desktop/
└── my_project/
    ├── data/
    ├── scripts/
    ├── figures/
    └── reports/
```

One project directory should contain the coherent work.

------------------------------------------------------------------------

## 25. Opening a Project Correctly

Once an RStudio Project exists, open the project itself rather than
opening arbitrary scripts from unrelated locations.

For example, open:

``` text
chapter01_project.Rproj
```

This establishes the intended project context.

A common mistake is:

``` text
Open RStudio
     ↓
Open random script
     ↓
Use setwd() until paths happen to work
```

A better workflow is:

``` text
Open project
     ↓
Project context established
     ↓
Open script
     ↓
Use project-relative paths
```

------------------------------------------------------------------------

## 26. One Project, One Purpose

A project should represent a coherent body of work.

Avoid creating:

``` text
all_my_research/
├── diabetes_project/
├── schizophrenia_project/
├── teaching/
├── taxes/
├── manuscript/
└── random_scripts/
```

as one R project.

Different bodies of work should usually have separate project
boundaries.

For example:

``` text
projects/
├── hla_variant_atlas/
├── schizophrenia_coloc/
└── r_course/
```

Each can have its own:

- code;
- data references;
- dependencies;
- Git history;
- README;
- outputs.

------------------------------------------------------------------------

## 27. Project Structure Is Not Universal

There is no single folder structure that every R project must use.

A Shiny application might look different:

``` text
shiny_app/
├── app.R
├── R/
├── data/
└── www/
```

An R package has a formal package structure:

``` text
package/
├── DESCRIPTION
├── NAMESPACE
├── R/
├── man/
└── tests/
```

A pipeline project may use:

``` text
_targets.R
```

and a different organization.

The goal of this lesson is not to impose one template forever.

It is to teach the principles:

``` text
clear boundaries
clear responsibilities
portable paths
separation of inputs and outputs
documented structure
```

------------------------------------------------------------------------

## 28. Build the Chapter 1 Practice Project

Create:

``` text
chapter01_project/
```

Then create:

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
├── data/
│   ├── general/
│   └── genomics/
├── scripts/
├── figures/
├── tables/
├── reports/
└── outputs/
```

This project will continue to grow during the remaining Chapter 1
lessons.

That continuity is deliberate.

Instead of creating unrelated examples in every lesson, we will
progressively improve one project.

------------------------------------------------------------------------

## 29. Create the Structure with R

Create:

``` text
scripts/03_create_project_structure.R
```

and add:

``` r
# ============================================================
# Script: 03_create_project_structure.R
# Project: Chapter 1 Practice Project
# Purpose: Create the standard project directories
# Author: Sandeep Kumar Singh
# ============================================================

project_dirs <- c(
  "data/general",
  "data/genomics",
  "scripts",
  "figures",
  "tables",
  "reports",
  "outputs"
)

for (dir in project_dirs) {
  if (!dir.exists(dir)) {
    dir.create(dir, recursive = TRUE)
    message("Created: ", dir)
  } else {
    message("Already exists: ", dir)
  }
}
```

Again, you are not expected to understand loops fully yet.

At this stage, focus on what the script accomplishes.

Later we will return to this code and rewrite it using concepts learned
in subsequent chapters.

------------------------------------------------------------------------

## 30. Inspect the Project Programmatically

Run:

``` r
getwd()
```

Then:

``` r
list.files()
```

And:

``` r
list.files(recursive = TRUE)
```

Try:

``` r
dir.exists("data")
dir.exists("scripts")
dir.exists("figures")
```

The IDE can display the files visually, but R can also inspect the
project structure.

That distinction is useful for automation.

------------------------------------------------------------------------

## 31. Common Mistakes

### Mistake 1 — One folder for everything

Code, data, figures, and reports become difficult to distinguish.

**Better:** separate files according to responsibility.

------------------------------------------------------------------------

### Mistake 2 — One giant project for unrelated analyses

This creates confusing dependencies and Git history.

**Better:** define meaningful project boundaries.

------------------------------------------------------------------------

### Mistake 3 — Using absolute paths everywhere

``` r
"C:/Users/name/Desktop/project/data/file.csv"
```

makes the project machine-dependent.

**Better:** think relative to the project root.

------------------------------------------------------------------------

### Mistake 4 — Overwriting raw data

Derived transformations should not silently destroy the original input.

**Better:** distinguish raw/source data from processed data when needed.

------------------------------------------------------------------------

### Mistake 5 — Creating dozens of empty folders

More structure is not automatically better.

**Better:** create directories that have clear responsibilities.

------------------------------------------------------------------------

### Mistake 6 — Treating `.Rproj` as the project itself

The `.Rproj` file is configuration associated with an RStudio Project.

The project is the complete directory and its contents.

------------------------------------------------------------------------

### Mistake 7 — Using `setwd()` repeatedly to repair a disorganized workflow

Changing directories until code works often hides the underlying
problem.

Project-relative organization is usually cleaner.

We will examine this properly in Lesson 1.5.

------------------------------------------------------------------------

## 32. Debugging Clinic

### Scenario 1 — `file not found`

Your script contains:

``` r
read.csv("data/sample.csv")
```

but the project contains:

``` text
dataset/
└── sample.csv
```

The problem is structural or path-related.

Do not immediately reinstall packages or rewrite the analysis.

First inspect:

``` r
getwd()
list.files()
file.exists("data/sample.csv")
```

------------------------------------------------------------------------

### Scenario 2 — Script works only when opened from one particular directory

This often indicates that the workflow depends on the current working
directory rather than a stable project context.

Lesson 1.5 will diagnose this in detail.

------------------------------------------------------------------------

### Scenario 3 — Output files appear in unexpected places

If a script writes:

``` r
write.csv(result, "summary.csv")
```

the output location depends on the active working directory.

A clearer project design would deliberately write to something like:

``` r
"tables/summary.csv"
```

------------------------------------------------------------------------

### Scenario 4 — Project works on your machine but not your collaborator’s

Possible causes include:

``` text
absolute paths
missing input files
undocumented package dependencies
different directory structure
case-sensitive filenames
```

Project architecture cannot solve every reproducibility problem, but it
removes many avoidable ones.

------------------------------------------------------------------------

## 33. Performance Corner

Project organization does not usually make R computations faster.

Its performance benefit is **human and operational**.

A clear project can reduce:

- time spent locating files;
- accidental re-analysis of wrong data;
- duplicated outputs;
- manual path changes;
- confusion during collaboration;
- errors during automation.

In real research, reducing human error can matter more than saving a
fraction of a second in a function call.

Computational performance receives dedicated treatment later.

------------------------------------------------------------------------

## 34. Expert Commentary

A common sign of growing programming maturity is that you begin
designing the analysis **before** writing the analysis.

For a new project, ask:

``` text
What are the inputs?
What code will transform them?
Which files are intermediate?
Which outputs are final?
What needs to be preserved?
What should be version-controlled?
What should be documented?
```

You will not always know every answer at the beginning.

That is fine.

Project architecture should evolve with the work.

But beginning with explicit structure is much better than allowing the
filesystem to become an accidental record of the research process.

------------------------------------------------------------------------

## 35. From the Reviewer’s Perspective

Imagine downloading supplementary code from a paper.

Repository A contains:

``` text
script1.R
script_new.R
data2.csv
final.csv
plot_new2.png
```

Repository B contains:

``` text
README.md
data/
scripts/
figures/
tables/
reports/
```

Before reading a single line of R, Repository B communicates more
clearly how the analysis is organized.

Good organization does not prove that the science is correct.

But poor organization makes scientific verification unnecessarily
difficult.

A reviewer should be able to identify:

``` text
inputs
code
analysis order
outputs
documentation
```

without reverse-engineering the author’s personal computer.

------------------------------------------------------------------------

## Practice Questions — Basic Level

### Concept Questions

1.  What is an analytical project?

2.  What is the difference between an R script and an R project?

3.  What is an RStudio Project?

4.  What is an `.Rproj` file?

5.  What is meant by the project root?

6.  Why are project-relative paths more portable than absolute paths?

7.  What is the purpose of a `README.md` file?

8.  Why might a project contain separate `data/` and `scripts/`
    directories?

9.  What is the purpose of a `figures/` directory?

10. Why might raw and processed data be stored separately?

11. Why should raw source data generally not be silently overwritten?

12. What benefit can numbering scripts provide?

13. Why is one giant R project for every research activity usually
    undesirable?

14. Does every R project need exactly the same folder structure?

15. Why might large genomic data files be excluded from GitHub even
    though they are part of an analysis?

16. Why should scripts and generated outputs normally be separated?

17. What is wrong with filenames such as `final_final_new2.R`?

18. Why is repeatedly using `setwd()` often a warning sign?

19. Does creating many folders automatically make a project
    professional?

20. What should determine the structure of a project?

------------------------------------------------------------------------

## Practical Exercises

### Exercise 1 — Create an RStudio Project

Create:

``` text
chapter01_project
```

as a new RStudio Project.

Confirm that the project contains an `.Rproj` file.

------------------------------------------------------------------------

### Exercise 2 — Confirm the Root

Run:

``` r
getwd()
```

Record the result.

Then run:

``` r
list.files()
```

------------------------------------------------------------------------

### Exercise 3 — Create Directories

Create:

``` text
data/
scripts/
figures/
tables/
reports/
outputs/
```

Verify them using:

``` r
dir.exists("data")
dir.exists("scripts")
```

------------------------------------------------------------------------

### Exercise 4 — Create Nested Data Directories

Inside `data/`, create:

``` text
general/
genomics/
```

Verify:

``` r
dir.exists("data/general")
dir.exists("data/genomics")
```

------------------------------------------------------------------------

### Exercise 5 — Inspect Recursively

Run:

``` r
list.files(recursive = TRUE)
```

Compare this with the RStudio Files pane.

------------------------------------------------------------------------

### Exercise 6 — General Project Design

Design a directory structure for:

``` text
student_performance_analysis
```

The project needs:

- one raw CSV;
- cleaned data;
- three R scripts;
- figures;
- summary tables;
- a final report.

Do not perform the analysis. Design only the project.

------------------------------------------------------------------------

### Exercise 7 — Computational Biology Project Design

Design a project structure for:

``` text
variant_annotation_project
```

It needs:

- an input variant table;
- annotation data;
- scripts;
- processed variants;
- figures;
- result tables;
- a report.

Again, focus on R project organization rather than variant biology.

------------------------------------------------------------------------

## Intermediate Thinking Exercise

You receive this directory:

``` text
Desktop/
├── gwas.R
├── gwas2.R
├── new_gwas.R
├── final_gwas.R
├── sumstats.tsv
├── filtered.tsv
├── manhattan.png
├── genes.csv
├── notes.txt
└── final_report.html
```

Without analysing any data:

1.  identify the organizational problems;
2.  propose a project name;
3.  design a cleaner directory structure;
4.  decide which files appear to be inputs and which appear to be
    outputs;
5.  suggest better script names;
6.  identify information you would need before deciding whether
    `sumstats.tsv` should be committed to GitHub.

This is our first small step beyond purely basic questions because it
combines several concepts from Lessons 1.1–1.4.

------------------------------------------------------------------------

## Mini Task — Build the Chapter 1 Project Skeleton

Your project should now look approximately like:

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
│
├── data/
│   ├── general/
│   └── genomics/
│
├── scripts/
│   ├── 01_check_r_installation.R
│   ├── 02_explore_rstudio.R
│   └── 03_create_project_structure.R
│
├── figures/
├── tables/
├── reports/
└── outputs/
```

Do not populate every directory yet.

We will use this same project in later Chapter 1 lessons.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.5, you should be able to explain:

``` text
project
project root
.Rproj
source data
processed data
script
generated output
project-relative organization
```

You should also be able to:

- create a new RStudio Project;
- identify its root;
- create a sensible directory structure;
- inspect directories from R;
- explain why data, code, and outputs are separated;
- explain why project organization improves portability;
- recognize a poorly structured analytical directory;
- redesign it without changing the scientific analysis.

------------------------------------------------------------------------

## Key Takeaways

You can now:

- distinguish a script from a project;
- explain the role of an RStudio Project;
- identify the project root;
- create a structured project directory;
- separate code, data, figures, tables, reports, and outputs;
- distinguish source data from derived data;
- use numbered scripts to communicate workflow order;
- understand why project-relative thinking improves portability;
- recognize common organizational mistakes;
- design both general and computational-biology project structures.

------------------------------------------------------------------------

## Repository Output from This Lesson

Your Chapter 1 material now grows to:

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    └── ...
```

And your continuing practice project becomes:

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
├── data/
│   ├── general/
│   └── genomics/
├── scripts/
├── figures/
├── tables/
├── reports/
└── outputs/
```

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

2.  Posit. *RStudio IDE User Guide*. Current official documentation,
    particularly material on RStudio Projects.

3.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

### Additional Reading

4.  Noble WS. A quick guide to organizing computational biology
    projects. *PLoS Computational Biology*. 2009;5(7):e1000424.

5.  Sandve GK, Nekrutenko A, Taylor J, Hovig E. Ten simple rules for
    reproducible computational research. *PLoS Computational Biology*.
    2013;9(10):e1003285.

6.  Bryan J. Project-oriented workflow resources for R users.

### Documentation Practice

Project conventions evolve as tooling changes. Prefer current official
Posit documentation for interface-specific instructions.

The durable principles are:

``` text
define the project boundary
organize inputs and outputs
document the structure
avoid machine-specific assumptions
preserve reproducibility
```

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.5 — Files, Folders and Paths

We now have a project.

The next question is:

> How should R reliably find files inside it?

Lesson 1.5 will cover one of the most practically important areas of
everyday R programming:

- current working directories;
- absolute versus relative paths;
- `getwd()` and `setwd()`;
- why repeated `setwd()` is fragile;
- `file.exists()` and `dir.exists()`;
- `list.files()`;
- `file.path()`;
- `normalizePath()`;
- Windows path separators;
- spaces and case sensitivity;
- the `here` package;
- project-root thinking;
- and portable file handling for both ordinary datasets and genomics
  files.

This is where the project architecture created in Lesson 1.4 begins to
directly improve our R code.

------------------------------------------------------------------------

## Lesson 1.5 — Files, Folders and Paths

### Where This Lesson Fits

In Lesson 1.4, we stopped treating an analysis as a collection of loose
files and created a structured R project.

That immediately creates the next practical question:

> How does R know where a file is?

This sounds simple until a script is moved to another computer, opened
from a different working directory, run on Linux instead of Windows, or
shared with a collaborator.

Many apparent “R problems” are actually file-path problems.

This lesson therefore focuses on a core professional skill: **reliable
and portable file handling**.

We will learn how R interprets paths, how the working directory affects
relative paths, how to inspect files before reading them, how to build
paths safely, and how project-root thinking reduces machine-specific
code.

------------------------------------------------------------------------

### Learning Objectives

After completing this lesson, you should be able to:

- explain what a file path represents;
- distinguish absolute and relative paths;
- explain the role of the current working directory;
- use `getwd()` and understand what `setwd()` changes;
- explain why repeated hard-coded `setwd()` calls are fragile;
- inspect files and directories using `file.exists()`, `dir.exists()`,
  and `list.files()`;
- create directories using `dir.create()`;
- construct paths using `file.path()`;
- inspect canonical paths using `normalizePath()`;
- handle Windows path separators correctly;
- understand basic path differences across Windows, macOS, Linux, and
  WSL;
- understand case sensitivity and filenames containing spaces;
- use the `here` package for project-root-oriented paths;
- diagnose common “file not found” problems systematically;
- apply the same path principles to general datasets and genomics files.

------------------------------------------------------------------------

## 1. What Is a Path?

A **path** describes the location of a file or directory in a
filesystem.

For example:

``` text
data/general/sales.csv
```

describes a file called:

``` text
sales.csv
```

inside:

``` text
general/
```

which is inside:

``` text
data/
```

A path therefore describes a sequence of locations:

``` text
data
  ↓
general
  ↓
sales.csv
```

R uses paths whenever it needs to:

- read data;
- write results;
- source another script;
- save a figure;
- open a report;
- locate a configuration file;
- inspect a directory.

Path handling is not a minor convenience. It is part of the
computational workflow.

------------------------------------------------------------------------

## 2. Files and Directories

A **file** contains information.

Examples:

``` text
sales.csv
analysis.R
variants.tsv
report.qmd
figure.png
```

A **directory** or folder contains files and possibly other directories.

Example:

``` text
project/
├── data/
│   └── sales.csv
├── scripts/
│   └── analysis.R
└── reports/
    └── report.qmd
```

R provides separate tools for asking whether a file or directory exists.

For example:

``` r
file.exists("data/sales.csv")
```

and:

``` r
dir.exists("data")
```

This distinction is useful when debugging.

------------------------------------------------------------------------

## 3. Absolute Paths

An **absolute path** describes a location from a filesystem root or
drive.

A Windows example might look like:

``` text
C:/Users/student/Documents/project/data/sales.csv
```

A Linux or macOS example might look like:

``` text
/home/student/project/data/sales.csv
```

Absolute paths answer:

> Exactly where is this file on this computer?

They can be useful for some system-level tasks.

But they are often a poor choice for files that belong inside a portable
analytical project.

Why?

Because another computer probably does not have:

``` text
C:/Users/student/
```

or:

``` text
/home/student/
```

in exactly the same way.

------------------------------------------------------------------------

## 4. Relative Paths

A **relative path** describes a location relative to some reference
point.

Inside our Chapter 1 project:

``` text
chapter01_project/
├── data/
│   ├── general/
│   │   └── measurements.csv
│   └── genomics/
│       └── example_gwas.tsv
└── scripts/
```

we might refer to:

``` text
data/general/measurements.csv
```

or:

``` text
data/genomics/example_gwas.tsv
```

These paths do not mention:

``` text
C:/Users/...
```

or:

``` text
/home/...
```

They describe the file’s location **inside the project**.

This makes the project easier to move.

------------------------------------------------------------------------

## 5. Relative to What?

This is the question that beginners often miss.

A relative path is always relative to a reference location.

In ordinary R file operations, that reference is commonly the **current
working directory**.

You can inspect it using:

``` r
getwd()
```

    ## [1] "E:/Github_Classes/R-for-Computational-Biology/R-for-Computational-Biology/chapters"

If `getwd()` returns:

``` text
C:/Users/student/projects/chapter01_project
```

then:

``` r
file.exists("data/general/measurements.csv")
```

is interpreted conceptually as:

``` text
C:/Users/student/projects/chapter01_project
+
data/general/measurements.csv
```

which becomes:

``` text
C:/Users/student/projects/chapter01_project/data/general/measurements.csv
```

This is why understanding the working directory matters.

------------------------------------------------------------------------

## 6. The Current Working Directory

The current working directory is the directory R currently uses as the
reference point for many relative file operations.

Check it:

``` r
getwd()
```

    ## [1] "E:/Github_Classes/R-for-Computational-Biology/R-for-Computational-Biology/chapters"

You can also inspect the contents:

``` r
list.files()
```

    ## [1] "Chapter_01_Building_a_Professional_R_Environment.Rmd"

In an RStudio Project, the working directory commonly begins at the
project root when the project is opened normally.

This is one reason project-oriented workflows are useful.

------------------------------------------------------------------------

## 7. What Does `setwd()` Do?

`setwd()` changes the current working directory.

For example:

``` r
setwd("C:/Users/student/Documents/project")
```

After this command:

``` r
getwd()
```

should report the new directory.

`setwd()` is a real and legitimate R function.

The problem is not that `setwd()` exists.

The problem is using machine-specific `setwd()` calls as the foundation
of every project.

------------------------------------------------------------------------

## 8. Why Hard-Coded `setwd()` Is Fragile

Consider:

``` r
setwd("C:/Users/Alice/Desktop/gwas_project")
```

Alice’s script works.

Bob clones the project to:

``` text
/home/bob/projects/gwas_project
```

The script fails immediately.

The path encoded Alice’s personal computer rather than the structure of
the project.

A better design is:

``` text
Open project
     ↓
Project root established
     ↓
Use project-relative paths
```

rather than:

``` text
Open random R session
     ↓
Hard-code personal absolute path
     ↓
Hope every computer looks the same
```

------------------------------------------------------------------------

## 9. When `setwd()` Can Still Be Useful

We should not teach rules as dogma.

`setwd()` can be useful during:

- temporary interactive exploration;
- teaching demonstrations;
- certain batch workflows;
- deliberately changing the reference directory;
- debugging filesystem behavior.

The professional question is not:

> Is `setwd()` forbidden?

It is:

> Should the reproducibility of this project depend on a path hard-coded
> for one person’s computer?

Usually, the answer is no.

------------------------------------------------------------------------

## 10. Inspecting Whether a File Exists

Before blaming an import function, ask whether R can actually see the
file.

Use:

``` r
file.exists("data/general/measurements.csv")
```

R returns:

``` text
TRUE
```

or:

``` text
FALSE
```

This is one of the simplest and most useful debugging checks in R.

A failed import can mean:

``` text
wrong path
wrong filename
wrong working directory
wrong capitalization
missing file
```

It does not automatically mean that `read.csv()` is broken.

------------------------------------------------------------------------

## 11. Inspecting Whether a Directory Exists

Use:

``` r
dir.exists("data")
```

or:

``` r
dir.exists("data/genomics")
```

This helps distinguish:

``` text
directory missing
```

from:

``` text
file missing inside an existing directory
```

That distinction makes debugging more systematic.

------------------------------------------------------------------------

## 12. Listing Files

To inspect the current directory:

``` r
list.files()
```

    ## [1] "Chapter_01_Building_a_Professional_R_Environment.Rmd"

To inspect a particular directory:

``` r
list.files("data")
```

To inspect recursively:

``` r
list.files("data", recursive = TRUE)
```

You can request full path-like output:

``` r
list.files("data", recursive = TRUE, full.names = TRUE)
```

These commands are extremely useful when you are unsure what R can
actually see.

------------------------------------------------------------------------

## 13. Filtering Listed Files

Suppose a directory contains:

``` text
sample1.csv
sample2.csv
notes.txt
report.pdf
```

You can search for CSV files:

``` r
list.files(
  path = "data",
  pattern = "\\.csv$"
)
```

The regular-expression syntax is not our focus yet.

For now, understand that `list.files()` can help locate files
programmatically instead of relying only on visual browsing.

In bioinformatics, this becomes useful when directories contain many
files.

------------------------------------------------------------------------

## 14. Creating Directories

Create a directory:

``` r
dir.create("results")
```

Create nested directories:

``` r
dir.create(
  "results/tables",
  recursive = TRUE
)
```

The `recursive = TRUE` argument allows parent directories to be created
when needed.

A safer project-setup pattern is:

``` r
if (!dir.exists("results")) {
  dir.create("results")
}
```

Again, control flow will be taught later. Focus here on the filesystem
operation.

------------------------------------------------------------------------

## 15. Building Paths with `file.path()`

You could write:

``` r
"data/general/measurements.csv"
```

directly.

R also provides:

``` r
file.path(
  "data",
  "general",
  "measurements.csv"
)
```

This constructs the path using the platform’s appropriate separator
conventions.

Try:

``` r
file.path("data", "general", "measurements.csv")
```

    ## [1] "data/general/measurements.csv"

For programmatic path construction, `file.path()` is usually clearer and
safer than manually pasting separators.

------------------------------------------------------------------------

## 16. Why `file.path()` Becomes Important

Suppose:

``` r
sample_id <- "S001"
```

and you want:

``` text
data/genomics/S001.csv
```

A programmatic approach could be:

``` r
sample_id <- "S001"

sample_file <- file.path(
  "data",
  "genomics",
  paste0(sample_id, ".csv")
)

sample_file
```

Now the filename can be generated from data or configuration.

This becomes useful when processing many samples.

We will study string construction properly later.

------------------------------------------------------------------------

## 17. `normalizePath()`

`normalizePath()` can return a normalized representation of a path.

For example:

``` r
normalizePath(".")
```

The dot:

``` text
.
```

represents the current directory.

Try:

``` r
normalizePath("data")
```

if the directory exists.

This can be useful when diagnosing exactly how R resolves a path.

Be aware that behavior and formatting can vary by operating system.

------------------------------------------------------------------------

## 18. Special Path Symbols: `.` and `..`

Two filesystem conventions are especially useful.

### Current directory

``` text
.
```

means:

``` text
current directory
```

### Parent directory

``` text
..
```

means:

``` text
one directory above the current directory
```

For example:

``` r
list.files(".")
```

lists the current directory.

And:

``` r
list.files("..")
```

lists the parent directory.

These conventions appear throughout command-line computing, not just R.

------------------------------------------------------------------------

## 19. Windows Backslashes

Windows commonly displays paths using backslashes:

``` text
C:\Users\student\project
```

But in R strings, a backslash has special meaning.

For example:

``` r
"\n"
```

represents a newline character.

Therefore, this can be problematic:

``` r
"C:\Users\student\project"
```

A convenient approach in R is to use forward slashes:

``` r
"C:/Users/student/project"
```

Alternatively, escaped backslashes can be written:

``` r
"C:\\Users\\student\\project"
```

For most ordinary R path work, forward slashes are easier to read.

------------------------------------------------------------------------

## 20. Why Backslashes Cause Strange Errors

Consider:

``` r
"C:\new\test"
```

R may interpret:

``` text
\n
```

as newline and:

``` text
\t
```

as tab.

So what visually looks like a Windows path may be interpreted as a
string containing escape sequences.

This is not a Windows filesystem failure.

It is an R string-literal issue.

Understanding this distinction prevents unnecessary confusion.

------------------------------------------------------------------------

## 21. Spaces in Filenames

A filename can contain spaces:

``` text
sample information.csv
```

R can work with it:

``` r
file.exists("data/sample information.csv")
```

However, spaces can create additional quoting requirements in shell
commands and external tools.

For project files, names such as:

``` text
sample_information.csv
```

or:

``` text
sample-information.csv
```

are often easier to use consistently.

This is especially helpful when R interacts with command-line
bioinformatics tools.

------------------------------------------------------------------------

## 22. Case Sensitivity

These names may not be equivalent:

``` text
Sample.csv
sample.csv
SAMPLE.csv
```

Filesystem case sensitivity differs across operating systems and
configurations.

A script that accidentally relies on case-insensitive behavior may work
on one machine and fail on another.

Good practice:

- use consistent lowercase naming where appropriate;
- match filenames exactly;
- do not assume capitalization will be ignored.

This becomes particularly important when moving projects between
Windows, Linux, containers, and HPC systems.

------------------------------------------------------------------------

## 23. File Extensions Matter

Consider:

``` text
variants.tsv
variants.tsv.gz
variants.csv
variants.txt
```

These are different filenames and potentially different file formats.

Do not rely solely on how a file manager visually displays names because
some operating-system settings hide extensions.

From R:

``` r
list.files("data/genomics")
```

shows what R sees.

For scientific workflows, exact filenames matter.

------------------------------------------------------------------------

## 24. The Home Directory

R can refer to a user’s home directory using:

``` text
~
```

For example:

``` r
path.expand("~")
```

This can be useful for user-level configuration.

However, using:

``` text
~/Desktop/project/data/file.csv
```

for every project still ties the workflow to one user’s filesystem
organization.

For project-owned files, project-relative paths remain preferable.

------------------------------------------------------------------------

## 25. Windows and WSL Paths Are Different

Suppose a Windows file exists at:

``` text
C:/Users/student/project/data/file.tsv
```

Inside WSL, the same Windows drive may be exposed through a path
resembling:

``` text
/mnt/c/Users/student/project/data/file.tsv
```

These are different path conventions in different operating
environments.

Similarly:

``` text
C:/...
```

is not a normal Linux path.

This matters because bioinformatics workflows frequently combine:

``` text
Windows R
WSL
Linux command-line tools
```

Always ask:

> Which environment is interpreting this path?

------------------------------------------------------------------------

## 26. Network Drives and Mounted Filesystems

Research environments may use:

- network drives;
- institutional storage;
- mounted servers;
- cloud-synchronized directories;
- HPC filesystems.

A path might work only when a drive is mounted or a network resource is
available.

Therefore:

``` text
file not found
```

can sometimes mean:

``` text
storage unavailable
```

rather than:

``` text
filename incorrect
```

The first diagnostic tools remain simple:

``` r
dir.exists(...)
file.exists(...)
list.files(...)
```

------------------------------------------------------------------------

## 27. Introducing the `here` Package

The `here` package provides a convenient way to construct paths relative
to a project root.

Install it once if needed:

``` r
install.packages("here")
```

Then:

``` r
library(here)
```

or use the namespace directly:

``` r
here::here()
```

Inside a correctly identified project, this reports the project root
determined by `here`.

------------------------------------------------------------------------

## 28. Building a Path with `here()`

Instead of:

``` r
"C:/Users/student/projects/chapter01_project/data/general/measurements.csv"
```

you can write:

``` r
here::here(
  "data",
  "general",
  "measurements.csv"
)
```

Conceptually:

``` text
project root
     +
data
     +
general
     +
measurements.csv
```

The result is a complete path constructed from the project context.

------------------------------------------------------------------------

## 29. Why `here()` Is Useful

Imagine two collaborators.

Alice:

``` text
C:/Users/Alice/projects/chapter01_project/
```

Bob:

``` text
/home/bob/projects/chapter01_project/
```

Both can use:

``` r
here::here("data", "general", "measurements.csv")
```

provided the internal project structure is the same and the project root
is identified correctly.

The personal filesystem prefix changes.

The code describing the project’s internal structure does not.

------------------------------------------------------------------------

## 30. `here()` Is Not Magic

It is important not to replace one misunderstanding with another.

`here()` must determine an appropriate project root.

If your files are scattered across unrelated directories, `here()`
cannot repair the project architecture.

Similarly, if you accidentally open or execute code in a context where
the intended root is not identifiable, you still need to understand the
filesystem.

Therefore:

> Learn paths first. Use `here()` as a project-oriented tool, not as a
> substitute for understanding paths.

------------------------------------------------------------------------

## 31. Inspecting the `here` Root

Run:

``` r
here::here()
```

Compare it with:

``` r
getwd()
```

In a straightforward project session they may point to the same project
directory, but they represent different concepts.

`getwd()` asks:

> What is the current working directory?

`here::here()` asks, conceptually:

> What root has `here` identified for this project context?

That distinction becomes useful in more complex workflows.

------------------------------------------------------------------------

## 32. General Practical Example

Our project contains:

``` text
data/general/measurements.csv
```

Before reading it:

``` r
general_file <- here::here(
  "data",
  "general",
  "measurements.csv"
)

general_file

file.exists(general_file)
```

Only after confirming that the file exists should we attempt to read it.

For example:

``` r
measurements <- read.csv(general_file)
```

This produces a useful debugging sequence:

``` text
Construct path
     ↓
Inspect path
     ↓
Check existence
     ↓
Read file
```

rather than:

``` text
Read file
     ↓
Error
     ↓
Guess randomly
```

------------------------------------------------------------------------

## 33. Computational Biology Practical Example

Suppose:

``` text
data/genomics/example_gwas.tsv
```

contains a small teaching dataset.

Construct:

``` r
gwas_file <- here::here(
  "data",
  "genomics",
  "example_gwas.tsv"
)
```

Then:

``` r
gwas_file
file.exists(gwas_file)
```

Only then:

``` r
gwas_data <- read.delim(gwas_file)
```

Again, this lesson is not about GWAS.

The genomics dataset demonstrates that the same path discipline applies
to scientific files.

------------------------------------------------------------------------

## 34. A Larger Genomics Example

Real bioinformatics files may have names such as:

``` text
gnomad.genomes.v4.1.sites.chr6.vcf.bgz
```

or:

``` text
PGC_SCZ_summary_statistics.tsv.gz
```

A project might store only a small teaching subset locally:

``` text
data/
└── genomics/
    └── chr6_example_variants.tsv
```

while documentation records where the full dataset came from.

The path principles remain unchanged:

``` r
variant_file <- here::here(
  "data",
  "genomics",
  "chr6_example_variants.tsv"
)
```

Large data changes storage strategy.

It does not change the basic logic of reliable path construction.

------------------------------------------------------------------------

## 35. Input Paths and Output Paths

Paths are not only for reading files.

Suppose we want a table written to:

``` text
tables/sample_summary.csv
```

Construct:

``` r
output_file <- here::here(
  "tables",
  "sample_summary.csv"
)
```

Then:

``` r
write.csv(
  sample_summary,
  output_file,
  row.names = FALSE
)
```

A professional script should be deliberate about both:

``` text
Where does input come from?
Where does output go?
```

------------------------------------------------------------------------

## 36. Check Output Directories Before Writing

Before saving a file:

``` r
dir.exists(
  here::here("tables")
)
```

If the directory does not exist, create it:

``` r
dir.create(
  here::here("tables"),
  recursive = TRUE
)
```

Later we will wrap patterns like this in reusable functions.

For now, understand the sequence.

------------------------------------------------------------------------

## 37. Do Not Construct Paths with `paste()` Unless Necessary

You may see:

``` r
paste("data", "general", "file.csv", sep = "/")
```

This can work.

But for filesystem paths, R already provides:

``` r
file.path("data", "general", "file.csv")
```

and project-oriented workflows can use:

``` r
here::here("data", "general", "file.csv")
```

Use tools designed for the problem.

------------------------------------------------------------------------

## 38. Avoid Embedding File Locations Everywhere

A poor script may contain:

``` r
read.csv("data/general/a.csv")
read.csv("data/general/b.csv")
write.csv(x, "tables/x.csv")
write.csv(y, "tables/y.csv")
```

This is not automatically wrong.

But larger projects benefit from making important locations explicit.

For example:

``` r
data_dir <- here::here("data", "general")
table_dir <- here::here("tables")
```

Then build paths from those locations.

Later we will use configuration objects and functions for more complex
workflows.

------------------------------------------------------------------------

## 39. A Path Debugging Workflow

When R reports that a file cannot be found, do not immediately edit the
import function.

Use this sequence.

### Step 1 — Inspect the working directory

``` r
getwd()
```

### Step 2 — Inspect the project/root context

``` r
here::here()
```

if using `here`.

### Step 3 — Inspect the directory

``` r
list.files("data", recursive = TRUE)
```

### Step 4 — Construct the expected path

``` r
expected_file <- file.path(
  "data",
  "general",
  "measurements.csv"
)
```

### Step 5 — Test it

``` r
file.exists(expected_file)
```

### Step 6 — Check spelling and capitalization

Compare the exact filename returned by `list.files()`.

This is far more efficient than random trial and error.

------------------------------------------------------------------------

## 40. Common Mistakes

### Mistake 1 — Hard-coding a personal absolute path

``` r
"C:/Users/name/Desktop/project/data/file.csv"
```

This reduces portability.

------------------------------------------------------------------------

### Mistake 2 — Repeatedly using `setwd()` throughout a script

The script’s meaning becomes dependent on hidden directory changes.

------------------------------------------------------------------------

### Mistake 3 — Confusing the script location with the working directory

The fact that an `.R` file lives in:

``` text
scripts/
```

does not automatically mean all relative paths are interpreted from that
script’s folder.

Always understand the execution context.

------------------------------------------------------------------------

### Mistake 4 — Using unescaped Windows backslashes

``` r
"C:\new\test"
```

may contain interpreted escape sequences.

------------------------------------------------------------------------

### Mistake 5 — Ignoring capitalization

``` text
Sample.csv
```

and:

``` text
sample.csv
```

may behave differently across systems.

------------------------------------------------------------------------

### Mistake 6 — Guessing filenames

Use:

``` r
list.files()
```

to inspect what R actually sees.

------------------------------------------------------------------------

### Mistake 7 — Assuming `here()` repairs a disorganized project

It does not.

Project architecture still matters.

------------------------------------------------------------------------

### Mistake 8 — Saving outputs without specifying a directory

``` r
write.csv(result, "result.csv")
```

may put the file somewhere you did not intend.

Use deliberate output locations.

------------------------------------------------------------------------

## 41. Debugging Clinic

### Scenario 1 — File exists, but R says it does not

You can see:

``` text
data/general/Measurements.csv
```

but code checks:

``` r
file.exists("data/general/measurements.csv")
```

On a case-sensitive filesystem, these are different names.

------------------------------------------------------------------------

### Scenario 2 — Windows path produces strange output

You wrote:

``` r
"C:\new\test"
```

The problem may be escape-sequence interpretation.

Try:

``` r
"C:/new/test"
```

or escaped backslashes.

------------------------------------------------------------------------

### Scenario 3 — Script works only after `setwd()`

This suggests that the code depends on a particular working-directory
state.

Ask whether the project should instead be opened at a stable root and
use project-relative paths.

------------------------------------------------------------------------

### Scenario 4 — RStudio sees the file but WSL tool does not

RStudio may be using Windows paths while the external tool is running
inside Linux/WSL.

Determine which operating environment is interpreting the path.

------------------------------------------------------------------------

### Scenario 5 — Output directory does not exist

A write function fails because:

``` text
tables/
```

was never created.

Check:

``` r
dir.exists("tables")
```

before blaming the output function.

------------------------------------------------------------------------

### Scenario 6 — `here()` points somewhere unexpected

Inspect:

``` r
here::here()
getwd()
```

Then inspect the project markers and how the current session was
started.

Do not concatenate additional `../..` fragments blindly until the path
happens to work.

------------------------------------------------------------------------

## 42. Performance Corner

For ordinary project files, path construction is rarely a computational
bottleneck.

The performance issue is usually **I/O**, meaning reading and writing
data.

For large biological datasets, performance may depend on:

- file compression;
- file format;
- network storage;
- disk speed;
- whether the entire file is read;
- whether indexing is available;
- the package used for import.

Those topics come later.

At this stage, optimize for:

``` text
correctness
clarity
portability
```

before optimizing file I/O speed.

------------------------------------------------------------------------

## 43. Expert Commentary

A useful diagnostic habit is to separate:

``` text
Can R locate the file?
```

from:

``` text
Can R understand the file?
```

These are different problems.

If:

``` r
file.exists(path)
```

returns `FALSE`, the problem is not yet CSV parsing, VCF parsing,
delimiters, column types, or statistical analysis.

R has not even found the file.

Debug the earliest failing layer first.

This principle generalizes far beyond paths.

------------------------------------------------------------------------

## 44. From the Reviewer’s Perspective

Suppose supplementary code contains:

``` r
setwd("D:/Sandeep/Paper/NewAnalysis/Final")
```

A reviewer immediately knows that the script was written around one
machine’s filesystem.

Now compare:

``` r
input_file <- here::here(
  "data",
  "example.tsv"
)
```

The second version communicates the project’s internal structure rather
than the author’s personal directory layout.

For reproducible computational research, this is a significant
improvement.

A reviewer should not need to reconstruct your hard drive to reproduce
your analysis.

------------------------------------------------------------------------

## Practice Questions — Basic Level

### Concept Questions

1.  What is a file path?

2.  What is the difference between a file and a directory?

3.  What is an absolute path?

4.  What is a relative path?

5.  Relative paths are relative to what in ordinary R file operations?

6.  What does `getwd()` return?

7.  What does `setwd()` do?

8.  Why can a hard-coded `setwd()` reduce portability?

9.  Is `setwd()` always wrong? Explain.

10. What does `file.exists()` return?

11. What does `dir.exists()` test?

12. What does `list.files()` do?

13. What does `recursive = TRUE` mean when listing or creating
    directories?

14. What is the purpose of `file.path()`?

15. What does `normalizePath()` help inspect?

16. What does `.` commonly represent in a path?

17. What does `..` commonly represent?

18. Why can Windows backslashes be problematic inside R strings?

19. Why can filename capitalization cause cross-platform problems?

20. What problem does the `here` package help solve?

21. Does `here()` eliminate the need to understand project structure?

22. Why should output paths be deliberate?

23. Why can spaces in filenames become inconvenient when R interacts
    with shell tools?

24. Why can Windows and WSL refer to the same file using different
    paths?

25. What should you check before debugging a data-import function?

------------------------------------------------------------------------

## Practical Exercises

### Exercise 1 — Inspect the Working Directory

Run:

``` r
getwd()
```

Then:

``` r
list.files()
```

Explain what you see.

------------------------------------------------------------------------

### Exercise 2 — Check Directories

Run:

``` r
dir.exists("data")
dir.exists("scripts")
dir.exists("figures")
```

------------------------------------------------------------------------

### Exercise 3 — Inspect Project Files

Run:

``` r
list.files(recursive = TRUE)
```

Then:

``` r
list.files(
  "data",
  recursive = TRUE,
  full.names = TRUE
)
```

------------------------------------------------------------------------

### Exercise 4 — Build a Path

Construct:

``` text
data/general/measurements.csv
```

using:

``` r
file.path()
```

Do not type the complete path as one string.

------------------------------------------------------------------------

### Exercise 5 — Check Before Reading

Store the path in:

``` r
general_file
```

Then test:

``` r
file.exists(general_file)
```

If it returns `FALSE`, diagnose the problem before attempting to read
the file.

------------------------------------------------------------------------

### Exercise 6 — Use `here`

Run:

``` r
here::here()
```

Then construct:

``` text
data/general/measurements.csv
```

using `here::here()`.

------------------------------------------------------------------------

### Exercise 7 — Genomics Path

Construct a path to:

``` text
data/genomics/example_gwas.tsv
```

Check whether it exists.

The exercise is about file handling, not GWAS.

------------------------------------------------------------------------

### Exercise 8 — Create an Output Directory

Using R, create:

``` text
outputs/checks/
```

only if it does not already exist.

Verify it with:

``` r
dir.exists()
```

------------------------------------------------------------------------

## Intermediate Exercises

### Exercise 9 — Diagnose the Broken Path

A collaborator sends:

``` r
setwd("C:\\Users\\Alice\\Desktop\\study")

data <- read.csv(
  "C:\\Users\\Alice\\Desktop\\study\\data\\samples.csv"
)
```

Rewrite the file-handling strategy so that it can work after the project
is moved to another computer.

Explain each change.

------------------------------------------------------------------------

### Exercise 10 — Cross-Platform Failure

A project contains:

``` text
data/genomics/Sample_01.tsv
```

The script uses:

``` r
file.exists("data/genomics/sample_01.tsv")
```

It works on one system but fails on another.

What is the likely problem?

How would you prevent it?

------------------------------------------------------------------------

### Exercise 11 — Windows and WSL

A Windows R session refers to:

``` text
C:/Research/project/data/variants.tsv
```

A command-line program running inside WSL cannot find that path.

Explain why.

What type of path would WSL normally require?

Do not hard-code a specific answer without checking the actual mount
configuration.

------------------------------------------------------------------------

## Challenge — Build a Path Diagnostic Script

Create:

``` text
04_check_project_paths.R
```

The script should:

1.  print the current working directory;
2.  print the root reported by `here::here()`;
3.  check whether `data/` exists;
4.  check whether `data/general/` exists;
5.  check whether `data/genomics/` exists;
6.  list files recursively under `data/`;
7.  construct the general teaching-data path;
8.  construct the genomics teaching-data path;
9.  test whether both files exist;
10. create `outputs/checks/` if necessary.

A possible starting structure is:

``` r
# ============================================================
# Script: 04_check_project_paths.R
# Project: Chapter 1 Practice Project
# Purpose: Inspect and validate important project paths
# Author: Sandeep Kumar Singh
# ============================================================

cat("Working directory:\n")
print(getwd())

cat("\nProject root:\n")
print(here::here())

# Continue...
```

Do not worry if your implementation differs.

The objective is to build a useful diagnostic script.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.6, you should be able to explain:

``` text
absolute path
relative path
working directory
project root
file
directory
.
..
```

You should be able to use:

``` r
getwd()
setwd()
file.exists()
dir.exists()
list.files()
dir.create()
file.path()
normalizePath()
here::here()
```

More importantly, you should be able to diagnose a file-not-found error
without randomly changing paths.

------------------------------------------------------------------------

## Key Takeaways

You can now:

- distinguish absolute and relative paths;
- explain how the working directory affects relative paths;
- understand why project-relative paths improve portability;
- use `getwd()` and understand `setwd()`;
- inspect files and directories before reading them;
- list project files programmatically;
- create directories;
- construct paths with `file.path()`;
- inspect resolved paths with `normalizePath()`;
- handle Windows path separators correctly;
- recognize case-sensitivity problems;
- understand basic Windows/WSL path differences;
- use `here::here()` for project-root-oriented paths;
- construct deliberate input and output paths;
- debug path failures systematically.

------------------------------------------------------------------------

## Repository Output from This Lesson

Your Chapter 1 code directory now grows to:

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    ├── 04_check_project_paths.R
    └── ...
```

Your continuing practice project remains:

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
├── data/
│   ├── general/
│   └── genomics/
├── scripts/
├── figures/
├── tables/
├── reports/
└── outputs/
```

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

2.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

3.  Müller K. `here`: A Simpler Way to Find Your Files. R package
    documentation.

### Scientific Computing and Reproducibility

4.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

5.  Noble WS. A quick guide to organizing computational biology
    projects. *PLoS Computational Biology*. 2009;5(7):e1000424.

6.  Sandve GK, Nekrutenko A, Taylor J, Hovig E. Ten simple rules for
    reproducible computational research. *PLoS Computational Biology*.
    2013;9(10):e1003285.

### Documentation Practice

For function behavior, consult R help directly:

``` r
?getwd
?list.files
?file.exists
?dir.create
?file.path
?normalizePath
```

For `here`, consult the current package documentation and vignettes.

Filesystem behavior can vary across operating systems, so cross-platform
code should be tested rather than assumed.

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.6 — Scripts, Console and Execution

We now know:

``` text
where the project is
```

and:

``` text
how R finds files inside it
```

The next question is:

> How should R code itself be organized and executed reliably?

Lesson 1.6 will go deeper than the introductory Source-versus-Console
discussion from Lesson 1.3.

We will cover:

- `.R` scripts;
- expressions and comments;
- execution order;
- running lines and blocks;
- `source()`;
- sourcing one script from another;
- `Rscript`;
- interactive versus non-interactive execution;
- command-line arguments at an introductory level;
- clean-session execution;
- script dependencies;
- exit status and errors conceptually;
- and designing scripts that can run reproducibly from beginning to end.

This will prepare us for functions, automation, pipelines, GitHub
Actions, and HPC workflows later in the course.

------------------------------------------------------------------------

## Lesson 1.6 — Scripts, Console and Execution

### Where This Lesson Fits

In Lesson 1.3, we introduced the difference between the **Source
editor** and the **Console**. In Lesson 1.4, we organized work into
projects. In Lesson 1.5, we learned how R finds files using working
directories, relative paths, and project-root-oriented paths.

We can now ask a deeper question:

> How should R code itself be written and executed so that the same
> script can run reliably from beginning to end?

This lesson moves beyond clicking **Run** in RStudio. We will examine
interactive execution, complete scripts, execution order, `source()`,
command-line execution with `Rscript`, clean-session testing, script
dependencies, introductory command-line arguments, and the difference
between code that works interactively and code that is genuinely
reproducible.

These ideas become essential later when R is used in automated
pipelines, GitHub Actions, Shiny applications, high-performance
computing, scheduled jobs, reproducible reports, and bioinformatics
workflows.

------------------------------------------------------------------------

### Learning Objectives

After completing this lesson, you should be able to:

- explain the difference between interactive and scripted execution;
- distinguish the Console from an `.R` script;
- explain why execution order matters;
- run single lines, selections, and complete scripts;
- use `source()` to execute another R script;
- understand dependencies created by sourced scripts;
- run an R script from the terminal using `Rscript`;
- explain the difference between RStudio and command-line execution;
- recognize scripts that depend on hidden session state;
- test a script from a clean R session;
- use introductory command-line arguments;
- understand the idea of failure and exit status in automated workflows;
- write a small script that can execute reproducibly from beginning to
  end.

------------------------------------------------------------------------

## 1. Interactive R Versus Scripted R

R is an interactive programming language.

You can enter:

``` r
2 + 2
```

in the Console and immediately obtain:

``` text
[1] 4
```

Interactive work is useful for:

- exploring;
- testing;
- inspecting;
- experimenting;
- debugging;
- learning.

However, interactive commands are not automatically a reproducible
computational record.

Suppose you perform 75 commands manually in the Console. A week later,
can you guarantee that you remember the exact commands, their order, all
parameter values, which objects existed beforehand, and which packages
had already been loaded?

Probably not.

Important work therefore belongs in scripts.

------------------------------------------------------------------------

## 2. What Is an R Script?

An R script is a plain-text file containing R code. It normally uses the
extension:

``` text
.R
```

For example:

``` text
analysis.R
```

A script might contain:

``` r
x <- 10
y <- 20

result <- x + y

print(result)
```

The file stores the computational instructions.

This makes the work:

- editable;
- reviewable;
- shareable;
- version-controllable;
- repeatable.

------------------------------------------------------------------------

## 3. Scripts Are Instructions, Not Stored Results

Consider:

``` r
x <- 10
y <- 20
z <- x + y
```

The script permanently stores these instructions. It does not
permanently store the in-memory objects `x`, `y`, and `z`.

Those objects are created when the script is executed.

``` text
script.R
   |
   | execute
   v
R session
   |
   ├── x
   ├── y
   └── z
```

Close the session and the in-memory state can disappear.

The script remains.

This is desirable: the analysis should be reconstructable from code.

------------------------------------------------------------------------

## 4. Execution Order Matters

R generally evaluates script expressions in order.

``` r
x <- 10
y <- 20
z <- x + y
```

works because:

``` text
create x
   ↓
create y
   ↓
calculate z
```

Now consider:

``` r
z <- x + y

x <- 10
y <- 20
```

From a clean session, the first line fails because `x` and `y` do not
yet exist.

A core principle follows:

> A script should create or obtain what it needs before using it.

------------------------------------------------------------------------

## 5. Hidden Session State Can Mask Bad Execution Order

Suppose yesterday you ran:

``` r
x <- 10
y <- 20
```

Now today’s script begins with:

``` r
z <- x + y
```

If `x` and `y` still exist in memory, the script appears to work.

Restart R and run the same script. It now fails.

The script was never self-contained.

This is why clean-session testing matters.

------------------------------------------------------------------------

## 6. Running One Line

In RStudio, place the cursor on:

``` r
x <- 10
```

and run the current line.

This is useful for learning and exploration.

But line-by-line execution can hide ordering problems when you manually
create objects in a sequence different from the script.

Therefore:

> Line-by-line execution is useful during development; complete-script
> execution is a stronger reproducibility test.

------------------------------------------------------------------------

## 7. Running a Selection

Suppose your script contains:

``` r
sample_a <- 15
sample_b <- 22
sample_c <- 19

sample_mean <- mean(
  c(sample_a, sample_b, sample_c)
)

print(sample_mean)
```

You can select several lines and execute them together.

This is useful for testing one logical block.

But selected execution still does not prove that the whole script runs
independently.

------------------------------------------------------------------------

## 8. Running the Complete Script

A stronger test is:

``` text
restart R
    ↓
run complete script
    ↓
does it succeed?
```

A complete script should ideally produce the intended result without
undocumented manual preparation.

------------------------------------------------------------------------

## 9. Comments in R Scripts

R comments begin with:

``` r
#
```

Example:

``` r
# Summarize sequencing depth before applying the QC threshold
mean_depth <- mean(sample_depth)
```

Comments are ignored during execution.

Good comments explain:

- why something is being done;
- non-obvious decisions;
- assumptions;
- unusual constraints.

Avoid comments that merely narrate obvious syntax.

------------------------------------------------------------------------

## 10. Blank Lines and Readability

R ignores ordinary blank lines.

Use them to separate logical steps:

``` r
input_file <- "data/input.csv"

data <- read.csv(input_file)

clean_data <- na.omit(data)

summary(clean_data)
```

Readable scripts are easier to debug and review.

------------------------------------------------------------------------

## 11. Script Sections

Longer scripts often benefit from visible sections:

``` r
# ============================================================
# 1. Setup
# ============================================================

# ============================================================
# 2. Import
# ============================================================

# ============================================================
# 3. Processing
# ============================================================

# ============================================================
# 4. Output
# ============================================================
```

This is a readability convention, not an R requirement.

Later, some long scripts should be replaced by reusable functions or
pipeline components rather than growing indefinitely.

------------------------------------------------------------------------

## 12. What Does `source()` Do?

`source()` asks R to execute code stored in another R script.

For example:

``` r
source("scripts/01_setup.R")
```

Conceptually:

``` text
current R session
      |
      | source(...)
      v
01_setup.R
      |
      | execute
      v
current R session changes
```

If `01_setup.R` creates:

``` r
threshold <- 0.05
```

then `threshold` may be available after the script is sourced.

------------------------------------------------------------------------

## 13. A Simple `source()` Example

Create:

``` text
scripts/helper_values.R
```

with:

``` r
sample_limit <- 100
qc_threshold <- 0.95
```

Then use:

``` r
source("scripts/helper_values.R")

print(sample_limit)
print(qc_threshold)
```

The second script now depends on the first.

This can be useful, but the dependency should be explicit.

------------------------------------------------------------------------

## 14. Sourcing One Script from Another

Suppose:

``` text
scripts/
├── 01_setup.R
├── 02_import.R
└── 03_analysis.R
```

`03_analysis.R` might begin:

``` r
source("scripts/01_setup.R")
source("scripts/02_import.R")
```

This can work in small projects.

However, the analysis can now depend on:

- objects created elsewhere;
- packages loaded elsewhere;
- directory changes made elsewhere;
- execution order.

As projects grow, reusable logic is often moved into functions and
explicit pipelines.

------------------------------------------------------------------------

## 15. Avoid Deep Chains of Sourcing

A fragile workflow might look like:

``` text
A.R sources B.R
B.R sources C.R
C.R sources D.R
D.R changes the working directory
```

Now someone running `A.R` may not understand why the environment
changes.

Prefer transparent dependencies.

If one script sources another, that relationship should be obvious and
justified.

------------------------------------------------------------------------

## 16. `source()` and Project Paths

Avoid:

``` r
source(
  "C:/Users/student/Desktop/project/scripts/setup.R"
)
```

Prefer:

``` r
source("scripts/setup.R")
```

or:

``` r
source(
  here::here(
    "scripts",
    "setup.R"
  )
)
```

The path principles from Lesson 1.5 apply to R scripts too.

------------------------------------------------------------------------

## 17. What Is `Rscript`?

`Rscript` is a command-line executable used to run R scripts
non-interactively.

From a terminal:

``` text
Rscript analysis.R
```

Conceptually:

``` text
terminal
   |
   | Rscript analysis.R
   v
new R process
   |
   | execute script
   v
output / files / exit
```

This differs from manually running lines in an existing RStudio session.

------------------------------------------------------------------------

## 18. Why `Rscript` Matters

Command-line execution matters because later workflows may run R without
RStudio.

Examples include:

- scheduled tasks;
- GitHub Actions;
- HPC jobs;
- Docker containers;
- pipelines;
- servers;
- cloud systems.

A script that can run with:

``` text
Rscript analysis.R
```

is much closer to automation-ready code.

------------------------------------------------------------------------

## 19. First Command-Line Script

Create:

``` text
scripts/05_execution_demo.R
```

with:

``` r
cat("Starting script...\n")

x <- 10
y <- 20

result <- x + y

cat("Result:", result, "\n")
cat("Script completed successfully.\n")
```

From a terminal opened at the project root:

``` text
Rscript scripts/05_execution_demo.R
```

Expected output:

``` text
Starting script...
Result: 30
Script completed successfully.
```

------------------------------------------------------------------------

## 20. `print()` Versus `cat()`

`print()` displays R objects:

``` r
print(result)
```

`cat()` can be convenient for simple progress messages:

``` r
cat("Result:", result, "\n")
```

For now:

- use `print()` when inspecting objects;
- use `cat()` for simple human-readable script messages.

------------------------------------------------------------------------

## 21. Interactive Versus Non-Interactive Sessions

R can check whether the current session is interactive:

``` r
interactive()
```

Inside an ordinary RStudio Console this often returns:

``` text
TRUE
```

A script executed through `Rscript` generally runs non-interactively.

This matters because code that waits for manual input can behave poorly
in automation.

------------------------------------------------------------------------

## 22. Why `readline()` Can Break Automation

Consider:

``` r
name <- readline("Enter your name: ")
```

This can be fine for an interactive teaching exercise.

But inside an automated nightly pipeline, the process may wait for a
human who is not there.

For automated or production-style workflows, important parameters are
usually supplied through:

- configuration files;
- command-line arguments;
- function arguments;
- structured metadata;
- environment variables where appropriate.

------------------------------------------------------------------------

## 23. Clean-Session Execution

A strong reproducibility check is:

1.  save the script;
2.  restart R;
3.  do not manually create objects;
4.  run the whole script;
5.  confirm that it succeeds.

This can expose:

- missing objects;
- missing package-loading steps;
- hidden working-directory assumptions;
- execution-order errors;
- undocumented dependencies.

------------------------------------------------------------------------

## 24. A Clean-Session Example

Fragile:

``` r
mean_depth <- mean(depth)
print(mean_depth)
```

This works only if `depth` already exists.

Self-contained teaching example:

``` r
depth <- c(30, 42, 28, 55, 37)

mean_depth <- mean(depth)

print(mean_depth)
```

Later, real data will usually be read from input files rather than
hard-coded.

------------------------------------------------------------------------

## 25. General Example — Complete Script

Create `scripts/05_execution_demo.R`:

``` r
# ============================================================
# Script: 05_execution_demo.R
# Project: Chapter 1 Practice Project
# Purpose: Demonstrate complete script execution
# Author: Sandeep Kumar Singh
# ============================================================

cat("Starting analysis...\n")

measurements <- c(
  12.4,
  15.1,
  11.8,
  16.3,
  14.7
)

mean_measurement <- mean(measurements)

cat(
  "Mean measurement:",
  mean_measurement,
  "\n"
)

cat("Analysis complete.\n")
```

Run it in RStudio, restart R and run it again, then run:

``` text
Rscript scripts/05_execution_demo.R
```

------------------------------------------------------------------------

## 26. Computational Biology Example — Sequencing Depth

Create:

``` text
scripts/06_depth_summary.R
```

with:

``` r
# ============================================================
# Script: 06_depth_summary.R
# Project: Chapter 1 Practice Project
# Purpose: Demonstrate reproducible execution with genomic-style data
# Author: Sandeep Kumar Singh
# ============================================================

cat("Starting sequencing-depth summary...\n")

sequencing_depth <- c(
  31,
  42,
  28,
  55,
  37
)

mean_depth <- mean(sequencing_depth)
minimum_depth <- min(sequencing_depth)
maximum_depth <- max(sequencing_depth)

cat("Mean depth:", mean_depth, "\n")
cat("Minimum depth:", minimum_depth, "\n")
cat("Maximum depth:", maximum_depth, "\n")

cat("Depth summary complete.\n")
```

The biological context is intentionally simple.

The lesson is execution, not sequencing analysis.

------------------------------------------------------------------------

## 27. Reading an Input File in a Complete Script

Suppose:

``` text
data/general/measurements.csv
```

exists.

A script might contain:

``` r
input_file <- here::here(
  "data",
  "general",
  "measurements.csv"
)

if (!file.exists(input_file)) {
  stop(
    "Input file not found: ",
    input_file
  )
}

measurements <- read.csv(input_file)

print(summary(measurements))
```

This performs two useful checks before analysis:

1.  construct the intended path;
2.  verify that the input exists.

`stop()` intentionally terminates execution with an error.

Formal error handling is taught later.

------------------------------------------------------------------------

## 28. Why Stopping Early Can Be Better

Suppose a workflow expects:

``` text
data/input.csv
```

but the file is missing.

A weak script may continue until a later step fails with a confusing
message.

A stronger script detects the problem immediately:

``` r
if (!file.exists(input_file)) {
  stop("Required input file is missing.")
}
```

This is the principle of **failing early**.

When a critical prerequisite is missing, a clear early failure is
usually better than producing unreliable downstream results.

------------------------------------------------------------------------

## 29. Script Dependencies

A script can depend on:

``` text
input files
packages
other scripts
environment variables
configuration files
external software
```

Good code makes important dependencies visible.

For example:

``` r
input_file <- here::here(
  "data",
  "general",
  "measurements.csv"
)
```

is clearer than assuming a hidden path state.

------------------------------------------------------------------------

## 30. Package Dependencies

Suppose a script requires `here`.

You might explicitly load it:

``` r
library(here)
```

or call:

``` r
here::here(...)
```

The latter visibly identifies the package providing the function.

Later we will treat dependencies more systematically with package
management and `renv`.

------------------------------------------------------------------------

## 31. Introductory Command-Line Arguments

A command-line script can receive arguments.

For example:

``` text
Rscript analysis.R input.csv output.csv
```

Inside the script:

``` r
args <- commandArgs(
  trailingOnly = TRUE
)
```

The resulting character vector might contain:

``` text
input.csv
output.csv
```

We introduce the mechanism here; validation comes later.

------------------------------------------------------------------------

## 32. A Small Argument Example

Create:

``` text
scripts/07_argument_demo.R
```

with:

``` r
args <- commandArgs(
  trailingOnly = TRUE
)

print(args)
```

Run:

``` text
Rscript scripts/07_argument_demo.R hello world
```

You may obtain:

``` text
[1] "hello" "world"
```

------------------------------------------------------------------------

## 33. Why Arguments Matter in Bioinformatics

Imagine a future script that processes one chromosome.

Instead of creating:

``` text
chr1_analysis.R
chr2_analysis.R
chr3_analysis.R
```

you could eventually reuse one script:

``` text
Rscript analyse_chr.R 1
Rscript analyse_chr.R 2
Rscript analyse_chr.R 3
```

This is closer to scalable scientific computing.

We are not building that pipeline yet.

------------------------------------------------------------------------

## 34. Standard Output, Errors and Exit Status

A command-line process can conceptually produce:

``` text
standard output
standard error
exit status
```

A successful script might print:

``` text
Analysis complete.
```

A failed script might produce:

``` text
Error: Input file missing.
```

Automated systems can detect whether execution succeeded.

Programs commonly use:

``` text
0 = success
```

while non-zero status values commonly indicate failure.

You do not need to manipulate exit codes manually at this stage.

The important point is that automation needs a clear distinction between
success and failure.

------------------------------------------------------------------------

## 35. Do Not Hide Errors Just to Keep a Script Running

Suppressing every error is dangerous.

If an input is invalid, continuing may produce results that look
legitimate but are scientifically unreliable.

A better principle is:

> Recover from expected problems when appropriate; fail clearly when
> continuing would make the result unreliable.

Formal error handling comes later.

------------------------------------------------------------------------

## 36. One Script Versus Many Scripts

A small analysis may reasonably fit in one script.

A 2,000-line script may become difficult to maintain.

Breaking work into:

``` text
01_import.R
02_clean.R
03_analyse.R
04_plot.R
```

can improve organization.

But splitting everything into dozens of tiny files can also create
unnecessary complexity.

Project structure should reflect meaningful responsibilities and
dependencies.

------------------------------------------------------------------------

## 37. Script Naming

Prefer names that communicate purpose and order.

Good:

``` text
01_import_data.R
02_clean_data.R
03_create_summary.R
04_generate_figures.R
```

Avoid:

``` text
script1.R
new.R
final.R
latest2.R
```

A filename is part of the project’s documentation.

------------------------------------------------------------------------

## 38. Script Headers

For this course, use a consistent header:

``` r
# ============================================================
# Script:
# Project:
# Purpose:
# Author:
# ============================================================
```

For example:

``` r
# ============================================================
# Script: 05_execution_demo.R
# Project: Chapter 1 Practice Project
# Purpose: Demonstrate complete script execution
# Author: Sandeep Kumar Singh
# ============================================================
```

Later, inputs, outputs, and dependencies can be documented where useful.

------------------------------------------------------------------------

## 39. Reproducible Script Checklist

Before considering a script complete, ask:

``` text
Does it define or read everything it needs?
Are important packages explicit?
Are paths project-oriented?
Does execution order make sense?
Does it work after restarting R?
Can it run from beginning to end?
Are required inputs checked?
Are outputs written deliberately?
Does failure produce a clear message?
```

This checklist will evolve throughout the course.

------------------------------------------------------------------------

## 40. Common Mistakes

### Mistake 1 — Running lines manually in a special order

The script appears to work but cannot reproduce itself.

### Mistake 2 — Depending on objects already in Environment

A clean session reveals the missing dependency.

### Mistake 3 — Sourcing scripts with personal absolute paths

This reduces portability.

### Mistake 4 — Creating deep chains of sourced scripts

Dependencies become difficult to inspect.

### Mistake 5 — Assuming RStudio and `Rscript` execution are identical in every detail

Session context can differ.

### Mistake 6 — Using interactive prompts in automated scripts

Execution may wait indefinitely.

### Mistake 7 — Ignoring missing input files until later

Fail early and clearly.

### Mistake 8 — Suppressing meaningful errors

Continuing with invalid inputs can be worse than stopping.

------------------------------------------------------------------------

## 41. Debugging Clinic

### Scenario 1 — Script works in RStudio but fails with `Rscript`

Possible causes include:

``` text
working-directory assumptions
hidden objects
interactive-only behavior
package differences
environment variables
relative-path problems
```

Inspect:

``` r
getwd()
R.version.string
.libPaths()
```

and verify input paths.

### Scenario 2 — `source()` reports file not found

Check:

``` r
file.exists("scripts/setup.R")
getwd()
list.files("scripts")
```

The problem may be a path issue rather than `source()`.

### Scenario 3 — Script fails after restarting R

The previous session contained something the script did not recreate.

Look for:

- missing objects;
- missing package loads;
- manual working-directory changes;
- unsaved code.

### Scenario 4 — Script writes output somewhere unexpected

Inspect the working directory and output path.

A path like:

``` r
write.csv(x, "result.csv")
```

uses the active path context.

### Scenario 5 — Argument script is run without arguments

If:

``` r
args <- commandArgs(trailingOnly = TRUE)
input_file <- args[1]
```

but no argument is supplied, `input_file` will not contain a valid
filename.

Argument validation will be introduced later.

------------------------------------------------------------------------

## 42. Performance Corner

The main performance lesson here is not CPU speed.

It is **execution efficiency and automation**.

A script that can run reliably with:

``` text
Rscript
```

can later be:

- scheduled;
- parallelized;
- submitted to HPC;
- wrapped in a pipeline;
- run across many datasets.

Reducing manual interaction can save far more time than micro-optimizing
trivial code.

------------------------------------------------------------------------

## 43. Expert Commentary

A major transition in R programming occurs when you stop asking:

> What lines should I run?

and start asking:

> What executable workflow should this script represent?

That change leads naturally to:

``` text
functions
tests
pipelines
packages
automation
```

A good analysis script is not simply a notebook of commands. It is an
explicit sequence of computational decisions.

------------------------------------------------------------------------

## 44. From the Reviewer’s Perspective

Imagine supplementary material containing:

``` text
Open script A.
Run lines 1–40.
Open script B.
Create object x manually.
Return to script A.
Run lines 80–120.
Ignore the warning.
```

This is difficult to reproduce.

Compare that with:

``` text
Rscript scripts/run_analysis.R
```

where the script:

- checks inputs;
- loads dependencies;
- performs the analysis;
- writes outputs;
- fails clearly if something essential is missing.

The second workflow is much easier to review and verify.

The long-term aim of this course is to move progressively toward that
standard.

------------------------------------------------------------------------

## Practice Questions — Basic Level

### Concept Questions

1.  What is an R script?
2.  What is the usual extension of an R script?
3.  What is the difference between code stored in a script and objects
    stored in memory?
4.  Why does execution order matter?
5.  How can hidden session state mask a bad script?
6.  What is the difference between running one line and running a
    complete script?
7.  What does `source()` do?
8.  What is a script dependency?
9.  Why can long chains of sourced scripts become difficult to maintain?
10. What does `Rscript` do?
11. Why is `Rscript` important for automation?
12. What is meant by interactive execution?
13. What does `interactive()` check?
14. Why can `readline()` be problematic in an automated workflow?
15. What is the purpose of `commandArgs(trailingOnly = TRUE)`?
16. What does it mean to fail early?
17. Why should missing critical inputs cause a clear error?
18. Why should important output locations be explicit?
19. Why should a script be tested after restarting R?
20. What does an exit status represent conceptually?

------------------------------------------------------------------------

## Practical Exercises

### Exercise 1 — Run a Complete Script

Create:

``` text
scripts/05_execution_demo.R
```

with:

``` r
x <- 20
y <- 30

result <- x + y

print(result)
```

Run it line by line, as a complete script in RStudio, and from a
terminal using `Rscript`.

### Exercise 2 — Expose Hidden State

Create:

``` r
result <- x + 10
print(result)
```

Manually create:

``` r
x <- 5
```

in Console. Run the script, restart R, and run it again. Explain the
result.

### Exercise 3 — Source Another Script

Create `scripts/helper_values.R`:

``` r
threshold <- 0.05
sample_limit <- 100
```

Then create `scripts/source_demo.R`:

``` r
source(
  here::here(
    "scripts",
    "helper_values.R"
  )
)

print(threshold)
print(sample_limit)
```

Run it from a clean session.

### Exercise 4 — Input Validation

Construct a path to:

``` text
data/general/measurements.csv
```

Check it with `file.exists()` and stop clearly if it is missing.

### Exercise 5 — General Script

Write a complete script that defines five numeric values, calculates
mean/minimum/maximum, prints all three, and runs after restarting R.

### Exercise 6 — Computational Biology Script

Use:

``` r
variant_p <- c(
  0.50,
  0.08,
  0.001,
  5e-08,
  0.42
)
```

Print:

- number of values;
- minimum P-value;
- maximum P-value.

Do not interpret the GWAS biology.

------------------------------------------------------------------------

## Intermediate Exercises

### Exercise 7 — Diagnose Script Dependencies

You receive:

``` r
source("setup.R")

result <- data$value * threshold

write.csv(
  result,
  "result.csv"
)
```

List everything this script appears to depend on. Which dependencies are
explicit? Which may be hidden?

### Exercise 8 — Convert an Interactive Workflow

A researcher currently:

``` text
opens RStudio
creates x manually
loads a package manually
changes directory manually
runs half of analysis.R
edits a threshold in Console
runs the rest
```

Redesign this conceptually as a reproducible script-based workflow.

### Exercise 9 — Run with an Argument

Create `scripts/07_argument_demo.R`:

``` r
args <- commandArgs(
  trailingOnly = TRUE
)

print(args)
```

Run:

``` text
Rscript scripts/07_argument_demo.R sample1 sample2
```

Explain what R receives.

------------------------------------------------------------------------

## Challenge — Build a Reproducible Execution Check

Create:

``` text
scripts/08_reproducible_execution_check.R
```

The script should:

1.  print a start message;
2.  print the R version;
3.  print the working directory;
4.  identify the project root with `here::here()`;
5.  construct a path to `data/general/measurements.csv`;
6.  check whether the file exists;
7.  stop with a clear error if it does not;
8.  read the file if it exists;
9.  print the number of rows;
10. write a small summary file to `outputs/execution_check.txt`;
11. print a completion message.

The script must run from a clean R session without relying on manually
created objects.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.7, you should be able to explain:

``` text
interactive execution
script execution
execution order
hidden state
source()
Rscript
script dependency
clean session
command-line argument
failure
exit status
```

You should also be able to:

- create a complete `.R` script;
- run it from RStudio;
- run it with `Rscript`;
- source another script;
- identify hidden dependencies;
- test after restarting R;
- check required input files before using them;
- stop clearly when a critical prerequisite is missing.

------------------------------------------------------------------------

## Key Takeaways

You can now:

- distinguish interactive exploration from reproducible script
  execution;
- understand why execution order matters;
- recognize hidden session state;
- execute complete R scripts;
- use `source()` deliberately;
- understand script dependencies;
- run scripts from the terminal with `Rscript`;
- understand introductory command-line arguments;
- test scripts from clean sessions;
- fail early when critical inputs are missing;
- understand why automation-ready code must minimize undocumented manual
  steps.

------------------------------------------------------------------------

## Repository Output from This Lesson

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    ├── 04_check_project_paths.R
    ├── 05_execution_demo.R
    ├── 06_depth_summary.R
    ├── 07_argument_demo.R
    ├── 08_reproducible_execution_check.R
    └── ...
```

Do not feel obligated to create every optional demonstration script
immediately. Preserve examples that are genuinely useful.

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

2.  R Core Team. *Rscript: Scripting Front-End for R*. R documentation.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

### Additional Reading

4.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

5.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

6.  Noble WS. A quick guide to organizing computational biology
    projects. *PLoS Computational Biology*. 2009;5(7):e1000424.

### Documentation Practice

Use R’s built-in documentation:

``` r
?source
?commandArgs
?interactive
?stop
?cat
```

For command-line behavior, consult current official R documentation
because platform-specific details can differ.

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.7 — Packages and Libraries

We now have:

``` text
a working R installation
+
an IDE
+
a project
+
reliable paths
+
reproducible script execution
```

The next major piece is package-level dependency management.

Lesson 1.7 will cover:

- what an R package contains;
- installed versus loaded packages;
- package libraries;
- `install.packages()`;
- `library()`;
- `requireNamespace()`;
- `packageVersion()`;
- `installed.packages()`;
- namespaces and `package::function`;
- updating and removing packages;
- CRAN versus Bioconductor installation;
- package conflicts;
- common installation failures;
- and making package requirements visible in a reproducible project.

This prepares us for `renv` later in Chapter 1.

------------------------------------------------------------------------

## Lesson 1.7 — Packages and Libraries

### Where This Lesson Fits

By this point, we have built several layers of a professional R
workflow:

``` text
R installation
      ↓
RStudio IDE
      ↓
R Project
      ↓
files and paths
      ↓
scripts and execution
```

But R becomes much more powerful when we use code written and
distributed by other developers.

That code is commonly organized into **packages**.

Packages provide tools for tasks such as:

- data manipulation;
- visualization;
- statistical modelling;
- genomic annotation;
- sequence analysis;
- GWAS;
- RNA-seq;
- interactive applications;
- parallel computing;
- reproducible workflows.

However, package terminology can be confusing for beginners.

For example:

``` r
install.packages("here")
library(here)
```

Why do we need both?

What does “install” mean?

What does “load” mean?

What is a **library**?

What is a **namespace**?

Why can this work:

``` r
here::here()
```

without first running:

``` r
library(here)
```

Why is Bioconductor installed differently from most CRAN packages?

This lesson builds the mental model required to answer those questions.

------------------------------------------------------------------------

### Learning Objectives

After completing this lesson, you should be able to:

- explain what an R package is;
- distinguish a package from a library;
- distinguish installing a package from loading it;
- explain why packages normally need to be installed only once per R
  installation/library environment but loaded again in new sessions when
  attached;
- inspect installed packages;
- inspect package-library locations;
- use `install.packages()`;
- use `library()`;
- understand `require()` and why it should not automatically replace
  `library()`;
- use `requireNamespace()` appropriately;
- use `package::function` notation;
- explain package namespaces conceptually;
- inspect package versions;
- update and remove packages;
- distinguish CRAN and Bioconductor installation workflows;
- recognize package conflicts;
- diagnose common package-installation and loading errors;
- make package dependencies more explicit in scripts.

------------------------------------------------------------------------

## 1. Why Packages Exist

Base R already contains many useful functions.

Examples include:

``` r
mean()
sum()
min()
max()
read.csv()
plot()
lm()
```

But no programming language can reasonably include every specialized
capability in its core installation.

R therefore has an extensible package ecosystem.

Conceptually:

``` text
R
│
├── Base R
│
├── recommended packages
│
└── additional packages
     ├── data science
     ├── visualization
     ├── statistics
     ├── genomics
     ├── reporting
     ├── databases
     └── many other domains
```

Packages allow R to grow without forcing every user to install every
possible tool.

------------------------------------------------------------------------

## 2. What Is an R Package?

An R package is a structured collection of resources designed to extend
R.

A package can contain:

``` text
R functions
documentation
datasets
compiled code
tests
vignettes
metadata
```

Not every package contains all of these components.

For example, a package may provide functions for:

- manipulating data;
- drawing plots;
- fitting models;
- working with genomic ranges;
- reading specialized file formats.

A package is therefore much more than “one function downloaded from the
internet.”

It is a structured unit of reusable R software.

------------------------------------------------------------------------

## 3. Package Versus Function

A package can contain many functions.

For example, conceptually:

``` text
package
│
├── function_a()
├── function_b()
├── function_c()
└── documentation
```

You install the **package**, not each function separately.

After the package is available, its exported functions can be used
according to the package’s interface.

------------------------------------------------------------------------

## 4. Package Versus Library

These two terms are frequently confused.

A **package** is the software unit.

A **library** is a directory where installed packages are stored.

Think of it this way:

``` text
Library
│
├── package A
├── package B
├── package C
└── package D
```

So:

> Packages live inside libraries.

This is different from the everyday meaning of “library” in some other
programming languages.

------------------------------------------------------------------------

## 5. Why `library()` Has That Name

The function:

``` r
library(here)
```

does **not** install `here`.

It finds the installed package in an R library and attaches it for use
in the current session.

The terminology can initially feel backwards:

``` text
R library = directory containing packages

library(package_name)
           =
attach an installed package
```

Once this distinction is clear, many package-related errors become
easier to diagnose.

------------------------------------------------------------------------

## 6. Installing Versus Loading

This is one of the most important distinctions in early R.

### Installing

``` r
install.packages("here")
```

means:

> Obtain and install the package into an R package library.

### Loading/attaching for the current session

``` r
library(here)
```

means:

> Make the installed package available on the search path for convenient
> use in this R session.

Conceptually:

``` text
Internet / repository
        |
        | install
        v
R package library on disk
        |
        | library()
        v
current R session
```

------------------------------------------------------------------------

## 7. Installation Usually Persists Across Sessions

Suppose you install:

``` r
install.packages("here")
```

Then restart R.

Normally, you do **not** need to install `here` again.

The package remains installed on disk unless:

- you remove it;
- you change R installations or library locations;
- the environment is rebuilt;
- the library is deleted;
- another environment-management strategy is being used.

But if your new R session needs the package attached, you may run:

``` r
library(here)
```

again.

A useful beginner rule is:

``` text
install occasionally
load/attach per session when needed
```

------------------------------------------------------------------------

## 8. Do Not Put `install.packages()` in Every Analysis Script

A common beginner script contains:

``` r
install.packages("here")
library(here)

install.packages("ggplot2")
library(ggplot2)
```

every time it runs.

This is usually poor project practice.

Why?

Because installation:

- modifies the software environment;
- may require internet access;
- may unexpectedly install a newer version;
- can be slow;
- may fail because of system dependencies;
- makes execution less predictable.

Analysis scripts should usually **use** declared dependencies, not
reinstall them on every run.

Later, `renv` will give us a much better project-level dependency
workflow.

------------------------------------------------------------------------

## 9. Installing a CRAN Package

A common installation command is:

``` r
install.packages("here")
```

R normally retrieves the package from a configured CRAN repository or
mirror.

Multiple packages can be requested:

``` r
install.packages(
  c(
    "here",
    "jsonlite"
  )
)
```

At this stage, use package installation deliberately rather than
installing large collections “just in case.”

------------------------------------------------------------------------

## 10. Loading a Package

After installation:

``` r
library(here)
```

You can then use exported functions conveniently.

For example:

``` r
here()
```

However, there is another important approach:

``` r
here::here()
```

This leads us to namespaces.

------------------------------------------------------------------------

## 11. The `::` Operator

The syntax:

``` r
package::function
```

means:

> Use this exported function from this specific package.

For example:

``` r
here::here()
```

explicitly says:

``` text
package = here
function = here
```

Another example:

``` r
utils::head(iris)
```

This makes the origin of a function explicit.

------------------------------------------------------------------------

## 12. Why `package::function` Is Useful

Suppose two packages both provide a function called:

``` text
filter()
```

If you simply call:

``` r
filter(...)
```

which function should R use?

The answer can depend on which packages are attached and in what order.

But:

``` r
dplyr::filter(...)
```

explicitly identifies the intended function.

This can improve:

- readability;
- dependency transparency;
- conflict avoidance.

------------------------------------------------------------------------

## 13. Does `package::function` Require `library()`?

Usually, if a package is installed, you can call an exported function
using:

``` r
package::function()
```

without first attaching the package with:

``` r
library(package)
```

For example:

``` r
here::here()
```

does not require:

``` r
library(here)
```

first.

The package still needs to be installed and loadable.

This distinction is useful in scripts where only a few functions are
required.

------------------------------------------------------------------------

## 14. What Is a Namespace?

A package namespace controls which objects belong to the package and
which of them are exposed for use.

Conceptually:

``` text
Package namespace
│
├── exported function A
├── exported function B
├── internal helper C
└── internal helper D
```

Users normally interact with the package’s **exported interface**.

The namespace helps packages:

- organize their own functions;
- import functions from dependencies;
- export selected functions;
- reduce accidental naming collisions.

We will study namespaces much more deeply during package development.

------------------------------------------------------------------------

## 15. `::` Versus `:::`

You may occasionally encounter:

``` r
package:::internal_function
```

Triple colon can access non-exported package objects.

This is usually **not** appropriate for ordinary analysis code.

Why?

Internal functions are not part of the package’s stable public interface
and can change without warning.

Prefer:

``` r
package::exported_function()
```

unless you have a specific development or debugging reason to inspect
internals.

------------------------------------------------------------------------

## 16. Inspecting Package Libraries with `.libPaths()`

Run:

``` r
.libPaths()
```

    ## [1] "C:/Program Files/R/R-4.5.3/library"         
    ## [2] "C:/Users/hp/AppData/Local/R/win-library/4.5"

This shows the directories R searches for installed packages.

You may see one or several locations.

Conceptually:

``` text
.libPaths()
   |
   ├── user library
   ├── system library
   └── other configured library
```

When R tries to load a package, these locations matter.

------------------------------------------------------------------------

## 17. Why Multiple Libraries Exist

Different libraries can serve different purposes.

For example:

``` text
system-level packages
user-installed packages
project-specific package environments
```

Permissions can also matter.

A user may not have permission to install packages into a system
library, so R may use a personal library instead.

Later, `renv` introduces project-local dependency management.

------------------------------------------------------------------------

## 18. Inspecting Installed Packages

R can inspect installed packages:

``` r
installed.packages()
```

This returns a matrix containing substantial package metadata.

For a simpler check:

``` r
"here" %in% rownames(
  installed.packages()
)
```

This returns `TRUE` if R sees `here` as installed in the active library
paths.

------------------------------------------------------------------------

## 19. `find.package()`

If a package is installed, you can ask where it lives:

``` r
find.package("here")
```

This returns the installation directory.

This is useful when diagnosing which library contains a package.

------------------------------------------------------------------------

## 20. Checking a Package Version

Use:

``` r
packageVersion("here")
```

A result might look like:

``` text
1.0.1
```

The exact version depends on your environment.

Version information matters because package behavior can change over
time.

A script that worked with one package version may behave differently
after a major update.

------------------------------------------------------------------------

## 21. Inspecting Loaded and Attached Packages

Run:

``` r
search()
```

    ## [1] ".GlobalEnv"        "package:stats"     "package:graphics" 
    ## [4] "package:grDevices" "package:utils"     "package:datasets" 
    ## [7] "package:methods"   "Autoloads"         "package:base"

This displays the current search path.

You may see entries such as:

``` text
".GlobalEnv"
"package:stats"
"package:graphics"
"package:utils"
"package:datasets"
"package:methods"
"Autoloads"
"package:base"
```

If you attach another package using `library()`, it normally appears on
this search path.

This is important for understanding name lookup and conflicts.

------------------------------------------------------------------------

## 22. `sessionInfo()` Revisited

We introduced:

``` r
sessionInfo()
```

earlier.

Now it becomes even more meaningful.

It reports information such as:

- R version;
- platform;
- locale;
- attached packages;
- loaded namespaces.

Run:

``` r
sessionInfo()
```

    ## R version 4.5.3 (2026-03-11 ucrt)
    ## Platform: x86_64-w64-mingw32/x64
    ## Running under: Windows 11 x64 (build 26200)
    ## 
    ## Matrix products: default
    ##   LAPACK version 3.12.1
    ## 
    ## locale:
    ## [1] LC_COLLATE=English_United States.utf8 
    ## [2] LC_CTYPE=English_United States.utf8   
    ## [3] LC_MONETARY=English_United States.utf8
    ## [4] LC_NUMERIC=C                          
    ## [5] LC_TIME=English_United States.utf8    
    ## 
    ## time zone: Asia/Calcutta
    ## tzcode source: internal
    ## 
    ## attached base packages:
    ## [1] stats     graphics  grDevices utils     datasets  methods   base     
    ## 
    ## loaded via a namespace (and not attached):
    ##  [1] compiler_4.5.3    fastmap_1.2.0     cli_3.6.6         tools_4.5.3      
    ##  [5] htmltools_0.5.9   rstudioapi_0.19.0 yaml_2.3.12       rmarkdown_2.31   
    ##  [9] knitr_1.51        xfun_0.57         digest_0.6.39     rlang_1.2.0      
    ## [13] evaluate_1.0.5

This is valuable when documenting or debugging a computational
environment.

------------------------------------------------------------------------

## 23. `library()` Versus `require()`

You may see:

``` r
library(here)
```

and:

``` r
require(here)
```

They are related but not identical in typical use.

`library()` generally raises an error when the requested package cannot
be loaded.

`require()` returns a logical value indicating whether loading succeeded
and is often used when code intentionally wants to test availability.

For ordinary analysis scripts, prefer:

``` r
library(package)
```

when the package is required.

Do not use `require()` merely because it sounds softer.

------------------------------------------------------------------------

## 24. `requireNamespace()`

`requireNamespace()` checks whether a package namespace can be loaded
without attaching the package to the search path.

Example:

``` r
requireNamespace(
  "here",
  quietly = TRUE
)
```

This returns:

``` text
TRUE
```

or:

``` text
FALSE
```

A common pattern is:

``` r
if (!requireNamespace("here", quietly = TRUE)) {
  stop(
    "Package 'here' is required. ",
    "Please install it before running this script."
  )
}
```

Then use:

``` r
here::here()
```

This makes the dependency explicit without attaching the package.

------------------------------------------------------------------------

## 25. `library()` or `package::function()`?

Both can be appropriate.

### Style A — Attach the package

``` r
library(ggplot2)

ggplot(...)
```

This is convenient when a script uses a package extensively.

### Style B — Explicit namespace

``` r
ggplot2::ggplot(...)
```

This is useful when:

- only a few functions are used;
- function origin should be obvious;
- conflicts are possible.

There is no need to turn this into a rigid rule.

Use a consistent style that keeps dependencies clear.

------------------------------------------------------------------------

## 26. What Is CRAN?

CRAN stands for:

**Comprehensive R Archive Network**

CRAN is the main repository for a large portion of the R package
ecosystem.

A typical CRAN installation uses:

``` r
install.packages("package_name")
```

CRAN also provides:

- R distributions;
- package source archives;
- package documentation;
- package checks;
- repository infrastructure.

CRAN is not a single R package.

------------------------------------------------------------------------

## 27. What Is Bioconductor?

Bioconductor is a major open-source software ecosystem focused on the
analysis and comprehension of high-throughput biological data.

It is especially important in:

- genomics;
- transcriptomics;
- annotation;
- genomic ranges;
- sequence analysis;
- differential expression;
- biological data structures.

Bioconductor is built around R but has its own coordinated
package-release ecosystem.

------------------------------------------------------------------------

## 28. Installing Bioconductor Packages

Bioconductor packages are commonly managed using `BiocManager`.

If needed:

``` r
install.packages("BiocManager")
```

Then a Bioconductor package can be installed with:

``` r
BiocManager::install("GenomicRanges")
```

This is preferable to assuming every biological package should be
installed with:

``` r
install.packages(...)
```

------------------------------------------------------------------------

## 29. Why Bioconductor Uses `BiocManager`

Bioconductor coordinates package versions with compatible versions of R
and the Bioconductor release.

`BiocManager` helps manage that compatibility.

This matters because biological analysis frequently depends on
interconnected packages.

The important mental model is:

``` text
CRAN package
   ↓
install.packages()

Bioconductor package
   ↓
BiocManager::install()
```

There are exceptions and additional repository types, but this is the
appropriate foundation.

------------------------------------------------------------------------

## 30. Checking the Bioconductor Environment

Once `BiocManager` is installed, you can inspect the Bioconductor
version:

``` r
BiocManager::version()
```

You can also use:

``` r
BiocManager::valid()
```

to assess whether installed packages are consistent with the expected
Bioconductor environment.

Do not worry about interpreting every detail yet.

We will revisit Bioconductor extensively later.

------------------------------------------------------------------------

## 31. A Computational Biology Example

Suppose a future analysis needs:

``` text
GenomicRanges
```

The installation step might be:

``` r
BiocManager::install(
  "GenomicRanges"
)
```

Then a script could attach it:

``` r
library(GenomicRanges)
```

or use exported functions explicitly where practical.

At this stage, we are learning package management, not genomic-range
analysis.

------------------------------------------------------------------------

## 32. Package Dependencies

Packages can depend on other packages.

Conceptually:

``` text
your script
    |
    v
package A
    |
    +---- package B
    |
    +---- package C
```

When installing package A, R may also need to install its dependencies.

This explains why:

``` r
install.packages("some_package")
```

can result in several packages being downloaded.

------------------------------------------------------------------------

## 33. System Dependencies

Not every package dependency is another R package.

Some packages require external software or system libraries.

Examples may include:

``` text
C/C++ compilers
Fortran compilers
SSL libraries
XML libraries
image libraries
database client libraries
```

Therefore, a package installation failure does not necessarily mean that
the R package itself is defective.

The missing component may exist outside R.

This becomes particularly relevant on Linux and in bioinformatics
environments.

------------------------------------------------------------------------

## 34. Binary Versus Source Packages

Depending on the operating system, repository, package, and R version, a
package may be installed from:

``` text
binary distribution
```

or:

``` text
source code
```

Installing from source may require compilation tools.

For example:

- Windows may require appropriate R build tools for some source
  installations;
- macOS may require relevant developer/compiler tooling;
- Linux often requires compilers and system development libraries.

Do not install build tools unnecessarily. First read the actual
installation error.

------------------------------------------------------------------------

## 35. Updating Packages

CRAN packages can be checked for updates using:

``` r
old.packages()
```

and updated using:

``` r
update.packages()
```

However, blindly updating every package in the middle of an important
analysis can change the computational environment.

A more reproducible strategy is to control project dependencies
explicitly.

That is one reason `renv` will be important later in Chapter 1.

------------------------------------------------------------------------

## 36. Removing a Package

A package can be removed using:

``` r
remove.packages("package_name")
```

Be deliberate.

Other packages or projects may depend on it.

------------------------------------------------------------------------

## 37. Detaching a Package Is Not the Same as Removing It

Suppose:

``` r
library(here)
```

attached the package.

You may detach it from the current session using a command such as:

``` r
detach(
  "package:here",
  unload = TRUE
)
```

This does not uninstall the package from disk.

Compare:

``` text
detach
=
change current session

remove.packages()
=
remove installed package from library
```

------------------------------------------------------------------------

## 38. Package Conflicts

Suppose two attached packages provide a function with the same name.

R may report that one function masks another.

Conceptually:

``` text
Package A: filter()
Package B: filter()
```

If both are attached, a plain call:

``` r
filter(...)
```

may depend on search-path order.

Explicit namespace syntax removes ambiguity:

``` r
dplyr::filter(...)
```

or another intended package’s implementation.

------------------------------------------------------------------------

## 39. What Does “Masked” Mean?

Suppose:

``` text
package A
```

and:

``` text
package B
```

both expose:

``` text
select()
```

If package B appears earlier on the search path, its `select()` may be
found first.

The other function still exists.

It has not been deleted.

Its name is simply being masked in unqualified lookup.

You can still call the intended function explicitly:

``` r
packageA::select(...)
```

------------------------------------------------------------------------

## 40. Inspecting Where a Function Comes From

If you are unsure where a name is found, R provides several inspection
tools.

For example:

``` r
find("filter")
```

You can also inspect help:

``` r
?filter
```

or explicitly request package help:

``` r
?stats::filter
```

Learning to ask “which function am I actually calling?” is an important
debugging habit.

------------------------------------------------------------------------

## 41. Package Startup Messages

Some packages print messages when attached.

These may describe:

- masked functions;
- package versions;
- important changes;
- citation information.

Do not automatically treat every startup message as an error.

Learn to distinguish:

``` text
message
warning
error
```

Formal condition handling comes later.

------------------------------------------------------------------------

## 42. Common Installation Error: Package Not Available

You may see a message indicating that a package is not available for
your version of R.

Possible reasons include:

- package name is misspelled;
- package is not on CRAN;
- package has been archived;
- package requires a different R version;
- package belongs to Bioconductor;
- repository configuration is wrong.

Do not immediately search for random installation commands.

First identify where the package is officially distributed.

------------------------------------------------------------------------

## 43. Common Loading Error: There Is No Package Called…

Suppose:

``` r
library(examplePackage)
```

returns an error saying the package is not installed.

This usually means:

``` text
R searched its active library paths
        ↓
package not found
```

Check:

``` r
.libPaths()
```

and:

``` r
"examplePackage" %in%
  rownames(installed.packages())
```

Then determine whether installation is required.

------------------------------------------------------------------------

## 44. Common Error: Package Installed but Not Found

This can happen when:

- multiple R versions are installed;
- the package was installed into another library;
- `.libPaths()` changed;
- a project-specific environment is active;
- permissions or library configuration differ.

Check:

``` r
R.version.string
.libPaths()
```

and, where appropriate:

``` r
find.package(
  "package_name"
)
```

------------------------------------------------------------------------

## 45. Different R Versions Can Have Different Package Libraries

Suppose you upgrade:

``` text
R 4.x
```

to a newer major/minor R release.

Your new R installation may use a different package-library directory.

You may then discover that packages previously installed for another R
version are not available in the new environment.

This is not necessarily data loss.

The new R installation may simply be looking in a different library.

Always inspect:

``` r
R.version.string
.libPaths()
```

before reinstalling everything blindly.

------------------------------------------------------------------------

## 46. Package Installation Should Be Reproducible Too

Consider two collaborators.

Researcher A has:

``` text
package X version 1
```

Researcher B has:

``` text
package X version 2
```

If package behavior changed, identical scripts may not behave
identically.

Therefore reproducibility requires more than:

``` text
same R code
```

It also involves:

``` text
R version
package versions
system environment
input data
```

This leads directly toward `renv`.

------------------------------------------------------------------------

## 47. General Example — Inspecting a Package

Use a package already installed in your environment, such as `stats`.

Try:

``` r
packageVersion("stats")
```

    ## [1] '4.5.3'

Then:

``` r
find.package("stats")
```

    ## [1] "C:/PROGRA~1/R/R-45~1.3/library/stats"

Inspect help for a function:

``` r
?stats::median
```

And use:

``` r
stats::median(
  c(10, 12, 15, 18, 100)
)
```

    ## [1] 15

The purpose is to connect:

``` text
package
version
location
function
namespace
```

------------------------------------------------------------------------

## 48. General Example — `here`

If `here` is installed:

``` r
packageVersion("here")
```

Then:

``` r
here::here()
```

Compare with:

``` r
library(here)
here()
```

Both approaches can work, but they express dependencies differently.

------------------------------------------------------------------------

## 49. Computational Biology Example — Bioconductor Availability

If `BiocManager` is installed:

``` r
BiocManager::version()
```

You can check whether a future package is installed:

``` r
requireNamespace(
  "GenomicRanges",
  quietly = TRUE
)
```

This does not require us to perform genomic-range analysis.

It simply tests whether the dependency is available.

------------------------------------------------------------------------

## 50. Making Dependencies Explicit at the Top of a Script

A script might begin:

``` r
# ============================================================
# Dependencies
# ============================================================

library(here)
```

or:

``` r
# ============================================================
# Dependency checks
# ============================================================

if (!requireNamespace("here", quietly = TRUE)) {
  stop(
    "Package 'here' is required. ",
    "Install it before running this script."
  )
}
```

Then later:

``` r
project_root <- here::here()
```

The dependency is now visible rather than hidden.

------------------------------------------------------------------------

## 51. Should a Script Automatically Install Missing Packages?

You will often see:

``` r
if (!requireNamespace("here", quietly = TRUE)) {
  install.packages("here")
}
```

This can be convenient in teaching scripts or controlled setup scripts.

But for serious reproducible analysis, automatically modifying the
package environment during execution is often undesirable.

Why?

Because the script may:

- require internet access;
- install an unexpected version;
- modify the user’s environment;
- fail because of permissions;
- produce different environments at different times.

A better long-term design separates:

``` text
environment setup
```

from:

``` text
analysis execution
```

Later, `renv` will formalize this.

------------------------------------------------------------------------

## 52. Setup Script Versus Analysis Script

A project may eventually distinguish:

``` text
setup
```

from:

``` text
analysis
```

For example:

``` text
scripts/
├── 00_setup.R
├── 01_import.R
├── 02_clean.R
└── 03_analysis.R
```

However, do not let `00_setup.R` become a dumping ground containing
hidden state.

The long-term goal is explicit, reproducible dependency management.

------------------------------------------------------------------------

## 53. Common Mistakes

### Mistake 1 — Confusing installation with loading

``` r
install.packages("here")
```

does not mean the same thing as:

``` r
library(here)
```

------------------------------------------------------------------------

### Mistake 2 — Installing packages every time a script runs

This unnecessarily modifies the environment.

------------------------------------------------------------------------

### Mistake 3 — Calling `library()` before installation and assuming R will install automatically

`library()` does not normally install a missing package.

------------------------------------------------------------------------

### Mistake 4 — Assuming every package is on CRAN

Many important computational-biology packages are distributed through
Bioconductor.

------------------------------------------------------------------------

### Mistake 5 — Ignoring the R version

Package compatibility and library locations can depend on the R version.

------------------------------------------------------------------------

### Mistake 6 — Treating every package startup message as an error

Some are informational.

------------------------------------------------------------------------

### Mistake 7 — Ignoring function conflicts

A function name may refer to a different attached package than expected.

------------------------------------------------------------------------

### Mistake 8 — Using `:::` routinely

Internal package functions are not stable public interfaces.

------------------------------------------------------------------------

### Mistake 9 — Updating packages during an important analysis without considering reproducibility

An update can change behavior.

------------------------------------------------------------------------

### Mistake 10 — Assuming an installation error always means the R package is broken

The problem may be a compiler, system library, permissions issue,
repository mismatch, or incompatible R version.

------------------------------------------------------------------------

## 54. Debugging Clinic

### Scenario 1 — `library()` says package is missing

Check:

``` r
R.version.string
.libPaths()
```

Then:

``` r
"packageName" %in%
  rownames(installed.packages())
```

If it is genuinely absent, identify its official repository before
installing.

------------------------------------------------------------------------

### Scenario 2 — Package worked before an R upgrade

Inspect:

``` r
R.version.string
.libPaths()
```

The new R version may be using a different library.

------------------------------------------------------------------------

### Scenario 3 — A Bioconductor package fails with `install.packages()`

First confirm whether the package is officially distributed through
Bioconductor.

If so, use the supported Bioconductor installation workflow:

``` r
BiocManager::install("PackageName")
```

------------------------------------------------------------------------

### Scenario 4 — Function behaves differently after loading another package

Inspect the search path:

``` r
search()
```

Then inspect:

``` r
find("function_name")
```

Use explicit namespace syntax where necessary.

------------------------------------------------------------------------

### Scenario 5 — Package installation requests compilation tools

Read the complete error.

Determine whether:

- a binary package is available;
- source compilation is actually required;
- a compiler is missing;
- a system dependency is missing.

Do not install random software without identifying the requirement.

------------------------------------------------------------------------

### Scenario 6 — Script works on one machine but package versions differ

Capture:

``` r
sessionInfo()
```

Compare:

``` text
R version
package versions
platform
```

This is an environment-reproducibility issue.

------------------------------------------------------------------------

## 55. Performance Corner

Loading dozens of packages “just in case” is rarely good practice.

It can:

- increase startup time;
- increase namespace conflicts;
- make dependencies harder to understand;
- load unnecessary code.

Use the packages your script actually needs.

For very small usage, explicit calls such as:

``` r
package::function()
```

can keep dependencies particularly clear.

Performance optimization is not the primary concern here; clarity and
reproducibility are.

------------------------------------------------------------------------

## 56. Expert Commentary

A beginner often thinks:

> My analysis is my R script.

A more mature view is:

``` text
analysis
=
code
+
data
+
R version
+
package dependencies
+
package versions
+
system environment
```

The script is central, but it does not exist in isolation.

This is why professional R programming eventually requires environment
management.

Packages are our first major step toward understanding that environment.

------------------------------------------------------------------------

## 57. From the Reviewer’s Perspective

Suppose a manuscript provides:

``` r
library(packageA)
library(packageB)
library(packageC)
```

but gives no information about versions.

A reviewer can run the code today, but may not be able to reconstruct
the original software environment later.

Now imagine the project also records:

``` text
R version
package versions
dependency lockfile
```

The computational environment becomes much easier to reconstruct.

This is one reason reproducibility is not merely about sharing scripts.

------------------------------------------------------------------------

## Practice Questions — Basic Level

### Concept Questions

1.  What is an R package?

2.  What types of resources can an R package contain?

3.  What is the difference between a package and a function?

4.  What is an R package library?

5.  What does `install.packages()` do?

6.  What does `library()` do?

7.  Why is package installation different from package loading?

8.  Does restarting R normally uninstall packages?

9.  Why should `install.packages()` usually not appear in every analysis
    script?

10. What does `.libPaths()` show?

11. What does `installed.packages()` inspect?

12. What does `packageVersion()` return?

13. What does `find.package()` help determine?

14. What is the purpose of the `::` operator?

15. What is a package namespace?

16. Why is `package::function()` useful when function names conflict?

17. Why should `:::` generally be avoided in ordinary analysis code?

18. What is CRAN?

19. What is Bioconductor?

20. Why are many computational-biology packages installed using
    `BiocManager::install()`?

21. What does `requireNamespace()` do?

22. What is the difference between `requireNamespace()` and attaching a
    package with `library()`?

23. What does `search()` show?

24. What does it mean when one package masks a function from another?

25. Why do package versions matter for reproducibility?

------------------------------------------------------------------------

## Practical Exercises

### Exercise 1 — Inspect Your Libraries

Run:

``` r
.libPaths()
```

How many package-library locations does your R installation currently
use?

------------------------------------------------------------------------

### Exercise 2 — Inspect Installed Packages

Run:

``` r
installed <- installed.packages()

dim(installed)
```

Then inspect:

``` r
head(
  rownames(installed)
)
```

Do not try to understand every metadata column yet.

------------------------------------------------------------------------

### Exercise 3 — Check Package Availability

Test:

``` r
requireNamespace(
  "here",
  quietly = TRUE
)
```

What does the result mean?

------------------------------------------------------------------------

### Exercise 4 — Inspect a Package

If `here` is installed:

``` r
packageVersion("here")
find.package("here")
```

Record:

- package version;
- package installation location.

------------------------------------------------------------------------

### Exercise 5 — Namespace Use

Compare:

``` r
library(here)
here()
```

with:

``` r
here::here()
```

Explain the difference in how the dependency is expressed.

------------------------------------------------------------------------

### Exercise 6 — Search Path

Run:

``` r
search()
```

Attach an installed package.

Run:

``` r
search()
```

again.

What changed?

------------------------------------------------------------------------

### Exercise 7 — Session Information

Run:

``` r
sessionInfo()
```

Identify:

- R version;
- operating platform;
- attached packages;
- loaded namespaces.

------------------------------------------------------------------------

### Exercise 8 — Bioconductor Check

If `BiocManager` is installed:

``` r
BiocManager::version()
```

Then:

``` r
requireNamespace(
  "GenomicRanges",
  quietly = TRUE
)
```

Do not install `GenomicRanges` merely to make this exercise return
`TRUE`.

The purpose is to inspect the environment.

------------------------------------------------------------------------

## Intermediate Exercises

### Exercise 9 — Diagnose the Script

A researcher writes:

``` r
install.packages("here")
library(here)

input <- here("data", "input.csv")
```

inside an analysis script that runs every morning.

Identify the design problem.

How would you separate environment setup from analysis execution?

------------------------------------------------------------------------

### Exercise 10 — Package Conflict

Suppose two attached packages provide:

``` text
select()
```

Explain:

1.  why `select(...)` can become ambiguous;
2.  how the search path affects function lookup;
3.  how `package::select(...)` resolves the ambiguity.

------------------------------------------------------------------------

### Exercise 11 — Different Computer, Different Result

Two researchers use the same R script and data but obtain slightly
different output.

Researcher A uses an older R version and older package versions.

Researcher B uses newer versions.

What information should they compare before assuming that the analytical
logic is wrong?

------------------------------------------------------------------------

## Challenge — Build a Package Environment Diagnostic Script

Create:

``` text
scripts/09_check_package_environment.R
```

The script should:

1.  print the R version;
2.  print `.libPaths()`;
3.  check whether `here` is installed;
4.  print the installed `here` version if available;
5.  print the installation location of `here`;
6.  check whether `BiocManager` is available;
7.  print the Bioconductor version if possible;
8.  print `sessionInfo()`;
9.  stop with a clear message only if a package that is genuinely
    required for the script is missing.

A possible starting point:

``` r
# ============================================================
# Script: 09_check_package_environment.R
# Project: Chapter 1 Practice Project
# Purpose: Inspect the R package environment
# Author: Sandeep Kumar Singh
# ============================================================

cat("R version:\n")
print(R.version.string)

cat("\nPackage libraries:\n")
print(.libPaths())

has_here <- requireNamespace(
  "here",
  quietly = TRUE
)

cat("\n'here' available:", has_here, "\n")

# Continue...
```

The goal is not merely to make the script run.

The goal is to make the software environment visible.

------------------------------------------------------------------------

## Lesson Competency Check

Before moving to Lesson 1.8, you should be able to explain:

``` text
package
library
installation
attachment
namespace
CRAN
Bioconductor
dependency
package version
function masking
```

You should also be comfortable using:

``` r
install.packages()
library()
requireNamespace()
packageVersion()
installed.packages()
find.package()
.libPaths()
search()
sessionInfo()
package::function()
BiocManager::install()
```

Most importantly, you should understand that:

``` text
installing
```

and:

``` text
using
```

a package are different operations.

------------------------------------------------------------------------

## Key Takeaways

You can now:

- explain what R packages contain;
- distinguish packages from package libraries;
- distinguish installation from attachment;
- inspect package-library locations;
- inspect installed packages and versions;
- use `library()` deliberately;
- use `package::function()` to make function origin explicit;
- understand namespaces conceptually;
- use `requireNamespace()` for dependency checks;
- distinguish CRAN and Bioconductor installation workflows;
- recognize package dependencies and system dependencies;
- diagnose common installation and loading failures;
- understand function masking;
- recognize why package versions are part of computational
  reproducibility.

------------------------------------------------------------------------

## Repository Output from This Lesson

Your Chapter 1 code directory can now grow to:

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    ├── 04_check_project_paths.R
    ├── 05_execution_demo.R
    ├── 06_depth_summary.R
    ├── 07_argument_demo.R
    ├── 08_reproducible_execution_check.R
    ├── 09_check_package_environment.R
    └── ...
```

At this stage, the learner has moved beyond simply installing packages
and can begin inspecting the software environment systematically.

------------------------------------------------------------------------

## References and Further Reading

### Essential Reading

1.  R Core Team. *R Installation and Administration*. R Foundation for
    Statistical Computing.

2.  R Core Team. *Writing R Extensions*. R Foundation for Statistical
    Computing.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

4.  Wickham H. *R Packages*, 2nd edition. O’Reilly Media.

### Computational Biology and Bioconductor

5.  Gentleman RC, Carey VJ, Bates DM, et al. Bioconductor: open software
    development for computational biology and bioinformatics. *Genome
    Biology*. 2004;5:R80.

6.  Huber W, Carey VJ, Gentleman R, et al. Orchestrating high-throughput
    genomic analysis with Bioconductor. *Nature Methods*.
    2015;12:115–121.

### Official Documentation

Consult current official documentation for:

- CRAN package installation and administration;
- `install.packages()`;
- `library()`;
- `requireNamespace()`;
- `.libPaths()`;
- `sessionInfo()`;
- Bioconductor package installation;
- `BiocManager`.

Useful built-in help commands include:

``` r
?install.packages
?library
?requireNamespace
?.libPaths
?installed.packages
?packageVersion
?sessionInfo
```

Package repositories and compatibility requirements evolve, so
installation instructions should always be checked against current
official package or repository documentation.

------------------------------------------------------------------------

## Next Lesson

### Lesson 1.8 — Getting Help and Reading Documentation

At this point, we have learned how to:

``` text
install R
use an IDE
create projects
manage paths
execute scripts
use packages
```

But professional programmers do not memorize every function and
argument.

They know how to **find reliable information efficiently**.

Lesson 1.8 will therefore cover:

- `?function`;
- `help()`;
- `??topic`;
- `help.search()`;
- `example()`;
- `args()`;
- function signatures;
- package help;
- package indexes;
- vignettes;
- `browseVignettes()`;
- reading CRAN documentation;
- reading Bioconductor documentation;
- understanding function usage sections;
- reading argument descriptions;
- interpreting examples;
- identifying package versions in documentation;
- distinguishing official documentation from secondary tutorials;
- and developing a systematic strategy for solving unfamiliar R
  problems.

The objective is not to memorize R.

It is to learn how to **interrogate R and its documentation
professionally**.

------------------------------------------------------------------------

## Lesson 1.8 — Getting Help and Reading Documentation

### Where This Lesson Fits

We can now install R, work in RStudio, organize an R Project, manage
paths, execute scripts, and use packages. The next professional skill is
knowing how to answer questions when we encounter unfamiliar R code.

> Professional R programmers do not memorize every function. They know
> how to find, read, test, and verify technical information efficiently.

This lesson develops that skill using R’s help system, package
documentation, vignettes, CRAN and Bioconductor resources, minimal
reproducible examples, and systematic debugging.

### Learning Objectives

After completing this lesson, you should be able to:

- use `?`, `help()`, `??`, and `help.search()`;
- inspect function signatures with `args()`;
- run documented examples with `example()`;
- interpret Description, Usage, Arguments, Value, Details, and Examples;
- recognize required arguments and defaults;
- understand `...` at an introductory level;
- inspect package documentation and vignettes;
- use `vignette()` and `browseVignettes()`;
- distinguish reference documentation from workflow tutorials;
- check package versions when reading documentation;
- investigate warnings and errors systematically;
- evaluate community and AI-generated guidance critically;
- build a repeatable workflow for unfamiliar R problems.

## 1. You Are Not Expected to Memorize R

R contains thousands of functions across base R, CRAN, Bioconductor, and
other ecosystems. Trying to memorize all of them is neither realistic
nor useful.

A stronger workflow is:

``` text
recognize the problem
      ↓
identify the likely function or package
      ↓
read authoritative documentation
      ↓
run a minimal example
      ↓
inspect the result
      ↓
adapt carefully
```

Documentation literacy is therefore part of programming skill.

## 2. Help for a Known Function: `?`

If you know the function name:

``` r
?mean
```

You can also request package-specific help:

``` r
?stats::median
```

This is one of the fastest ways to answer:

> How is this function intended to be used?

## 3. `help()`

The functional form is:

``` r
help(mean)
```

or:

``` r
help("mean")
```

You can specify a package:

``` r
help(
  "median",
  package = "stats"
)
```

`?mean` is convenient interactively; `help()` is useful when you want a
more explicit or programmatic form.

## 4. When You Do Not Know the Function Name

Suppose you know the concept:

``` text
correlation
```

but not the relevant function.

Search installed documentation:

``` r
??correlation
```

or:

``` r
help.search("correlation")
```

These searches operate on documentation available in your installed R
environment. They are not general internet searches.

## 5. `?` Versus `??`

Remember:

``` text
?name
```

means roughly:

> Show help for this known topic.

While:

``` text
??concept
```

means:

> Search installed documentation for this concept.

For example:

``` r
?lm
```

versus:

``` r
??regression
```

## 6. Anatomy of an R Help Page

Help pages commonly contain sections such as:

``` text
Description
Usage
Arguments
Details
Value
References
See Also
Examples
```

Not every page contains exactly the same sections.

A useful reading order is often:

``` text
Description
   ↓
Usage
   ↓
Arguments
   ↓
Value
   ↓
Examples
   ↓
Details, when needed
```

## 7. Read the Description First

The Description answers:

> Is this actually the function or method I need?

Never choose a function only because its name resembles your task.

## 8. Read the Usage Section

A help page may show:

``` r
some_function(x, method = "default", ...)
```

The Usage section helps identify:

- function name;
- argument names;
- argument order;
- defaults;
- whether `...` is accepted.

Do not simply copy the signature. Read what the arguments mean.

## 9. Read the Arguments Section

Argument names do not tell the whole story.

For each important argument, determine:

``` text
What type of input is expected?
What does the argument mean?
Is it required?
What values are allowed?
What is the default?
Are there important constraints?
```

## 10. Required and Optional Arguments

Consider:

``` r
analyse(
  x,
  method = "standard",
  verbose = FALSE
)
```

`x` has no visible default and is likely required.

`method` and `verbose` have defaults and can usually be omitted if those
defaults are appropriate.

Conceptually:

``` text
no default
    ↓
usually supply it

default present
    ↓
optional unless behavior must change
```

## 11. Defaults Are Analytical Decisions

Suppose documentation shows:

``` r
na.rm = FALSE
```

If missing values occur, this default can affect the result.

Professional users ask:

> Which defaults am I accepting implicitly?

This matters particularly in statistical and biological analyses.

## 12. Inspect Arguments Quickly with `args()`

Use:

``` r
args(mean)
```

or:

``` r
args(stats::median)
```

This provides a compact view of a function signature.

But `args()` does not tell you the full meaning of those arguments.

Use the help page for interpretation.

## 13. What Does `...` Mean?

The ellipsis:

``` r
...
```

indicates that additional arguments can be accepted or passed onward.

Exactly what happens depends on the function.

Never assume `...` means “any argument is valid.”

Read the documentation.

We will revisit `...` when we learn to write functions.

## 14. The Value Section

One of the most important help-page sections is:

``` text
Value
```

It tells you what the function returns.

Possible return types include:

- a number;
- vector;
- matrix;
- list;
- data frame;
- model object;
- specialized S3 or S4 object.

Before placing a function inside a workflow, ask:

> What comes back?

## 15. Inspect What You Actually Received

Documentation tells you what should be returned. R lets you inspect what
was actually returned.

Useful tools include:

``` r
class()
typeof()
str()
```

Example:

``` r
result <- mean(
  c(10, 20, 30)
)

class(result)
typeof(result)
str(result)
```

This habit becomes especially important with specialized biological
objects.

## 16. The Examples Section

Examples demonstrate intended use.

A strong learning sequence is:

``` text
read example
      ↓
run example
      ↓
modify one element
      ↓
observe the result
```

Examples can reveal valid inputs, common arguments, and expected
behavior.

## 17. Run Packaged Examples with `example()`

For example:

``` r
example(mean)
```

Be aware that package examples may:

- create objects;
- produce plots;
- take time;
- depend on optional packages;
- demonstrate edge cases.

Run them deliberately.

## 18. Minimal Reproducible Examples

Your own small example is often better for debugging than your full
dataset.

Instead of debugging a 20-million-row table, reproduce the issue with
something like:

``` r
x <- c(1, 2, NA, 4)
```

A minimal reproducible example removes unrelated complexity and makes
the underlying behavior easier to understand.

## 19. General Example — Learning `median()`

Suppose `median()` is unfamiliar.

Start with:

``` r
?median
```

Then:

``` r
args(stats::median)
```

Test:

``` r
values <- c(
  2,
  4,
  6,
  8,
  100
)

stats::median(values)
```

Inspect:

``` r
result <- stats::median(values)

class(result)
str(result)
```

You have now combined documentation, signature inspection, testing, and
output inspection.

## 20. Search by Concept with `help.search()`

Suppose you want documentation related to principal components:

``` r
help.search(
  "principal component"
)
```

or:

``` r
??"principal component"
```

The results identify candidate topics among installed documentation.

Search results are leads, not proof that every returned function is
appropriate.

## 21. Package-Level Help

If you suspect a package contains the tools you need:

``` r
help(
  package = "stats"
)
```

For another installed package:

``` r
help(
  package = "here"
)
```

Package-level help is useful for understanding the package’s documented
interface rather than discovering functions randomly.

## 22. What Is a Vignette?

A help page is generally a reference entry for a function or topic.

A **vignette** is usually a longer-form explanation of a package,
concept, or workflow.

Think:

``` text
Help page
=
reference

Vignette
=
guided workflow or tutorial
```

For an unfamiliar package, an introductory vignette is often a better
starting point than randomly opening individual function pages.

## 23. Finding Vignettes

List available vignettes:

``` r
vignette()
```

For one package:

``` r
vignette(
  package = "packageName"
)
```

Open a known vignette:

``` r
vignette(
  "vignette-name",
  package = "packageName"
)
```

Exact names depend on the installed package.

## 24. `browseVignettes()`

Use:

``` r
browseVignettes()
```

or:

``` r
browseVignettes(
  package = "packageName"
)
```

This is useful for packages with substantial tutorial documentation.

## 25. Why Vignettes Matter in Computational Biology

Bioconductor packages often use specialized biological classes and
coordinated workflows.

A single function page may not explain:

``` text
input data
    ↓
specialized object
    ↓
quality control
    ↓
transformation
    ↓
analysis
    ↓
result object
```

A vignette often provides this larger context.

## 26. Reference Documentation Versus Tutorials

Different resources answer different questions.

### Reference documentation

Best for:

``` text
exact arguments
defaults
return values
formal behavior
```

### Official vignettes/tutorials

Best for:

``` text
workflow
motivation
typical usage
package concepts
```

### Books and teaching resources

Best for:

``` text
mental models
progressive explanation
broader context
```

Use the right documentation type for the question.

## 27. CRAN Documentation

For CRAN packages, authoritative resources commonly include:

- installed help pages;
- reference manuals;
- vignettes;
- package metadata;
- CRAN package pages;
- official package sites maintained by package authors.

If a tutorial contradicts current package documentation, investigate the
discrepancy. The tutorial may describe an older version.

## 28. Bioconductor Documentation

Bioconductor packages commonly provide:

- reference manuals;
- vignettes;
- workflow documents;
- package pages;
- release/development information.

Version awareness is important because Bioconductor releases are
coordinated with R versions.

Ask:

> Is this documentation for the package and Bioconductor version I am
> using?

## 29. Package Versions and Documentation

Check:

``` r
packageVersion(
  "packageName"
)
```

If your installed package is older or newer than an online example, the
interface may differ.

Compare:

``` text
your R version
your package version
documentation version
```

before concluding that your code is wrong.

## 30. Find Where a Function Comes From

If a function is on the search path:

``` r
find("filter")
```

You may also encounter:

``` r
getAnywhere("filter")
```

which can help locate objects beyond ordinary search-path lookup.

The key debugging question is:

> Which implementation am I actually examining?

## 31. `methods()` — A First Look

Some functions behave differently for different object classes.

For example:

``` r
methods("summary")
```

or:

``` r
methods("print")
```

At this stage, simply recognize that:

``` r
summary(x)
```

may behave differently depending on the class of `x`.

Object-oriented programming is taught later.

## 32. Documentation Can Look More Advanced Than Your Current Level

You may encounter terms such as:

``` text
S3
S4
generic
method
formula
dispatch
```

You do not need to master every concept immediately.

Start with:

``` text
What does this function do?
What input does it need?
Which arguments matter?
What does it return?
Can I reproduce the example?
```

Then go deeper when the task requires it.

## 33. Read Error Messages Before Searching

Suppose R reports:

``` text
Error in some_function(x) : object 'x' not found
```

Do not search only for:

``` text
R error
```

Identify the useful information:

``` text
object 'x' not found
```

Then ask:

- Which operation failed?
- Does `x` exist?
- Is it spelled correctly?
- Did an earlier command fail?
- Is the script being run in the expected order?

## 34. Message, Warning and Error Are Different

Conceptually:

### Message

Usually informational.

### Warning

Something potentially problematic occurred, but execution may continue.

### Error

The operation cannot complete normally.

Do not ignore a warning simply because R continues.

In scientific computing, a warning may indicate a methodologically
important problem.

## 35. Search Exact Error Phrases Carefully

When local documentation is insufficient, search a distinctive stable
portion of the error together with the function or package name.

Avoid project-specific noise such as sample names and local paths.

Then verify proposed solutions against current official documentation.

## 36. A Practical Source Hierarchy

A useful default order is:

``` text
1. R built-in help
2. official package documentation
3. official package vignettes
4. CRAN/Bioconductor resources
5. maintainer documentation/repository
6. high-quality books and tutorials
7. community discussions
8. AI assistance
```

This is not an absolute ranking. A community thread can be the best
source for a rare platform bug.

The principle is to match the source to the problem and verify
consequential claims.

## 37. Community Discussions

Community resources can be valuable for:

- unusual errors;
- edge cases;
- platform-specific behavior;
- practical explanations.

Check:

``` text
date
R version
package version
deprecated functions
maintainer comments
```

A highly rated old answer may no longer apply.

## 38. GitHub Issues and Release Notes

Package issue trackers can help when:

- a bug is suspected;
- behavior changed after an update;
- an error is version-specific.

Read the whole issue, especially maintainer responses and linked fixes.

Also inspect:

``` text
NEWS
CHANGELOG
release notes
```

when an update changes behavior.

## 39. Documentation and Reproducibility

Suppose an analysis relies on a default argument that later changes.

The code may still run but produce a different result.

Documentation helps identify defaults important enough to specify
explicitly.

Thus, documentation literacy is also a reproducibility skill.

## 40. General Practical Example — `quantile()`

Suppose `quantile()` is unfamiliar.

Open:

``` r
?quantile
```

Inspect:

``` r
args(quantile)
```

Test:

``` r
values <- c(
  10,
  12,
  15,
  18,
  21,
  25
)

quantile(values)
```

Inspect:

``` r
result <- quantile(values)

class(result)
str(result)
```

Then change one argument:

``` r
quantile(
  values,
  probs = c(
    0.25,
    0.50,
    0.75
  )
)
```

This is documentation-driven learning.

## 41. Computational Biology Example — Learn a Package Before Using It

Suppose you learn that `GenomicRanges` is widely used for genomic
interval operations.

Do not begin by copying a large workflow.

A stronger sequence is:

``` text
confirm official package source
        ↓
check package version
        ↓
open package-level documentation
        ↓
find introductory vignette
        ↓
identify core object class
        ↓
run minimal documented example
        ↓
inspect returned object
        ↓
adapt to real data
```

If installed:

``` r
help(
  package = "GenomicRanges"
)
```

and:

``` r
vignette(
  package = "GenomicRanges"
)
```

The biological analysis itself comes later.

## 42. Computational Biology Example — Documentation Before VCF Analysis

Before building a VCF workflow, determine:

``` text
Which package reads the file?
Which function is recommended?
What file formats/compression are supported?
Is an index required?
What object class is returned?
What genome/build assumptions matter?
```

These are documentation questions.

A command that merely runs is not enough for biological analysis.

## 43. Statistical Documentation Requires Extra Care

For functions involving:

``` text
regression
normalization
multiple testing
imputation
differential expression
```

do not read only syntax.

Inspect:

- assumptions;
- defaults;
- method references;
- output interpretation;
- edge-case behavior.

Syntactically valid code can still be scientifically inappropriate.

## 44. Using AI for R Help

AI can help:

- explain dense documentation;
- create minimal examples;
- interpret error messages;
- compare functions;
- suggest debugging steps.

But AI can also:

- invent functions;
- invent arguments;
- use outdated APIs;
- confuse packages;
- misstate defaults;
- provide biologically inappropriate interpretations.

Use:

``` text
AI suggestion
     ↓
verify against documentation
     ↓
run minimal example
     ↓
inspect output
```

AI is an accelerator, not a replacement for verification.

## 45. Asking Better Technical Questions

Weak:

``` text
Fix my R code.
```

Stronger:

``` text
This code uses package X version Y with R version Z.
Here is the exact error.
Explain the likely cause.
Use the documented package interface.
Show a minimal reproducible correction.
```

Precise questions produce more useful debugging.

## 46. A Systematic Help Workflow

When an unfamiliar R problem appears:

### Step 1 — Classify the problem

Is it mainly:

``` text
syntax
object
function
package
path
data type
method
installation
version
```

### Step 2 — Inspect the relevant object/environment

For example:

``` r
class()
str()
typeof()
R.version.string
packageVersion()
```

### Step 3 — Use local function help

``` r
?function
args(function)
```

### Step 4 — Search installed documentation

``` r
??topic
help.search("topic")
```

### Step 5 — Inspect package documentation

``` r
help(
  package = "packageName"
)

vignette(
  package = "packageName"
)
```

### Step 6 — Build a minimal example

Remove unrelated complexity.

### Step 7 — Consult authoritative online resources

Prefer current official documentation.

### Step 8 — Search community discussions when necessary

Check versions and dates.

### Step 9 — Use AI assistance if useful

Ask for explanation or debugging support.

### Step 10 — Verify

Run the solution, inspect the result, and confirm documented behavior.

## 47. Do Not Debug Everything at Once

Suppose:

``` text
read data
   ↓
filter
   ↓
annotate
   ↓
join
   ↓
plot
```

fails.

Find the earliest failing step.

Inspect the object immediately before it:

``` r
class(object)
str(object)
head(object)
```

Then read the documentation for the failing operation.

Debugging becomes easier when the problem is localized.

## 48. Common Mistakes

### Mistake 1 — Trying to memorize every function

Learn how to retrieve reliable information instead.

### Mistake 2 — Choosing a function from its name alone

Read its documented purpose.

### Mistake 3 — Ignoring Arguments

Inputs and defaults matter.

### Mistake 4 — Ignoring Value

You need to understand what is returned.

### Mistake 5 — Copying examples without checking object classes

Your data may not match the example.

### Mistake 6 — Assuming online documentation matches your installed version

Check versions.

### Mistake 7 — Ignoring warnings

Warnings may have analytical significance.

### Mistake 8 — Searching vague error phrases

Use the distinctive error plus function/package context.

### Mistake 9 — Trusting old community answers without verification

APIs evolve.

### Mistake 10 — Treating AI output as authoritative documentation

Verify software behavior using primary sources.

## 49. Debugging Clinic

### Scenario 1 — Unused Argument

You see:

``` text
Error: unused argument (...)
```

Inspect:

``` r
args(function_name)
?function_name
```

Then check:

``` r
packageVersion("packageName")
```

Possible causes include a wrong argument name, outdated tutorial, wrong
function, or version difference.

### Scenario 2 — Function Not Found

Determine which package provides the function.

Check package availability and whether explicit namespace syntax is
appropriate:

``` r
packageName::functionName()
```

### Scenario 3 — Documentation Example Works but Your Data Fail

Compare object structure:

``` r
class(your_object)
str(your_object)
```

The input type may differ from the documented example.

### Scenario 4 — Online Code Uses an Argument Missing Locally

Check package version.

The online code may target a different API version.

### Scenario 5 — Same Function Name in Multiple Packages

Request package-specific help:

``` r
?packageName::functionName
```

or:

``` r
help(
  "functionName",
  package = "packageName"
)
```

### Scenario 6 — Old Bioconductor Workflow Fails

Check:

``` text
R version
Bioconductor version
package version
current official vignette
```

before modifying code randomly.

## 50. Performance Corner

Documentation skill improves **developer productivity**.

A programmer can spend 30 minutes guessing argument names or two minutes
reading:

``` r
?function
```

Similarly, reading the `Value` section before writing downstream code
can prevent hours of debugging an unexpected object class.

Efficient programming is not only faster computation. It is also faster,
more reliable problem solving.

## 51. Expert Commentary

A sign of increasing proficiency is not that you stop consulting
documentation.

It is that you consult it more effectively.

Experienced programmers routinely check:

``` text
function signatures
defaults
return values
package versions
vignettes
release notes
```

The difference is that they know what information they need and where to
find it.

## 52. From the Reviewer’s Perspective

A methods section stating:

``` text
Data were processed using Package X.
```

is often insufficient.

Reproducibility may require:

``` text
package version
specific function
important non-default arguments
software environment
methodological references
```

Documentation literacy improves not only code, but scientific reporting.

## Practice Questions — Basic Level

1.  Why is memorizing every R function unnecessary?
2.  What does `?mean` do?
3.  What does `help(mean)` do?
4.  What is the difference between `?topic` and `??topic`?
5.  What does `help.search()` search?
6.  Why may local help not find an uninstalled package?
7.  Name five common sections of an R help page.
8.  What information does Usage provide?
9.  Why should Arguments be read carefully?
10. What is a default argument?
11. Why can defaults affect an analysis?
12. What does `args()` show?
13. Why does `args()` not replace full documentation?
14. What does `...` mean at an introductory level?
15. Why is Value important?
16. What does `example()` do?
17. What is a vignette?
18. How does a vignette differ from a help page?
19. What does `browseVignettes()` do?
20. Why should package versions be checked?
21. What is a minimal reproducible example?
22. Why should warnings not automatically be ignored?
23. When can GitHub issues be useful?
24. Why should old community answers be checked carefully?
25. Why should AI-generated R advice be verified?

## Practical Exercises

### Exercise 1 — Read a Help Page

Open:

``` r
?mean
```

Identify Description, Usage, Arguments, Value, and Examples.

### Exercise 2 — Inspect Signatures

Run:

``` r
args(mean)
args(stats::median)
args(quantile)
```

Identify visible defaults.

### Exercise 3 — Run an Example

Run:

``` r
example(mean)
```

Then create your own smaller example.

### Exercise 4 — Search by Concept

Use:

``` r
??correlation
help.search("correlation")
```

Inspect the results without assuming every result is relevant.

### Exercise 5 — Package Documentation

Run:

``` r
help(
  package = "stats"
)
```

Choose three unfamiliar functions and read their descriptions.

### Exercise 6 — Inspect Output

``` r
values <- c(
  10,
  20,
  30,
  40,
  50
)

result <- quantile(values)

class(result)
typeof(result)
str(result)
```

Compare the result with the documentation.

### Exercise 7 — Package Version

Choose an installed non-base package:

``` r
packageVersion(
  "packageName"
)
```

Record the version before reading online documentation.

### Exercise 8 — Vignettes

For an installed package:

``` r
vignette(
  package = "packageName"
)
```

Identify an introductory vignette if available.

## Intermediate Exercises

### Exercise 9 — Diagnose an Unused Argument

Suppose:

``` r
some_function(
  x,
  remove_na = TRUE
)
```

returns:

``` text
unused argument (remove_na = TRUE)
```

Describe a debugging sequence using `args()`, help, package
identification, and `packageVersion()`.

### Exercise 10 — Documentation Version Mismatch

An old tutorial uses:

``` r
packageX::analyse(
  data,
  old_argument = TRUE
)
```

Your installed version rejects `old_argument`.

Determine whether the tutorial is outdated, the wrong function is being
called, or the API changed.

### Exercise 11 — Bioconductor Documentation Audit

Choose one installed Bioconductor package and identify:

1.  package version;
2.  package-level help;
3.  available vignettes;
4.  one core object class mentioned;
5.  one major workflow described.

Do not perform the full biological analysis.

## Challenge — Build an R Help Toolkit Script

Create:

``` text
scripts/10_help_and_documentation_toolkit.R
```

The script should:

1.  print the R version;
2.  check whether a selected package is installed;
3.  print its version;
4.  locate its installation directory;
5.  inspect the arguments of one function;
6.  identify where that function is found;
7.  print the class of a small example result;
8.  print `sessionInfo()`.

Example beginning:

``` r
# ============================================================
# Script: 10_help_and_documentation_toolkit.R
# Project: Chapter 1 Practice Project
# Purpose: Demonstrate systematic documentation inspection
# Author: Sandeep Kumar Singh
# ============================================================

cat("R version:\n")
print(R.version.string)

package_name <- "stats"

cat("\nPackage version:\n")
print(
  packageVersion(
    package_name
  )
)

# Continue...
```

## Mini-Project — Learn One Function Without a Tutorial

Choose one R function not yet taught in the course.

Initially, do **not** use Google, YouTube, Stack Overflow, or AI.

Using R’s documentation, determine:

``` text
What does the function do?
Which package provides it?
What arguments does it accept?
Which arguments have defaults?
What does it return?
Can you run a minimal example?
What changes when one argument changes?
```

Then consult one authoritative external resource and compare your
understanding.

## Lesson Competency Check

Before moving to Lesson 1.9, you should be comfortable using:

``` r
?function
help()
??topic
help.search()
args()
example()
help(package = ...)
vignette()
browseVignettes()
find()
getAnywhere()
methods()
class()
typeof()
str()
packageVersion()
sessionInfo()
```

You should be able to explain:

``` text
reference documentation
vignette
function signature
argument
default
return value
minimal reproducible example
warning
error
version mismatch
authoritative source
```

Most importantly, when you encounter an unfamiliar function, your
response should become:

> I know how to investigate it.

## Key Takeaways

You can now:

- use R’s built-in help system;
- search documentation without knowing the exact function;
- read help pages strategically;
- inspect function signatures and defaults;
- understand why return values matter;
- use examples and minimal reproducible examples;
- find package-level help and vignettes;
- distinguish reference documentation from workflow documentation;
- check versions before following external examples;
- investigate errors and warnings systematically;
- evaluate community sources more critically;
- use AI assistance while retaining documentation-based verification.

## Repository Output from This Lesson

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    ├── 04_check_project_paths.R
    ├── 05_execution_demo.R
    ├── 06_depth_summary.R
    ├── 07_argument_demo.R
    ├── 08_reproducible_execution_check.R
    ├── 09_check_package_environment.R
    ├── 10_help_and_documentation_toolkit.R
    └── ...
```

## References and Further Reading

### Essential Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

2.  R Core Team. *R Language Definition*. R Foundation for Statistical
    Computing.

3.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

4.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

### R Packages and Documentation

5.  Wickham H, Bryan J. *R Packages*, 2nd edition. O’Reilly Media.

6.  R Core Team. *Writing R Extensions*. R Foundation for Statistical
    Computing.

### Computational Biology

7.  Gentleman RC, Carey VJ, Bates DM, et al. Bioconductor: open software
    development for computational biology and bioinformatics. *Genome
    Biology*. 2004;5:R80.

8.  Huber W, Carey VJ, Gentleman R, et al. Orchestrating high-throughput
    genomic analysis with Bioconductor. *Nature Methods*.
    2015;12:115–121.

### Scientific Computing Practice

9.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

10. Noble WS. A quick guide to organizing computational biology
    projects. *PLoS Computational Biology*. 2009;5(7):e1000424.

### Documentation Practice

Useful built-in commands include:

``` r
?help
?help.search
?example
?args
?vignette
?methods
?getAnywhere
?sessionInfo
```

For package-specific behavior, consult documentation corresponding to
the package version actually installed.

## Next Lesson

### Lesson 1.9 — Understanding the R Session

We now know how to find help when R, a package, or a function is
unfamiliar.

The next step is to understand what exists **inside a running R
session**.

Lesson 1.9 will cover:

- the lifecycle of an R session;
- the global environment;
- objects in memory;
- `ls()` and `objects()`;
- `rm()` and object removal;
- `search()` and the search path;
- attached packages versus loaded namespaces;
- `sessionInfo()`;
- environment variables at an introductory level;
- startup files conceptually;
- `.RData`;
- `.Rhistory`;
- workspace saving and restoration;
- why “works on my machine” often reflects session state;
- clean-session discipline;
- and capturing session information for reproducibility.

This prepares us directly for **Lesson 1.10 — Reproducible Package
Environments with `renv`**.

------------------------------------------------------------------------

## Lesson 1.9 — Understanding the R Session

### Where This Lesson Fits

By this point, we have learned how to install R, work in RStudio,
organize an R Project, manage paths, execute scripts, use packages, and
read documentation. The next step is to understand what actually exists
**inside a running R process**.

Many beginner problems that appear mysterious are caused by **session
state**: an object exists from an earlier command, a package is attached
in one session but not another, a function name is being masked, a
working directory was changed manually, an `.RData` file silently
restored objects, or startup configuration altered the environment
before the script began.

A script can therefore appear to work while depending on invisible
state.

> The goal of this lesson is to make R’s session state visible,
> inspectable, and reproducible.

### Learning Objectives

After completing this lesson, you should be able to:

- explain what an R session is;
- distinguish code on disk from objects in memory;
- explain the role of `.GlobalEnv`;
- list objects with `ls()` and `objects()`;
- test for objects with `exists()`;
- remove objects with `rm()`;
- explain why `rm(list = ls())` is not equivalent to restarting R;
- understand and inspect the search path;
- distinguish attached packages from loaded namespaces;
- inspect session metadata with `sessionInfo()`;
- understand environment variables at an introductory level;
- understand the roles of `.Rprofile`, `.Renviron`, `.RData`, and
  `.Rhistory`;
- recognize hidden state and workspace restoration problems;
- distinguish session state from project state;
- test code from a clean R session;
- diagnose common “works on my machine” failures.

## 1. What Is an R Session?

An **R session** is one running instance of R.

When you start R, a process begins. During that process, R can hold:

``` text
objects
packages
functions
working-directory state
options
environment variables
random-number state
connections
temporary files
```

Conceptually:

``` text
Start R
   ↓
new session
   ↓
objects and state accumulate
   ↓
commands execute
   ↓
session ends
```

Much of this live state disappears when the session ends unless it has
been explicitly written to disk or restored later.

## 2. Code on Disk Is Not Session State

Suppose a script contains:

``` r
x <- 10
y <- 20
z <- x + y
```

The `.R` file stores these instructions on disk.

The objects `x`, `y`, and `z` exist in memory only after the code has
been executed.

``` text
.R script
=
instructions stored on disk

R session
=
current live computational state
```

A reproducible workflow should be able to reconstruct important objects
from code and data rather than depending on a previous session.

## 3. The Global Environment

The environment in which objects created interactively or by ordinary
top-level script execution commonly appear is:

``` text
.GlobalEnv
```

Conceptually:

``` text
.GlobalEnv
│
├── x
├── sample_size
├── results
└── other user-created objects
```

The Global Environment is **not** your project directory. It exists
inside the current R session.

## 4. Inspecting `.GlobalEnv`

Create some objects:

``` r
sample_size <- 120
threshold <- 0.05
study_name <- "Example Study"
```

Now run:

``` r
ls()
```

You may see:

``` text
"sample_size"
"study_name"
"threshold"
```

`ls()` shows object names in the environment being inspected.

## 5. `objects()`

`objects()` is closely related to `ls()`:

``` r
objects()
```

For ordinary interactive use they are often effectively interchangeable.

The important lesson is not which alias you prefer. It is that you can
**inspect the current session rather than guessing what exists**.

## 6. Inspection Before Assumption

Suppose you do not remember whether `gwas_data` exists.

Do not immediately run code that assumes it exists.

First inspect:

``` r
ls()
```

If the object exists, inspect it further:

``` r
class(gwas_data)
str(gwas_data)
```

Throughout this course we will repeatedly use the pattern:

``` text
Do not guess
   ↓
inspect
   ↓
understand
   ↓
modify
```

## 7. Testing Whether an Object Exists

Use:

``` r
exists("x")
```

Example:

``` r
x <- 10

exists("x")
```

returns:

``` text
TRUE
```

while:

``` r
exists("object_that_is_not_present")
```

returns:

``` text
FALSE
```

`exists()` is useful for diagnostics, but analysis scripts should not
routinely depend on whatever happens to be left in `.GlobalEnv`.

## 8. Removing Objects with `rm()`

Use:

``` r
rm(x)
```

to remove an object from the relevant environment.

Example:

``` r
x <- 10
rm(x)
exists("x")
```

The final command should return `FALSE`.

Removing an object from memory does not delete the script that created
it.

## 9. Removing Multiple Objects

You can remove several objects:

``` r
rm(x, y, z)
```

or use a character vector of names:

``` r
rm(
  list = c(
    "x",
    "y",
    "z"
  )
)
```

Again, this changes session state. It does not remove files from disk.

## 10. The Famous `rm(list = ls())`

You will often encounter:

``` r
rm(
  list = ls()
)
```

This removes ordinary objects listed in the current environment.

It can be useful, but it is frequently misunderstood.

> `rm(list = ls())` does **not** completely reset R.

The session can still retain:

``` text
attached packages
loaded namespaces
working-directory changes
options
environment variables
random-number state
open connections
other process state
```

This is why restarting R is a stronger test of reproducibility.

## 11. Restarting R Versus Clearing Objects

Compare:

``` text
rm(list = ls())
```

with:

``` text
Restart R
```

The first primarily clears objects from an environment.

The second starts a new R process and resets substantially more state.

A useful professional workflow is:

``` text
save scripts
    ↓
restart R
    ↓
open project
    ↓
run script from beginning
```

If the script fails, the old session was probably supplying something
invisibly.

## 12. The Search Path

When you type a name such as:

``` r
mean
```

R needs to determine where that name comes from.

Inspect the search path:

``` r
search()
```

A typical session may include entries such as:

``` text
.GlobalEnv
package:stats
package:graphics
package:grDevices
package:utils
package:datasets
package:methods
Autoloads
package:base
```

The exact output depends on the session.

## 13. Search-Path Mental Model

A simplified mental model is:

``` text
.GlobalEnv
    ↓
attached package/environment 1
    ↓
attached package/environment 2
    ↓
...
    ↓
base
```

R searches attached environments according to lookup rules until it
finds the requested name.

This is one reason function masking can occur.

## 14. Why the Search Path Matters

Suppose two packages export a function called:

``` text
filter()
```

An unqualified call:

``` r
filter(...)
```

may depend on which package is encountered first.

Explicit namespace syntax removes the ambiguity:

``` r
dplyr::filter(...)
```

or:

``` r
stats::filter(...)
```

when that is the intended function.

## 15. Avoid Reusing Important Function Names

Creating objects with common function names makes code harder to
understand.

For example:

``` r
mean <- 10
```

is poor naming practice.

Even though R’s lookup behavior has nuances, reusing familiar function
names unnecessarily creates confusion for readers and debuggers.

Prefer descriptive object names such as:

``` r
mean_expression <- 10
```

## 16. Attached Packages

When you run:

``` r
library(dplyr)
```

`dplyr` becomes attached to the search path.

You can verify this using:

``` r
search()
```

Its exported functions can then often be called without the package
prefix.

## 17. Loaded Namespaces Are Different

This is an important concept that many beginner courses omit.

A package namespace can be **loaded** without being **attached**.

For example:

``` r
here::here()
```

can use the `here` namespace without requiring:

``` r
library(here)
```

first.

Conceptually:

``` text
loaded namespace
=
package code is available internally

attached package
=
package exports are placed on the search path
```

## 18. Inspecting Loaded Namespaces

Use:

``` r
loadedNamespaces()
```

Compare:

``` r
search()
```

with:

``` r
loadedNamespaces()
```

You may see namespaces that are loaded but not attached.

That is normal. Packages can load dependencies internally without
attaching every dependency to the user’s search path.

## 19. Why “Attached” and “Loaded” Must Not Be Treated as Synonyms

Suppose:

``` r
search()
```

does not contain:

``` text
package:here
```

but:

``` r
loadedNamespaces()
```

contains:

``` text
here
```

This can happen because the package was accessed through namespace
syntax or loaded as a dependency.

Understanding this distinction becomes important later in package
development and debugging.

## 20. Finding Where a Name Comes From

Useful inspection tools include:

``` r
find("filter")
```

and:

``` r
getAnywhere("filter")
```

These help answer:

> Which implementation of this name am I currently looking at?

## 21. `sessionInfo()`

One of the most useful environment diagnostics is:

``` r
sessionInfo()
```

It reports information such as:

- R version;
- platform;
- operating-system information;
- locale;
- attached packages;
- loaded namespaces;
- package versions.

This is a compact snapshot of the active software session.

## 22. Why `sessionInfo()` Matters

Suppose a collaborator says:

> Your script does not work on my machine.

Compare:

``` text
R version
package versions
platform
attached packages
loaded namespaces
```

Differences here may help explain the behavior.

`sessionInfo()` is not a complete reproducibility solution, but it is
valuable evidence.

## 23. Saving Session Information

For a substantial analysis, you can save session information:

``` r
session_file <- here::here(
  "outputs",
  "session_info.txt"
)

writeLines(
  capture.output(
    sessionInfo()
  ),
  session_file
)
```

This creates a human-readable record of the computational environment.

Later, `renv` will provide stronger package-environment control.

## 24. Quick R-Version Inspection

For a concise version check:

``` r
R.version.string
```

You can also inspect:

``` r
R.version
```

or:

``` r
version
```

The right level of detail depends on the question you are trying to
answer.

## 25. Environment Variables

R can read **operating-system environment variables**.

Examples may include:

``` text
HOME
PATH
API configuration
temporary-directory settings
thread settings
software locations
```

Inspect them with:

``` r
Sys.getenv()
```

This is not the same thing as an R environment such as `.GlobalEnv`.

## 26. R Environment Versus Environment Variable

Do not confuse these two uses of the word “environment.”

``` text
R environment
=
structure containing R bindings/objects

OS environment variable
=
named configuration value exposed to a process
```

For example:

``` r
Sys.getenv("HOME")
Sys.getenv("PATH")
```

## 27. Inspecting Environment Variables Safely

Try:

``` r
Sys.getenv("HOME")
```

and:

``` r
Sys.getenv("PATH")
```

You can inspect all visible environment variables with:

``` r
Sys.getenv()
```

but be careful when sharing the output.

Environment variables can contain sensitive information such as tokens
or credentials.

## 28. Setting an Environment Variable for the Current Process

R can set an environment variable:

``` r
Sys.setenv(
  EXAMPLE_SETTING = "test"
)
```

Then:

``` r
Sys.getenv(
  "EXAMPLE_SETTING"
)
```

This changes the current process environment. It is not necessarily a
permanent operating-system setting.

## 29. Do Not Hard-Code Secrets

Future R projects may need:

``` text
API keys
database credentials
cloud tokens
private configuration
```

Do not place secrets directly into scripts that may be committed to
GitHub.

Environment variables are one mechanism for separating sensitive
configuration from source code.

Secure secrets management will be treated more deeply later when
relevant.

## 30. Startup Behavior

A new R process is not always identical on every machine.

Startup behavior can be influenced by:

``` text
R installation
startup files
environment variables
IDE settings
project configuration
workspace restoration
```

This is why “fresh session” and “identical environment” are not exactly
the same thing.

## 31. `.Rprofile`

R can read startup configuration from files named:

``` text
.Rprofile
```

These can contain R code that modifies startup behavior.

For example, an `.Rprofile` might set:

``` text
options
repository settings
custom helper functions
other user configuration
```

You do not need to customize `.Rprofile` yet.

You do need to recognize that startup files can modify the session
before your analysis begins.

## 32. `.Renviron`

A file named:

``` text
.Renviron
```

can be used to define environment variables available to R.

A useful introductory distinction is:

``` text
.Rprofile
=
R code used during startup

.Renviron
=
environment-variable configuration
```

## 33. Startup Files and “Works on My Machine”

Suppose one computer has an `.Rprofile` that changes an R option or
defines a helper function.

Another computer does not.

Both researchers restart R, but their sessions are still not equivalent.

This is why reproducibility requires awareness of startup configuration,
not merely an empty Global Environment.

## 34. `.RData`

R can save a workspace image containing session objects.

A common default filename is:

``` text
.RData
```

Functions related to workspace images include:

``` r
save.image()
```

and:

``` r
load()
```

For example:

``` r
save.image(
  file = "workspace.RData"
)
```

Later:

``` r
load(
  "workspace.RData"
)
```

can restore saved objects.

## 35. Why Automatic `.RData` Restoration Can Be Risky

Imagine a project opens and these objects silently appear:

``` text
data_clean
model
results
threshold
```

Your script runs because the objects already exist.

A collaborator opens the same project without that workspace and the
script fails.

The problem is hidden state.

A safer default for reproducible analysis is often:

``` text
recreate objects from code and declared inputs
```

rather than:

``` text
depend on automatically restored memory
```

## 36. Saving One Object Versus Saving a Whole Workspace

There is an important conceptual difference between saving a deliberate
output and saving the entire session.

For example, later you may use:

``` r
saveRDS(
  result,
  "result.rds"
)
```

and:

``` r
readRDS(
  "result.rds"
)
```

to persist one explicit object.

That is different from relying on an automatically restored `.RData`
file containing many unrelated objects.

The long-term principle is:

> Prefer explicit state over hidden state.

## 37. `.Rhistory`

R can store interactive command history in a file such as:

``` text
.Rhistory
```

This may help recover exploratory commands.

But command history is not a substitute for scripts because it may
contain:

- failed attempts;
- duplicated commands;
- experiments;
- commands executed in a non-reproducible order.

## 38. History Versus Script

A useful distinction is:

``` text
.Rhistory
=
record of what you happened to type

.R script
=
deliberate computational instructions
```

The script should become the authoritative record of important analysis
logic.

## 39. Workspace Settings in RStudio

RStudio can be configured to save or restore workspaces and retain
command history.

For reproducible analytical projects, many experienced users prefer not
to automatically restore `.RData` workspaces.

The reason is not that workspace saving is inherently wrong.

The concern is that automatic restoration can make objects appear
without explicit code.

## 40. Clean-Session Discipline

A professional habit is to ask regularly:

> Would this script still work if I restarted R now?

A practical test is:

``` text
save scripts
   ↓
restart R
   ↓
open project
   ↓
run analysis from the beginning
   ↓
inspect outputs
```

If it fails, identify what the previous session supplied implicitly.

## 41. Restarting R Does Not Delete Your Project

Restarting the R process does not delete:

``` text
scripts
data
reports
figures
saved outputs
```

It resets the live session.

This is another reason to distinguish:

``` text
session state
```

from:

``` text
project files
```

## 42. Session State Versus Project State

A useful mental model is:

``` text
SESSION STATE
-------------
objects in memory
attached packages
loaded namespaces
working directory
options
random-number state
process environment

PROJECT STATE
-------------
scripts
data
README
reports
saved outputs
configuration
renv.lock (later)
```

A reproducible project tries to move important information from
undocumented session state into explicit project state.

## 43. Working Directory Is Session State

Earlier we learned:

``` r
getwd()
```

and:

``` r
setwd()
```

The current working directory belongs to the active session.

If a script works only after a manual `setwd()` call, it depends on
hidden session preparation.

This connects Lesson 1.5 directly to session-state thinking.

## 44. Package Attachment Is Session State

When you run:

``` r
library(here)
```

`here` becomes attached in the current session.

Restart R and the attachment disappears.

The package may still remain installed on disk.

Therefore:

``` text
installed package
=
persistent software on disk

attached package
=
current-session state
```

## 45. Options Are Session State

Inspect all options:

``` r
options()
```

or one option:

``` r
getOption(
  "digits"
)
```

Options can influence printing, warnings, repositories, and
package-specific behavior.

You do not need to memorize them.

The key point is that session behavior depends on more than objects
listed by `ls()`.

## 46. Random-Number State — An Important Preview

R also maintains pseudo-random number generator state.

For example:

``` r
runif(3)
```

changes the random-number state.

Running the same command again typically gives different values.

Later we will study reproducible randomness using:

``` r
set.seed()
```

This is another example of state that `rm(list = ls())` does not reset.

## 47. Temporary Files and `tempdir()`

R creates a temporary directory for the session.

Inspect it:

``` r
tempdir()
```

R and packages may place transient files there.

Temporary files should not be treated as durable project outputs.

If a result matters scientifically, write it deliberately to the
project.

## 48. General Example — Hidden Dependency

Suppose you manually create:

``` r
tax_rate <- 0.18
```

Then your script contains:

``` r
price <- 1000

final_price <- price * (
  1 + tax_rate
)

print(final_price)
```

The script works in the current session.

Restart R and run only the script.

It fails because `tax_rate` was never defined in the script.

Correct version:

``` r
tax_rate <- 0.18
price <- 1000

final_price <- price * (
  1 + tax_rate
)

print(final_price)
```

Now the dependency is explicit.

## 49. Computational Biology Example — Hidden Threshold

Imagine you manually create:

``` r
p_threshold <- 5e-8
```

Then your GWAS-style teaching script uses:

``` r
significant <- gwas_data[
  gwas_data$p < p_threshold,
]
```

The script works in your current session, but the threshold is not
documented in the script.

A better version defines it explicitly:

``` r
p_threshold <- 5e-8

significant <- gwas_data[
  gwas_data$p < p_threshold,
]
```

The genomics concept is intentionally simple. The programming lesson is
that analytical parameters should not be hidden in session history.

## 50. Computational Biology Example — Package State

Suppose a script calls:

``` r
filter(...)
```

and works because `dplyr` is already attached.

A colleague’s clean session does not have `dplyr` attached.

A clearer script can use:

``` r
dplyr::filter(
  data,
  p < 5e-8
)
```

or attach the required package explicitly at the beginning.

Again, the issue is session state, not GWAS methodology.

## 51. Why Beginner Courses Often Skip Session State

Introductory courses usually prioritize visible results such as:

``` text
vectors
data frames
plots
models
```

Session state is less visually exciting.

But misunderstanding it causes many real-world problems:

``` text
works only after manual steps
works only in one RStudio session
functions change after loading packages
objects appear unexpectedly
code fails after restart
```

Learning the session model early prevents these behaviors from becoming
normal practice.

## 52. Professional Workflow — Session Hygiene

A robust analysis often follows:

``` text
open project
   ↓
start/restart R
   ↓
load declared dependencies
   ↓
read declared inputs
   ↓
create objects from code
   ↓
perform analysis
   ↓
write explicit outputs
   ↓
capture useful environment metadata
```

Avoid workflows such as:

``` text
open old session
   ↓
reuse mysterious objects
   ↓
manually change settings
   ↓
run fragments of scripts
   ↓
save workspace
```

The first workflow is easier to test, explain, automate, and review.

## 53. Common Mistakes

### Mistake 1 — Treating Environment objects as permanent data

Objects in memory can disappear when the session ends.

**Better:** reconstruct important objects from scripts and declared
data.

### Mistake 2 — Assuming `rm(list = ls())` fully resets R

It does not reset all session state.

**Better:** restart R when testing reproducibility.

### Mistake 3 — Depending on automatically restored `.RData`

Old objects can hide missing code.

**Better:** make object creation explicit.

### Mistake 4 — Using History instead of scripts

History records exploration, not necessarily a valid workflow.

**Better:** move deliberate code into scripts.

### Mistake 5 — Ignoring the search path

You may call a different function than intended.

**Better:** inspect with `search()` and `find()` and use explicit
namespace syntax where useful.

### Mistake 6 — Confusing attached packages and loaded namespaces

They are related but different.

**Better:** compare `search()` with `loadedNamespaces()`.

### Mistake 7 — Assuming every fresh session is identical across machines

Startup files, environment variables, R versions, package versions, and
operating systems can differ.

**Better:** inspect and document the relevant environment.

### Mistake 8 — Sharing every environment variable

Some may contain credentials.

**Better:** inspect selectively and redact before sharing.

## 54. Debugging Clinic

### Scenario 1 — Object Exists Today but Not Tomorrow

**Problem:**

``` text
object 'threshold' not found
```

**Likely cause:** the object was created manually in an earlier session.

**Diagnose:**

``` r
ls()
exists("threshold")
```

**Correction:** create or read the object explicitly in the script.

### Scenario 2 — Wrong `filter()` Function

**Likely cause:** package attachment changed the search path.

**Diagnose:**

``` r
search()
find("filter")
```

**Correction:** use explicit namespace syntax.

### Scenario 3 — Script Works Only After Opening an Old RStudio Project

**Likely cause:** workspace restoration or startup configuration is
supplying hidden state.

**Diagnose:** restart R without relying on restored objects, then run
the script from the beginning.

### Scenario 4 — Collaborator Gets Different Package Behavior

**Diagnose on both machines:**

``` r
sessionInfo()
```

Compare R version, package versions, platform, attached packages, and
loaded namespaces.

### Scenario 5 — `rm(list = ls())` Does Not Fix the Problem

The issue may involve state outside `.GlobalEnv`, such as:

``` text
options
attached packages
working directory
environment variables
random-number state
```

**Correction:** restart R and rerun from the project entry point.

### Scenario 6 — API Code Works Only on One Machine

An environment variable may exist only on that computer.

**Diagnose:**

``` r
Sys.getenv(
  "MY_API_KEY"
)
```

Do not print secrets into shared logs.

## 55. Performance Corner

Session management is not mainly about CPU speed.

Its benefit is **operational reliability**.

Controlled state reduces:

- accidental reuse of old objects;
- time spent diagnosing hidden dependencies;
- package-conflict confusion;
- repeated manual setup;
- inconsistent behavior across collaborators.

For large automated workflows, predictable state becomes essential.

## 56. Expert Commentary

A beginner often sees R as:

``` text
a place where commands are typed
```

An experienced programmer sees:

``` text
a process with state
```

That state has a lifecycle.

Objects appear and disappear. Packages are attached. Namespaces are
loaded. Options change. Environment variables influence behavior.
Startup files can modify the process before analysis begins.

Once this mental model is clear, many apparently mysterious R behaviors
become inspectable rather than magical.

## 57. From the Reviewer’s Perspective

Suppose supplementary code works only when the author’s `.RData` file is
restored.

A reviewer cannot easily determine:

- where those objects came from;
- which transformations produced them;
- whether they are stale;
- whether they correspond to the manuscript.

A workflow that starts in a clean session and reconstructs the analysis
from documented code and inputs is substantially easier to audit.

A reproducible analysis should minimize dependence on invisible session
history.

## 58. General Practical Example — Session Inspection

Start a fresh session and run:

``` r
student_name <- "Alex"

scores <- c(
  72,
  81,
  88,
  90
)

mean_score <- mean(scores)
```

Inspect:

``` r
ls()
class(scores)
str(scores)
exists("mean_score")
```

Remove one object:

``` r
rm(
  student_name
)
```

Then:

``` r
ls()
```

This reinforces:

``` text
create
  ↓
inspect
  ↓
remove
  ↓
verify
```

## 59. Computational Biology Practical Example — Session Audit

Create:

``` r
variant_p <- c(
  0.20,
  0.01,
  5e-8,
  0.50
)

sample_depth <- c(
  32,
  41,
  27,
  55
)
```

Inspect:

``` r
ls()
class(variant_p)
str(variant_p)
class(sample_depth)
str(sample_depth)
```

Then record:

``` r
R.version.string
sessionInfo()
```

The biological vectors are deliberately simple. The lesson is to make
the computational environment visible.

## Practice Questions — Basic Level

1.  What is an R session?
2.  What is the difference between an `.R` script and objects in memory?
3.  What is `.GlobalEnv`?
4.  What does `ls()` do?
5.  What does `objects()` do?
6.  What does `exists()` test?
7.  What does `rm()` do?
8.  Does `rm()` delete a script from disk?
9.  Why is `rm(list = ls())` not identical to restarting R?
10. What does `search()` show?
11. Why does the search path matter?
12. What does it mean for a package to be attached?
13. What is a loaded namespace?
14. How is a loaded namespace different from an attached package?
15. What does `loadedNamespaces()` show?
16. What does `sessionInfo()` report?
17. Why do package versions matter for reproducibility?
18. What does `Sys.getenv()` do?
19. What is an environment variable?
20. What is `.RData`?
21. Why can automatic `.RData` restoration be risky?
22. What is `.Rhistory`?
23. Why is `.Rhistory` not a substitute for an R script?
24. What is `.Rprofile` conceptually?
25. What is `.Renviron` conceptually?
26. Why should secrets not be hard-coded in scripts?
27. Why can two fresh R sessions behave differently on different
    machines?
28. Why is restarting R a useful debugging technique?
29. What is the difference between session state and project state?
30. Why can a script work in one session but fail in another?

## Practical Exercises

### Exercise 1 — Inspect the Global Environment

Create:

``` r
x <- 10
y <- 20
study <- "demo"
```

Run:

``` r
ls()
objects()
```

Compare the results.

### Exercise 2 — Remove and Verify

Run:

``` r
rm(x)
exists("x")
```

Explain the result.

### Exercise 3 — Inspect the Search Path

Run:

``` r
search()
```

Attach one installed package and run `search()` again. What changed?

### Exercise 4 — Loaded Namespace Check

Compare:

``` r
loadedNamespaces()
```

with:

``` r
search()
```

Identify a namespace that is loaded but not attached, if one is present.

### Exercise 5 — Capture Session Information

Run:

``` r
sessionInfo()
```

Identify the R version, platform, attached packages, and loaded
namespaces.

### Exercise 6 — Environment Variables

Run:

``` r
Sys.getenv("HOME")
Sys.getenv("PATH")
```

Explain why the results may differ across operating systems.

### Exercise 7 — Clean-Session Test

Create `threshold <- 0.05` manually in the Console.

Create a script that uses `threshold` but does not define it.

Run the script, restart R, and run it again.

Explain what happened.

### Exercise 8 — Workspace Risk

Imagine `temporary_result <- 123` is automatically restored whenever a
project opens.

Explain how this could hide a missing step in the project’s scripts.

## Intermediate Thinking Exercises

### Exercise 9 — Diagnose a Hidden-State Workflow

A researcher says:

> The analysis works only after I open RStudio, run some commands from
> History, load two packages, and then execute lines 80–200 of the
> script.

Identify the session-state problems and redesign the workflow
conceptually.

### Exercise 10 — Attached Versus Loaded

Suppose `search()` does not contain `package:here`, but
`loadedNamespaces()` contains `"here"`.

Explain how this can happen.

### Exercise 11 — Clean Session Across Machines

Two researchers both restart R and run the same script, but obtain
different results.

List at least five environment/session-related things they should
compare before assuming the analytical algorithm is wrong.

## Challenge — Build a Session Diagnostic Script

Create:

``` text
scripts/11_session_diagnostic.R
```

The script should:

1.  print the R version;
2.  print the current working directory;
3.  list objects in `.GlobalEnv`;
4.  print the search path;
5.  print loaded namespaces;
6.  print `.libPaths()`;
7.  print selected non-sensitive environment variables such as `HOME`;
8.  print selected R options such as `digits`;
9.  print `sessionInfo()`;
10. write the diagnostic output to `outputs/session_diagnostic.txt`.

A possible starting point is:

``` r
# ============================================================
# Script: 11_session_diagnostic.R
# Project: Chapter 1 Practice Project
# Purpose: Inspect important R session state
# Author: Sandeep Kumar Singh
# ============================================================

output_file <- here::here(
  "outputs",
  "session_diagnostic.txt"
)

diagnostic <- capture.output({

  cat("R VERSION\n")
  print(
    R.version.string
  )

  cat("\nWORKING DIRECTORY\n")
  print(
    getwd()
  )

  cat("\nGLOBAL ENVIRONMENT OBJECTS\n")
  print(
    ls(
      envir = .GlobalEnv
    )
  )

  cat("\nSEARCH PATH\n")
  print(
    search()
  )

  # Continue...
})

writeLines(
  diagnostic,
  output_file
)
```

Do not include secrets or credential-bearing environment variables in a
shared diagnostic file.

## Mini-Project — Reproduce from a Clean Session

Take one simple script from an earlier Chapter 1 lesson and perform this
audit:

``` text
1. restart R
2. open the project
3. inspect ls()
4. run the script from the beginning
5. inspect search()
6. inspect sessionInfo()
7. confirm outputs
```

If the script depends on anything created manually before execution,
identify and remove that hidden dependency.

## Lesson Competency Check

Before moving to Lesson 1.10, you should be able to explain:

``` text
R session
.GlobalEnv
session state
project state
search path
attached package
loaded namespace
environment variable
.RData
.Rhistory
.Rprofile
.Renviron
clean session
```

You should be comfortable using:

``` r
ls()
objects()
exists()
rm()
search()
loadedNamespaces()
sessionInfo()
R.version.string
Sys.getenv()
Sys.setenv()
options()
getOption()
tempdir()
```

Most importantly, you should be able to recognize when code works
because of **hidden state** rather than because the script is
reproducible.

## Key Takeaways

You can now:

- explain the lifecycle of an R session;
- distinguish code on disk from live objects in memory;
- inspect `.GlobalEnv`;
- list, test for, and remove objects;
- explain why restarting R is stronger than clearing objects;
- inspect the search path;
- distinguish attached packages from loaded namespaces;
- recognize function masking as a session-state issue;
- capture session metadata with `sessionInfo()`;
- understand environment variables and startup configuration
  conceptually;
- explain the roles and risks of `.RData` and `.Rhistory`;
- recognize how startup files can create machine-specific behavior;
- separate session state from project state;
- test scripts from clean sessions;
- diagnose hidden dependencies systematically.

## Repository Output from This Lesson

Your Chapter 1 code directory can now include:

``` text
code/
└── 01_Building_a_Professional_R_Environment/
    ├── 01_check_r_installation.R
    ├── 02_explore_rstudio.R
    ├── 03_create_project_structure.R
    ├── 04_check_project_paths.R
    ├── 05_execution_demo.R
    ├── 06_depth_summary.R
    ├── 07_argument_demo.R
    ├── 08_reproducible_execution_check.R
    ├── 09_check_package_environment.R
    ├── 10_help_and_documentation_toolkit.R
    ├── 11_session_diagnostic.R
    └── ...
```

## References and Further Reading

### Essential Reading

1.  R Core Team. *An Introduction to R*. R Foundation for Statistical
    Computing.

2.  R Core Team. *R Language Definition*. R Foundation for Statistical
    Computing.

3.  Wickham H. *Advanced R*, 2nd edition. Chapman & Hall/CRC.

4.  Wickham H, Çetinkaya-Rundel M, Grolemund G. *R for Data Science
    (2e)*. O’Reilly Media.

### Reproducible Research and R Environments

5.  Ushey K. *renv: Project Environments for R*. Package documentation.

6.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*.
    2017;13(6):e1005510.

7.  Sandve GK, Nekrutenko A, Taylor J, Hovig E. Ten simple rules for
    reproducible computational research. *PLoS Computational Biology*.
    2013;9(10):e1003285.

### Computational Biology

8.  Gentleman RC, Carey VJ, Bates DM, et al. Bioconductor: open software
    development for computational biology and bioinformatics. *Genome
    Biology*. 2004;5:R80.

9.  Huber W, Carey VJ, Gentleman R, et al. Orchestrating high-throughput
    genomic analysis with Bioconductor. *Nature Methods*.
    2015;12:115–121.

### Official Documentation

Useful built-in documentation includes:

``` r
?ls
?rm
?search
?loadedNamespaces
?sessionInfo
?Sys.getenv
?options
?Startup
?save
?load
```

Startup behavior can vary across operating systems, R installations, IDE
settings, and project configurations. When exact behavior matters,
consult current official R and Posit documentation.

## Next Lesson

### Lesson 1.10 — Reproducible Package Environments with `renv`

We now understand the underlying problem:

``` text
same code
+
different session/package environment
=
potentially different behavior
```

The next lesson introduces a professional solution for controlling
project dependencies.

Lesson 1.10 will cover:

- what a reproducible package environment means;
- why global package libraries are insufficient for reproducible
  research;
- `renv::init()`;
- project-local libraries;
- `renv.lock`;
- `renv::snapshot()`;
- `renv::restore()`;
- dependency discovery;
- sharing an `renv` project;
- Git integration;
- common `renv` problems;
- Bioconductor considerations;
- and how `renv` fits into larger reproducible computational-biology
  workflows.

------------------------------------------------------------------------

## Lesson 1.10 — Reproducible Package Environments with `renv`

### Where This Lesson Fits

Lesson 1.9 showed that an R analysis depends on more than scripts. The
running session also depends on R itself, installed packages, package
versions, startup configuration, and other environmental state. This
lesson introduces `renv`, a practical way to record and reproduce
project-specific R package dependencies.

### Learning Objectives

By the end of this lesson, you should be able to explain why a global
package library is insufficient for strict reproducibility, initialize
an `renv` project, distinguish the project library from the user
library, understand `renv.lock`, use `snapshot()` and `restore()`,
inspect dependency status, and describe how `renv` fits into Git and
collaborative research.

## 1. The Problem: Same Script, Different Packages

Consider two researchers running the same script:

``` text
Researcher A: dplyr version A
Researcher B: dplyr version B
```

If package behavior or defaults changed, identical code can behave
differently. The script alone is therefore not a complete description of
the software environment.

A reproducible project needs to answer:

``` text
Which packages were used?
Which versions?
Where did they come from?
Can another computer recreate them?
```

## 2. What `renv` Does

`renv` creates a project-oriented R package environment.

Its central components are:

``` text
project/
├── renv/
├── renv.lock
├── .Rprofile
└── project files
```

The most important idea is separation:

``` text
global/user package library
            ≠
project-specific package environment
```

## 3. Install `renv`

Installation is an environment-setup step:

``` r
install.packages("renv")
```

Once installed, initialize a project with:

``` r
renv::init()
```

Run this from the intended project root.

## 4. What `renv::init()` Changes

Initialization typically creates project metadata and configures the
project so future R sessions activate the `renv` environment.

Do not treat `renv/` as mysterious generated clutter. It is part of the
environment-management machinery.

The important persistent artifact is:

``` text
renv.lock
```

## 5. The Lockfile

`renv.lock` records package-environment information in a
machine-readable form.

Conceptually:

``` text
Package A → version X
Package B → version Y
Package C → version Z
R        → version information
```

The lockfile is not the same as the packages themselves. It is a
reproducibility specification.

## 6. `renv::snapshot()`

After your project dependencies change, use:

``` r
renv::snapshot()
```

This updates the lockfile to reflect the project environment.

Mental model:

``` text
current project library
        ↓
snapshot
        ↓
renv.lock
```

Do not snapshot blindly. Review changes, especially in important
research projects.

## 7. `renv::restore()`

A collaborator who receives the project can use:

``` r
renv::restore()
```

Conceptually:

``` text
renv.lock
    ↓
restore
    ↓
reconstruct package environment
```

This is one of the key reproducibility benefits of `renv`.

## 8. `renv::status()`

Use:

``` r
renv::status()
```

to inspect whether the current project library and lockfile are
synchronized.

This is a useful diagnostic command when you are uncertain whether the
environment has changed since the last snapshot.

## 9. Project Library Versus Global Library

Without project isolation, projects may compete for one package library:

``` text
Project A ┐
Project B ├── global package library
Project C ┘
```

With project-specific management:

``` text
Project A → environment A
Project B → environment B
Project C → environment C
```

This reduces accidental cross-project dependency drift.

## 10. Package Discovery

`renv` can discover dependencies by inspecting project files. This is
useful, but automated discovery is not omniscient.

Dependencies may be missed when code is created dynamically, loaded
indirectly, or stored outside scanned files. Expert practice therefore
combines automation with inspection.

## 11. Git and `renv`

A typical reproducible project tracks the lockfile in Git:

``` text
renv.lock
```

while package binaries and caches should not be committed as though they
were source code.

Use the `.gitignore` guidance created by `renv` rather than manually
committing the full package library.

## 12. Bioconductor Considerations

Computational biology projects frequently mix CRAN and Bioconductor
packages. `renv` can record these dependencies, but compatibility still
depends on R and Bioconductor release relationships.

For a Bioconductor-heavy project, record and inspect:

``` text
R version
Bioconductor version
Bioconductor package versions
CRAN package versions
```

## 13. General Example

Suppose a simple analysis uses:

``` r
here::here()
jsonlite::toJSON(
  list(
    project = "demo",
    version = 1
  )
)
```

After adding the required packages, inspect:

``` r
renv::status()
```

and update:

``` r
renv::snapshot()
```

## 14. Computational Biology Example

Imagine a small project that depends on:

``` text
GenomicRanges
VariantAnnotation
data.table
ggplot2
```

The scientific question is not relevant to this lesson. The
reproducibility question is:

> Can another researcher reconstruct the software environment in which
> these tools were used?

That is where `renv.lock` becomes valuable.

## 15. Common Mistakes

- Running `renv::init()` in the wrong directory.
- Treating the lockfile as optional documentation.
- Updating packages and forgetting to review/snapshot the environment.
- Committing package-library binaries to Git.
- Assuming `renv` captures external system dependencies such as
  `bcftools`.
- Assuming a lockfile guarantees identical results across all operating
  systems.
- Using `renv` without recording data provenance and analysis
  parameters.

## 16. Debugging Clinic

If a package is available globally but not inside the project, inspect:

``` r
.libPaths()
renv::status()
```

If the lockfile expects a package that is missing locally:

``` r
renv::restore()
```

If you intentionally changed dependencies:

``` r
renv::snapshot()
```

If the environment behaves unexpectedly, first confirm that the intended
project is active.

## 17. Expert Commentary

`renv` solves one layer of reproducibility: the R package layer. It does
not replace containers, data-version tracking, external-tool management,
workflow orchestration, or scientific validation.

A mature reproducibility stack may eventually look like:

``` text
Git
+
renv
+
Quarto/R Markdown
+
targets
+
Docker
+
external tool versions
+
data provenance
```

Each tool solves a different problem.

## Practice Questions

1.  Why can two researchers obtain different behavior from the same R
    script?
2.  What is the difference between a package library and `renv.lock`?
3.  What does `renv::init()` do conceptually?
4.  What does `renv::snapshot()` record?
5.  What does `renv::restore()` reconstruct?
6.  What does `renv::status()` help diagnose?
7.  Why should `renv.lock` normally be tracked in Git?
8.  Why does `renv` not completely solve reproducibility?
9.  Why are Bioconductor release relationships relevant?
10. Why should package updates be deliberate during an active analysis?

## Practical Exercises

1.  Create a throwaway RStudio Project and initialize `renv`.
2.  Inspect `.libPaths()` before and after activation.
3.  Install one small CRAN package in the project.
4.  Run `renv::status()`.
5.  Run `renv::snapshot()` and inspect `renv.lock`.
6.  Copy the project to a new directory and examine the restore
    workflow.

## Challenge — Reproducible Chapter 1 Environment

Initialize `renv` in `chapter01_project`, snapshot its dependencies, and
add a short README section explaining how another learner can restore
the environment.

## Lesson Competency Check

You should now be comfortable with:

``` r
renv::init()
renv::status()
renv::snapshot()
renv::restore()
```

and be able to explain project-local package environments, dependency
lockfiles, and the limits of package-level reproducibility.

## References and Further Reading

### Essential Reading

1.  `renv` official package documentation and vignettes.
2.  Wickham H, Bryan J. *R Packages*, 2nd edition.
3.  Wilson G, Bryan J, Cranston K, et al. Good enough practices in
    scientific computing. *PLoS Computational Biology*. 2017.

## Next Lesson

### Lesson 1.11 — Introduction to Reproducible Documents

The next step is to combine explanatory text, code, results, and figures
in a document that can be rebuilt from source.

------------------------------------------------------------------------

## Lesson 1.11 — Introduction to Reproducible Documents

### Where This Lesson Fits

We now have a structured project, explicit scripts, stable paths,
package awareness, and an `renv` environment. The next problem is
reporting: how do we combine narrative, code, output, tables, and
figures so that the report itself can be regenerated?

### Learning Objectives

You should be able to explain literate programming, distinguish `.Rmd`,
`.md`, HTML, PDF, and Quarto source/output roles, understand code
chunks, control whether code executes or appears, and create a small
GitHub-oriented reproducible report.

## 1. The Reproducibility Problem in Manual Reporting

A weak workflow looks like:

``` text
run analysis
→ copy result
→ paste into Word
→ modify analysis
→ forget to update pasted result
```

The report and analysis can drift apart.

A reproducible document keeps narrative and executable analysis closer
together.

## 2. What Is R Markdown?

An `.Rmd` file can contain:

``` text
YAML metadata
Markdown prose
R code chunks
inline R expressions
```

A rendering system executes the document and produces an output format.

## 3. Source Versus Output

For this project:

``` text
.Rmd = editable source
.md  = rendered GitHub-readable output
```

The source is the master artifact. The generated Markdown is a
distribution format.

## 4. YAML

A simple GitHub-oriented YAML header is:

``` yaml
---
title: "Example Report"
author: "Sandeep Kumar Singh, PhD"
output:
  github_document:
    toc: true
    toc_depth: 3
    html_preview: false
---
```

YAML controls metadata and rendering configuration.

## 5. Code Chunks

Executable chunk:

```` text

``` r
x <- c(10, 20, 30)
mean(x)
```

```
## [1] 20
```
````

Displayed but not executed:

```` text

``` r
install.packages("example")
```
````

Plain illustrative code can also use a standard Markdown code fence.

## 6. Chunk Options

Important early options include:

``` text
eval
echo
include
warning
message
```

Do not memorize every option. Learn what each changes in the rendered
report.

## 7. Inline R

A value can be inserted into prose using inline R syntax.

The important idea is that reported numbers can come directly from the
analysis rather than manual transcription.

## 8. Why This Matters Scientifically

If a table or number changes after rerunning the analysis, a
reproducible report can update automatically.

This reduces transcription errors and stale results.

## 9. Quarto Relationship

Quarto is a newer multi-language publishing system that supports R and
many other execution engines.

At this stage:

``` text
R Markdown
=
important established R-centric reproducible-document workflow

Quarto
=
modern broader publishing system
```

The core literate-programming principles transfer between them.

## 10. General Example

Create a report that defines:

``` r
scores <- c(
  72,
  81,
  88,
  90
)
```

and reports their mean, minimum, and maximum.

## 11. Computational Biology Example

Use a tiny vector:

``` r
sequencing_depth <- c(
  31,
  42,
  28,
  55,
  37
)
```

Generate a summary directly in the report.

The biological context remains deliberately simple.

## 12. Common Mistakes

- Copying output manually into prose.
- Using `eval=FALSE` when the intention is to regenerate results.
- Allowing hidden session objects to satisfy chunks.
- Writing chunks that depend on running them manually out of order.
- Confusing `.Rmd` source with the generated `.md`.
- Storing huge datasets directly in a teaching repository.

## 13. Clean Rendering

A reproducible document should render from a clean environment rather
than depending on whatever exists in the interactive workspace.

This connects directly to Lesson 1.9.

## 14. GitHub Workflow

For this course:

``` text
lesson.Rmd
   ↓ render
lesson.md
   ↓ commit
GitHub-readable chapter
```

Figures created during `github_document` rendering should be organized
predictably.

## Practice Questions

1.  What problem does literate programming solve?
2.  What is the role of YAML?
3.  What is the difference between `.Rmd` and `.md`?
4.  What does `eval=FALSE` mean?
5.  Why can manual copy/paste create stale results?
6.  Why should a report render from a clean environment?
7.  How does Quarto relate conceptually to R Markdown?

## Practical Exercises

1.  Create a small `.Rmd` with YAML and two headings.
2.  Add one executable R chunk.
3.  Add one `eval=FALSE` chunk.
4.  Render to `github_document`.
5.  Inspect the generated `.md`.
6.  Add a small genomics-style vector and report its summary.

## Challenge — Chapter 1 Reproducibility Report

Create:

``` text
reports/chapter01_environment_report.Rmd
```

The report should show the R version, project root, selected package
versions, and `sessionInfo()`.

## References

1.  R Markdown official documentation.
2.  Quarto official documentation.
3.  Xie Y, Allaire JJ, Grolemund G. *R Markdown: The Definitive Guide*.

## Next Lesson

### Lesson 1.12 — Git and GitHub in an R Workflow

The next lesson adds version control so that code and documents can be
tracked as they evolve.

------------------------------------------------------------------------

## Lesson 1.12 — Git and GitHub in an R Workflow

### Where This Lesson Fits

A reproducible project needs more than organized files. It also needs a
reliable history of how those files changed. Git provides version
control; GitHub provides a collaborative hosting platform built around
Git repositories.

### Learning Objectives

You should be able to explain repository, commit, staging area, branch,
remote, clone, pull, push, `.gitignore`, and a safe beginner RStudio/Git
workflow.

## 1. Git Is Not GitHub

``` text
Git
=
version-control system

GitHub
=
online platform that hosts Git repositories and collaboration features
```

You can use Git without GitHub.

## 2. Why Version Control Matters

Without Git:

``` text
analysis.R
analysis_final.R
analysis_final2.R
analysis_final_revised.R
```

With Git, one meaningful filename can evolve through documented commits.

## 3. Repository

A Git repository tracks a project directory and its history.

Initialize carefully at the intended project root.

## 4. Working Tree, Staging Area, Commit

Mental model:

``` text
edit files
   ↓
working tree
   ↓ git add
staging area
   ↓ git commit
repository history
```

A commit is a recorded project state plus metadata and a message.

## 5. `git status`

One of the most important Git commands is:

``` text
git status
```

It tells you what changed, what is staged, and what is untracked.

Use it frequently.

## 6. `git add`

Stage a file:

``` text
git add README.md
```

Staging lets you decide what belongs in the next commit.

## 7. `git commit`

Create a commit:

``` text
git commit -m "Add Chapter 1 project structure"
```

Good commit messages explain the purpose of the change.

## 8. `.gitignore`

Not every project file belongs in Git.

Common exclusions include:

``` text
temporary files
large generated data
credentials
local IDE state
package-library caches
```

A `.gitignore` file records these rules.

## 9. R Project Files and Git

A coherent R repository may include:

``` text
README.md
.Rproj
.Rmd
.R
renv.lock
small teaching data
```

while excluding private, large, or generated files according to project
needs.

## 10. GitHub Remote

A local repository can be connected to a remote repository.

Conceptually:

``` text
local Git repository
       ↕
GitHub remote
```

Typical operations include:

``` text
push
pull
fetch
clone
```

## 11. Clone

`git clone` creates a local copy of a remote repository and its history.

This is generally preferable to downloading ZIP snapshots when you
intend to participate in version-controlled development.

## 12. Pull and Push

``` text
git pull
=
integrate remote changes locally

git push
=
send local commits to remote
```

Do not think of GitHub as a live shared folder. Git operations
synchronize histories.

## 13. RStudio Integration

RStudio can expose Git controls graphically. Use them if convenient, but
understand the underlying Git concepts.

The GUI should not replace the mental model.

## 14. Branches — Introductory View

A branch lets development proceed along a separate line of history.

At this stage, learn:

``` text
main
feature branch
merge
```

without building an elaborate branching strategy.

## 15. Merge Conflicts

A conflict occurs when Git cannot automatically reconcile competing
changes.

Do not panic and do not delete conflict markers blindly. Read the
conflicting versions and decide what the correct file should contain.

## 16. Computational Biology Considerations

Do not commit:

``` text
hundreds of GB of FASTQ/BAM/VCF files
controlled-access data
credentials
```

Instead, track:

``` text
download instructions
checksums
small teaching subsets
metadata
processing scripts
data provenance
```

## 17. General Workflow

``` text
git status
git add ...
git commit ...
git pull
git push
```

The exact order depends on context, but `git status` should remain a
frequent diagnostic step.

## 18. Common Mistakes

- Creating a Git repository one directory too high.
- Committing credentials.
- Committing huge raw datasets.
- Using vague commit messages.
- Treating `git add .` as harmless without reviewing changes.
- Pulling/merging without understanding local edits.
- Confusing Git history with file backup alone.

## 19. Reviewer Perspective

A well-maintained repository can reveal:

``` text
project organization
development history
analysis scripts
environment lockfile
documentation
release state
```

Git does not guarantee scientific correctness, but it greatly improves
traceability.

## Practice Questions

1.  What is the difference between Git and GitHub?
2.  What is a repository?
3.  What is the staging area?
4.  What does `git status` show?
5.  Why is `.gitignore` important?
6.  Why should raw genomics data often not be committed?
7.  What is a commit?
8.  What is a remote?
9.  What is a branch?
10. What is a merge conflict?

## Practical Exercises

1.  Initialize a practice Git repository.
2.  Create and stage a README.
3.  Commit it with a meaningful message.
4.  Modify the README and inspect `git status`.
5.  Create a `.gitignore`.
6.  Connect a disposable repository to GitHub if appropriate.

## Challenge — Version-Control Chapter 1

Place `chapter01_project` under Git, commit the project structure,
scripts, `renv.lock`, and report source, while deliberately excluding
files that should not be version controlled.

## References

1.  Chacon S, Straub B. *Pro Git*.
2.  Bryan J, Hester J. Happy Git and GitHub for the useR.
3.  Git official documentation.
4.  GitHub documentation.

## Next Lesson

### Lesson 1.13 — Chapter Project

The final Chapter 1 lesson integrates environment, projects, paths,
scripts, packages, documentation, `renv`, reproducible documents, and
Git.

------------------------------------------------------------------------

## Lesson 1.13 — Chapter Project: A Professional Reproducible R Project

### Project Goal

Build a small R project that another learner can clone, restore,
inspect, and run without relying on your personal computer state.

The project deliberately uses simple data. The goal is environment and
workflow engineering, not advanced statistics.

### Required Structure

``` text
chapter01_project/
├── chapter01_project.Rproj
├── README.md
├── .gitignore
├── renv.lock
├── data/
│   ├── general/
│   │   └── measurements.csv
│   └── genomics/
│       └── example_gwas.tsv
├── scripts/
│   ├── 01_check_r_installation.R
│   ├── 02_explore_rstudio.R
│   ├── 03_create_project_structure.R
│   ├── 04_check_project_paths.R
│   ├── 05_execution_demo.R
│   ├── 09_check_package_environment.R
│   ├── 10_help_and_documentation_toolkit.R
│   └── 11_session_diagnostic.R
├── reports/
│   └── chapter01_environment_report.Rmd
├── outputs/
└── figures/
```

The exact script list may vary. Include only scripts that serve a clear
educational purpose.

## Part 1 — Create the Project

Create a new RStudio Project.

Verify:

``` r
getwd()
list.files()
```

## Part 2 — Create Data

Create a simple general dataset:

``` r
measurements <- data.frame(
  sample_id = paste0(
    "S",
    1:5
  ),
  measurement = c(
    12.4,
    15.1,
    11.8,
    16.3,
    14.7
  )
)
```

Write it deliberately to the project.

Create a small synthetic GWAS-like teaching table:

``` r
gwas <- data.frame(
  SNP = paste0(
    "rs",
    1:5
  ),
  CHR = rep(
    6,
    5
  ),
  BP = c(
    26000000,
    27500000,
    28700000,
    31300000,
    32600000
  ),
  P = c(
    0.5,
    0.02,
    1e-4,
    5e-8,
    0.3
  )
)
```

This is synthetic teaching data, not a scientific GWAS dataset.

## Part 3 — Use Portable Paths

Use project-oriented paths with:

``` r
here::here()
```

Check all required files before reading them.

## Part 4 — Run from a Clean Session

Restart R.

Run the relevant scripts from the beginning.

No manually created Console object should be required.

## Part 5 — Inspect Dependencies

Record:

``` r
R.version.string
packageVersion("here")
sessionInfo()
```

Initialize and snapshot the project with `renv`.

## Part 6 — Reproducible Report

Create `chapter01_environment_report.Rmd` containing:

- project purpose;
- R version;
- package versions;
- file checks;
- simple dataset summary;
- synthetic genomics dataset summary;
- session information.

Render it to GitHub Markdown.

## Part 7 — Git

Initialize Git.

Create a `.gitignore`.

Commit the source files, README, small teaching data, and `renv.lock`.

Do not commit secrets, irrelevant local state, or large/generated files
without purpose.

## Part 8 — README

The README should answer:

``` text
What is this project?
What are the inputs?
How is it organized?
How do I restore dependencies?
How do I run it?
What outputs should appear?
```

## Part 9 — Reproducibility Test

Pretend you are a collaborator.

From a fresh session:

``` text
open project
restore renv
run scripts
render report
check outputs
```

Record every hidden dependency you discover and eliminate it.

## Part 10 — Competency Audit

By the end of Chapter 1, you should be able to:

- explain R versus RStudio;
- verify an R installation;
- create an RStudio Project;
- understand project roots;
- use portable paths;
- write and execute scripts;
- use packages and namespaces;
- read documentation;
- inspect session state;
- use `renv`;
- create reproducible documents;
- use Git at a basic level.

## Reviewer Checklist

A reviewer should be able to identify:

``` text
project entry point
data
scripts
dependency record
analysis order
report
outputs
Git history
```

without reconstructing your personal computer.

## Chapter 1 Completion Criteria

The project is complete when:

1.  it runs from a clean R session;
2.  package dependencies are restorable;
3.  paths are portable;
4.  inputs and outputs are separated;
5.  the report renders;
6.  Git tracks meaningful source artifacts;
7.  README instructions are sufficient for another learner.

## Next Chapter

### Chapter 2 — Understanding How R Thinks

Chapter 2 moves from environment management into the R language itself:
objects, assignment, evaluation, types, coercion, vectorization, missing
values, attributes, and the mental models required to reason about R
code.
