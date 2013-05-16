ArityProlog32
=============

Arity's Prolog Compiler and Interpreter for Microsoft Windows open source


Arity/Prolog32 was developed at Arity Corporation by Peter Gabel, Paul Weiss, and Jim Greene. For a number of years Arity provided binaries for Arity/Prolog32 at no charge.  Now, both source and binaries are available on Github as open software with the very liberal MIT license. Complete documentation is available at www.peter-gabel.com.

 
What Is Prolog?
===============

Prolog is a “logic programming language” which was designed to balance procedural and declarative styles of expression of code.  Prolog programs are made up of a set of clauses that are either facts or rules.  A fact expresses something that holds true about the information you give it.  A rule, on the other hand, expresses how new facts may be inferred. Built-in procedures provide side-effects for performing operations such as I/O, arithmetic, and interaction with a database.

Prolog is relevant today because it embodies many of the characteristics that are desired for the management of linked data and the semantic Web. The structure of Prolog data (“terms”) is more general than JSON or XML structures and very well suited to the representation and manipulation of JSON, XML, RDF, OWL and other complex data formats. The ability to store Prolog terms in a large, indexed database enables the construction of efficient and highly advanced knowledge discovery appliations.

Prolog's ability to infer solutions to problems differs from the computational model that most programmers are familiar with.  In a procedural language such as C, for example, the programmer concentrates on specifying the process of the problem, building control constructs such as "for" and "while."  A procedural program may be readily visualized as a flowchart. Procedural thinking centers on describing how an algorithm is to be carried out.  An object oriented language such as C++ or Java extends this procedural style through better encapsulation of data and functions

Prolog, on the other hand admits both a procedural reading and a declarative reading. The declarative style of Prolog allows the programmer to concentrate primarily on how data may be derived from other data by expressing programs as sets of conditions as rules.  Essentially, you as a Prolog programmer, can describe rules that generate true relationships when other relationships are found to be true. Declarative thinking centers on describing what relationships hold true under different patterns of input. This is why Prolog is considered to be a descriptive or relational programming language.

The mathematical formalization of logical reasoning initiated the study of the relationship between computation and machine intelligence.  Many practical applications have been developed out of this tradition, often in Prolog and indeed, often in Arity/Prolog32.

One area with a rich history of development and use of Prolog is natural language understanding. In fact, Prolog was originally designed to perform natural language experimentation.  The definite clause grammar formalism of Prolog parses simple natural language grammars easily and effectively. Current work in more sophisticated grammar formalisms continues to often use Prolog or be strongly influenced by Prolog technology. For example, Arity/Prolog32 is being successfully used commercially for large-scale construction grammar development based on feature logics and chart parsing technology.

Prolog's formal precision and power of interpretation makes it particularly well suited for knowledge representation.  Some of the work being performed in this area includes semantic networks, frames and scripts, and production systems. Arity/Prolog32 has been used to create several description logic inference engines, including a sophisticated implementation of the description logic EL++.

The logic-based computational model that underlies Prolog is an extension of the model that underlies relational databases. SQL can be viewed as a declarative language where queries are processed as rules for computing tables.  Prolog can be viewed, in part, as a declarative language where computation is initiated by a “goal” (akin to a query) which is processed by a set of rules for computing results.  Generally, a Prolog program’s most important output is produced through side-effects rather than the bindings created as an answer to the goal.  But much of what a Prolog program does may be viewed as a generalization of the operations within a relational database system. For this and other reasons, Prolog is useful for information management application. 



Prolog Implementations and Standards
====================================

Many implementations of Prolog have been created by developers worldwide for different hardware and software platforms. Each implementation has a different emphasis on features and targeted application areas.  Many implementations emphasize a particular set of features related to logic programming such as constraint handling or alternative control schemes (such as datalog).  Other implementations provide significant extensions for user interface, program structure, or other application support functions.

As Prolog evolved, several informal and formal standards emerged. The core features of Prolog were most often identified as “Edinburgh Prolog” or “Clocksin-Mellish Prolog” (after the book, Programming in Prolog, by William F. Clocksin and Christopher S. Mellish, 3rd Edition. Berlin: Springer-Verlag, 1987).  The ISO Prolog standard ISO/IEC 13211-1 was first published in 1995. Most implementations of Prolog were faithful to the spirit of these standards but deviated from them in significant ways.

Arity had a long history of implementing and using Prolog, releasing its first compiler and interpreter for Prolog for 16 bit MS-DOS.  Subsequent versions supported OS/2 (both 16 and 32 bit), Windows NT, and was ported to specific platforms that were common in Japan.  The version of Arity’s Prolog described in this book may be run on 32 and 64 bit versions of Microsoft Windows.  It has also been successfully used on Linux using WINE.
Arity/Prolog32

Arity/Prolog32 encompasses all of the predicates and functionality of Prolog associated with “Clocksin-Mellish Prolog”.  In addition, Arity/Prolog32 contains many predicates and features that make it ideal for constructing and deploying complex applications.

These features include:

    Expanded database support providing control over data persistence and including linked records, B-trees, hash tables and the ability to create specialized indexing structures;
    The ability of Arity/Prolog32 code to call and be called by code written in other  languages, including ‘C’;
    Text support including an integrated approach to atoms and strings;
    File management including input and output to file handles;
    Multi-threaded programming support;
    Run-time loadable dynamic linked library support;
    Sophisticated arithmetic operations including an integrated approach to integer and floating point numbers; and
    Many other extensions.

Arity/Prolog32 provides a compiler which creates highly efficient static code, an interpreter for dynamic (run-time modifiable) code, and an extended interpreter with features that aid in the debugging of Prolog programs.  The extended interpreter is itself extensible with the ability for compiled code to be added.

Compiled code is packaged in the form of DLLs (Dynamically Linked Libraries) which can be used to build self-standing applications or be used as extensions of larger applications.

Earlier versions of Arity/Prolog included a “DOS box” windowing system including menus and dialog boxes. This has now been deprecated.

 
The Arity/Prolog32 Interpreter
==============================

There are two primary uses for interpreting Prolog code.  First, Prolog has a different execution model than other languages which is complemented with a style of debugging called the “box model”.  Arity/Prolog32 contains an extended interpreter that provides this debugging support. Thus, a key use of the Arity/Prolog32 interpreter is for the development of new applications.

Second, Arity/Prolog32 provides an interpreter that may be invoked from compiled code (and may call compiled code) for applications that require dynamically modifiable code or that load portions of an application as code that may be changed by users.

Usually, when we refer to the interpreter, we are referring to the first sense of the word – the extended Arity/Prolog32 interpreter with its debugging support.

The extended Arity/Prolog32 interpreter is an application called API32.exe.  It has two modes of execution.  The default mode provides a deprecated style of interaction that contains a small integrated development environment.  This includes edit buffers and menu items to common operations.  However, this mode depends on the old deprecated “DOS box” windowing system.  We do not suggest using this mode.

The preferred mode of execution of API32.exe is called “vanilla”.  Vanilla mode allows you to execute Prolog code in a “Command Prompt” window.   You can use your favorite editor or IDE to create your application and to interact with the API32 window.

Code (structured as “predicates” containing “clauses”) is stored within the internal database of Arity/Prolog32.  By default, the internal database of API32.exe is API.idb.

 
The Arity/Prolog32 Compiler
===========================

The Arity/Prolog32 compiler produces fast, efficient code as object modules. Object modules may be linked to produce executable images and to produce dynamic linked libraries.  Code produced by other compilers may be linked with Arity/Prolog32 object code.

Typical application development begins with the Arity/Prolog32 interpreter since it allows you to run, debug, and change your program instantly. As selected portions of your program are completed, you can compile these portions and incorporate them into the interpreter by rebuilding the interpreter or by loading DLLs from interpreted code. When your application is complete the main entry point and associated code is compiled and the application is created as a new executable, independent of API32.exe.  Or, you may build applications where your compiled code becomes incorporated into a larger system written in another language, such as 'C'.
