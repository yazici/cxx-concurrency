# Concurrency in C++

Introduction to standard library features for multi-threading.

## Background

### Language Support

C++'s support for concurrency has evolved over time. The language largely predates
multi-threaded system, so older language specs have no built-in support.
Most concurrency support was added in C++11; C++14 and 17 refine these features.

A timeline is roughly:
  * C++98 - no concurrency
  * C++11 - most features: threads, mutexes, locks, conditions, futures/promises
  * C++14 - refinement: shared locks
  * C++17 - refinement: scoped locks, shared mutexes

### Debugging

Debugging multi-threaded systems is [notoriously difficult](https://bholley.net/blog/2015/must-be-this-tall-to-write-multi-threaded-code.html).
There are a variety of tools (and [languages](https://www.rust-lang.org/)!)
available to help solve these problems at compile time or run time.
Here we will add support for one tool, the [thread sanitizer](https://github.com/google/sanitizers/wiki/ThreadSanitizerCppManual).
This seems to have begun [in clang](https://clang.llvm.org/docs/ThreadSanitizer.html)
but is also supported [in gcc](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html).

The thread sanitizer is built in to the compiler itself. If enabled, it reports
on concurrency bugs as they are encountered at run time. Importantly, tsan
*only* reports on bugs that actually occur, so its report can vary between
executions!

### Terminology

I attempt to distinguish between data races and API races as referred to by Google.

## Requirements

  * C++11 or more recent
  * A corresponding version of CMake
  * POSIX threading library (pthread)

## Getting Started

Documentation coming soon!
