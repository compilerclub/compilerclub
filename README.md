# Compiler Club

Compiler Club is a reading, study, and meetup group based in Portland, OR, USA.

We will schedule in-person meetings through [our Meetup group](http://meetu.ps/c/3zSq0/11BPD/f).

## Workshop Possibilities

One possible set of activities the club could do is a series of workshops. These could vary in tone from being lecture-heavy, similar to the classroom, to more hands-on, depending on what the members are interested in.

Here are some example workshops. These could be combined or split up more as necessary.

* History of Programming Languages
* Assembly Language Crash Course (just enough to understand other topics)
* Implementation of Programming Languages (parameter stacks, call stacks, parameter passing, ABIs, frames, threads, processes)
* Compiling Overview
* Lexical analysis (scanning)
* Syntax analysis (parsing)
* Intermediate representations
* Code generation
* Basic optimizations
* VMs: LLVM, Clang
* Case studies: Clang, GCC, CPython
* Building a full compiler with LLVM

## Reading Lists

### Books

* [Compilers: Principles, Techniques, and Tools](http://amzn.to/2fToqKo) (Aho, Lam, Sethi, Ullman), a.k.a., the dragon book. The definitive classic reference.
* [Language Implementation Patterns: Create Your Own Domain-Specific and General Programming Languages](http://amzn.to/2yb0QUn) (Parr). Modern book that uses ANTLR, an advanced parser generator written by Parr.

### Misc Papers

* [An Incremental Approach to Compiler Construction](http://scheme2006.cs.uchicago.edu/11-ghuloum.pdf) (Ghuloum).

### Unladen Swallow Papers

The Google project Unladen Swallow (porting CPython to LLVM) had a [great list of papers](https://web.archive.org/web/20100210150911/http://code.google.com:80/p/unladen-swallow/wiki/RelevantPapers) relevant to 2009-era effort. The links are reproduced here:

#### Phase One Papers:

* [The behaviour of efficient virtual machine interpreters on modern architectures](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.12.918) (Ertl & Gregg, 2001) Argues for using some variation of direct threading for opcode dispatch, rather than a switch statement.
* [Virtual Machine Showdown: Stack Versus Registers](http://www.usenix.org/events/vee05/full_papers/p153-yunhe.pdf) (Shi, Gregg, Beatty & Ertl, 2005) Experiment in converting the JVM from a stack-based design to a register architecture. They observed a 32% speed-up in their benchmarks due to this change.
* [The Structure and Performance of Interpreters](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.37.8546) (Romer et al, 1996) Comparison of a variety of high- and low-level interpreters. May be somewhat out of date.
* [Context Threading: A Flexible and Efficient Dispatch Technique for Virtual Machine Interpreters](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.59.1271) (Berndl et al, 2005) An enhancement to the direct threading approach advocated by Ertl.
* [The Implementation of Lua 5.0](http://www.tecgraf.puc-rio.br/~lhf/ftp/doc/jucs05.pdf) (Ierusalimschy, Henrique de Figueiredo & Celes, 2005) Interesting notes on moving from a stack-based VM to a register-based VM, including benchmarks comparing just the stack vs register aspect.
* [The Effect of Unrolling and Inlining for Python Bytecode Optimizations](http://doi.acm.org/10.1145/1534530.1534550) (Ben Asher & Rotem, 2009) Applies a lot of traditional optimizations to Python bytecode, with some good results. Complementary to the approach we're taking. Their source code is available from our Downloads page.

#### Phase Two Papers:

* http://lambda-the-ultimate.org/node/3159: [Verifying Compiler Transformations for Concurrent Programs](http://research.microsoft.com/apps/pubs/default.aspx?id=76524): When we start really optimizing Python programs, we'll want to verify that our optimizations preserve our memory model.
* [The Design and Implementation of the SELF Compiler, an Optimizing Compiler for Object-Oriented Programming Languages](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.30.1652) (Chambers, 1992)
* [Making the Compilation “Pipeline” Explicit: Dynamic Compilation Using Trace Tree Serialization](http://www.ics.uci.edu/~franz/Site/pubs-pdf/ICS-TR-07-12.pdf) (Gal et al, 2007)
* [Efficient Just-In-Time Execution of Dynamically Typed Languages Via Code Specialization Using Precise Runtime Type Inference](http://www.ics.uci.edu/~franz/Site/pubs-pdf/ICS-TR-07-10.pdf) (Chang et al, 2007)
* [One Method at a Time is Quite a Waste of Time](http://www.ics.uci.edu/~franz/Site/pubs-pdf/C44Prepub.pdf) (Gal, Bebenita & Franz, 2007)
* [Iterative type analysis and extended message splitting: Optimizing dynamically-typed object-oriented programs](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.46.1558) (Chambers & Ungar, 1990)
* [Efficient implementation of the smalltalk-80 system](http://portal.acm.org/citation.cfm?id=800542) (Deutsch & Schiffman, 1984)
* [Adaptive optimization for Self: Reconciling High Performance with Exploratory Programming](http://research.sun.com/self/papers/urs-thesis.html) (Hölzle, 1994)
* [Optimizing Dynamically-Typed Object-Oriented Languages With Polymorphic Inline Caches](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.41.4430) (Hölzle, Chambers & Ungar, 1991) Long-form paper that originally introduced the type feedback system in Hölzle, 1994.
* [Debugging Optimized Code with Dynamic Deoptimization](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.49.1810) (Hölzle, Chambers & Ungar, 1992) Long-form paper of the section of Hölzle, 1994 that deals with dynamically deoptimizing SELF code for debugging purposes.
* [Type Feedback vs. Concrete Type Inference - A Comparison of Optimization Techniques for Object-Oriented Languages](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.34.1419) (Agesen & Hölzle, 1995) A comparison of type inference and type feedback, and analyzing how they can be mutually beneficial.
* [Measurement and Application of Dynamic Receiver Class Distributions](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.30.4066) (Garrett et al, 1994) "We apply dynamic proﬁle information to determine the dynamic execution frequency distributions of the classes of receivers at call sites. We show that these distributions are heavily skewed towards the most commonly occurring receiver class across several different languages. Moreover, we show that the distributions are stable across program inputs, from one version of a program to another, and even to some extent across programs that share library code."
* [Towards Better Inlining Decisions Using Inlining Trials](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.50.1043) (Dean & Chambers, 1994) Improving compile time by keeping a database of which inlining operations actually produced a benefit.
* [Strongtalk: Typechecking Smalltalk for a Production Environment](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.51.4406) (Bracha & Griswold, 1993)
* [Optimization of Object-Oriented Programs Using Static Class Hierarchy Analysis](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.47.7437) (Dean, Grove & Chambers, 1994)
* [The Cartesian Product Algorithm: Simple and Precise Type Inference Of Parametric Polymorphism](http://portal.acm.org/citation.cfm?id=646153.679533) (Agesen, 1995)
* [Localized Type Inference of Atomic Types in Python](http://www.ocf.berkeley.edu/~bac/thesis.pdf) (Cannon, 2005) A cautionary tale of an attempt at type inference in Python. Things to think about once/if we start looking at type inference for Python.

#### Garbage Collection:

* [Java without the coffee breaks: A nonintrusive multiprocessor garbage collector](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.19.1065) (Bacon et al, 2001) Presents Recycler, a reference counting GC system we might reuse for Python.
* [MMTk: The Memory Management Toolkit](http://cs.anu.edu.au/~Robin.Garner/mmtk-guide.pdf) (Blackburn et al, 2006) The garbage collector used by JikesRVM.
* [MC2: high-performance garbage collection for memory-constrained environments](http://portal.acm.org/citation.cfm?id=1028984&coll=GUIDE&dl=GUIDE&CFID=13233945&CFTOKEN=85731901) (Sachindran et al, 2004) Describes "Memory-Constrained Copying" technique.
* [The Compressor: concurrent, incremental, and parallel compaction](http://portal.acm.org/citation.cfm?id=1134023&coll=GUIDE&dl=GUIDE&CFID=13233945&CFTOKEN=85731901) (Kermany & Petrank, 2006) Another algorithm implemented on JikesRVM, claims to be "the most efficient compactor known today".
* [An on-the-fly mark and sweep garbage collector based on sliding views](http://portal.acm.org/citation.cfm?doid=949343.949329) (Azatchi et al, 2003) A collector designed to minimize pause times. This one is worth reading if you are interested in the details of the sliding window technique, mutator synchronization, and write barriers.
* [A generational mostly-concurrent garbage collector](http://portal.acm.org/citation.cfm?id=362422.362480&type=series) (Printezis & Detlefs, 2000) Worth reading for its description of card marking algorithms.

#### Regular Expressions:

* [Overview of Chrome's new regex engine](http://blog.chromium.org/2009/02/irregexp-google-chromes-new-regexp.html)
* [Pointer to Squirrelfish Extreme's regex JIT](http://webkit.org/blog/214/introducing-squirrelfish-extreme/)
* [Article advocating the use of Thompson NFAs for regex implementations](https://swtch.com/~rsc/regexp/regexp1.html)
* [Insecure Context Switching: Inoculating Regular Expressions for Survivability](http://www.usenix.org/event/woot08/tech/full_papers/drewry/drewry.pdf) (Drewry & Ormandy, 2008)

#### Related Work, Related Results:

* [Results from the TraceMonkey JIT](http://weblogs.mozillazine.org/roadmap/archives/2008/08/tracemonkey_javascript_lightsp.html). Includes comparison with the previous non-JIT version.
* [Results from the SquirrelFish JIT](http://webkit.org/blog/214/introducing-squirrelfish-extreme/). Includes comparison with the previous non-JIT version.
* [Recent work to improve V8 performance](http://chrome.blogspot.com/2009/03/google-chrome-has-new-beta_17.html). Only JIT/JIT comparisons, no non-JIT/JIT comparison.

## Members

* Christopher Swenson (swenson@swenson.io)
