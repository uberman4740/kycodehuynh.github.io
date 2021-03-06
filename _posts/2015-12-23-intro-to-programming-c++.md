---
layout: post
title: Introduction to Programming with C++
---

Below are my notes from CS 31 during the Fall 2013
quarter at UCLA. This is the first CS class at UCLA, 
teaching basic object-oriented programming with C++. I hope that current CS 31
students find them useful, as well as students at other schools using C++, or
those who would like to see the C++ equivalent of what they are taught
in Java, Python, and so on.

I also highly recommend the notes
and practice problems by [Andrew Forney](http://web.cs.ucla.edu/~forns/classes/fall-2014/cs-31/cs-31.html), one of the best CS TAs at UCLA. 

[Open a pull request](https://github.com/KyCodeHuynh/kycodehuynh.github.io/compare) if you find any 
errors, and I'll gladly correct them. To read the notes offline,
download this page's [Markdown version](https://raw.githubusercontent.com/KyCodeHuynh/kycodehuynh.github.io/master/_posts/2015-12-23-CS-31.md)
and open it in [Sublime Text](https://www.sublimetext.com/3), 
with the [MarkdownEditing](https://packagecontrol.io/packages/MarkdownEditing)
package installed. 

Happy studying!

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Lecture 1: 27 September 2013](#lecture-1-27-september-2013)
  - [Introduction](#introduction)
  - [History](#history)
  - [Components of Computing](#components-of-computing)
  - [Audio](#audio)
  - [Images](#images)
  - [Video](#video)
  - [CPU](#cpu)
  - [Hypothetical Machine](#hypothetical-machine)
- [Lecture 2: 30 September 2013](#lecture-2-30-september-2013)
  - [Administrative Information](#administrative-information)
  - [Tips for Succeeding in CS 31](#tips-for-succeeding-in-cs-31)
    - [Example of Project Mistakes](#example-of-project-mistakes)
  - [Academic Integrity](#academic-integrity)
  - [Language Level Abstractions](#language-level-abstractions)
  - [Higher-Level Languages](#higher-level-languages)
  - [Cooking Robot Example](#cooking-robot-example)
- [Lecture 3: 2 October 2013](#lecture-3-2-october-2013)
  - [Cooking robot continued](#cooking-robot-continued)
  - [Evolution of C++](#evolution-of-c)
  - [C++ Oddities](#c-oddities)
  - [Our first C++ Program](#our-first-c-program)
    - [Why we have cout](#why-we-have-cout)
    - [Language vs. Library](#language-vs-library)
  - [The complete "Hello there" program:](#the-complete-hello-there-program)
  - [Example Program with Input](#example-program-with-input)
    - [cin](#cin)
  - [Identifiers](#identifiers)
  - [Variables](#variables)
  - [Comments](#comments)
- [Lecture 4: 7 October 2013](#lecture-4-7-october-2013)
  - [Earnings Calculator Continued](#earnings-calculator-continued)
  - [Arithmetic expressions](#arithmetic-expressions)
  - [Result Types](#result-types)
  - [Repeating ourselves correctly](#repeating-ourselves-correctly)
  - [Program execution](#program-execution)
  - [More tricky arithmetic](#more-tricky-arithmetic)
  - [A program with strings](#a-program-with-strings)
    - [Complications with string](#complications-with-string)
    - [Why we have <string>](#why-we-have-string)
  - [Closing notes](#closing-notes)
- [Lecture 5: 9 October 2013](#lecture-5-9-october-2013)
  - [Operating Model](#operating-model)
    - [Solution](#solution)
  - [The IF Statement](#the-if-statement)
  - [Boolean Operators](#boolean-operators)
  - [Compound Statements](#compound-statements)
  - [More If Statements](#more-if-statements)
  - [Assignment Statements](#assignment-statements)
- [Lecture 6: 14 October 2013](#lecture-6-14-october-2013)
  - [Improving the Earnings Calculator](#improving-the-earnings-calculator)
  - [Constants](#constants)
  - [Nested If Statements](#nested-if-statements)
  - [And & Or](#and-&-or)
    - [The OR Operator](#the-or-operator)
    - [The AND Operator](#the-and-operator)
  - [More Caveats](#more-caveats)
    - [De Morgan's Laws](#de-morgans-laws)
  - [Handling Value Ranges](#handling-value-ranges)
    - [Derivation of Else if](#derivation-of-else-if)
  - [](#)
  - [Switch statements](#switch-statements)
  - [While Loops](#while-loops)
- [Lecture 7: 16 October 2013](#lecture-7-16-october-2013)
  - [Compound Assignment Operators](#compound-assignment-operators)
  - [Increment and Decrement Operator](#increment-and-decrement-operator)
  - [Common Looping Errors](#common-looping-errors)
  - [Do While Loops](#do-while-loops)
  - [More Looping Errors](#more-looping-errors)
  - [For Loops](#for-loops)
    - [Form options of for loop](#form-options-of-for-loop)
    - [Practice](#practice)
  - [For vs. While](#for-vs-while)
  - [A Starry Rectangle (Nested For Loop)](#a-starry-rectangle-nested-for-loop)
  - [A Dangling String](#a-dangling-string)
  - [.size()](#size)
  - [Counting Letters](#counting-letters)
- [Lecture 8: 20 October 2013](#lecture-8-20-october-2013)
  - [Reminders](#reminders)
  - [Characters](#characters)
  - [String Comparison Caveats](#string-comparison-caveats)
  - [Phone Number Check](#phone-number-check)
  - [Helpful Standard Library Functions](#helpful-standard-library-functions)
    - [A Comprehensive List](#a-comprehensive-list)
  - [Mistakes Possible](#mistakes-possible)
  - [Functions](#functions)
    - [Prototypes](#prototypes)
    - [Parameters and Arguments](#parameters-and-arguments)
    - [Returning Values](#returning-values)
  - [Random Header](#random-header)
- [Lecture 9: 23 October 2013](#lecture-9-23-october-2013)
  - [Example Program with Functions](#example-program-with-functions)
    - [Note on Boolean-returning function style](#note-on-boolean-returning-function-style)
    - [Appending Strings](#appending-strings)
    - [Design Paradigms](#design-paradigms)
  - [Another example program](#another-example-program)
    - [Passing-by-value](#passing-by-value)
    - [Reference-to types](#reference-to-types)
  - [Looping for correct input](#looping-for-correct-input)
  - [Break](#break)
- [Lecture 10: 28 October 2013](#lecture-10-28-october-2013)
  - [Continue statement](#continue-statement)
  - [Pass-by-reference continued](#pass-by-reference-continued)
    - [Example of extractWord()](#example-of-extractword)
  - [More caveats](#more-caveats)
  - [Censorship program example](#censorship-program-example)
  - [Another example](#another-example)
  - [Month Printer -- Arrays](#month-printer----arrays)
  - [Program](#program)
  - [Caveats on other languages](#caveats-on-other-languages)
  - [Use cases](#use-cases)
- [Lecture 11: 30 October 2013](#lecture-11-30-october-2013)
  - [Static Cast](#static-cast)
  - [More Bugs](#more-bugs)
  - [Passing Arrays as Arguments](#passing-arrays-as-arguments)
  - [Example: Movie Theater Attendance](#example-movie-theater-attendance)
  - [Two-Dimensional Arrays](#two-dimensional-arrays)
- [Lecture 12: 4 November 2013](#lecture-12-4-november-2013)
  - [Passing two-dimensional arrays](#passing-two-dimensional-arrays)
  - [Initializing a 2-D array](#initializing-a-2-d-array)
  - [Characters, Integers, and Strings](#characters-integers-and-strings)
  - [C++ standard rules on encoding](#c-standard-rules-on-encoding)
  - [Comparing and Sorting Strings](#comparing-and-sorting-strings)
  - [Recap on Strings](#recap-on-strings)
  - [Interfacing with C](#interfacing-with-c)
  - [C-strings](#c-strings)
- [Lecture 13: 6 November 2013](#lecture-13-6-november-2013)
  - [Input into a C-string](#input-into-a-c-string)
  - [Determining Size of C-strings](#determining-size-of-c-strings)
  - [Assigning C-strings to C-strings](#assigning-c-strings-to-c-strings)
    - [Warnings](#warnings)
  - [Concatentation with C-strings](#concatentation-with-c-strings)
  - [Comparing C-strings](#comparing-c-strings)
  - [Pitfalls of C-strings](#pitfalls-of-c-strings)
  - [Passing C-strings to Functions](#passing-c-strings-to-functions)
  - [Arrays of C-strings](#arrays-of-c-strings)
    - [Check if C-string is empty](#check-if-c-string-is-empty)
  - [Additional C-string notes](#additional-c-string-notes)
- [Lecture 14: 18 November 2013](#lecture-14-18-november-2013)
  - [Pointers](#pointers)
  - [Syntax](#syntax)
  - [Revisiting Passing-by-Reference](#revisiting-passing-by-reference)
    - [The Pointer Version](#the-pointer-version)
  - [Backend of Pointers](#backend-of-pointers)
  - [Pointer Examples](#pointer-examples)
  - [More Pointer Examples](#more-pointer-examples)
  - [Even More Pointers](#even-more-pointers)
  - [Uninitialized pointers](#uninitialized-pointers)
  - [Assigning pointers to pointers](#assigning-pointers-to-pointers)
  - [Pointers to Pointers](#pointers-to-pointers)
  - [Comparison with Pointers](#comparison-with-pointers)
- [Lecture 15: 20 November 2013](#lecture-15-20-november-2013)
  - [Traversing Arrays with Pointers](#traversing-arrays-with-pointers)
  - [Advancing the Pointer](#advancing-the-pointer)
    - [Pictorially](#pictorially)
    - [Algebraically](#algebraically)
    - [Machine Level](#machine-level)
  - [Leaving the Loop](#leaving-the-loop)
    - [Pictorially](#pictorially-1)
    - [Machine Level](#machine-level-1)
    - [Algebraically](#algebraically-1)
    - [Stop Condition](#stop-condition)
    - [Notational Convenience](#notational-convenience)
  - [Why do any of this?](#why-do-any-of-this)
  - [Array Parameters Revisited](#array-parameters-revisited)
  - [lookup() revisited](#lookup-revisited)
    - [Subscripting a Pointer](#subscripting-a-pointer)
    - [Iterating without []](#iterating-without-)
  - [Advancing a Non-Array Pointer](#advancing-a-non-array-pointer)
  - [Examples](#examples)
    - [Machine Level](#machine-level-2)
  - [Returning a Pointer](#returning-a-pointer)
    - [Null Pointers](#null-pointers)
  - [More Pointer Notes](#more-pointer-notes)
  - [Pointer Arithmetic Rules](#pointer-arithmetic-rules)
  - [Additional Notes from Forney](#additional-notes-from-forney)
- [Lecture 16: 25 November 2013](#lecture-16-25-november-2013)
  - [Structures](#structures)
    - [Employee struct example](#employee-struct-example)
  - [Input into a Struct Data Member Instance](#input-into-a-struct-data-member-instance)
  - [Shorthand Declaration of Instances](#shorthand-declaration-of-instances)
  - [Structs in Memory](#structs-in-memory)
  - [Arrays of a Struct](#arrays-of-a-struct)
  - [Function Using Struct Type as a Parameter](#function-using-struct-type-as-a-parameter)
    - [Passed-by-Value](#passed-by-value)
    - [Passed-by-Reference](#passed-by-reference)
  - [Select a member via a Pointer](#select-a-member-via-a-pointer)
    - [Access Members of Struct-Based Objects](#access-members-of-struct-based-objects)
  - [Reminders](#reminders-1)
  - [A Video Game with Targets](#a-video-game-with-targets)
- [Lecture 17: 27 November 2013](#lecture-17-27-november-2013)
  - [Target struct](#target-struct)
    - [Implementing member functions](#implementing-member-functions)
  - [Constructors](#constructors)
  - [Access Specifiers](#access-specifiers)
    - [Private](#private)
    - [Public](#public)
    - [Modified](#modified)
  - [Accessors](#accessors)
  - [Mutators](#mutators)
  - [Non-Member Functions](#non-member-functions)
  - [Const Member Functions](#const-member-functions)
  - [Classes](#classes)
- [Supplemental Notes: 29 November 2013](#supplemental-notes-29-november-2013)
  - [Based on the Book](#based-on-the-book)
    - [The new Operator](#the-new-operator)
    - [Memory Management](#memory-management)
    - [Dynamic Arrays](#dynamic-arrays)
    - [An Array of Class Objects](#an-array-of-class-objects)
    - [Returning an Array from a Function](#returning-an-array-from-a-function)
    - [Multidimensional Dynamic Arrays](#multidimensional-dynamic-arrays)
      - [Graphically: 2D Dynamic Array](#graphically-2d-dynamic-array)
      - [Machine-Level: 2D Dynamic Array](#machine-level-2d-dynamic-array)
      - [Machine-Level: Non-Dynamic 2D Array](#machine-level-non-dynamic-2d-array)
    - [Toss](#toss)
  - [Smallberg's Video Lectures](#smallbergs-video-lectures)
    - [Dynamic Allocation](#dynamic-allocation)
    - [Dynamic Deallocation](#dynamic-deallocation)
    - [Constructors with Arguments](#constructors-with-arguments)
    - [Follow the Pointer Again and Again](#follow-the-pointer-again-and-again)
    - [Destructors](#destructors)
  - [Toss](#toss-1)
- [Lecture 18: 2 December 2013](#lecture-18-2-december-2013)
  - [Creating Many Instances from a Class](#creating-many-instances-from-a-class)
  - [The new Operator](#the-new-operator-1)
  - [The delete Operator](#the-delete-operator)
  - [Constructor with Arguments](#constructor-with-arguments)
  - [Dynamic Data Members](#dynamic-data-members)
  - [Destructors](#destructors-1)
- [Lecture 20: 4 December 2013](#lecture-20-4-december-2013)
  - [Recall](#recall)
  - [Creating Objects from a Class](#creating-objects-from-a-class)
  - [Pointer Data Members](#pointer-data-members)
  - [Complex Numbers Class Example](#complex-numbers-class-example)
    - [Encapsulation](#encapsulation)
    - [Overloading](#overloading)
  - [Interfacing Classes](#interfacing-classes)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Lecture 1: 27 September 2013

### Introduction

Professor Smallberg is making it clear that this is a C++ programming course,
not a broad overview survey course of CS in general. That said, we're
apparently beginning with some sort of historical flashback to help us with
problem-solving and trouble-shooting.


### History

Reprogrammability of historical mechanical trinkets and machines were obviously
very difficult to reconfigure for different purposes.

Relevant development: textile manufacturing in the early 1800s with a loom that
allowed for fancier patterns. It was controlled by some hooks (that picked up
threads to let a shuttle through) blocked/not blocked by boards with holes in
them that could be moved to change the pattern.

** Jacquard designed that.

This is programmability: no need to significantly change the machine to change
its behavior.

Interestingly, some evidence that da Vinci may have designed a programmable
floor bot that could move about.

** Now, we have Charles Babbage, and his Difference Engine, finally, used for
   computing values, useful for functions like the trig ones and logs. It was
   never finished though, due to his personality, engineering difficulties, and
   eventual loss of funding. That said, the tolerances for building the parts
   was difficult for that time, but a 1980s project showed it to be possible
   and the machine does work.

He went on to design the Analytical Engine, still mechanical, but it was
programmable, able to store numbers and compute with them.

** Ada Augusta, daughter of Lord Byron, and designed some programs for the
   Analytical Engine, and is credited as the world's first programmmer. To this
   day, no Analytical Engine has been built based on that original design.

Later technology developments forgot/ignored Babbage and Ada's work.

1880s, US: A census has to happen, and it works via census workers doing
surveys house-to-house, with the data collected on little cards, finally
completed in 1892 because of the manual processing needed for it all.

The proposed solution: a series of holes to encode the information, a certain
hole pattern representing something, with the cards put through a cylinder with
copper contacts to use the idea of circuits completing; we can detect the
little pulses.

** This was Hollerith --> created a company for creating machines catering to
   businesses, --> BAM! --> IBM (International Business Machines), which had
   the market cornered till the personal computer revolution of 70s/80s onward

** Next: Atanasoff & Berry: the first electromechanical computer, done at Iowa
   State Uni.

** Zuse, in Germany, with similar work; his machine was lost to WWII bombs

** Alan Turing (!): in Britain, working on computers (the Colossus) for
   cryptographic work

** The three above were forgotten until post-1970s; remembered:

    Aiken, -- Harvard Mark I
    ENIAC -- military artillery calculations, used for artillery tables
        its clock speed: ~0.0000005 GHz
    EDSAC
    ...[all post-WWII]
    
Until this time, "computer" meant a person doing calculations

There were also "differential analyzers" which were mechanical but could plot
differential equations' outputs/inputs; LA's is now held at the Smithsonian.

NIST came up with the SEAC, SWAC (Standard's West Automatic Computer)
-- both late 1940s to early 1950s.

The rate of computing speed increasing is insane; pity the airline industry
couldn't sustain similar growth.

Popular culture in the 1950s thought that things like chess were hard, not the
problems we consider hard today, like facial recognition, natural language
processing, etc. Sci-fi saw bigger and bigger computers, centralized and
"smarter", "knowing everything".

Our modern use of computers for entertainment and communication would have been
unimaginable back then.


### Components of Computing

- Memory

- Central Processing Unit (CPU)

- Input/Output Devices (e.g. keyboard, monitor, etc.)

Memory stores integers, with each stored in a location. Memory location numbers
and content numbers.

How about dealing with fractions and decimals if we have only integers?

43.78 --> 4378 100 [irrational fraction]

          4378 1 [scientific notation-like system; most modern ones use this]

          43 78 [split it into parts]

How about text using just numbers?

--> map characters to numbers with an encoding scheme: a sequence of numeric codes
represents a certain character sequence:

    H e l l o --> 72 45 76 76 24
   
Input/output will ultimately reduce down to numbers.

"Character" includes %$876(), tabs, newlines, etc. Problem with this: different
manufacturers may choose different encoding schemes. A standard mapping is
needed: ASCII -- 0-127

What about other languages and their characters, e.g. ¢, £, ¡?

Common solution: map ASCII codes to different characters, but this created many
different national schemes. Western Europe isn't too bad. What about Asia?

Unicode --> one universal coding scheme to deal with this fragmentation, 0 -
~65,000 [2^16] It actually includes dead languages and fictional ones, like
Tolkien's Elvish, and its first 128 characters match ASCII.

Next: how do we represent the actual digits? Use different digits to represent
them. No biggie. From the numbers, we go to controlling pixel lighting/darking.

Programs themselves may interpret input differently.


### Audio

How about input/output of sound? Changing voltages in a continuous electrical
signal can represent a sound. How do we store that as numbers? A curve is an
infinite number of numbers. Instead, we can sample it at intervals: every
_seconds, we get the value of that curve at the point. We'll end with an
approximation (we can even transform it for filters, etc.) of little straight
lines between distinct points that we can then output to sound similar enough
to fool our ears.

To reduce the amount of storage used, we can sample less frequently.

Thus, computer audio becomes a sequence of numbers. This is why audio files are
quite a bit bigger than text ones.


### Images

How do we store pictures? Pixels. Divide the image into a large amount of small
squares and then within each square, we have it black/white [for a monochrome
display], e.g. 1/0, if the majority is dark/not-dark. Thus, 1000x800 becomes
800,000 little dots. It's pointilism epitomized.

We could also do whole shapes with just a few numbers, e.g. circle is radius,
center coordinates, etc. This is more resource-efficient, but it's very
difficult to analyze a scene for these shapes.

How about color? RGB --> Red, Green, Blue: given a color, we break it down into
RGB, with each having 0-255 for the amount of red, etc, where 0 is none, and
255 is the max.

Thus, on a computer, we might have a color as 213, 123, 0.

To each pixel: 3 bytes per pixel [RGB] times the resolution.

Compression technique: scan and count to see what's actually lighted up and
where. Store just those numbers and boom.


### Video

For continuous motion, we can sample with a bunch of stills played-back at a
certain rate that fools our eyes into seeing motion.

The problem: 24 fps, means 24x more data just for 1 frame of a video. It takes
much more data. On the Internet, data consumption goes biggest to smallest:
video --> images --> text

Video is also compressible. Most of the pixels from one frame to the next are
the same. Instead of re-saving all those pixels, we can store just what
changed, for example.


### CPU

It executes a series of instructions to run programs. Mostly, the architecture
copies numbers around.

After all, memory just stores and retrieves numbers in locations.

When new data is stored in a location previouly occupied, the old data is
totally lost.

The CPU actually has its own very high speed cache memory and moves numbers
from the the RAM to its cache for various purposes.

ALU (Arithmetic Logic Unit) is the circuitry that does the actual arithmetic.


                       Number   Number |        | |        |
                      
Operation [e.g. add] -->     ALU    -- > Result


The program tells the CPU what to do.

In the olden days, we programmed via a plugboard, switches, etc.

John von Neumann came up with an architecture that allowed for memory to store
the program's instructions. CPU would go through the instructions one at a
time, getting them from memory.


### Hypothetical Machine

Locations:

0: 21004
1: 11005
2: 22006
3: 99000
4: 00042
5: 00013
6: 72578
...

Program counter (instruction counter) is part of the CPU's memory: 0 [start value]
Accumulator: 38597

Take number in program counter. Memory, fetch number at the location number.

21                   004
Operation code       Memory address

[I see assembly code!]

Here, 21 might mean: Copy the number at the indicated memory address into the accumlator

Accumulator is now: 00042 [Copied from address 004]

Move something from memory to accumulator

Next:

Program counter is now 1.

11: Add the number at the indicated memory to the accumulator

Number at address 5 is 00013.

ALU, add these two numbers, and CPU, put the result into the accumulator.

Accumulator is now 00055
Program counter is now 2.

22              0006
Operation code  Address

22: Copy the number in the accumulator to the indicated memory location

Take 00055 from the accumulator and replace the number in address 6 with it.

// Continued in Lecture 2 (30 September 2013)

Program counter is now 3. (We're cycling forward).

Next:

99              00000
Operation code  Address

99: Halt and ignore the address part

Behold, we just ran through a program. Note how we just manipulated numbers,
doing arithmetic with the ALU, copying and storing values into memory, etc.

In modern CPUs with multiple cores, we can cache instructions ahead of time,
run instructions in parallel, etc.

Example of an error: we slipped on instruction 3, and 99 was replaced with 00,
which might mean: Copy the address part of the instruction to the program
counter, which would cause an unintended loop.



## Lecture 2: 30 September 2013


### Administrative Information

All HSSEAS students are required to take CS31, and mostly CS, CSE, EE take it
in the fall. Others take it in later quarters typically.

No prior knowledge assumed for this class, but those with prior knowledge
shouldn't coast along.

It doesn't matter which lecture or discussion section we go to. We can always
drop by another one if scheduling is weird that day. We can also go to the
office hours of any of the TAs, normally held in Boelter 2432.

It is highly recommended that we go get help early; the minute there is
confusion, seek out help.

*** See the website for office hours ***

The book is technically optional and serves mainly as supplemental reading.

*** All projects will have to meet general requirements, plus more specific
    ones ***

Programming projects and homework are due at 9 PM, with late submission
steadily losing points (10% per hour).

See the syllabus, but note that assignment scores are capped to 30 points above
the mean of the exam scores, designed to compensate for those who rely on
others for their projects.

*** All programs must be able to run under Visual Studio and Xcode/g++ ***

Thus: it must run under **two** "official" compilers. This change came about
because Smallberg et al. noticed how the VS-users and Xcode-users would commit
different errors in common and vice-versa. Thus, now we have multiple compilers
take a look at our code.

*** Go back and forth between compilers to have multiple set of eyes examine
    the code ***


### Tips for Succeeding in CS 31

1. Start early on **everything**. Coding especially will take much longer than
   you think. Software development projects are infamous for missing deadlines
   and budgetary limits. This is true even for seasoned professionals. Start
   early. Immediately begin work on projects once they're posted. Skating by on
   procrastination and last-minute work does not work here like it did
   (unfortunately) in high school. I avoided this, but a lot of people did not.
   Start early. Don't start the weekend before. There's no office hours, no
   tutoring, etc. We may even want to head out somewhere, but we won't be able
   to, or if we do, it leaves us screwed for the projects and homework.

2. Develop incrementally. Do not try to do it all at once, as there will most
   likely be error after error after error. There's likely to be misconceptions
   happening again and again. Fix and prevent them at the outset by doing a bit
   at a time to get at least some bits working. Commit to git often. Begin by
   figuring out subsets of the project requirement, build that, run, test,
   debug, etc. and get that working. Move on by adding simple use cases (avoid
   accounting for everything all at once) and get them working one part at a
   time. Build it up slowly. At any stage, we have a shippable set of code and
   any errors that pop up are likely from the newest code, making debugging a
   lot easier and faster. We use up less time and we are more likely to have a
   working project, getting at least substantial partial credit, from passing
   some of the test cases.
   
3. Read what Professor Smallberg and his TAs write. Testing of submitted
   projects will be done by automated test scripts, but that requires that our
   programs meet the specifications posted for homework projects. They are
   *very* specific and detailed. Read the specs again and *again* and **again**
   so that we do not miss any details.
   
   
#### Example of Project Mistakes

Test script expects (and the spec will clearly specify):

    Departing from: Los Angeles
    Arriving at:    New York

This would fail the test case:
    
    Departing From: Los Angeles
    Arriving At:    New York

Adhere **exactly** to the spec. The test scripts will expect
exactly what is specified. 

*** Attention to detail matters in programming. ***

*** Always compare our output to the specified output ***

*** Projects can be re-submitted multiple times before the due date ***

Why does this matter in software development? The programs we write may
be communicating with other programs rather than with humans. We will
have to adhere the specified communication avenues, e.g. for file compatibility.

CS 32 will begin the efficiency-optimization aspect of CS. 31 focuses on correctness,
e.g. how to distribute papers, an example of algorithms! 


### Academic Integrity

In the real world, we'll work in teams, but *everyone* will have a minimal
level of skill and experience. Here, we have to build skills and knowledge.
That will not happen if we do not do the work ourselves. The UCLA policy is
less clear when it comes to programming work. The CS department has addressed
this.

*High-level* discussions and *rare* assistance on some small, isolated bug are
acceptable, no actual code should *ever* be given/traded/etc.

For work from the course text or the work of a CS 31 instructor/TA (*after* the
start of this quarter), we can use it without credit, as the instructors/TAs
will recognize it.

**Do not reuse code from previous quarters' posted solutions, etc.**

Don't let the cheaters prosper and increase standards at companies because they
think that a certain GPA from UCLA means we're not actually capable because of
the cheaters.

That's the example of *Charlie the Cheater*.


### Language Level Abstractions

Remember: the computer will do **exactly** what we tell it to do.

Here, at this low-level machine code, it's tedious to do even simple tasks, and
errors are easy to commit, as we can easily lose track of what we are actually
doing.

It's best to begin with a high-level sketch of what we want to accomplish, e.g.
load, add, and the variables we'll need.

Here's the abstraction that was implemented: take a higher-level sketch and
*translate* it into machine code. That entails designing an *assembler* to take
the *assembly language* and make it into *machine code*.

Example of language syntax:

 LOAD PRICE // We start with a space to denote that it's an instruction
    ADD FEES
    STORE TOTAL
    HALT

PRICE DATA // Variables
FEES DATA
...

The assembly code is translated into machine language, which is then run.

Now we go higher, as assembly is still tedious. 


### Higher-Level Languages

Pseudo-code:

    integer price = 42
    integer totalCost = price + fees

This is a *higher-level language*.

Remember that we **copy** from memory but when we store something *new*, the
old will be **wiped out**.

Note that assembly language has close correspondence to the machine language of
a specific machine and its architecture, preventing easy multi-platform
compatibility. So, instead, we create a higher-level language that can be
translated into different machine languages by a *compiler*. In one high-level
statement, we may actually be expressing many machine code statements. An
assembler is typically linked to a specific assembly language and machine code
statement rules. A compiler is typically specific to just the high-level
language.


### Cooking Robot Example

                                                 Ingredients
                                                        |
                                                        |
recipe in English --> Robot1 --> recipe in Chinese [--> Robot2] --> Yummy food
                    [translator]                    [Chinese chef]
                    
To get food, we take the initial instructions, translate, and then they're
actually run.

C++ --> compiler --> machine language --> Executed

Errors may occur in the C++ syntax (compiler error), at run-time (we're doing
silly things).


## Lecture 3: 2 October 2013

### Cooking robot continued

Example high-level statement: beat 3 eggs into a mixing bowl

Example with mistakes: into eggs mix 3 bowl a

This is violating the rules of the high-level language. It never gets to
execution because it can't even be interpreted by the compiler.

This is a *compilation error*, also called a *syntax error*.

These are easy to avoid/fix with experience and compiler help. The fun has only
started though. We can make syntactically correct statements and still get
nonsensical results.

Example: beat 3333 eggs into a mixing bowl. Once we get to the execution stage,
we may not have that many eggs!

Ideally, we should get a warning that we don't have that many resources to
allocate. However, if we don't have that contingency built-in, then all sorts
of errors can occur.

The robot might order more eggs, not realize the bowl is overfilling, etc.

This type of error is called a *run-time error*, also called a *logic error*.


### Evolution of C++

In 1971, we got C.

Later, Bjarne Stroustrup, began working in 1980 on C++, and it was released in
1985 to the world.

Soon, a move to standardize came about. In 1998, ISO Standard got released;
this version is sometimes called C++98.

In recent years, C++11 is the most current standard; it was originally called
C++0x as it was supposed to be finished in the early oughts. Most recent
compilers do expect C++11, so we don't need to worry about that, never mind the
fact that we won't even need the advanced features.

We now expect C++14.

Objective-C was a competitor to C++ in the 80s, and C++ won that battle and
Obj-C was used mainly by NeXT, later utitlized by Apple.

Java used C++ as a base and went from there. Microsoft developed C# based on
Java because Sun wouldn't let them call it Java since MS wanted to add many
non-Java features.

UCLA uses C++ instead of Java as a starting point because of how many languages
are similar to it and so that we get a deeper understanding of concepts like
pointers.

The syntax for C++ is very tight and precise because it would take far too long
to do natural language processing just to figure out what's intended for the
program and to then translate that down to the machine code level.


### C++ Oddities

We're just learning a new syntax, a new set of grammar rules.

Professor Smallberg: "To avoid getting probed by aliens,
learn the rules of the language!"


### Our first C++ Program

int main()
{
    cout << "Hello there!" << endl;
}

To someone who doesn't understand what's needed for this, this seems like a lot
of work for just a simple little statement.

This is somewhat true, but there's actually a lot of stuff needed just for
this.

Every C++ program must have a main() program. Here, we declare main(), which
returns an int, takes no arguments, and it is automatically called when the
program is run. Depending on the environment it runs in, different things will
happen once the program finishes executing.

The returned integer indicates to the operating system the results of the
program run. This becomes important when we write programs that run other
programs, when we need to care about whether a program ran correctly before
running the next one. This is an *exit status*. By default, "0" means it ran
successfully.

"return 0;" is not necessary in C++ actually, œapparently.


#### Why we have cout

We could have had write(" ");

What about to where? By default, it's the screen, indicated by cout, the
standard output destination. endl moves the cursor to the beginning of the next
line.

We could have had write(cout, "Hello");

Instead, C++ has us writing the first argument, a symbol, and then the second.

--> cout << "Hello World!\n"

We're just calling a function. This is not a particularly special statement.

We can write multiple things with multiple <<.

The data "points" to where it's going. It's going toward cout, a destination.


#### Language vs. Library

The language is the coreset of rules, certain keywords, etc. that form the
language's grammar and what-not. The library holds much more functionality but
must be added-in manually. They're available but they're not always all needed,
e.g. like the specialized argot of a doctor.

Analogy to English: the number of conjunctions, prepositions, etc. doesn't
change, but the set of nouns, verbs, etc. constantly changes. We could imagine
basic grammar and conjunctions, etc. as the language, and the massive pool of
other words we draw from as the library. The prepositions, etc. are *function
words*.

The C++ standard library is divided into several main parts and we have to tell
the compiler when we want to use things from the library.

Here,

    #include <iostream>
    
the part of the library that deals with input/output.

But we also need std::cout and std::endl; "std" --> "standard" from the
standard library. It's in a namespace. This matters because there are other
libraries that may have identical names for things and so we declare which
namespace we're using. This way, we can have multiple libraries without having
to worry about naming conflicts.

Analogy: we have last names, which identifies us as belonging to a particular
family (namespace!) as well as our first name (identifier). Together, we can
identify the specific person/library component we want.

What if we're recounting a story and don't want to keep repeating the last
name? We can declare that we mean a particular namespace when we use various
components.

Here:

    using namespace std;
    
    
### The complete "Hello there" program:

    #include <iostream> 
    using namespace std;
    
    int main() 
    { 
        cout << "Hello there!" << endl; 
    }
    
Remember that it's machine-language translations that are actually being
executed, not our C++ program directly.

*** Remember that C++ is case-sensitive ***

Main() is different from main().

*** C++ ignores whitespace but don't make it unreadable ***

Codebases are read by people too, and we often need to modify, add new
features, debug, etc.

Tips:

* Indent what is enclosed within curly braces

* Space out things

* Line up curly braces

     
### Example Program with Input

What if we want something like this?

    How many hours did you work this week? [Input]
    What is your hourly rate of pay? [Input]
    You earned [Output]
    [Number] was withheld. 

Let's do it:

// While Smallberg was lecturing

    #include <iostream>
    using namespace std;
    
    int main()
    {
        int hours;
        double payPerHour;
        double earnings;
        double amountWithheld;
        double pctWithheld = 0.10;
        
        cout.setf(ios::fixed);       // see pp. 30-31 in Savitch book
        cout.precision(2);
        
        // Pay attention to where newlines are supposed to happen!
        cout << "How many hours did you work this week? ";
        cin >> hours;
        cout << "What is your hourly rate of pay? ";
        cin >> payPerHour;
        
        earnings = hours * payPerHour;
        amountWithheld = earnings * pctWithheld;
        cout << "You earned $" << earnings << endl;
        cout << "$" << amountWithheld << " was withheld.\n";
    }
    
Normally, languages distinguish between different types of numbers, etc.

Machine language instructions working with integers is historically
faster than dealing with numbers with fractional parts 
(i.e. floating-point types). 

We need to consider what type of number we'll need. 
Here, for example, we can have fractional hours worked.


#### cin

Analogous to cout: cin >> variable;
    

### Identifiers

Rules:

1. Starts with a letter or underscore, followed by 0 or more letters, digits,
   or underscores. *NO spaces*. Cannot begin with a number.
   
Example of a bad name: expertsexchange.com

*Be careful when running words together*

Conventions:

1. Run-together: hoursworked

2. Underscores (snake_case): hours_worked

3. CamelCase: hoursWorked
        
        
*** Single-letter variables are a BAD idea in programming ***


### Variables

First, we **declare** variables, specifying their type and identifier.

Example:

    double hoursWorked;

Range for doubles: -/+ 10e-308 to -/+ 10e308

And for signicant digits, there is a limit: about 15 for a double,
and 6-7 for a float.


/* TABLE: Variable Types

|-------|--------|
| Variable Types |
|-------|--------|


| Type |            | Size |            | Values |

  bool               1 byte         True (1) or False (0)

  char               1 byte         a-z, A-z, 0-9, space, tab, etc.
  
  short              2 bytes        [-]2^15 to (2^15)-1 --> [-]32,768 to 32,767
  
  int                4 bytes        [-]2^31 to (2^31)-1 --> 2,147,483,648 to 2,147,483,647

  long               4 bytes        [-]2^31 to (2^31)-1 --> 2,147,483,648 to 2,147,483,647

  float              4 bytes        [+/-]2^(-126) to 2^128 --> ( 1.2 * 10^(-38) to 3.4 * 10^38)

  double             8 bytes        [+/-] (2.3 * 10^(-308) to 1.7 * 10^308)
  
*/


### Comments

// This is a comment, meant for human readers



## Lecture 4: 7 October 2013



### Earnings Calculator Continued

    #include <iostream>
    using namespace std;
    
    int main()
    {
            
            // Smallberg's stylefor "section headings" for explaining   

        int hours;
        double payPerHour;
        double earnings;
        double amountWithheld;
        const double PCT_WITHHELD = 0.10;
        
        cout.setf(ios::fixed);       // see pp. 30-31 in Savitch book
        cout.precision(2);
        
        // Pay attention to where newlines are supposed to happen!
        
        cout << "How many hours did you work this week? ";
        cin >> hours;
        
        cout << "What is your hourly rate of pay? ";
        cin >> payPerHour;
        
        earnings = hours * payPerHour;
        amountWithheld = earnings * PCT_WITHHELD;
        
        cout << "You earned $" << earnings << endl;
        
        // Don't forget the dollar sign; the computation
        // won't automatically prefix it to the result
        
        cout << "$" << amountWithheld << " was withheld.\n";
        
        // Don't forget to place space characteres where
        // we want/need them. They won't automatically be
        // placed there otherwise. 
    }
    
Remember that variables are declared (including their type and identifier)
before they can be used. Typically, variables are declared right before they
are used. Remember also that where they are declared affects their scope and
lifetime.

To make code more readable, we can separate code into "paragraphs" based on
what that bit of code is doing.

To aid debugging, we may want to place little bits of code (typically cout
statements) to check something is working correctly. This is easy to do in
programmming: it's cheap and trivial to experiment. These statements can then
be commented out or removed altogether.

*** When in doubt, place parentheses to control the order of precedence ***

When we write out double values (by default), it will suppress any
insignificant trailing zeros and even the decimal point. To make things look
like how we conventionally write monetary amounts, we'll use
cout.setf(ios::fixed) and cout.precision(#). This modifies the default behavior
of double output to always have it as fixed point notation (rather than
scientific notation) and a specified number of digits after the decimal point.

Any following doubles will follow this specified format until we re-declare
otherwise.

What if a number is actually 123.4589? It will round it to 123.46

It does NOT modify the true value of the double, only how it is displayed.

How do we represent irrational numbers? We typically just truncate to an
approximate double. However, this means that (2/3) * 3 will not return exactly
2. It'll be slightly off because of the original approximation of (2/3).

To reset cout.setf and cout.precision, Smallberg forgets.

Negative precision would round to the nearest thousand, etc., digits in front
of the decimal point.


### Arithmetic expressions

Pronounced "air-eeth-metic" when used here as a modifier.

* /
+ -

Standard order of precedence, with parentheses to modify and control.

Note however that we must use the * operator to indicate multipliation; (2)(3)
will not produce 6.

For operators with equal precedence, e.g. - & +, the associativity here is
left-to-right; use parentheses otherwise.

Tricky: 27 / 3*3

Would produce 27, not 3. The compiler is going left-to-right and this really
translates to (27/3)*3.


### Result Types

If there is any sort of double involved (e.g. 3.0) in the
expression, then the result will be a double.

If both are ints, then the result is an int. 

*** An int divided by an int gives you an int, even if ***
*** the result is supposed to be double! ***

14.3 / 5.0 = 2.86
13.4 / 5 = 2.86
14 / 5.0 = 2.8

But:

14 / 5 = 2

and

2/3 = 0

Here, there is a remainder (i.e. a fractional part) but it's 
dropped altogether.

To get the remainder, use the modulus operator %.

14 % 5 = 4

This is useful for when we want to check evenness or oddness,
divisibility, etc., e.g. for books when we put even page numbers
in the top right, and odd page numbers in the top left. 

Note also that the determination as to whether or not
a result is an int is based only on the immediately surrounding
operands. 


### Repeating ourselves correctly

If we intend to say the same thing or do the same thing
in multiple places and we do this manually, we are asking
for errors, e.g. the hours * payPerHour calculation being
repeated in multiple places. It's too easy to accidentally
use the wrong operator, place things in the wrong order, etc.

Do the computation just once, store the result, etc. It's easier
to change the computation formula later on, etc. Use functions,
constants, variables, etc. rather than repeating literals and
mathematical expressions.

Previously: _type _identifier = _value;

In C++11: _type _identifier { _value }; for *initialization*


### Program execution

When we declare a variable without initializing it, we'll
have something like this:

_variable: [junk value]

Whatever was there before in memory will be the value of the
newly declared variable, including possibly a value
not usable as that variable's type.

Do not use *uninitialized variables* as they'll have some unknown
value. 

In this particular program, it doesn't matter, as we immediately
assign user input to the variable. 

Next, we create the earnings variable of type double AND initialize
it with the result of the computation. And so on with the rest
of the program.

What if we forgot one of the cin statements for user input?
Well, the program still executes, but now we'll be computing with
some junk value. This is *undefined behavior*: syntactically correct
but the behavior is undefined, meaning it's up the compiler for
intepretation. The compiler writers can then optimize legal code
as fast as possible. 

So here, the program might crash, produce incorrect results,
produce correct results, launch a nuclear strike, etc.
Most compiler writers choose to do the simplest action possible,
meaning it'll simply use the uninitialized variables as normal,
but if it has an invalid value unusable for doubles, then the
program may crash.

**Garbage in, garbage out.**


### More tricky arithmetic

double x = 3.1 + 14/5;

will have x as 5.1 not 5.9

The immediate operands around the /
gives an integer result even though the end expression result
is going into a double.

int a = 10;
int b = a * a;
int c = 25/(b-100);

We have division by zero!
Again: undefined behavior. It's up to the compiler as to what
to do and the result will be system-dependent, e.g. the ALU
gives different results. The program may crash, give a very
large result to c (as dividing by a number approaching zero
explodes toward infinity), etc.

double d;
double e = 2 * d;
cout << e;

d was undefined. e will (likely) be twice the garbage value.

int f = 1000;
int g = f * f * f;
int h = f * g;

1000 * a billion, producing a trillion, which is too big for 
a variable of type int. The standard specifies this as
undefined behavior. Compilers may "wrap" back to the
the minimum value like an odometer on a car past its limits.
We lose the higher-order bits and preserve just the lower-order
ones, including the ones that specify a number as negative/positive.

999999 + 1
becomes 000000 on the odometer.


### A program with strings

Specified program behavior:

[Indicates input]

What is your name? [Sir Robin]
What is your quest? [To seek the Holy Grail]
Hello, brave Sir Robin
You want To seek the Holy Grail

    #include <iostream>
    
    using namespace std;
    
    int main()
    {
        cout << "What is your name? ";
        string persons_name;
        
        
    }
    
This will not compile. Why? String is not a
primitive type; it's a class included in the 
standard library.

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        cout << "What is your name? ";
        string persons_name;
        
        
    }

This can now compile.
Note that this is <string>, not <string.h> or
<cstring>. Those are different altogether.

persons_name is currently uninitialized.
Unlike primitive types, it will actually
have a well-defined value. In this case,
a blank, empty string, because this is specified
by the class' constructor! 

*Thus, we do not need to declare string _identifier = "";*

We can just declare string _identifier;

Examples:

"Hello there" 11-character string
"8%" 2-character string
"." 1-character string

"" 0-character string --> empty string

But "     " is a 5-character string (with 5 spaces).

"Empty string" *specifically* means a string with nothing
in it whatsoever.


#### Complications with string

To read in a string (e.g. all of the user input, not just one word),
use:
    
    getline(cin, persons_name); 
    // Read a line of text into persons_name

getline(input_source, string variable) is a library function.

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        cout << "What is your name? ";
        string persons_name;
        getline(cin, persons_name);
        
        cout << "What is your quest? ";
        string quest;
        getline(cin, quest);
        
        cout << "Hello, brave " << persons_name << "!" << endl;
        cout << "You want " << quest << endl;
        
        // We don't yet know how to change the "To"
        // from the quest variable to lowercase
    }


#### Why we have <string>

Historically, C turns string literals into arrays of characters.
There is no built-in support for handling strings "properly".
We're kind of stuck with this, as we wanted to maintain compatibility
with C.


### Closing notes

Use getline() for user input of strings, etc., NOT cin.
HOWEVER, getline() won't work for numbers. It works
ONLY for strings.

int b = a * a;
int a = 10;
cout << b;

Will this compile? No, because we used 'a' before we declared it.
This is different from mathematics.



## Lecture 5: 9 October 2013

More stuff to do:

What is your name? [Sir Robin]
What is your quest? [To seek the Holy Grail]
Hello, brave Sir Robin
You want To seek the Holy Grail
If you live, next year you will be 33

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        cout << "What is your name? ";
        string persons_name;
        getline(cin, persons_name);
        
        cout << "What is your quest? ";
        string quest;
        getline(cin, quest);
        
        // We're going to have to do arithmetic
        // Inputted age + 1
        // It'll have to be a number at some point
        
        cout << "How old are you? ";
        int age;
        cin >> age;
        
        cout << "Hello, brave " << persons_name << "!" << endl;
        cout << "You want " << quest << endl;
        cout << "If you live, next year you will be " << age + 1 << endl;
        
        // We don't yet know how to change the "To"
        // from the quest variable to lowercase
    }
    
Smallberg says the above would produce

What is your name? [Sir Robin]
How old are you? [32]
What is your quest? Hello, brave Sir Robin!
You want
If you live, next year you will be 33

The program doesn't pause for the quest input and
moves on. Strangely though, I don't get this error...

UPDATE: Yup, it does happen. I just had the cin
statement after both the getline()'s.

Smallberg is doing the analogy of a little kid
learning that a light switch is controlling a light.
What about when a light bulb burns out? It takes knowledge
to not be totally confused.

Model of what happens behind the scenes:

Normally, a character is pressed and it appears on the screen.


### Operating Model

              OS Writes           OS Holds            Available to Program

You type 'x'      x                   x

You type 'y'      y                   x y

You type BS  BS space BS              x

// BS moves cursor left; space overwrote the 'y'

You type z        z                   x z

You type Enter    CR LF                                   x z newline

// Takes a carriage return character (beginning of current line) 
// and a newline character (linefeed) that moves cursor down one line
// CRLF! That's a standard line ending scheme under Windows

**Until we hit [Enter], nothing is available to the program**

This allows us to backspace and modify our input before entering it.
Otherwise, the program would have to process all the backspaces and 
associated junk.

getline(cin, s);                               [s gets "xz"; program has nothing]   

// getline() gets characters up to newline, throw away the newline,
// and put the rest into the string

getline(cin, s);                               [Program waits for user input]

You type 'w'      w                   w

You type [Enter] CR LF                                  w newline

// Program finally has characters and newline it was waiting for

[then]                                         [s gets 'w']

cin >> i;                                      [Program waits for input]

You type 3        3                   3

You type 2        2                   3 2

[Enter]           CR LF                        3 2 newline

[Then]                                         newline     [i gets 32]

                  // Takes 3, then 2, then makes 32, BUT leaves the newline alone
                  // Will gobble up whitespace characters in front, use digit
                  // characters, but LEAVE the non-digit characters like newline
                                               

getline(cin, s);                               [s gets ""]


#### Solution

**
Reading in a number followed by a string will result in string getting the
leftover non-digit characters.
**

We have to throw away the leftover characters before reading in for the string.

    cin >> age;
    [Throw away the rest of the line]
    
    ...
    getline(...)
    
To do so:

    cin.ignore([], [])

cin.ignore(,'\n')

Throw away until newline character or until you've thrown away a certain
number of characters, *whichever comes first*.

For us, just put a big number, because we want to toss stuff till the 
newline, so that we don't accidentally not throw everything out
that we need to.

***Reading in a number, then a string? USE cin.ignore after cin***

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        cout << "What is your name? ";
        string persons_name;
        getline(cin, persons_name);
        
        cout << "What is your quest? ";
        string quest;
        getline(cin, quest);
        
        // We're going to have to do arithmetic
        // Inputted age + 1
        // It'll have to be a number at some point
        
        cout << "How old are you? ";
        int age;
        cin >> age;
        cin.ignore(10000, '\n'); // Toss rest of line
        
        cout << "Hello, brave " << persons_name << "!" << endl;
        cout << "You want " << quest << endl;
        cout << "If you live, next year you will be " << age + 1 << endl;
        
        // We don't yet know how to change the "To"
        // from the quest variable to lowercase
    }

Another solution:

    cin >> age;
    string junk;
    getline(cin, junk);
    
Because getline() will throw away newline characters

This suggests "junk" is a significant string though.


### The IF Statement

if (condition)
    statementIfConditionTrue;
else
    statementIfConditionFalse;


### Boolean Operators

<
<=
>
>=
!= [Not equal]
== [Equal to]

***Remember to consider the equal case***

If something is on the boundary of less/greater than,
how will we handle it?


### Compound Statements

Also known as *blocks*.

{
...;
...;
...;
}

Or { ...; ...; ...; }

Remember: C++ doesn’t care about whitespace


### More If Statements

    if (string == "")

is possible, apparently,
as well as comparing strings in general.

    if (persons_name == "")
        cout << "You didn't enter a name!" << endl;
        
The *else* statement can be omitted if we don't want to
anything to happen unless the *if* statement is triggered.

Example with earnings calculator:

Instead of:

    if (payPerHour >= 12.00)
    ...
    else
    ...
    
Where the result differs only in the amountWithheld calculation,
then instead of a full if-else statement, we can use the 
ternary conditional operator:

    (condition) ? expression1 : expression 2;

    if (...)
        variable declared here;
        
    cout << variable_just_declared_used;
    
Compiler error. The variable declared inside the IF statement
is limited in scope. 

The declaration should happen outside and *before* the control statement.


### Assignment Statements

When we have a variable previously declared and now we want to
give it a value, we *assign* data to the variable.

_identifier = _value;

Remember that this is a left-associate statement. It only assigns,
not changing the value of what is on the right side of the
assignment. This is different from what is the case in math.

Another thing. If we have:
    
    n = 1;
    m = 2;
    n = m * 2;
    m = 5;
    
Unlike spreadsheet formulas, *n* will not change value just
because *m* changed. ONLY *m* changed here.

Statements are not revisited; there is no history to the variables.
Only the immediate operations and currently stored values matter.



## Lecture 6: 14 October 2013


### Improving the Earnings Calculator

We want to avoid magic numbers, something arbitrary that could
change according to requirements. Typically 1 or 0 are not
arbitrary.

The problem is dealing with magic numbers buried deep in a 
program where they're scattered everywhere. If we have
updated requirements, we'd have to find *all* of them
and change them by hand.

So, we give the magic numbers names (identifiers)
and use that variable whenever we need that number.


    How many hours did you work? 40
    What is your hourly rate of pay? 12.13
    You earned $485.20
    $48.52 will be withheld
    
    ======================================================
    
    #include <iostream>
    using namespace std;
    
    int main()
    {
       const double PAY_RATE_THRESHOLD = 12.00;
       const double HIGH_WITHHOLDING_RATE = 0.10;
       const double LOW_WITHHOLDING_RATE = 0.05;
    
         // Gather work data
    
       cout << "How many hours did you work? ";
       double hoursWorked;
       cin >> hoursWorked;
    
       cout << "What is your hourly rate of pay? ";
       double payRate;
       cin >> payRate;
    
         // Compute and print earnings
    
       double amtEarned = hoursWorked * payRate;
       cout.setf(ios::fixed);
       cout.precision(2);
       cout << "You earned $" << amtEarned << endl;
    
         // Compute and print withholding

       double withholdingRate;
    
       if (payRate >= PAY_RATE_THRESHOLD)
          withholdingRate = HIGH_WITHHOLDING_RATE;
       else
          withholdingRate = LOW_WITHHOLDING_RATE;
    
       cout << "$" << withholdingRate * amtEarned
            << " will be withheld" << endl;
    }

Now, it's easy to change the numbers as needed. 
We change them in *just one place*.


### Constants

Next, we make them **constants**; if we ever
try to change them after they've been declared
and initialized will trigger a compilation
error. To change the program at a later time,
the source code will have to be modified. This is
why we typically list constants toward the top of
the program.

This particular type of constant is known as a
**symbolic constant**.

Note also that constants are typically in 
*all-caps*.


### Nested If Statements

string citizenship;
int age;
...

if (citizenship == "US")
    if (age >= 18)
        cout << "You can vote in US elections" << endl;
    else 
        cout << "You are not a US citizen" << endl;
    
We see the intent here, but it doesn't work for all
cases. Why? Because the else is paired with the top level if.
It's ambiguous how it should be interpreted. Note that
curly braces are very much needed.

Else statements are paired up with the *nearest if statement*
*not enclosed in curly braces*.

One way to resolve the above

    if (...)
        if (...)
            ...
        else
            ;
    else 
        ...
    
Better way:

    if (...)
    {
        if (...)
            ...
    }
    else 
        ...

When we have nested if-else statements, etc., use curly braces.
Use them anyway if in doubt but be aware that they do enclose
off that block.


### And & Or


#### The OR Operator

Example:

    if (citizenship == "US" || citizenship = "Canada")
        cout << "The country code is 1" << endl;

Syntax:

    expression1 || expression2
    
OR is TRUE if expression1 OR expression2 are TRUE.

Both expressions must be *complete* and able to stand by 
themselves, e.g. NOT (var == value1 || == value2)
or (var == value1 || value2).

Both operands must be evaluable to true or false.

Warning also on: (age == 18 || 19 || 20)
which will always be true, as it sees "age == 18", goes
"Okay", but in C/C++, 0 is FALSE, and non-zeroes are treated
as TRUE. 19 and 20 will always be TRUE to the compiler.

Thus: (true/false || true || true), no matter what the age is.


#### The AND Operator

Example:

    if (citizenship == "US" && age >= 18)
        cout << "You can vote in US elections << endl;
        
Syntax:

    expression1 && expression2
    
AND is TRUE if expression1 AND expression 2 are TRUE.

If *either one* is FALSE, the AND statement is FALSE.

And again, we need complete expressions, we cannot
shortcut.

DO NOT: if (age >= 18 && <= 20) // Compilation error

DO NOT: if (age >= 18 && 20) // Right side always true

DO NOT: if (18 <= age <= 20) // Always true

The compiler associates left-to-right. 
Is true/false <= 20? True/false is 1 or 0. 
This is seen as ((18 <= age) <= 20),
which is (1 <= 20) or (0 <= 20)


### More Caveats

int n = 17;
cout << "n is " << n << endl;

if (n = 0) // Will compile, because it sets n to zero!
           // This isn't a test for equality
    cout << "n is zero" << endl;
else
    cout << "n is not zero, it is " << n << endl;

Trace:

n is initialized to 17
"n is 17"
n is assigned the value of 0
if evaluates to true because an assignment will return
    the newly assigned value. so if (0)
"n is not zero, it is 0"

I love this example program, haha.

With numbers, mistakes like these often will compile
and slip by compiler checks.

    if (rating < 1 || rating > 10)

is NOT opposite to

    if (rating > 1 || rating < 10)
    
What about:
    
    if (rating >= 1 || rating <=10)
    
The latter two will always be TRUE in fact.

The opposite of < is >= and > is <=

Thus we actually need an AND:

    if (rating >= 1 && rating <= 10)
    
    
#### De Morgan's Laws

    not(A or B) =opposite=> (not A) and (not B)
    
    not(A and B) =opposite=> (not A) or (not B)
    
    
Extended:

    not (a < b)  --> a >= b
    not (a <= b) --> a > b
    not (a > b)  --> a <= b
    not (a >= b) --> a < b
    
In English, we might say "not something OR something",
but we really mean "not something AND not something".

In code, we are **explicit**.

Something like this:

    if (age != 18 || age != 19)
    
is always true. Even if someone is 18, he/she is still
not 19 and vice versa.


### Handling Value Ranges

Example:
    
    if (income < 30000)
        cout << "Low";
    if (income > 30000 && income < 100000)
        cout << "Middle";
        
// Well, we accounted for the &&, but not the
// threshold itself.

It should be:

    if (income < 30000)
        cout << "Low";
    if (income >= 30000 && income < 100000)
        cout << "Middle";
    if (income >= 100000 && income < 500000)
        cout << "High";
    if (income >= 500000)
        cout << "Very high";
        
This is one way to write this, but it has a lot of repetition,
positive and negative forms of statements. It's easy to make
mistakes here: test against wrong numbers, add an extra zero, etc.

Why bother repeating if tests if only one case is ever going
to be true.

    if (income < 30000)
        cout << "Low";
    else
    {
        if (income >= 30000 && income < 100000)
            cout << "Middle";
        if (income >= 100000 && income < 500000)
            cout << "High";
        if (income >= 500000)
            cout << "Very high";
    }

This is an amateurish attempt.
Further optimization possible. See that income >= 30000?
It's not needed; we can't get to the else branch unless
the if branch was false, meaning income was at least 30000.
There's no need to repeat the test.

    if (income < 30000)
        cout << "Low";
    else
    {
        if (income < 100000)
            cout << "Middle";
        if (income >= 100000 && income < 500000)
            cout << "High";
        if (income >= 500000)
            cout << "Very high";
    }

Remember that *the order* of if, else if, and else statements
*matters*.

    if (income < 30000)
        cout << "Low";
    else
    {
        if (income < 100000)
            cout << "Middle";
        else
        {
            if (income < 500000)
                cout << "High";
            if (income >= 500000)
                cout << "Very high";
        }
    }

Now we're nesting and eliminating another test rendered redundant
by the branching structure.

    if (income < 30000)
        cout << "Low";
    else
    {
        if (income < 100000)
            cout << "Middle";
        else
        {
            if (income < 500000)
                cout << "High";
            else
                cout << "Very high";
        }
    }

And finally, the last and only condition that could be true
is a very high income.

Now each test is done only once.
Compare to: 

    if (income < 30000)
        cout << "Low";
    if (income >= 30000 && income < 100000)
        cout << "Middle";
    if (income >= 100000 && income < 500000)
        cout << "High";
    if (income >= 500000)
        cout << "Very high";
        

#### Derivation of Else if

However, heavy nesting is hard to interpret.

The style for nesting recalls that

    if (income < 500000)
        cout << "High";
    else
        cout << "Very high";

is a single statement.

Thus gives us:

    else if (income < 500000)
        cout << "High";
    else
        cout << "Very high";

This is the derivation of ELSE IF! :D

    if (income < 30000)
        cout << "Low";
    else if (income < 100000)
        cout << "Middle"; 
    else if (income < 500000)
        cout << "High";
    else
        cout << "Very high";
        
Sometimes known as an **if ladder**,
very handy for conditions related
to regions and sub-regions of a range
of values, etc.

But remember to **test them in-order**,
whatever that order should be.

Again, compare to:

    if (income < 30000)
        cout << "Low";
    if (income >= 30000 && income < 100000)
        cout << "Middle";
    if (income >= 100000 && income < 500000)
        cout << "High";
    if (income >= 500000)
        cout << "Very high";
        
Consider also:

    if (income < 30000)
    {
        cout << "Low";
    }
    else if (income < 100000)
    {
        cout << "Middle"; 
    }
    else if (income < 500000)
    {
        cout << "High";
    }
    else
    {
        cout << "Very high";
    }

Or even:

    if (income < 30000) 
    {
        cout << "Low";
    }
    
    else if (income < 100000)
    {
        cout << "Middle"; 
    }
    
    else if (income < 500000)
    {
        cout << "High";
    }
    
    else
    {
        cout << "Very high";
    }


### 

Example:

    int main()
    {
        ...
        int choice;
        cin >> choice;
            ...
        if (choice == 1)
            ...
        else if (choice == 2 || choice == 4)
            ...
        else if (choice == 3 || choice == 5)
            ...
        else
        {
            cout << "Choice must be 1 through 5. Goodbye" << endl;
        }
        ...
    }
    
Problem: We continue onward despite the error message.
We want to terminate the program immediately after encountering
an error that would preclude logical continuation.
        
So:

    else
    {
        cout << "Choice must be 1 through 5. Goodbye" << endl;
        return 1;
    } 

A return here means a return for main(), which will end the program
immediately, meaning we never get to the code after it.

Back to the new if ladder we just got.

We're testing some number for exact equality against constants,
which is perfect for switch!


### Switch statements

Syntax:

    switch (choice)
    {
        case (constant1):
            ...
            break;
        case (constant2):
            ...
            break;
        case (constant3):
        case (constant4):
        case (constant5):
            ...
            break;
        default:
            ...
    }
    
It'll check choice agains the case
constants. "break" indicates an exit
from the switch statement.

What about when there isn't a break 
immediately following the case label?

It keeps going until it hits the
next break, which means 3, 4, and 5 will
all result in the same statements being
executed. This may be referred to as
"falling-through"

What about when an inputted choice doesn't
match any of the case labels? It'll go to
the default case, which is at the end.

Once we hit the end of the switch, we exit it
and continue with the rest of the program.

Switch statements cannot be used for ranges:
no Boolean operators. They do not work with
strings, doubles, etc. Integers are the name
of the game for switches.


### While Loops

We want to repeat something based upon a condition.

So:

    ...
    cout << "How many times do you want to be greeted?" << endl;
    int nTimes;
    cin >> nTimes;
    
    int n = 0;
    while (n < nTimes)
    {
        cout << "Hello" << endl;
        n = n + 1; 
        // n += 1;
        // n++;
    }
    
While n is less then specified number of times, it'll
do actions so ordered in the while statement.

How does it work for the last one? Well, the incrementation
or decrementation operation doesn't happen until the actions
are done. And thus it finishes one last time before the condition
goes false. 3 times where counter starts at 0 means "0, 1, 2"
in the counter--count 'em, 3 times!

It should be noted that the counting variable needs to be
declared before the while loop. I believe a variable
declared for counting inside the while loop might not work
as it would be restricted in scope. Let's see.

Yes, the counting variable must be before the while loop,
as it doesn't exist before the while loop starts otherwise.



## Lecture 7: 16 October 2013


### Compound Assignment Operators

n = n + 7 --> n += 7;

k = k * 2 --> n *= 2;

n = n / 10 --> n /= 10;

k = k - (3 * n) --> k -= (3 * n);

These make arithmetic expression writing
a lot faster.

Example:

    employee[current]->salary = employee[current]->salary*1.10;
    
This is an array, pointer, etc. It's annoying to write.
Much less annoying:

    employee[current]->salary *= 1.10;

// I find it remarkable how Smallberg's voice is able to reach
// the whole lecture hall


### Increment and Decrement Operator

Even lazier: 

n++;

++n;

There *is* a difference between prefix and postfix/suffix forms.

--> n += 1;
--> n = n + 1;

Similarly:

n--;

--n;

--> n -= 1;
--> n = n - 1;


### Common Looping Errors

If we use <= or >= than the counter,
and *n* is the specified number of loops,
then the loop will actually run *n+1* times,
because the final increment will satisfy
the "or-less-than" part of the Boolean operator.

To take care of this, start *n* at 1.

The counter can represent either the number of times it has
run (start at 0, use >, <), or what run iteration it will be 
(start at 1, use >=, <=).

Otherwise, we have a *off-by-one-error* or *fencepost error*.
(One time too many or too few).

Explanation: Let's say we're passing fenceposts and there's
posts 100 feet apart. We go 500 feet and will see *6* posts,
not 5. It demonstrates how quick reasoning can fail us.

Be careful and *be consistent*.

**ALWAYS:**

* Check starting count

* Check condition

* Check that loop will terminate

* Trace-through the loop manually for a few iterations


### Do While Loops

With a regular while loop, the loop will never run
if the condition is never satisfied.

With a **do-while loop**, it will always run *at least once*.

Syntax:

    do
        statement;
    while (condition);
    
Do NOT forget the semicolon. With code scrolled up, it
may look like the beginning of another while statement.

Suggestion:

    do
    {
        ...
    } while (...);
    
Example:

    int n = 0;
    do
    {
        cout << "Hello" << endl;
        n++;
    } while (n < nTimes);
    
Trace-through:

* Initialize n to 0

* Do the statements.

* Test while (condition)

* Continue/not continue loop

Unlike a while statement, the do { } statements
will always run at least once, including when
the while (condition) is not satisfied at the beginning.

According to Smallberg, do while loops
are quite rare as we usually want to check the condition
beforehand. 

Application: if we find ourselves thinking do while
is the only way to solve something, it's likely that
there's an easier and more conventional way to solve
it using more common loops like while and for.


### More Looping Errors

What if we had a while loop that executes a lot of statements?

Stylistic issue: to understand a particular while loop's control
mechanism, we have to look in two places: at the very bottom 
and at the very top.

Worse: It's easy to forget the increment/decrement operator
at the end of all that code and bang--we probably have an
*infinite loop*, which besides stealing resources, means
we never get to the rest of our program.

Haha, Smallberg actually asked the symptom of an infinite
loop: a bunch "Hello"'s for example.

FAR more pernicious and subtle: a loop doing calculations
and internal manipulations again and again. The program 
would likely hang, drain battery, etc.

This can be hard to debug: can't accept input, calculations
are taking too long. But if it's remote, the server's fans
kick up, not yours.

To interrupt an infinite loop: close the window, Ctrl-C,
etc.

Loops in general: we have the goal of making the terminating
condition true; every iteration should work toward that goal.


### For Loops

Example:

    for (int n = 0; n < nTimes; n++)
    {
        ...
    }
    
Syntax:

    for (initialization; stay-in-loop condition; prepare-for-next-iteration)
    {
        statements;
    }
    
For the initialization step, we can either use a previous
variable, or declare and initialize a new one. Note, however,
that the new variable will be restricted in scope and lifetime
to that particular loop. This makes it easy to reuse a common
for loop counter variable again and again, e.g. c, n, i, etc.

Trace-through:

* Initialize counting variable or refer to previously declared one

* Check against the condition for continue/not continue

* Execute the statements

* Prepare for the next iteration (increment/decrement the counter)

As before, watch out for initializing to 0 or 1, the Boolean operator
in the condition, and the iteration preparation step (e.g., if it
was multiply/divide instead of add/subtract)

Microsoft is lame:

    for (int n = 0; n < nTimes; n++)
    {
        ...
    }
    
    cout << n << endl; // Error in standard C++; Visual C++ allows this
    
This is because of how some legacy code is. We should **not** do this,
as we'll be using multiple compilers, which will not allow this behavior.


#### Form options of for loop

Form 1:

    for (int n = 0; n < nTimes; n++)
    {
        ...
    }
    
Form 2:

    int n;
    for (n = 0; n < nTimes; n++)
    {
        ...
    }

Form 3:

    int n = 0;
    for ( ; n < nTimes; n++)
    {
        ...
    }
    
// Side-note: experimenting in CS is very easy and quick.
// Curious? Just try it and see what happens!
// This is the Hacker Way!


#### Practice

What does this do?

    for (int k = 10; k >= 0; k--)
        cout << k << endl;
        
This will print:

    10
    9
    8
    7
    ...
    1
    0

Why 0 too? Because 0 >= 0

What about:

    int k;
    for (k = 10; k >= 0; k--)
        cout << k << endl;
    cout << "The final value of k is " << k << endl;
    
This would produce:

    10
    9
    8
    7
    ...
    1
    0
    The final value of k is -1
    
Why -1? Because the for loop isn't false (and thus terminated)
until we have k < 0 to no longer satisfy k >= 0.

But what about?

    int k;
    for (k = 10; k > 0; k--)
        cout << k << endl;
    cout << "The final value of k is " << k << endl;

    10
    9
    8
    7
    ...
    1
    The final value of k is 0
    
The difference? The condition. **Always consider the threshold case**

Consider what we want/need and how to accomplish it.

Another example:

    for (int = 1; p < 1000; p *= 2)
        cout << p << endl;
        
This is 2^n toward 1000.


### For vs. While

Choose a for loop when prepare-for-next iteration
is simple and related to the stay-in-loop condition.

Choose a while loop when preparation is many steps
and unrelated to the stay-in-loop condition.


### A Starry Rectangle (Nested For Loop)

Let's say we wanna generate something like:

    ****
    ****
    ****
    
And later, we'll write code that can resize this easily.

Pseudo-code:

    // r is row number
    
    for (int r = 1; r <= 3; r++)
    {
        ...print out the rth row;
    }
    
But what about the number of stars per row?
This requires a nested for loop!

    // r is row number
    
    for (int r = 1; r <= 3; r++)
    {
        for (int s = 1; s <= 4; s++)
            cout << "*";
    }

This alone will not produce 3 rows of 4 stars.
It'll produce 12 stars on one line!

Why? A group of 4 stars (done by inner loop) is
printed out 3 times (done by outer loop). Loops
of loops: repetition of repetitions. We group
together repetitions when we do nested for loops.

What about where cout << endl; is placed?

    // r is row number
    
    for (int r = 1; r <= 3; r++)
    {
        for (int s = 1; s <= 4; s++)
            cout << "*";
    }
    cout << endl;
    
Here, the newline is after a line of 12 stars:
    
    ************
    

How about:

    // r is row number
    
    for (int r = 1; r <= 3; r++)
    {
        for (int s = 1; s <= 4; s++)
            cout << "*" << endl;
    }

Actually produces:

    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    
Correct placement:

    // r is row number
    
    for (int r = 1; r <= 3; r++)
    {
        for (int s = 1; s <= 4; s++)
        {
            cout << "*";
        } 
        // Use the curly braces to avoid confusion
        cout << endl;
    }

This means a row of 4 stars, then a newline,
then repeat the row-of-stars-writing.

How many times is a statement executed?
Multiply the count of its enclosing loop
times any outer loops.

Example: circuits in tennis where we do suicides
multiple times during each round. Suicides end
up being done (rounds * suicides rounds) times.

Considerations:

* What should be done once.

* What should be done each time with the inner loop?

* What should be done each time with the outer loop?


### A Dangling String

Let's get a string and output it vertically:

    H
    e
    l
    l
    o
    
Let's assume here that we already have the string.

    string s = "Hello";
    
This would take treating the string as an array, I think...

    for (int k = ...; ...; ...)
        cout << ... << endl;

How is the string stored? Each character is stored and has a position
or *index number*, starting at 0 for the first character. The final
character thus has index number n-1, where n is the number of characters.

01234
Hello

With this loop, we need to write out the character at position
k of the string s.

    for (int k = 0; k <= 4; k++)
        cout << s[k] << endl;
        
Here, the condition must include 4 if we want s[4].

Alternatively:

    for (int k = 0; k < 5; k++)
        cout << s[k] << endl;
        
Even easier:

    for (int k = 0; k != s.size(); k++)
        cout << s[k] << endl;
        
s is a string. k is an integer.
s[k] means "the character at position k of s" (positions start at 0).

Consider how this relates to math where we have a sequence
and then number its elements with subscripts, e.g. a1, a2, a3, etc.

Here, the [] indicates a subscript.

We often say "s sub k"

**Undefined behavior:** s[k] when k is not a valid position; This is
*walking off the array* and might lead to accessing memory used by other
programs, our program crashing, our program throwing an exception, etc.
It depends on the system environment.

Do not think that accessing the position one after the string does **not**
guarantee that we'll magically get a zero-byte. This is not true in C++.

Make *no assumptions* about what comes before or after.


### .size()

.size() will act on a string and give its number of characters.
This is useful for these for loops, as the number of characters - 1
will be the limit of the size of the array as we begin indexing at 0.
It'll terminate (if we set it correctly!) when it's greater than
or equal to the size.


### Counting Letters

Example:

    cout << "Enter some text: ";
    string t;
    getline(cin, t);
    
             111111
   0123456789012345   
t: Everyone, hello!

    int count_Es;
    for (int k = 0; k != t.size(); k++)
    {
        if (t[k] is an uppercase E || t[k] is a lowercase e)
        {
            increment count of e's;
        }
    }
    cout << "The number of E's (upper and lower case) is " << count_Es << endl;

To check upper or lowercase: Use 'E' or 'e' with Boolean equality check.

Remember: "stseoprjeowr" --> string; 's' --> character.



## Lecture 8: 20 October 2013


### Reminders

Accessing outside of an array is **undefined behavior**.
What the program does will vary but it probably won't
be good.

In the standard Visual Studio debug configuration,
it will check for any walks off the array with an
"out-of-range" error. g++, with all the extra
warnings turned on, will do the same, *but* Xcode
doesn't necessarily give any of the warnings.


### Characters

New data type: characters.

They *cannot be empty*. Unintialized
characters will have a garbage value.

To get a char from a string, we can just use specify
the element in the sequence of characters.

    string s = "String";
    
    char c = s[0]

Note that:

    string s = "C"; // This is fine
    
    string s = 'C'; // This is NOT fine.
    
    char c = "S"; // NOT okay either; different types
    
Escaped characters like '\n' or '\t' are
characters too and can be stored in variables
of type character. 

Backslashes *escape* a character, and escaped
characters will be treated as a single character.

They're needed for when we want literally write out
things like double-quotes, backslashes themselves, etc.

Single-quotes inside of double-quotes do not have
to be escaped however.


### String Comparison Caveats

Right way:

    if (t[k] == 'e' || t[k] == 'E')
    
Wrong way:

    if (t[k] == 'e' || 'E')
    
This will compile. Why? Characters
and integers can technically be mixed,
with the compiler using the integer encoding
of the character. And again, non-zeros
are treated as true.

Thus: ( anything || true) will always be true.


### Phone Number Check

Scenario: Whoo, hot person just gave me
a phone number! Let's check if it's a valid phone
number, using the one rule: if it's 10 digits long.


    #include <iostream>
    #include <string>
    #include <cctype>
    using namespace std;
    
    int main()
    {
        cout << "Enter a phone number: "
        string num;
        getline(cin, num);
        
        int count_digits = 0; // Counter
        
        // Count number of digits
        for (size_t c = 0; c != num.size(); c++)
        {
            // To check: isDigit. Options:
            // A long OR statement.
            // A switch statement
            // Or, just use the std library:
            
            if (isdigit(num[k]))
                count_digits++;
        }
        
        if (count_digits != 10)
            cout << "A phone number must have 10 digits"
                    << endl;


### Helpful Standard Library Functions

The standard library function is:

    isdigit(single character)
    
and returns TRUE if the argument is a digit, or vice versa
FALSE.

We'll need <cctype> for isdigit().

Other useful functions:

    islower(single character) --> is lowercase 
    isupper(single character) --> is uppercase
    isalpha(single character) --> is in the English alphabet

Use the unary NOT operator (!) to check if false, etc.

A good spacing for it:

    if ( ! isdigit(num[k]))
    
This emphasizes the not.

Consider if there is an alternative way to
write it without using the NOT operator.
It's typically used for reversing functions
returning Boolean values.

Always strive for the clearest expression
possible.

Remember also that:

    if (1 <= x <= 10)
    
Does things with C++'s associativity rules.

"Is 1 less than or equal to x?"

Then: "Is True/False (1/0) less than or equal to 10?"

Yes, always, thus rendering it always true.


#### A Comprehensive List

    isdigit(char) --> true if char is a numerical digit
    islower(char) --> true if char is a lowercase letter
    isupper(char) --> true if char is an uppercase letter
    isalpha(char) --> true if char is in the English alphabet
    tolower(char) --> gives lowercase equivalent of char
    toupper(char) --> gives uppercase equivalent of char
    .substr(int, int) --> cuts a substring. First int is starting
    position; second one is how many to go forward. To get the
    last set of something: .substr(3, .size()-3) [cuts the remaining]
    
Both tolower() and toupper() will leave things that don't
need to be changed alone, including non-alphabetical characters
like '?'.

We can now write functions that will convert things to
Title Case, Sentence case, lowercase, UPPERCASE, etc.

Awesome!

Example:

    string s;
    getline(cin, s);
    s[0] = toupper(s[0]);
    
    // Note that we re-store the new value in the
    // original place
    
Caveat: What if it's an empty string? toupper() on
an empty string (there are no valid positions)
is *undefined behavior*. Sometimes, things even
work with undefined behavior, but more often not.

**Never rely on undefined behavior**

Check for this always!

    if (s != "")
        ...

Or:

    if (s.size() > 0)
        ...


### Mistakes Possible

If we just do:

    ...
    toupper(s[0]);
    
Then all we get an uppercase equivalent
of s[0] and we don't do anything with it.
The value is a throwaway one. Re-assign
the original variable.

Creative check:

    if (toupper(s[0]) == 'E')
        ...
        
Only true if s[0] is 'E' or 'e'

Just calling functions by themselves
won't always do what we intended.


### Functions

Analogy of cookbooks, which will have
subsequences of instructions held elsewhere,
e.g. "make icing" is a whole set of instructions
onto its own. This also allows us for to reuse
sets of instructions, store them separately,
etc.

Execution order:

* main()
* Stuff in main, including other functions

When we want to use a function, we "call" it
or "invoke" it by writing:

    _functionIdentifier();
    
Remember that functions don't return anything
are given the return type "void".


#### Prototypes

Typically, we might want to put main() first
than all the functions and their definitions,
but without all the implementation details of 
getting in the way of readibility.

So:

    return_type prototype(formal parameters);
    
    main()
    {
        ...
    }
    
    return_type definition(formal parameters)
    {
        ... // Implementation
    }
    
Make sure that the prototype and definition
declarations of the functiona are identical.


#### Parameters and Arguments

Rather than repeat code that is quite similar
again and again (e.g. icing with different flavors),
we call the functions and pass different arguments
that are compatible with the function's specified
formal parameters.

Terminology: parameter is the placeholder; argument
is what is actually used.

Example:

    
    void greet(int n)
    {
        for (int k = 0; k < n; k++)
        {
            cout << "Hello" << endl;
        }
    }

Now we can write out "Hello" however many times we
want.

Remember also rules on variable scope and lifetime.
Both are limited unless they're global variables
(which we try to avoid using).

Here's the greet() function with a second argument:

    void greet(int n; string greeting)
    {
        for (int k = 0; k < n; k++)
        {
            cout << greeting;
        }
    }
    
Note that this function doesn't try to get
user input as well. *Because* it does *less*,
this will allow us to reuse this function in
far more places and this affords us more flexibility
in our use of it, e.g. maybe we have other functions
to modify/reformat the inputted greeting before we
repeatedly output it.

Note also: **arguments must be in the order of parameters**.
Otherwise, we're likely trying to pass the wrong
argument data types.

Similarly, we must have the same number of arguments,
unless we've overloaded the function and have another
function ready to accept the different number of 
arguments.


#### Returning Values

When we do have a return value required,
we'll need a return statement somewhere in the function,
and the returned value is the answer to the function
call. 

In fact, the original function call is replaced with
its return value, allowing us to call functions as
arguments for other functions!

Example:

    int square(int k)
    {
        return k * k;
    }
    
    int main()
    {
        int x = square(2);
        int y = 3 * square(x + 1) + 2;
        ...
        greet(square(x), "Hello");
        ...
    }


### Random Header

Hello world! [This resets Markdown's (or perhaps
Texastic's) inability to jump header levels]



## Lecture 9: 23 October 2013


No limit to how deeply we can nest function 
calls within arguments and what-not.

All we need before we call a function is its
declaration; the definition can come after other
definitions that might call it even.

bool isdigit(char c)
{
   if (...)
        return true;
    else
        return false;
}

But the if statement itself is true/false,
meaning we have if true, return true, else
false, return false.

Better:

return (Boolean expression);

That's awesome!

How do we return true and false?
A Boolean, named after Geroge Boole 
(1800s British maths dude).
It can only hold TRUE or FALSE.


### Example Program with Functions

User dialog:

    Enter a phone number: (310) 825-4321
    The digits in the number are 3108254321
    
This extracts the digits, letting us 
re-punctuate them as we like. Then,
we can also check the phone number's validity,
as before.

To make things much easier, we can split
things up into functions.

Remember: code incrementally and test constantly!
Just put in placeholder code and insert the
actual implementation later on.

    #include <iostream>
    #include <string>
    #include <cctype>
    
    using namespace std;

    string extractDigits(string number);
    bool isValidPhoneNumber(string number);

    int main()
    {
        cout << "Enter a phone number: ";
        string phone;
        getline(cin, phone);
        
        if (isValidPhoneNumber(phone))
            cout << "The digits in the number are "
                    << extractDigits(phone) << endl;
        else
            cout << "A phone number must have 10 digits" << endl;
    }
    
    string extractDigits(string number)
    {
        string digits;
        
        for (size_t k = 0; k != number.size(); k++)
        {
            if (isdigit(number[k]))
            {
                digits += number[k];
                // OR: digits[k] = number[k];
                
                // Note the difference:
                // The first appends the character
                // to the end of the first character
                
                // This works ONLY BECAUSE
                // the standard library implements
                // += like that for string;
                // Right-hand side must be a string
                // or a character, no ints, etc.
                
                // The second changes the string 
                // element by element.
            }
        }
        return digits;
        // Will return empty string if no digits
        // We should account for that
    }
        
        
    // Returns true if valid phone number (10 digits)
    bool isValidPhoneNumber(string number)
    {
        int count; // Count number of digits
        
        for (size_t k = 0; k != number.size(); k++)
        {
            if (isdigit(number[k]))
                count++;
        }
        
        if (count == 10)
            return true;
        else
            return false;
            
        // Or, if (...)
        //          ...
        //     return false;
        // Because we can't get to the end unless if was false
        
        // Best of all:
        
        // return (count == 10);
        
        // This evaluates the Boolean expression
        // and returns its result: true or false
             
    }
    
Another implementation: 

    return extractDigits(phone).size() == 10;
    
This works, but from performance stand-point,
we are calling extractDigits() twice, which
slows stuff down. 

It's less code though!
    
Here, we might have undefined behavior. Why?
Because we need to return something in *every* case.
What if count is less than 10? On most systems,
we'll continue execution but the returned value
will be some random bit battern.

Most compilers will warn us that we don't return
a value in every case: "Control reaches end of
non-void function".

For testing these functions individually,
the class test driver will test each one individually.

// Confirmed the above program as working
            
       
#### Note on Boolean-returning function style

Notice the style of bool-returning functions:
there tends to be a predicate, e.g. isAwesome(),
hasNoProblems(), existsIn(), etc.

#### Appending Strings

s+= c; where c is a character

s.append(c);

s.push_back(c); C++11


#### Design Paradigms

Here, we went top-down, starting with main()
and then implementing functions as needed.

Another option is to go bottom-up,
as I am with Project 3, and create
components as needed, test them individually,
then bring them together to create the ultimate
end-goal.


### Another example program

We want Polar to Cartesian coordinates convert.

Recall that polar coordinates indicate an angle theta
from 0 and a distance rho from the origin.

x = rcos(theta)
y = rsin(theta)

**<cmath> includes functions like cos() and sin()!**

    #include <iostream>
    #include <cmath>
    
    using namespace std;
    
    void polarToCartesian(double rho, double theta, double x, double y);
    // Declare the function
    
    
    int main()
    {
        double r;
        double angle;
        double x;
        double y;
        
        
        // Get values for r and angle
        
        polarToCartesian(r, angle, x, y);
        // Why are we passing x and y as arguments?
        
    }
    
    void polarToCartesian(double rho, double theta, double xx, double yy)
    // Don't forget to remove the semicolon when copy-pasting a
    // function's declaration
    {
        xx = rho * cos(theta);
        yy = rho * sin(theta);
        
        
    }
    
    
    
Functions can only return one value.
This alone shows how we shouldn't try to do
too much with any one particular function.

Here, we want x and y from the r and angle
inputs.

Solutions possible:

Declare a function returning a type void
that does the stuff we want it to.


#### Passing-by-value

When pass arguments to a function,
we often set-up the function such that it
takes arguments and uses them to initialize
its parameters for manipulation.

The computation is correct, but we didn't do anything
We made copies of the arguments into the parameters
known as passing-by-value, but we didn't change the
original variables outside the function.

So we want a placeholder name for caller's argument.
This is why we have x and y as arguments, so that
we don't create new ones.


#### Reference-to types

Example:

    double&

This a reference-to-double. 

Some people do <type> & <identifier>

Others do <type> &<identifier>

A reference is another name for an already-existing
object.

Now, xx and yy are passed-by-reference; they are 
other names for existing objects in the caller.

The third and fourth arguments to the polarToCartesian()
call were x and y. Now, because the prototype has the parameters
accepting arguments as pass-by-reference, *we now change*
*x and y, because xx and yy are referring to the same*
*piece of memory*.

This also resolves my previous struggles with dealing
with variable scope issues, e.g. **functions trying to change**
**variables declared in main().**

Previously, we'd been making copies of everything.

Example: a guy in Sacramento named Jerry Brown, the governor
of California. Two different names, but they refer to the
same person!

Example: the state constitution says "the Governor",
referring to the current governor. We don't make copies.

Now, when we leave the function, 
x and y have still been changed,
even though the parameters are now gone.

**When we need to change something,**
**we should it pass it by reference**

We can see the arguments passed as:

(input, input, output, output)

Meaning take these inputs, and do things with 
the output parameters,

    extractWord(string& text)

Pass that string by reference. Use type&
for reference-to-<type>.

**cos() and sin() take arguments in radians!**

WATCH OUT FOR THIS and create functions
to convert as necessary and advise the user.


### Looping for correct input

Instead of a while or do-while loop checking
the input to be acceptable, we can 
use *break* to leave the nearest enclosing loop
or switch statement.

    for(;;)
    
We always go into the for loop, and set breaks
manually within the loop. Just make sure
there's always a way out, e.g. if-else leading
to a break.

This is sometimes called an *N-and-a-half-times loop*
because we leave it in the middle.


### Break



## Lecture 10: 28 October 2013


### Continue statement

Abandons rest of current iteration
of loop, but does not break out
of the loop altogether.

This avoids a heavily indented if-ladder.

Break goes to right after the curly brace
enclosing the loop. Continue is like going
to right before it, *inside the loop*.


### Pass-by-reference continued

Pass-by-ref is useful:

we can just call a reference and modify
a variable or perform other operations
without having to do another assignment 
statement (which can be easy to forget).

Note also that we cannot assign
something to the value of a function that
does not return a value (void).

What if we wanted to pass an argument
like (_variable + 1)?

When we expect a reference-to-something,
_variable + 1 is a value, but is a location
in memory. This *does work* for pass-by-value
parameters. Those are just values, not
memory locations.

We cannot pass arbritary expressions,
etc. with a pass-by-reference parameter.

They're meant to accept *variable arguments*.


#### Example of extractWord()

In Project 3, we wanted the value of the
first word, and the rest of the string.

So, we returned one and modified one.


### More caveats

Remember that we can't do something
like:

    if (passByRef(variable) < expression)
    
If passByRef() isn't designed to return
a value.


### Censorship program example

    What should I censor? My SSN is 827-42-0397.
    My SSN is ***_**_****.
    
    void censorDigits(string& s);
    // Must be passed-by-reference to modify it
    
    int main()
    {
        cout << "What should I censor? ";
        string message;
        getline(cin, message);
        censorDigits(message);
        cout << message << endl;
        
    }
    
    void censorDigits(string& s)
    {
        for (int k = 0; k != s.size(); k++)
        {
            if (isdigit(s[k]))
            {
                s[k] = '*';
            }
        cerr << "We produced the string " << s << endl;
    }

If we didn't have "string& s",
cerr would show the censored message, but main()
would show that main()'s message string was never
modified.

We would thus find out that our algo was correct,
but our implementation needed to be pass-by-reference.


### Another example


    int main()
    {
        ...
        int a;
        int b;
        cin >> a >> b;
        if (a < b)
        {
            exchange(a, b);
        }
        cout << a << " is at least as big as " << b << endl;
        
Here, we want to switch the values of a and b.

Let's implement!

    void exchange(int x, int y)
    {
        x = y;
        y = x;
    }
    
Does this work? NO! Why not? 
Because of the order in which we do these
steps, we lose x's original value
Both will end up with y's original value
If vice versa, we lose y's value

When dealing with something like this,
use a temporary variable to store it!

Instead:

    void exchange(int& x, int& y)
    {
        int temp = x;
        x = y;
        y = temp;
    }

This is a typical pattern.

But if we run this function, it doesn't
quite work. We'll get:

    x is 5, y is 3
    3 is at least as big as 5

More debugging:

    void exchange(int& x, int& y)
    {
        cerr < "x starts as " << x << ", y as " << y << endl;
        int temp = x;
        x = y;
        y = temp;
        cerr << "x is " << x << ", y is " << y << endl;
    }
    
When these paramters are not passed-by-reference,
the local variables will pass out-of-scope,
and the changes are never main to main()'s a and b.

We need:

    void exchange(int& x, int& y)
    {
        ...
    }
    
    
### Month Printer -- Arrays

What if we want to 

    switch(m)
    {
        case 1: cout << "January"; break;
        
    ...

But, let's do:

    monthNames: "January", "February", etc.

Where each element is indexed, starting
at 0. So each month is n - 1. E.g., 1 - 1 = 0,
equals January.

We want an array of 12 strings!

    string monthNames[12];
    
This doesn't initialize it; this does:

    string monthNames[12] = { "January", etc. };
    
Layout of the *initializer list* doesn't matter;
just make it readable.

Just like before, we can do:

    cout << monthNames[#];
    
We can access individual elements of arrays. Awesome!

Note though, that if we insert the wrong number,
we will *walk off the array*. 

Check position **before** we access! It should
be within its limits.

The size of the array must be known at
compile time. Later on, we'll learn about
more dynamic array types.

Arrays can be initialized like this:

    _type _identifier[] = { // Initializer list };
    
The array will automatically be given a size
equal to the number of elements in the
initializer list.

BUT, we cannot do:

    _type _identifier[];
    
We need a size at compile-time, either specified,
or implicit from the intitialization.

So, this is acceptable:

    _type _identifier[#];

**Arrays can be constant**

**Arrays cannot be initialized to size 0**

    const int daysInMonth[12] =
    {31, 28, 31, 30, 31, 30,
     31, 31, 30, 31, 30, 31 };
     
We wanna print all months with 31 days.

So we visit positions 0-12 in daysInMonth[].
We can then take this same position and apply
it to the monthNames array if we want the
textual names.


### Program

Implementation:

    for (int k = 0; k < 12; k++)
    {
        if (daysInMonth[k] == 31)
        {
            cout << monthNames[k] << endl;
        }
    }
    
Badda-bing!

What if we wanted the first letter of each
month with 31 days in it, displayed vertically?

J
M
M
J
A
A
O
D

monthNames[k] is monthNames sub k, a full string.

How do we get a character of a string?

    monthNames[k][0].

A note on style: even though 12 is
obviously the number of months, we should
still use a defined constant to name it.

**NO magic numbers!**

Do this instead:

    const int NUM_MONTHS = 12;
    
And then:

    string monthNames[NUM_MONTHS] = { ... };
    
Got it?


### Caveats on other languages

In Java, we could ask _array.length() or _array.size()

No such luck in C++, unfortunately.


### Use cases

What if we want to get the mean from an
input of a huge amount of numbers?

Do we need to use an array? No, why?
We can just have one number as the running
total, and another variable as the counter
for the number of numbers. Then, divide, haha.

So:

    cout << "Enter the scores 
            << " (negative number to quit): " << endl;
            
    // Always consider where we're placing variables
    // in relation to the loop!
    
    int total = 0;
    int num_numbers = 0;
    
    for (;;)
    {
        int number;
        cin >> number;
        if (number < 0)
        {
            break;
        }
        
        total += number;
        num_numbers++;
    }
    
    cout << "The average of all the scores " 
            << total/num_numbers << endl; // This is buggy, apparently



## Lecture 11: 30 October 2013

// The mean-computing example we're continuing
// now is similar: we can use running totals

    cout << "The average of all the scores " 
            << total/num_numbers << endl; // This is buggy, apparently

Why was this potentially buggy? If we have
integer division. Smallberg notes that
simply declaring total or num_numbers as doubles
from the outset is potentially misleading:
neither will hold fractional values. 

We can have another variable re-hold the
value of total, e.g. double totalAsDouble = total;

Instead we can wanna take a variable and 
convert it to a different type.

This is **type casting**!


### Static Cast

Syntax:

    static_cast<double>(_variable)
    
To make the code more readable,
we might declare and assign:

    mean = static_cast<double>(total) / num_numbers;
    
The old C-style cast:

    static_cast(_toType)(_variable)
    
is not advisable according to Smallberg 
for working well with the rest of C++

***

NOTE: total is not changed to a double,
we simply temporarily take its value
and make it a double for immediate usage.
In the rest of the program, total is still
an int.

***


### More Bugs

What if num_numbers were 0?

Back through the logic of the program,
we must have received a negative number
as the very first input, meaning we
broke before we got to num_numbers++,
meaning no scores.

So yes, this undefined behaviour can
occur.

So, we simply add the check for that
usage case.
    
    cout << "Enter the scores 
            << " (negative number to quit): " << endl;
            
    // Always consider where we're placing variables
    // in relation to the loop!
    
    int total = 0;
    int num_numbers = 0;
    
    for (;;)
    {
        int number;
        cin >> number;
        if (number < 0)
        {
            break;
        }
        
        total += number;
        num_numbers++;
    }
    
    if (num_numbers == 0
    {
        cout << "There were no scores, so no mean" << endl;
    }
    else
    {
        double mean  = static_cast<double>(total) / num_numbers;
        cout << "The average of all the scores is " 
                << mean << endl; // This is buggy, apparently
    }
    
What if we want the standard deviation? We need the
difference from the mean, so we need an array to store
the numbers for computation.
    
    cout << "Enter the scores 
            << " (negative number to quit): " << endl;
            
    // Always consider where we're placing variables
    // in relation to the loop!
     
    // We don't know how many numbers we'll need to hold
    // We can't first ask the user; the array must be known
    // at compile-time!
    
    // So, we'll have to pick a number larger than likely
    // ever needed. So:
    
    int scores[10000];
    int total = 0;
    int num_numbers = 0;
    
    for (;;)
    {
        int number;
        cin >> number;
        if (number < 0)
        {
            break;
        }
        
        total += number;
        
        // Where will the position
        // be? Related to num_numbers
        // which says how many numbers
        // are interesting
        
        // It also lets us know which
        // index number we're at,
        // the next available spot
        
        scores[num_numbers] = s;
        num_numbers++;
    }
    
    if (num_numbers == 0
    {
        cout << "There were no scores, so no mean" << endl;
    }
    
    else
    {
        double mean  = static_cast<double>(total) / num_numbers;
        
        cout << "The average of all the scores is " 
                << mean << endl; 
                
        // Now standard deviation time!
        
        // Take each number, find difference, square difference,
        // Add these squared differences, and sqrt that divided
        // by num_numbers
        
        double sumOfSquares = 0;
        
        // Visit each element of array and perform operations
        // Only visit interesting items; otherwise,
        // we're performing operations on uninitialized
        // junk values!
        
        for (int k = 0; k < num_numbers; k++)
        {
            double diff = scores[k] - mean;
            
            sumOfSquares += diff * diff;
        }
        
        cout << "The std. deviation is" 
                << sqrt(sumOfSquares / num_numbers) << endl;
    }
    
This is a common pattern of setting up
a large array, using only part of it,
and only ever visiting that interesting part.

We need to track the interesting part!

Undefined behavior is still possible here.
Not dividing by zero, not doing a sqrt(negative),

Possibility: we walk off the array. 

So, convince ourselves of the soundness of the
design. num_numbers can't ever be negative,
but it can exceed the array size of 10,000.

While no human will likely ever do that,
we often have to interact with other
programs that may well feed in that 
many scores.

Solutions?

We test for not walking off.

Wrong solution:

    while (num_numbers < 10000)
    {
        ...
    }

This won't let us mark the end of
the scores with a negative number.
We will confuse the user otherwise. 
The program is suddenly ending abruptly.

Another check possibility:

    if (s < 0 || num_numbers == 10000)
    {
        break;
    }
    
Again, the user may be abruptly interrupted.
We should implement separately and tell the user,
if they tried to enter anything beyond 10,000
without terminating right before with a negative to
end.

    if (number < 0)
    {
        break;
    }
    
    if (num_numbers == 10000)
    {
        cout << "I can handle only 10,000 scores!" << endl;
        cout << "Here are the statistics for just the first"
                <" 10,000 scores." << endl;
    }
    
    
Error messages should be helpful, and then give
information on what it's doing to deal with it.
    
To test this, temporarily set the array size
to something small and push against that 
boundary.

Of course, `10000` is a magic number. Give it a
name, e.g. `MAX_NUM_SCORES`
    
    
### Passing Arrays as Arguments

What if we want a function that operates 
on an array?

    double computeMean(int a[]);

    int main()
    {
        const int MAX_NUM_SCORES = 10000;
        int scores[MAX_NUM_SCORES];
        int nScores = 0;
        ... // Fill-up array, perhaps only partially
        
        double m = computeMean(scores);
        
    }
        
        
    // We need to give a name to the int array
    // parameter but it should be generic
    // because we could be passing many
    // different things
    
    // We pass an array of integers
    // but what about the number of elements?
    double computeMean(int a[])
    {
        if (... == 0)
        {
            return 0;
        }
        
        int total = 0;
        for (int k = 0; km < ...; k++)
        {
            total += a[k];
        }
        
        return static_cast<double>(total) / ...;
    }
    
Next consideration: are we passing arrays
by value? No, because arrays can be memory-expensive.
We’re often not even using all of that array!

This is not quite passing-by-reference.

When pass an array, we're really working with
the original. It's a pointer. 
    
What about the size of the array? It doesn't
matter for arguments, because all we need
is where the array is. 

What happens if we do put a number? It's ignored.

But inside of the loop:

    for (int k = 0; km < ...; k++)
        {
            total += a[k];
        }

We do need to know the size of the array to
know how many times to iterate.

There is NO built-in way to find out
the size of an array when it's an array parameter.

The parameter contains no info about the size
of the array. Instead, we pass *another parameter*,
the number of items to look at in the array. 

    double computeMean(int a[], int n)
    {
        if (... == 0)
        {
            return 0;
        }
        
        int total = 0;
        for (int k = 0; km < ...; k++)
        {
            total += a[k];
        }
        
        return static_cast<double>(total) / ...;
    }
    
Example call: (omit [] with array argument)

    computeMean(scores, nScores);
    
This second argument makes the 
function accepting arrays as arguments
far more useful.

Another example function:

    void setAll(int a[], int n, int value);
    {
        for (int k = 0; k < n; k++)
        {
            a[k] = value;
        }
    }
    
This sets a certain number of values within 
the array to some defined value.
    
What if we wanted to denote that a function
will not modify anything passed to it.
Use *const*!

Example:

    double computeMean(const int[a], int n);
    
Whenever we do not plan on modifying something,
make it **constant**.

This will allow compilers to check our
implementation too, to make sure that we're not 
accidentally modifying it.

We can constants to something not planning
on modifying its arguments, but we CANNOT
pass constants (by reference or via pointers)
to a function that plans on modifying them.

Functions that modify something are like a
little kid that may break something. Functions
that do not modify things are like a very
careful museum curator.


### Example: Movie Theater Attendance

We want to measure audience size at
a movie theater over time. 

We want to now things like average
audience on a particular day of the
week, etc.

So 5 weeks worth of 7 days each, with numbers
for each day. It wouldn't just be a list
of 35 numbers, but a table of days and weeks. [

This is a multi-dimensional array!


### Two-Dimensional Arrays

Week number and days of each week.

Syntax:

    int attendance[5][7];
    
Meaning 5 weeks, 7 days here.
Number of rows, number of columns.

So we eval as row, then number.

Again, numbering will begin at 0.

So now whenever we wanna access data,
give both constraints:

    cout << attendance[2][5];
    
In this context, week 2, day 5. 

Magic number aspect just got waay
more annoying.

    const int NWEEKS = 5;
    const int NDAYS = 7; 
    
    int attendance[NWEEKS][NDAYS];
    ...

Now we want total attendance per week,
assuming we already have the data stored,
35 days worth attendance statistics:

    for (int w = 0; w < NWEEKS; w++)
    {
        cout << "The total for week " w << " is "
                << ... << endl;
    }

Now, let's get the total for each week. We
can just run through the days of a week:

    for (int w = 0; w < NWEEKS; w++)
    {
        int total = 0; // Total for week
        
        for (int d = 0; d < NDAYS; d++)
        {
            total += attendance[w][d];
        }
        
        cout << "The total for week " w << " is "
                << ... << endl;
    }

This is cool! It's adding up totals per week,
then printing out those totals for each week too!

    const string dayNames[NDAYS] =
        { "Monday", "Tuesday", ... "Sunday" };
        
Now let's compare the days of each week.
e.g. Totals of all the Mondays, Tuesdays, etc.

We'll have 7 totals at the end.

    for (int d = 0; d < NDAYS; d++)
    {
        ...
        cout << "The total for " << dayNames[d]
                << " is " << t << endl;
    }



## Lecture 12: 4 November 2013

    const int NWEEKS = 5;
    const int NDAYS = 7;
    
    ...
    int attendance[NWEEKS][NDAYS]
    ...

    for (int w = 0; w < NWEEKS; w++)
    {
        int total = 0; // Total for week
        
        // Going row-by-row to add up
        // attendance for each week
        
        for (int d = 0; d < NDAYS; d++)
        {
            total += attendance[w][d];
        }
        
        cout << "The total for week " w << " is "
                << total << endl;
    }

    // We need to have day names 
    // corresponding to day numbers.
    // We'll group weekend days together
        
    // 0 is Monday; weekends are 4, 5, 6
    
    const string dayNames[NDAYS] =
        { "Monday", "Tuesday", ... "Sunday" };

    int grand_total = 0; 

    // Now counts attedance for each day of the week
    
    for (int d = 0; d < NDAYS; d++)
    {
        int t = 0;
        for (int w = 0; w < NWEEKS; w++)
        {
            t += attendance[w][d];
        }
        cout << "The total for " << dayNames[d]
                << " is " << t << endl;
                
        grand_total += t;
    }
    
    cout << "Over the course of " << NWEEKS << " weeks, "
            << "the attendance was " << grand_total << endl;

Weeks and Days loops are switched here!
Which loop is outer vs which one is outer is
reversed. The inner one goes faster than the
outer one. 

It's row-by-row vs. day-by-day. 

Note that if grand_total were initialized inside
one of the loops, we'd be initializing EVERY single
iteration. 

In the context of a program:

    const int NWEEKS = 7;
    const int NDAYS = 5;
    
    // We need to pass a two-dimensional array!
    // 
    
    double meanForADay(const int, int nRows, int day_number);
    
    int main()
    {
        ...
        int attendance[NWEEKS][NDAYS];
        ...
        // Pass the array
        double meanWed = meanForADay(attendance, NWEEKS, 2);

    }

    double meanForADay(int a[][NDAYS], int nRows, int day_number)
    {
        if (nRows == 0)
        {
            return 0;
        }
        int total = 0; 
        for (int w = 0; w < NRows; w++)
        {
            total += a[w][day_number];
        }
        
        return static_cast<double>(total) / nRows;
    }
    
    
### Passing two-dimensional arrays

Leave off first-dimension but second dimension
parameter must be known at compile-time.
    
This is apparently a quirk of C++ carried over
from C. 

2-D arrays:

* When accessing a specific element, supply both parameters

* When passing the array, specify the second parameter

Now, what we have a multiplex and want to compare
different screens. 

Now, we need a three-dimensional array!
    
    // [screens, rows, days]
    int bigTheaterAttendance[16][5][7];

What if we have a chain of big theaters?
Four-dimensional array!

    // [theater, screens, rows, days]
    int bigChainAttendance[10][16][5][7];

In practice, most arrays are one-dimensional,
only a few are two-dimensional, and very, very
few go beyond two dimensions.


### Initializing a 2-D array

Generally, there isn't a need for initializing
a 2-D array.

Syntax:

    int b[2][3] = {
        { 10, 20, 30 },
        { 40, 50, 60 },
    };
    
    int c[4][2][3] = {
    { {10, 20, 30},  {20, 30, 60} },
    { {10, 20, 30},  {10, 20, 30} },
    { {10, 20, 30},  {10, 20, 30} },
    { {10, 20, 30},  {10, 20, 30} },
    };
    
Four things, with two things of three things
in each.

If we wanted to declare a function
that could take a 3-D array:

    f(c,4);

    void f(int x[][2][3], int n);
    
For arrays larger than one dimension:
leave off the first dimension and supply the
rest.

For the first dimension, we left off everything,
since there's nothing after the first dimension
to leave off. We just passed the array ('s memory
location).


### Characters, Integers, and Strings

We know:

    int k = 97;
    char c = 'a';
    
Recall that characters are simply
stored as a small integer, often
as an 8-bit byte, meaning we have 256
possible values. 

Strange thing, this is legal in C/C++:

    int k2 = 'a';
    
k2 will have the value of whatever encoding
value is used for that value, which will
vary by system. 

If ASCII, 97; if EBCDIC, 129

**Never** assume that we'll always
have ASCII encoding.

Instead of comparing to that number,
compare an int to a character's encoding:

    if (k2 == 'a');
    
    char c2 = 97; // If ASCII, c2 = 'a'; 
                  // if EBCDIC, c2 is '/'

Can we do this:

    k++;
    
Yes, k is now 98.

How about:
    
    c++;
    
Arithmetic on a character? Yes.
    
    // c = c + 1
    
We'll add one to the integer corresponding
to the character stored by c.

So c would become 98, which in ASCII
is 'b'.

More stuff:

    double d = 3.5;
    cout << d;
    
<< is an operator that takes destination
on the left and something to be displayed/stored
on the right. The library's function for
displaying a human-readable form of the double
will be called.

So we get three characters: '3' '.' '5',
in ASCII, 51, 46, 43

If this is ASCII, we send to the output destination
three small integers corresponding to those characters. 

    cout << k;
    
This calls the library function that writes out ints,
resulting in '9' '8', in ASCII, 57, 56.

    cout << c;
    
This calls the library function in charge of single 
characters, here 'b', in ASCII, 98.

Why don't we see 98 in place of 'a' or vice versa?
It depends on the function called, which depends
on the type declaraction made.


### C++ standard rules on encoding

* Whatever numerical code used for ' ', it is less than
  that of any visible printable character.
  
This is important for sorting

* Whatever code for 'A' is less than 'B' is less than ... 'Z'

This does NOT mean that 'B' is one away from 'A', or that
the 26 encodings are contiguous in numeric relation.
This is true in ASCII, but not in other encodings.

* Whatever code for 'a' is less than 'b' is less than ... 'z'

* Code for '0' is one less than that for '1', which is
  one less than '2', which is ... one less than '9'
  
Thus, the numerals 0-9 are contiguous in encoding values.
  

### Comparing and Sorting Strings  

If we have strings of characters, how we do sort 
and compare them? What does it mean for one string
to be less than another?

    string s1 = "hello";
    string s2 = "help";
    
    if (s1 < s2)
        ...
        
This is valid. The comparison is done character-by-character,
up until a difference or one of the two runs out. 

'l' < 'p' here. Letters coming later in the alphabet
are "greater".

    string s3 = "helping";
    
    if (s2 < s3) // True
        ...
        
We do not compare sums. We compare character
against character. 

If one runs out but the other continues, then the one
that ran out is considered "less than" the one that
continues.

All the directional comparison operators are valid
for characters and strings, which will run left-to-right,
which mostly corresponds to how we sort things in
dictionaries and what-not.

What about comparing 'e' and 'E'? This depends
on the encoding. 'e' < 'E'; false for ASCII,
true for EBCDIC. 

In Project 4, this wasn't a problem.


### Recap on Strings

C++ strings (from <string>)
were used when we used:

    #include <string> 
    using namespace std;
    
At declaration, we are guaranteed
an empty string:

    string s;
    // s is ""
    
We can get a string's size via .size()
    
    int size = s.size();

We can access invidual characters
of a string: _identifier[]

    individual = s[3];

We read into strings via:

    getline(cin, _identifer)
    
We can set strings equal to each other's
values.

    s = t;

We can concatentate strings via +=,
adding on either characters or strings.

    s += "";
    
We can cut substrings via .substr(start, length)

    sub = s.substr(#, #)
    

### Interfacing with C

Problem: a lot of code is written in C,
and we wanna interface with in C++.

We can do this because we wanted to
be able to use previously written
awesome libraries.

We can use C libraries in C++ quite
easily. All of the primitive data types
of C++ exist in C too.

BUT, C doesn't have <string> like we 
do in C++ with the Standard Library. 

So, we have to learn C-strings, because
we may have to interact with code written
in C.


### C-strings

C does *not* have a type string. 

In C, we hold a bunch of characters,
in arrays instead. 

     0     1     2     3     4     5
t:  'h'   'e'   'l'   'l'   'o'   '!'

What if we have an array larger than needed?

To know when we've hit the end of the string,
we use a special character value to mark
the end of the string:

    '\0'
    
This is a ZERO, not a capital 'O'.
By convention, this marks the end of a 
C-string.

This is a known as a *zero-byte*. 
When dealing with C-strings, we don't 
care about what comes after the zero-byte.
We only go up to the zero-byte, not including
it.

So how we do declare a C-string?

Like this:

    char t[10] = 
    { 'H', 'e', 'l'. 'l', 'o', '!', '\0' };

Possible. Giving an array initializer fewer
values than the specified size of the array
is possible; the rest will be zeros.

C/C++ allows for an abbreviation:

    char t[10] = "Hello!";
    
This will put the characters of the string
literal into consecutive positions and add
a zero-byte afterward, with zeros for any 
remaining positions.

    char s[100];
    
If we just declare and don't initialize:

     0     1     2     3     4     5 ... 99
s:  ???   ???   ???   ???   ???   ???    ???

*Junk values*, just like unintialized
instances of other primitive data types.

If we want the empty string, UNLIKE
<string>-class strings, we need to specify:

    char s[100] = "";
    
With C-strings, we have to specify
some (often arbritary) number of interesting
characters.

Note that _identifier[10] means space for 9
interesting characters, because the *last one*
is *needed* for the zero-byte!

What about printing individual characters
of a C-string? The for-loop condition
can no longer rely on .size(); we don't have
a built-in way to check array size in C/C++.

So:

    for (int k = 0; t[k] != '\0'; k++)
    {
        cout << t[k] << endl;
    }
    
This prints out individual characters so long
as we haven't hit the zero-byte. Instead of
testing position, we test for the presence
of the zero-byte.

The library does let us write a C-string
the same way as a <string>-class string.
*Normally, we can't write out arrays directly*;
we'd get its memory location.

*Character arrays are the exception*, as they
are treated as a C-string. The library will
write the characters as a contiguous sequence
up until the zero-byte.



## Lecture 13: 6 November 2013

C-strings are arrays of characters,
with a zero-byte ('\0') to mark
the end of the string. 

Anything after the zero-byte
is conventionally ignored.

Remember that the size of the 
array must account for the 
zero-byte as well.

Empty C-string is just a zero-byte
at the beginning and nothing else.

A C++ string will adjust its
size to match the size
of the string stored into it.

This is NOT the case with
C-strings. 

Stylistic tip:

    char _identifier[9+1] = "Hello";
    
We could also use a symbolic constant,
of course. The first number lets us
know how many intersting characters
are possible. The 1 lets us know that
we accounted for the zero byte.

Remember that when we iterate through
C-strings, we stop at the zero-byte.

    for (int k = 0; k != '\0'; k++)
    {
        ...
    }
    
Recall also that cout << c-string
will print out everything up to but
not including the zero-byte.


### Input into a C-string

Different syntax used for C-strings:

    cin.getline(char[], max_pos);
    
Read into a character array specified
in first argument; second argument
says the max number of positions
available in that array. This is
to prevent cin.getline() from 
walking off the array. 

The getline() used for C++ strings
will not compile if we try to read
into a C-string.

If the user types >= max_pos characters,
an error will occur. 

Otherwise, it'll store the characters 
and add a zero-byte after them. We will
not have multiple zero-bytes though.


### Determining Size of C-strings

We could just write a simple function
to loop through and count, but the library
already provides this via <cstring>

Use:
    
    strlen(_c-string);
    
This returns an int, the number of 
interesting characters in the string
(those that exist before the zero-byte). 
If no zero-byte exists though, 
**undefined behavior**;
it's just looking for a zero-byte.

strlen() - 1 is the position
of the last interesting character.

Note that it's not examining its
declared size but the actual content
at its call up until the zero-byte.

This does not work on C++ strings
or non-character arrays. It only works
because we have an ending encoded into
C-strings.

If we use strlen(), we **must** 
pass a valid C-string.

Note also that performance can be slow if
we're counting through a large C-string.

In contrast, accessing or comparing
specific characters is must faster.

Warning: don't use strlen()
for a for-loop visiting a C-string;
we'd be counting through it every single
interation of the for-loop otherwise!


### Assigning C-strings to C-strings

We cannot assign arrays to arrays!

This presumes compatible sizes, types,
that we want to assign every single element,
etc.

    s = t; // Will not work
    
This is true in C and C++.

Possible solutions: we could write
a loop that assigns character-by-character
up to and including the zero-byte.
Again, <cstring> includes a solution:

    strcpy(_destination, _source);
    
Where the two arguments are both
C-strings. This will copy 
everything from the source C-string,
up to and including the zero-byte, 
into the destination C-string.

// My typing is already improving 
// with this new, more correct method

The reason that we can use '='
with C++ strings is because the Library
defines a way for us to use '='
for string copying, and automatically
accounts for size.

If _destination is larger than
_source, only part of _destination
is assigned to _source's value then;
the rest if *untouched*. The zero-byte
is the marker of where to end operations.


#### Warnings

What if _destination wasn't large enough
for _source? **Undefined behavior**

strcpy() would walk right off the freakin'
array. 

What if _source didn't have a zero-byte,
strcpy() would walk off _source until
it found a zero-byte!

**Be very careful to stay within bounds!**


### Concatentation with C-strings

We can't use '+=' like with C++
<string>'s. It's not defined for
arrays in C.

Workaround: we figure out where
the zero-byte is and add stuff to the
end then add a zero-byte.

Again, <cstring> to the rescue:

    strcat(_recipient, "Add this!");
    
The second argument can be a string
literal or another C-string variable.
Undefined behavior if second
argument doesn't have a zero-byte!

strcat() works by finding the zero-byte
in _recipient, then replaces with the
second argument's values, then caps
it off with a zero-byte.

Again, _recipient must be large enough to
receive additional elements!

Is there a standard function for
**pre-pending**? No, we'd have to
manually shift everything over manually
then add the new elements.


### Comparing C-strings

So how we compare C-strings?

We could compare manually
via for-loop, up until one
or both's element at a position
has a zero-byte. The one that runs
out first should be considered 
less than other.

There is only one function
for comparing C-strings in <cstring>:

    strcmp(_first, _second);
    
    if (strcmp(a, b) < 0)

Strcmp() returns a negative
if a comes before b.

a zero, if a == b

a positive, if a > b

Ask if a < b:

    strcmp(a, b) < 0
    
Ask if a > b:

    strcmp(a, b) > 0
    
ask if a == b:

    strcmp(a, b) == 0
    
Thus, we can do most everything via 
C-strings, but it's a bit more painful.


### Pitfalls of C-strings

Common mistakes: 

Are s[] and t[] equal?

Wrong:

    if (strcmp(s, t))
        ...

This is actually asking the opposite:
remember that if() considers non-zero
values to be true. 

If s & t are equal, strcmp() returns 0, 
causing if() to be evaluated as false!

Right:

    if (strcmp(s, t) == 0)
        ...
        
We have to test the integer result
returned by strcmp().

Another common mistake is when we want
to ask if one C-string is less than another
one:

Wrong:

    if (t < s)
        ...

Right:

    if (strcmp(t, s) < 0)
        ...

Unfortunately, this wrong way actually 
compiles. This happens because it's actually
*comparing the memory addresses* of the 
arrays. This has *nothing* to do with 
the content of the two arrays. The result
will be compiler-dependent. 


### Passing C-strings to Functions

Example for C++ strings:

    void makeUppercase(string& s)
    {
        for (int k = 0; k != s.size(); k++)
        {
            s[k] = toupper(s[k]);
    }

For a C-string:

    // Just pass the array itself
    void makeUppercase(char s[])
    {
        for (int k = 0; k != '\0'; k++)
        {
            s[k] = toupper(s[k]);
        }
    }

What if we passed a char[] and the 
number of interesting elements?

Unnecessary, as have the zero-byte to 
mark the end of the C-string. This 
wouldn't be a worry unless the zero-byte's
location were somehow inconsistent with the
number of interestin elements.


### Arrays of C-strings

Previously, with <string>
in C++:

    string sa[10];
    
What about C-strings? That'd
be an array of arrays!

Rows: individual C-string

Columns: individual characters of each

Thus, number of rows is the number
of C-strings and the number of columns
is the upper limit of the size
of each C-string, *including '\0'*

Again, whatever comes after the zero-byte
doesn't matter. 

Syntax:

    char _identifier[NSTRINGS][MAXLENG]

Initialization:

Multiple initializers are needed, but we
can just use:

    char pets[5][7] = {
        "cat", "mouse", "eel", "ferret", "horse"
    };
    
**This is a shorthand for char arrays ONLY**
    
    for (int k = 0; k < 5; k++)
    {
        cout << pets[k] << endl;
        
        // pets[k] means the whole kth row
    }
    
**This does NOT work for non-char arrays**
We'll likely get the array's memory location
instead.
    
This works. We leave off specifying a specific
character, so it just punches out that specific
C-string instead. 

The for-loop condition should be replaced by a symbolic
constant, of course. 

So how do we fill up an array of C-strings
with user input? 

We want a list of people and their associated
uni:

    const int MAX_NAMES = 1000;
    const int MAX_NAME_LENGTH = 15;
    const int MAX_LINE_LENGTH = 100;
    
    int tally(const char a[][MAX_NAME_LENGTH + 1], int n, const char target[]);

    int main()
    {
        char names[MAX_NAMES][MAX_NAME_LENGTH+1]
        
        // The +1 is for the zero-byte
        
        int nNames; // Tracks number of names
        
        // Read in names, ending with empty line
        
        for (;;)
        {
            // Read a line, break if empty,
            // otherwise store it
        
            // What if we have a school name
            // greater than 15 chars?
            
            // We'll have an intermediate variable
            // to hold the school name for eval

            char s[MAX_LINE_LENGTH + 1];
            
            cin.getline(s, MAX_LINE_LENGTH + 1);
            
            if (s[0] == '\0')
            {
                break;
            }
            
            // What if strlen(s) > MAX_NAME_LENGTH?
            
            if (strlen(s) > MAX_NAME_LENGTH)
            {   
                cout << "The name is too long!" << endl;
                continue; // Skip to next iteration
            
            // What if we have more than 1000 names?
            
            if (nNames == MAX_NAMES)
            {
                cout << "Too many names!" << endl;
                break;
            }
            
            
            strcpy(names[nNames], s);
            
            // If we give only the first constraint,
            // we'll be dealing with the whole row
            
            
            nNames++;
            // This - 1 (after the increment)
            // tells how many interesting elements
            // we have stored and itself is the next
            // row we'll be storing into
        }
        
        // Find out how many people from UCLA
        
        cout << "UCLA appears " << tally(names, nNames, "UCLA"")
                << "times." << endl;
    }
    
    // Remember that we have to always specify sizes after first one
    // Constants because we won't be modifying these arrays
    
    int tally(const char a[][MAX_NAME_LENGTH + 1], int n, const char target[])
    {
        int count = 0; 
        
        for (int k = 0; k < n; k++)
        {
            // REMEMBER: C-strings are compared with strcmp
            if ( (strcmp(a[k], target0) == 0)
            {
                count++;
            }
        }
        
        return count;
    }
            
            
#### Check if C-string is empty

This can be done via:

    strlen(_c-string) == 0;
    
    strcmp(_c-string, "") == 0;
    
    _c-string[0] == '\0';
    
Notice how this is similar to 
inputting into an array of C++ strings,
but we have to add checks for going out
of bounds of arrays. 


### Additional C-string notes

From awesome TA Forney's examples:

* Do not manually null-terminate 
  C-strings when using = "" initialization
  BUT we NEED to for { ' ', '', ... }
  initialization
  
* If we manually place zero-bytes
  in a C-string (that has space),
  any cout on that C-string will
  display characters only up to
  that zero-byte
  
* The = "" shortcut for C-strings
  can ONLY be used for initialization
  At any other time, we'll have to 
  assign one element at a time
  or do a strcpy(_c-string, "literal"),
  but that requires <cstring>
  
* <string> class objects can be assigned
  value of C-strings
  
* <string> concatentation with + 
  works with a <string> + C-string (or vice versa)
  but NOT if both operands to +
  are C-strings
  


## Lecture 14: 18 November 2013


### Pointers

Pointers are another way to implement
passing by reference, specifically in
C, which doesn't have reference-to types.

They can be used to traverse arrays.
A lot of library data types use pointers
when it comes to interacting with
arrays.

They allows us to manipulate
dynamic storage.

They represent relationships in data
structures. 


### Syntax

Declaration: 
    
    _dataType *_pointerIdentifier
    
To assign it a memory address of an
object, use the address-of operator
on that object:

    _pointerIdentifier = &_variable;

Note that that the pointer and the 
object must be of compatible
data types; there is no interchanging
allowed!

To get an object's value through a
pointer, we "follow the pointer",
known as dereferencing or indirection:

    _var2 = *_pointer; 
    // Gives var2 value of pointed-to
    // object
    
Again, compatible data types are required!

To use pointers in function parameters:

    _returnType _name(_dataType *_pointer);
    
Then, when we call the function, we pass:

    _name(_sameType &_object);
    
And in the function implementation,
we use *_pointerParameter if we want
to change the value of that passed
argument; we're just changing the pointer
otherwise.


### Revisiting Passing-by-Reference

Recall that passing-by-reference 
allowed us to change variables
passed to a function rather 
making separate copies
when we passed by value. 


#### The Pointer Version

    void polarToCartesian(double rho, double theta, double *xx, double *yy)
    {
        xx = rho * cos(theta);
        
        yy = rho * sin(theta0);
    }
    
xx and yy will contain values that *point* to where
x and y are. 

We use the asterisk, meaning that a variable
holds a **pointer to** something. 

In main(), when we call, we need to generate
a pointer to something, using the ampersand again,
meaning **address-of**.

    polarToCartesian(r, angle, &x, &y

&variable means "generate a pointer to"

So now, xx points to x, and yy points to y. 

When we call function that takes pointers 
as arguments, we generate the pointers-to-stuff.

    void polarToCartesian(double rho, double theta, double *xx, double *yy)
    {
        xx = rho * cos(theta);
        
        yy = rho * sin(theta0);
    }

xx and yy now hold pointers; they can't hold doubles,
but rather pointers to doubles!

We need to say: store rcos(theta) in the double
that xx points to.

     void polarToCartesian(double rho, double theta, double *xx, double *yy)
    {
        *xx = rho * cos(theta);
        
        *yy = rho * sin(theta0);
    }
    
*pointer

Again, the asterisk; here it is the indirection/dereferencing
operator, meaning "the object that that pointer points to"
or "follow the pointer"

C has only pass-by-value and passing pointers; C++ adds
passing-by-reference

Remember: don't mix up pointers and the objects
that they point to! Use some naming convention
like p_variable so that we know that that variable
is a pointer.

Analogy: a house is some data type, and its value is
some person in the house; a pointer would be a piece
of paper or a sign telling us the house's address. 

We can't put a person in the piece of paper or
in an address, but we can put them in the house
that the paper/sign direct us to.

There are reasons why we'll need pointers rather
than passing-by-reference.

We have to explicitly create and follow pointers
here. 


### Backend of Pointers

Memory is a bunch of integers, and each one 
has an address. We're using the memory address
of objects. 

A pointer is given the memory location of 
something else, and we can use this to get us
to the something else. We care about data types
so that pointers don't point to incompatible data
types; only a pointer-to-a-double can point to a 
double. 

Pointer types must match the type of the object
they point to. There is no automatic casting
like with int/double when we do assigning with them.

&variable can be seen as generating an arrow
pointing to that variable. **Address-of**

*variable can be seen as following the pointer
arrow to object that it points to. **Dereferencing**


### Pointer Examples

    double a = 3.2;
    double b = 5.1;
    
    double *p = &a;
    
    // p now points to a
    // It holds the memory address of a
    // Note p is a pointer-to-a-double;
    // If a were an int; compile error!
    
    double *q = 7.8; 
    
    // Illegal; this isn't a memory address!
    // q is a pointer-to-a-double; it can
    // only hold a pointer-to-a-double not a 
    // double itself!
    
    double c = a;
    
    // Legal; this is simply assigning 
    // the value of a to c
    // a itself is not changed
    // a and c are both doubles
    
    double d = p;
    
    // Illegal! d is a double
    // p is a pointer-to-a-double
    
    // We cannot interchange pointers-to
    // and the objects they point to
    
Here, the house and address analogy
rather breaks down; a sign/paper can
be put into a house. It has to be thought
of more abstractly, like trying to stuff
a whole plot of land into a house.

    // If we do want to use d and p here
    
    double d = *p;
    
    p = b;
    
    // Illegal! p is a pointer-to-a-double
    // b is a double
    
    // If we want to use this expression,
    // what we likely meant to say is
    // have p point to b now:
    
    p = &b;
    
    // This is akin to a sign being
    // changed to point to a different house
    
    // But this could also mean that
    // we want b's value to be stored
    // into the object that p points to:
    
    *p = b;
    
    // This is akin to kicking out
    // whoever was living at the address
    // that p points to

Be careful not to mix-up what
we're trying to do. Consider
if we meant to reassign where a 
pointer is pointing to or if we're
trying to change the value of the object
that a pointer is pointing to.

Example demonstration code:

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main() 
    {
        double a = 8.9;
        double *p_a = &a;
        
        cout << "Memory address p_a points to: " << p_a << endl;
        
        cout << "Via pointers, the value there is: " << *p_a << endl;
        
        cout << "Modifiying pointer p_a: " << endl;
        
        p_a = p_a - 105;
        
        cout << "New address of that p_a points to is: " << p_a << endl;
        
        cout << "Via pointers, the value there is: " << *p_a << endl;
        
        cout << "\nChanging value there via p_a." << endl;
        
        *p_a = *p_a - 1;
        
        cout << "The value there is now: " << *p_a << endl;
        
        
        return 0;
    }
    

### More Pointer Examples

    double a = 3.2;
    double b = 5.1;
    
    double *p = &a;
    
    *p = b;
    // a now equal to 5.1
    p = &b;
    
    *p += 4;
    // Equivalent to *p = *p + 4

    // Does this work? Yes!
    // p currently points to b,
    // and *p means go to and use b
    
    // b now = 9.1
    
We need to develop an intuitive
understanding (and eventually,
a rigorous, technical one) of what
is happening here.

Draw pictures, draw pictures!


### Even More Pointers
    
    // p already declared as double p*
    
    int k = 2; 
    
    p = &k;

    // Illegal! p is a pointer-to-a-double,
    // and CANNOT point to an int
    
If pointers could point to other
types, and we tried to store *p,
then we'd try storing incompatible
values into what we think is a double
at that memory address.

    int *z = &k;
    
    cout << (k * b) << endl;
    
    // Writes out 18.2
    // k and b are both doubles
    
    cout << (k * p) << endl;
    
    // This is multiplication
    
    // Multiplying pointers is not 
    // allowed; but we could do:
    
    cout << (k * *p) << endl;
    
    // Writes out 18.2, as it's
    // k times value that p points to
    
    // To be confusing: k**p;
    // don't use this masochistic style
    
    // To really confuse people:
    
    cout << *z**p << endl;
    
    // Far better:
    cout << (*z) * (*p) << endl;
    
    
    
    
    
    
### Uninitialized pointers

"Well, let's try it!" was 
Smallberg's response to my question, haha.

(I asked: "What happens if we try using
an uninitialized pointer?")

    double *q;
    *q = 4.3;
    
What double does q point to?

Uninitialized pointer variables point
to whatever junk pattern stored in q.

q could point to something something not
even in the memory allocated to our program,
leading to a crash.

I get a seg fault error when I try:


    int k = 2;
    
    int *z;
    
    *z = 4;
    
    cout << z << endl;
    
    cout << *z << endl;

Leads to error:

    Run Command: line 1: 21572 Segmentation fault: 11  ./"$2" "${@:3}"
    
Same error even if we comment out *z = 4;

If we access memory in our allocation but
in the memory of something else in our program,
then we just overwrote the memory needed for
something else.

In other words, **uninitialized pointers** lead
to lots and lots of **undefined behavior** and we
should never follow a bad pointer.


### Assigning pointers to pointers

This is possible. Example:

    double z = 5.0;
    
    double *p = &z;
    
    double *q = p;
    
    // q and p now both point to z


### Pointers to Pointers

These are possible. Example:

    double z = 5.0;
        
    double *p = &z;
        
    double *q = p;
    double **qq = &p;
    
    cout << p << endl;
    cout << *p << endl;
    
    cout << q << endl;
    cout << *q << endl;
    
    qq = &p;
    
    cout << qq << endl;
    cout << *qq << endl;
    cout << **qq << endl;


### Comparison with Pointers

Where we have double* p, r, q

a = 9.1;
b = 9.1;

and r = &a;
and p = &b;
and q = p;

and a and b have different values.

Can we do:

    if (p == r)
    {
        cout << "Hello" << endl;
    }
    
This if will evaluate as false.

Yes, but we are comparing
the pointers themselves, the
memory addresses. If they point
to different places, they will have
different values.

    if (p == q)
    {
        cout << "This will execute" << endl;
    }

p and q point to the same address. Comparing
them will eval. to true.

What if we want compare values using pointers?

    if (*p == *r)
    {
        cout << "a and b have equivalent values!" << endl;
    }
    
**Pay attention: are we comparing pointers (pointing to same place?)
or are we comparing the objects the pointers point to (are the houses
at those addresses identical?)?**

**This is if both pointers point to the same data type!**

We can do Boolean comparison; I need to test out the
other Boolean arithmetic operators. 



## Lecture 15: 20 November 2013

A pointer is not another name for 
something (like a reference-to variable)
but rather is a variable dedicated 
to pointing to another variable

Note that to compare pointers, the pointers
have to point to the same data type.

Assuming that, they will NOT be equal
if they do not point to the sam ething,
even if the objects themselves hols
the same values. 


### Traversing Arrays with Pointers

We can go through arrays with indices
or via pointers and the latter is similar
in syntax to traversing other data structures.

Say we have an array of 5 doubles.

The C++ standard guarantees that the elements
of an array will be contiguous in memory. 
Each of these memory bytes will have a unique
address. For a double, this means 8 bytes
per double. 

    const in MAXSIZE = 5;
    double da[MAXSIZE];
    int k;
    double *dp;
     
[0]    [1]   [2]  [3]   [4]   [5] 
// 5 is not part of this array

1000  1008  1016  1024  1032   1040

Smallberg is chatting away about
how pointers are typically presented:
pictorially, in terms of memory addresses,
in terms of math (sounds terrible), etc. 

He's saying that different people
understand pointers differently
and that many get confused when people
aren't taught the way that is clearest to
them. Solution: teach it all three ways!

Let’s make everything 3.6 in the array!

    for (k = 0; k < 5; k++)
    {
        da[k] = 3.6;
    }

Now, we'll make a pointer that points
to the first element of the array and
then increment the pointer along
to visit every element of the array.

// dp points to a double

+---------+
|         |
|         |
|         |
|         | dp
|         |
|         |
|         |
+---------+

We want to initialize dp to point
to the first element of the array.

We cannot just do dp = da[0]; 
this would be trying to assign
a double to pointer-to-a-double.

So instead:

    double *dp;

    for (dp = &da[0]; 
    {
        *dp = 3.6; // Follow the pointer
    }
  
[0] [1] [2] [3] [4]     
 ^   
 |   
dp
    
Which means that dp is equal to &da[0],
which has the memory address 1000. 

so: +--------+
    | 1000   |
    | &da[0] |    
    +--------+

Thus, *dp would mean follow the pointer
and store 3.6 at that point. 

*dp = 3.6 means that we go to the address
stored in dp (1000) and store 3.6 there. 

Algebraically, we need to know that 
an:

    *&x ==> x

This is generating a pointer and then following
it. * and & are inverse operators.
    
So *dp = 3.6 requires that we find out
what dp is:

    *dp = 3.6

    *(&da[0]) = 3.6
    
Which leads to:

    da[0] = 3.6
    
By ***&_var = var**.


### Advancing the Pointer

Now, we need to advance te pointer.
We can simply do:

    dp++
    
This means:

    dp = dp +1
    dp += 1
    
So what does dp + 1 means?
This is adding an integer to
a pointer.

If you add/subtract an integer
from a pointer in an array,
will give a pointer pointing
that +/- amount element in the array.

So dp + 1 would mean moving the 
pointer one element forward. 


#### Pictorially


This looks like:

[0]     [1]
         ^
         |
         |
dp ---> dp
    

#### Algebraically

    dp++
    
    dp = dp + 1
    
    dp = &da[0] + 1
    
Then we need to know that:

    &a[i] + j ==> &a[i+j]
    
    &a[i] - j ==> &a[i-j]
    
Then:

    dp = &da[0+1]
    
    dp = &da[1]
    

#### Machine Level

This is seen in terms of doubles
as units.

1 double * 8 bytes / double = 8 bytes

    dp++
    
dp = address stored in dp + 1 double's worth of bytes

Address stored in dp is now 1008

We're gonna be in terms of the data
types and we'll need to convert to bytes
based on the known amount of memory occupied
by an object of a certain data type. 

We don't do this to go forward two doubles: dp += 16;

This means going forward 16 doubles!

Alternatively, this can be seen as going (16 doubles * 8 bytes)
bytes forward in memory. The compiler will take care
of this conversion. 

Could we take an array of elements (each taking up more
than 1 byte) and go byte by byte, e.g. pointer to a
string then pointer again to a character? Yes,
we'd be type-casting the pointer. 


### Leaving the Loop

Can we do dp < something?

Yes. Less than what?


#### Pictorially

So at this point we have: 

[4]
 ^
 |
 |
dp = &da[4] = memory address 1032

If we have two pointers into the same
array, we can ask if one less/greater
than the other. 

If they're pointing at different
things not in the same array,
we can still compare, but that's
just gonna be dependent on where
the compiler placed things in memory.

Within an array, a pointer pointing
to elements earlier in the array
is less than a pointer pointing to
later elements. This works because
an array's elements are laid
out consecutively in order of the subscripts.


#### Machine Level

This can be seen as address 1000 < address 1032


#### Algebraically

&a[i] < &a[i] ==> TRUE if i < j

Same for other Boolean comparison operators


#### Stop Condition

What if we could do dp < &da[5]? 
This would mean as long as dp
points to some element preceding da[5].
This makes sense in all three ways
laid out here for understanding pointers:

[0] < [1] < [2] < [3] < [4] 

1000 < 1008 < 1016 < 1024 < 1032 

We can generate a pointer to a
non-existent element not in array
but we cannot follow it (undefined behavior).

This lets us easily check if we've hit the
end of an array. 

so:

    for (dp = &da[0]; dp < &da[5]; dp++)
    {
        *dp = 3.6;
    }

On the last run, dp is increment do &da[5]

&da[5] is NOT < &da[5]

1040 NOT < 1040

[5] NOT < [5]

So we leave BEFORE trying to access 
da[5] via *dp = *(&da[5])

Note that we can also decrement
pointers. 

As long as a pointer into an array +/- 
an integer results in a pointer ALSO
pointing INTO the array, then we're okay.


#### Notational Convenience

&array[0] = array

This means that an array name by itself
is (in most contexts) a pointer to element
zero of the array. This relates to how
C++ deals with arrays. 

This means we can do:

    &da[0 + 5]
    
    &da[0] + 5
    
    da + 5
    
So we can do:

    for (dp = da; dp < da + 5; dp++) 
        *dp = 3.6;
        
With a symbolic constant:

    for (dp = da; dp < da + MAXSIZE; dp++)
        *dp = 3.6;
        
Fall back to the algebraic substitutions
and run backward to make sense of any
confusing expression. 
    
    

    
    
### Why do any of this?

Well, going through data structures
we'll learn in CS 32 means using syntax similar
to pointers in C++. 

Dang, we're at 6,000 lines of notes already?

Imagine what a whole OS must be like with
hundreds of millions of lines of code. 


### Array Parameters Revisited

We've actually already used the notational
shorthand of an array's first element
position being noted by its identifier.

Example: 
    
    int lookup(const string a[], int n, string target)
    
    int main()
    {
        string names[5] = { ""...};
        
        int n = lookup(names, 5, "walter"); // 3
    ]
    
So here, we passed names, meaning:

    int n = lookup(&names[0], 5, "walter");
    
We don't pass the whole array; we pass a pointer
to its first element!

In the declaration, a[] really means a pointer
or:

    int lookup(const string* a, int n, string target)
    
As a PARAMETER to a function, _type a[] = _type* a
meaning that we pass a pointer to the first element
of an array of any base type.    
    
This also means that we can pass a pointer
to whatever element in the array that we want:

    int lookup(&names[2], 3, "walter"); // Returns 1
    
This makes the function think that the array
starts at names[2] so it only looks at
[2] [3] [4] and treats those three as 
[0] [1] [2] and we can adjust via return + shift

If we started at pos 2, then 1 of the last three is 
really 3 or 1 + 2. This lets us easily do subsequences
automatically. 

Some of the test data in Project 4 reuses arrays
by using only portions of them for later tests. 

So in this function: names + 2 means start at
element 1 + 2, then int n gives the length of this 
portion. 


### lookup() revisited

Redone with pointer notation:

    int lookup(const string* a, int n, string target)
    {
        for (int k = 0; k < n; k++)
        {
            if (a[k] == target)
            {
                return k;
            }
        }
        return -1;
    }
            
What'a a[k] doing here? a is really a pointer,
not an array! It doesn't make sense with our old
hand-waving, as starting at names + 2
would render a[k] non-sensical


#### Subscripting a Pointer

pointer[i] ==> *(p + i)

Find the object that is i
elements after the object that
p points to. We are following the
result of p being momentarily shifted
forward. 

What pointer points to is not changed!

So a[k] is (&names[2])[1] ==> 

*(&names[2] + 1) ==> *(&names[2+1])

==> *(&names[3]) ==> names[3]

We do not change pointer,
we use pointer's value to figure out
another and use that. 


#### Iterating without []

The above function could also
be done as:

    int lookup(const string* a, int n, string target)
    {
        for (string* k = a; *k != target; k++)
        {
            if (a[k] == target)
            {
                return k;
            }
        }
        return -1;
    }


### Advancing a Non-Array Pointer

If we have something like:

    int main()
    {
        double eks;
        
        double *dp;
        
        dp = &eks;
        
        dp++; // UNDEFINED behavior!
    }
    
This is because we don't know where 
dp is pointing to now. eks isn't
an array. Probably what will happen
is that the pointer will advance forward
one data type size in memory and that
value there will be interpreted as a double. 

Again, this isn't guaranteed, so undefined
behavior. 


### Examples

Say we have a function looking
for the position of the first
negative double in an array
of doubles. 

    int findFirstNegative(double* a, int n)
    {
        for (double *p = a; p < a + n; p++)
        // p will now point at each successive double
        {
            if (*p < 0)

But what do we return? We want to return a position,
not a memory address. Recall that &a[i] + j ==> &a[i+j]

What we have here is &a[i] and &a[i+j] but we want 
j (i starts at 0). 

More simply: if a + b = c, what is b? 
b = c - a !

C++ allows: &a[i] - &a[j] ==> i - j

This is how far ahead is one pointer in an array
than the other. How many _types apart are they?

This assumes both pointers point
into the same array!

So: return p -a;


#### Machine Level

1024 bytes - 1000 bytes = 24 bytes

24 bytes / 8 bytes/double = 3 doubles

This is the answer, again automatically
handled by the compiler.

Pointer arithmetic is in
terms of the data types.


### Returning a Pointer

What if modified the above function
to return a position to the first
negative double instead?

    double* findFirstNegative(double a[], int n)
                        // Parameter notation interchangeable
    {
        ...for-loop...
            if (*p < 0)
                return p;
        ...
        // Default case: return a null pointer
        return nullptr;
                        
    int main()
    {
        double *fnp = firstFirstNegative(da, 5);
        
        cout << "The first negative value is " << *fnp << endl;
        
        cout << "It's at element number " << fnp - da << endl;
    }

#### Null Pointers

*nullptr* is the keyword introduced by C++11.

A null pointer has a well-defined value,
but we CANNOT follow it. It points to nothing.

Instead, we compare against it or assign it
other pointer to nullify them.

nullptr is really memory address 0x0, address
address 0, (may vary by machine). 

Can also be represented via *NULL* in C, C++98, C++11


### More Pointer Notes

Say we have the following code:

    const char test2[] = "TESt1!";
    
    for (const char *c = test2; *c != '\0'; c++)
    {
        cout << c << endl;
        cout << *c << endl;
    }
    
    cout << test2 << endl; // C-string unmodified

What will it do? It'll print out:

    TESt1!
    T
    ESt1!
    E
    St1!
    S
    t1!
    t
    1!
    1
    !
    !
    TESt1!

Why? Because we're advancing a pointer along. 
Then we tell cout to print out the pointer,
which it knows is a pointer-to-a-char,
so it follows it and punches out a char array,
a C-string.

After all, the iterator, c, a pointer,
is equal to test2, a C-string, and array
identifiers are basically pointers to 
the start of an array in memory.

Here, we've made a copy of that pointer,
then passed it to cout, thus leading to
the same output. 

What about the single chars? Those ones are
produced by *c, which forces a follow-the-pointer
to the specific char. 

Why is the C-string shortening?

Well, the pointer that marks the beginning
of the C-string's char array is being moved along.

*c* is initialized to the value of the array's
identifier, meaning that it points at the first
element. Then, it's moved to point at successive
chars in the array.

When this happens, cout will think that the
start point of this C-string is at the spot
in memory that *c* points to. It then prints
out the C-string, starting with *c till the
first '\0'.

Notice, however, that the pointer for test2[]
was never changed; in fact, the compiler doesn't
seem to be letting us do so!

We've only been changing *c*, a copy of the pointer
that test2 is. So, when we order cout << test2,
we simply get the expected (and whole) C-string back again!

'Tis a way to print out shortened versions of
a string without modifying it!

Can we do this in the opposite direction, e.g.
"Hello" --> "ello" --> "llo" --> "lo" --> "o"?

Is there a way to do this without changing
the original C-string, and without having to 
make a copy? I think the second condition
renders this impossible.

Let's do this with pointers, but making
a copy. 

    const char test2[] = "TESt1werwe!sef";
    
    char copy[100];
    
    // Could be done via a laborious for-loop
    // strcpy(copy, test2);
    
    // Here's that laborious loop:
    // This assumes copy is large enough
    // to hold test2
    
    char *p1 = copy;
    
    // *(p2-1) is trying to copy everything, up to
    // and including the first zero-byte
    
    for (const char *p2 = test2; *p2 != '\0'; p2++)
    {
        *p1 = *p2;
        p1++;
    }
    
    cout << copy << endl;
    
    
    // Now we handle the gradual reverse truncation
    
    // int length = strlen(copy); // The easy way
    
    // The hard way:;
    
    int length = 0;
    char *k = copy;
    for (; *k != '\0'; k++)
        ;
    length = (k) - copy;
    cerr << length << endl;
    
    int count = 0;
    // Off-by-one if not copy - 1; stops right before last (first)
    // char otherwise
    for (char *p3 = copy + length; p3 != (copy - 1); p3--)
    {
        cout << p3 << endl;
        // cerr << ++count << endl;
    }


Oh whoops! The above actually gives the opposite
gradual truncation of the preceding example:

    TESt1werwe!sef
    14
    
    f
    ef
    sef
    !sef
    e!sef
    we!sef
    rwe!sef
    erwe!sef
    werwe!sef
    1werwe!sef
    t1werwe!sef
    St1werwe!sef
    ESt1werwe!sef
    TESt1werwe!sef
          
We want a different result though,
one where we're steadily chipping
off the right-side characters. 

The above is easily modified to:

    int count = 0;
    // Off-by-one if not copy - 1; stops right before last (first)
    // char otherwise
    for (char *p3 = copy + length; p3 != copy - 1; p3--)
    {
        cout << copy << endl;
        *p3 = '\0';
        // cerr << ++count << endl;
    }
    
This gives:

    TESt1werwe!sef
    14
    TESt1werwe!sef
    TESt1werwe!sef
    TESt1werwe!se
    TESt1werwe!s
    TESt1werwe!
    TESt1werwe
    TESt1werw
    TESt1wer
    TESt1we
    TESt1w
    TESt1
    TESt
    TES
    TE
    T

N.B. that we're able to cout << copy
and still see this result. Why?
Because we're modifying the values
whose start *copy* points to.

We're doing this via *p3. which was
initialized to point to the same 
memory address as copy.
    

            
### Pointer Arithmetic Rules

*&var ==> var

The parantheses wrap like this: *(&(var))

&(a[i] + j) ==> &(a[i+j])
    
&(a[i] - j) ==> &(a[i-j])
    
&a[i] < &a[i] ==> TRUE if i < j
    Same for other Boolean comparison operators
    If we have pointers into the SAME array,
    they can be used this way too
    
&a[0] ==> a from &(*(p + 0))

pointer[i] ==> *(p + i)  

&a[i] - &a[j] ==> i - j


### Additional Notes from Forney

If we want to change a pointer within
a function, we need to pass it by reference:

<type>* &<pointer>

Otherwise, we're creating a local copy of a pointer
for a function to use when we pass it as an argument.

*** Note that adding two pointers is ILLEGAL. ***

Also, local variables are NOT safely allocated once
we return from a function that uses them. Thus,
if we had a pointer whose scope and lifetime
superseded and outlasted them, but pointed to one
of them, we would NOT be able to safely follow it.

There WILL no be guarantee that those variables
and their values will still be there. 


    
    

## Lecture 16: 25 November 2013

Smallberg begins by posing a problem
and then proposes a solution. This is an 
awesome way to teach: it demonstrates that
things have been built the way they are because
of problems previously encountered. 

Example given: a game where we want variables
to represent aliens as a type. 

Sounds like we're about to learn classes! :D

So it breaks down to this: each alien has
a set of attributes associated with it. 

We could store all this in several different
arrays, with corresponding positions across
the arrays showing the info for one alien, e.g.
the one with 110 health, 25 attack, 35 defense.

However, this is only true because of the convention
we set up; there is nothing in the code itself
that shows those attributes as belonging to 
particular aliens. We want to group them.

Can we do this with a multi-dimensional arrays?
No, because then we're mixing up types, e.g. 
strings, doubles, and ints. 

So, we extend the language by creating new types:
**structs**. Classes will come later, for when 
we want to associate methods with these new
object types. 


### Structures

Keyword: struct

    struct Employee
    {
        string name;
        double salary;
        int age;
    };

Note the convention of
naming structs using sentence case.

This is a new type, type Employee,
with every new Employee having
these three *data members* or
*fields* or *instance variables*
or *attributes*. 

Objects created from the model of a
struct are called *instances* of it.

Note that this is just a declaration:
this is what it means to be an Employee,
but we haven't created any employees yet. 

Note that the semicolon is **required**. 
Do NOT forget it!

Note also that we **cannot initialize** at
declaration--when we're using pre-C++11-compliant
compilers; C++11 gives us the option of assigning
default values to struct and class data members.

Otherwise, the compiler thinks that the 
struct declaration isn't yet finished
and misinterprets the rest of the code as part of it. 

Note that structs are conventionally declared outside of 
any other function, but can be declared elsewhere
and *scope rules still apply to them as well*.

"Don't forget the semicolon!"

Omg, Smallberg is emphasizing it so much, haha.


#### Employee struct example

Normally, we'll create many Employees,
but we'll create just one as an example:

    struct Employee
    {
        string name;
        double salary;
        int age;
    };

    int main()
    {
        double d; // Syntax: <type> <identifier>
        
        Employee e1; // Same with structs
        
        Employee e2; 
    }
    
So what does this mean? 

e1 is created and has:

    name: ""
    salary: ???
    age: ???
    
e2 is created and has:

    name: ""
    salary: ???
    age: ???

Note that they are not initialized.
All the members are thus initialized
the way they would be as instances of
types not associated with a struct. 

So, name is the empty string and the 
other two are junk values.

When if we want to change a particular 
employee's member's value?

Use the **dot operator**:

    e1.name = "Fred";

lvalue should be an object; rvalue should
be a member of that object:

    object.member

Another example:

    e1.

Here, only legal possibilities to follow
that dot: name, salary, age. 

    e1.salary = 50000;
    
e1 currently has:

    name: "Fred"
    salary: 50000
    age: ???

What if we had:
    
    e1.age = 35;
    e1.age++;
    
Here, we apply the postfix incrementation
to the age member of e1.

"Happy birthday, Fred, you're now 36."

name: "Fred"
    salary: 50000
    age: 36

We haven't changed what we can do with
built-in types and types created by classes;
we've just found a way to package them together.


### Input into a Struct Data Member Instance

This is perfectly possible:

    cout << "Enter a name: "; // Suppose user enters "Ethel"
    getline(cin, e2.name):

    cout << "Enter a monthly salary: "; // Suppose user enters 5000
    cin >> e2.salary;
    e2.salary *= 12; // To get annual salary
    
    
### Shorthand Declaration of Instances

Structs can have instances of them declared
at the same time as their own declaration:

    struct Such 
    {
      char soCstring[5] = "test";
      int muchNumber = 5;
      
      // Instances of struct Such:
    } doge, doge2, doge3;
    
Syntax:

    struct _identifier
    {
        ...
        // Members
        ...
    } _instance1, _instance2, ...;
    
    
### Structs in Memory

// From Forney's notes

Memory addresses are segmented into
**machine words**, which is the maximum
data size that a CPU is capable of processing,
something that will vary by architecture.

On a 64-bit system, that's 8 bytes.

A **word boundary** is the end address of a
word in memory. For a 64-bit system that has something
starting at address 1000, the word boundary would be
1007; counting 1000-1007 (rather than just finding the
difference of 1007 minus 1000) gives us 8 bytes, as expected.

Here's the important part: a struct/class individual 
members will be sequential *but not necessarily contiguous*
in memory. No variables not belonging to that struct/class
will be stored in between its members in memory though.
This allows the compiler to add padding in memory to align
things properly. 

The following example illustrates this:

    #include <iostream>
    #include <string>
    #include <cstring>
    
    using namespace std;
    
    struct inStructive {
    int i;
    double d;
    char c;
    };
    
    int main () {
    inStructive s;
    
    cout << static_cast<void *>(&s.i) << endl;
    cout << static_cast<void *>(&s.d) << endl;
    cout << static_cast<void *>(&s.c) << endl;
    } 
    

### Arrays of a Struct

Example:

    Employee company[100];
    
    // 100 things in an array,
    // each of which is an employee
    
    // Analogous to:
    
    double ky[5];
    
    ... // We fill elements 0 and 1
    
What company looks like:

company:    [0]             [1]         [...]
        
            name:           name:
            salary:         salary:
            age:            age:

What if we want to add another employee to this array?

    company[2].name = "Ricky";
    
This selects one of the employees in the array,
then selects one of its members:

        [2] 

    name: "Ricky"

Work the hierarchy from top to bottom to avoid
getting confused. 

Typically, we would use this array as we have been:
only partially filling it, so we'd also have an int
variable telling us the number of employees. 

What does this do?

    for (int k = 0; k != company[2].name.size(); k++)
    {
        cout << company[2].name[k] << endl;
    }
    
This prints "Ricky" vertically.

This selecting company[2], Employee Ricky,
then we access the name member, then we access
its individual chars. 

Don't be intimidated by the dots and the brackets.

If we were accessing company via a pointer:

    company[2]->name[k];
    
Note also that creating an array with a base 
type of a class or struct will call the constructor
for *each and every element* of that array!

To avoid this, create an array of pointers to 
instances of that class/struct type instead,
and allocate dynamically as needed.

    Employee* company[100];
    
    // To track how much of array is used
    int nCorps = 0;
    
    // Need to create new conglomerate:
    
    for (int i = 0; i < 15; i++)
    {
        company[i] = new Employee;
        nCorps++;
    }

    // Using crazy pointer-to-pointer
    // notation is also possible, but
    // this is unnecessary because of pointer
    // arithmetic
    
    for (Employee** p = company; p < 15; p++)
    {
        *p = new Employee;
        nCorps++;
    }
    

### Function Using Struct Type as a Parameter


#### Passed-by-Value

Assume we have:

    struct Employee
    {
        string name;
        double salary;
        int age;
    };
    
Then go to:
    
    // We pass an object of type Employee

    // We pass by value here, so a brand-new
    // Employee object e is created as a local
    // variable that has the scope and the lifetime
    // of the function
    
    // Copies will be made of the passed Employee's
    // data members into e
    
    void printPayCheck(Employee e);
    
    int main()
    {
        Employee company[100];
        int nEmployees = 0;
        
        ... // Fill array, set nEmployees

        // nEmployees is now 2
        
        // Elements [0] and [1] are filled
        
        // Let's print a paycheck
        
        printPayCheck(company[1]);
        
        // We have a function, and we want
        // to pass a struct object to it
        
    }

    void printPayCheck(Employee e)
    {
        cout << "Pay to the order of " << e.name
                << " the sum of $" << e.salary/12 << endl;
    }
    
Here, we passed-by-value, but this is impractical
when we deal with real-world scenarios, as we'll be
copying a lot of data (and wasting memory and time and CPU)
just to look at the members.

Here, we copy over every member, even if we only need some
of them. 


#### Passed-by-Reference

Instead, we can do:

    void printPayCheck(Employee& e)
    {
      cout << "Pay to the order of " << e.name
                << " the sum of $" << e.salary/12 << endl;
    }
    
So a call like:

    printPayCheck(company[1]);
    
Means that e is another name for this
particular employee. 

But since we see Employee& in the function prototype,
we have to be suspicioius: Do we need to change
any member values?

With PBV, we don't worry, because we're just
manipulating a copy. 

So we want: we want e to be another name
for an employee but not be able to change it:

    void printPayCheck(const Employee& e)
    {
        ...
        cout << ... << e.salary/12 << ...;
        ...
    }

e.salary/12 is still possible though. Why?
Because we're not reassigning e.salary!
We're only accessing its value, using it, 
outputting that result, then that is lost
afterward unless we store it into a variable.

So, void f(Blah b) is inferior to void f(const Blah& b)

What's cheap-to-copy? Built-in types 
and short strings. 

Anything bigger? Use PBCR. (Pass-by-constant-reference)
    
What if we want to change the big stuff?
Use PBMR (Pass-by-modifiable-reference) [omit the const]


### Select a member via a Pointer

Now, let's try celebrateBirthday():

    void celebrateBirthday(Employee& e)
    {
        // Change age
        e.age++;
    }
    
Pointer instead of a reference (we'll
be passed a pointer to an employee):

    void celebrateBirthday(Employee* ep)
    {
        // So how we change age?
        
        ep.age++; 
        // Error; ep is a pointer; there
        // is no .age member to access
        
        *ep.age++;
        // Idea: Follow the pointer to the object
        // and then access its .age member
        
        // Error: order of precedence 
        // has * being higher than ++
        // So it treats it as *(ep.age)++
        
        // This is indirection on an
        // attempt to access a non-existent
        // member of a pointer,
        // then we increment
        // Fail!
        
        // We could do:
        
        (*ep).age++;
        
        // This follows the pointer to the object
        // then we acess and increment the member
        
        // This is ugly; we want to select
        // a member of an object via a pointer
        
        ep->age++;
        
        // This correctly executes our idea
        
    }

Syntax:

    ptrToObject->member;
    
    // Equivalent to:
    
    (*ptrToObject).member;  
    
Both . and -> select members of an object
of a struct type. 

Use . when we're given the object directly,
and -> when we're given or using a pointer
to an object. 

The function call would require us to remember
to have an ampersand in front of the passed
employee:

    celebrateBirthday(&company[0]);
    
Note that pointers to instances of a struct/class
must have that class/struct type:

    class Blah {...};
    
    Blah test;
    
    Blah* ptrToBlahInstance = &test;
    
Note also that that pointer will point to the 
memory address of that object's first member.


#### Access Members of Struct-Based Objects

Now let's try printTotalPayRoll():

    double printTotalPayroll(const Employee* company, const int nEmployees)
    
Or:

    double printTotalPayroll(const Employee company[], const int nEmployees)
    {
        double total = 0;
        
        for (int k = 0; k < n; k++)
        {
            total += company[k].salary;
            
            // With a pointer: company[k]->salary
            // Hey, Smallberg did this once briefly
            // to show us what would come!
        }
        
        return total;
    }

What if want to print a list of our employee's names?

    // Visit each element of the array with a pointer
    for (Employee* ep = company; ep < company + nEmployees; ep++)
    {
        // Access member through pointer
        cout << ep->name << endl;
    }

Over 7,000 lines of notes! :D


### Reminders

- Don't forget the semicolon after struct { };

- Access members via . and -> (when using pointer to object)


### A Video Game with Targets

Let's say we have moving targets
("Catch that butterfly!") with it moving
one dimension, able to move left or right
on the integer number line. 

Next, we'll reanimate the game and have the 
targets keep track of their movements so that
we can later access their previous moves to 
show off in game replays.

Let's try:

    struct Target
    {
        int pos; // Current position
        
        // int history[1000]; 
        // Array to hold previous moves  
        
        // We could hold an array
        // of ints, e.g. bools, chars, etc.
        // 1,0; L/R; etc.
        
The problem: sizing this array. How large
does it need to be? It's totally arbitrary!

We want to dynamically size this log
of moves history. We could do this via <string>,
which dynamically resizes. 

        string history;
        
    };

Onward:

    int main()
    {
        Target t;
        .... // Moves
        
t:  pos: -1
    history: "RRLLLLR"

This is the current state of t.

But suppose we had:

    t.pos += 42;
    
t:  pos: 41

This isn't consistent with our
movement history. 

    t.history = "Hello"
    
Also doesn't make any sense.

One of the problems here is that 
we may have an idea of what it means
for a Target and its instance objects
to be valid, but we currently have no
way to make it impossible to prevent user
tampering with Target's objects. 

Firstly, what does it mean for an object
of type Target to be in a valid state?

- targets begin at pos 0

- .history should consist of only capital 'L' and 'R'

- pos should have only integer values

- Relationship between pos and history:
  pos is the end result of  
  the number of R's - the number of L's 
  (+1 and -1)
  
Properties like these are called **invariants**.

Everything we do with an object of type Target
should not change these invariants. We want the
language to enforce these constraints, helping
to eliminate many bugs. 

  
    
## Lecture 17: 27 November 2013


### Target struct

    struct Target
    {
        // Invariant:
            // History consists only of R's and L's
            // pos == # R's - # L's
        int pos;
        string history;
    }
    
    
    // We want to ensure that targets are
    // never put into an invalid state,
    // e.g. like how <string> always works
    
    
    int main()
    {
        Target t;
        Target t2;
        ...
    }

t | pos:
    history:
    
t2 | pos:
     history:
    
So what stops a user from changing
data and putting it into an invalid state,
e.g. t.history = "hello"?

Step 1: Encourage people to manipulate
objects using provided functions rather
than doing it directly. This can be enforced.
The functions themselves will manipulate 
whatever needs to be manipulated. 

We do this via:

    struct Target
    {
        // Member functions
        void init();
        bool move(char dir);
        void replayHistory();
        
        // Invariants:
            // History consists only of R's and L's
            // pos == # R's - # L's
        int pos;
        string history;
    }
    
"Member functions" are also called "methods"
or "operations". 

How do we use these?

    int main()
    {
        Target t;
        Target t2;
        
        t.init();
        t2.init();
        
        t.move('R');
        t.move('R');
        t.move('L');
        
        t.replayHistory();
        
        t2.move('L');
        ...
    }
    
.init() should initialize
pos to 0 and history to the 
empty string. 

After the above series of
moves:

t | pos: 1
    history: "RRL"

t2 | pos: -1
     history: "L"   
    
Thus, if we implement these
correctly and the user only uses
our provided functions, then we shouldn't
ever have a case where something is put
into an invalid state.  
    
    
#### Implementing member functions

When we call a member function
on an object, it is automatically
passed a pointer to the object it
is acting upon. 

.init() is passed
no parameters and returns nothing, but
it is automatically passed a pointer to 
the object. This is available to the
member function as the pointer keyword
**this**.



So, let's implement Target's member functions:

    void Target::init()
    {
        this->pos = 0;
        this->history = ""; // Make it explicit
                            // For coder's benefit
        
        // "this" is a pointer
        // to the object that
        // called the init() function,
        // e.g. Target t
        // t.init()
        
    }

We use the scope resolution modifier to 
tell the compiler that we are implementing the init()
member function that specifically belongs
to Target. Other structs might also have
an init() function. 

Why not the dot operator? The dot
expects an lvalue of an object, not an 
ADT like a struct.  
    
C++ does allow us to declare and implement
member functions inside of a struct/class, but
OOP and convention has us separating interface
and implementation, which is what we'll do
all the time when we have separate compilation. 

If we wanted to, it's considered acceptable
to implement really short functions inside of the
struct/class declaration itself, with *no semicolon*
following its implementing code block.

this-> is repetitive though. In fact, we can leave
off the "this->" altogether! It's just understood
that a member function is manipulating or accessing
the data members of the object that it is acting upon,
the one that the this pointer is pointing to. 

Onward:

    bool Target::move(char dir)

What if move() is called and passed
an invalid argument? We should have move()
return a bool to indicate if it succeeded.
    
In main(), we'll get a move character and then
pass that as an argument to move().

We can then test the return value of move()
to see if it worked or not--and display an
error message in the latter case. 

We don't have to test it everytime; just
when there's a possibility of invalidity.

We'll accept R and r, L and l,
but only store R and L in the history.
This makes things easier for user and developer.

    bool Target::move(char dir)
    {
        switch (dir)
        {
            case 'R':
            case 'r':
                pos++;
                // Or this->pos++;
                break;
            
            case 'L':
            case 'l':
                pos--;
                break;
            
            default:
                return false;
        }
        
        // Could not have gotten here
        // if invalid move
        history += toupper(dir);
        
        return true;
    }
    

We need to use the this-> if we have
another variable used in the function 
implementation with the same identifier
as a data member of the object.

    void Target::replayHistory()
    {
        for (size_t k = 0; k != history.size(); k++)
        {
            cout << history[k] << endl;
        }
    }
    
Note that replayHistory() uses a variable k.
Do we need this in Target? No. Data members are
for when we need an object to retain an attribute. 

Member function implementations can create
and use their own local variables alongside
data members of an object. 

As part of our testing process, we should check
that every member function never renders an object
invalid in some way. So long as this is true
and users use only these verified functions, then
we're good to go. 


### Constructors

There's still an opportunity for error here though.
Until we call init(), the target may be invalid. 

We want to ensure that Targets come into being
in a valid state. We want this to be automatic.
This function will automatically be called when
the object is created. We do not explicitly call it.

The magic name is simply the name of the struct/class:

    Target();
    
NO return type, NOT even void!

Implementation is what we previously did with init():

    Target::Target()
    {
        pos = 0;
        history = "";
    }
    
It will automatically be called when we create an object
of a type and is designed to initialize it into
a valid state. It is possible to have (multiple)
constructors with arguments. 

A constructor that takes NO arguments is called
the **default constructor**; it is the one called
when we do something like:

    <class> <new_object>;
    
Otherwise:

    <class> <new_object>(arg1, arg2, ...);


### Access Specifiers

    struct Target
    {
        Target(); // Constructor
        bool move(char dir);
        void replayHistory();
        
        // Invariants:
            // History consists only of R's and L's
            // pos == # R's - # L's
        int pos;
        string history;
    }

With a large program, we'll have
multiple created types, many different
functions, etc. 

Here, we want to enforce restricted
access to the data members.


#### Private

These members are accessible only to 
member functions. 


#### Public

Accessible to anything that can access the object.


#### Modified

Now so modified:

    struct Target
    {
        public:
            Target(); // Constructor
            bool move(char dir);
            void replayHistory();
        
        private:
            // Invariants:
                // History consists only of R's and L's
                // pos == # R's - # L's
            int pos;
            string history;
    }
    
So, move(), replayHistory() could access
pos and history, even though they're private,
but this is because they're member functions.

Think of it as only a player's internal
bodily functions being able to change heartbeat rate
for example. 

The public members are the interface to a new
**abstract data type (ADT)**. The private members
and the implementation of public member functions
are what allow us to have that interface actually
do stuff. 

So, we can no longer do:

    int main()
    {
        ...
        cout << t.pos; 
        // ERROR: trying to access private member
        ...
    }

The reason we don't allow this is so that we can
easily change our implementation without worrying
about the interface. We might, for example, not store
pos; we could just calculate it from history whenever
needed instead. 

Thus, all the other code that uses our
interface can continue to use it even if we totally
changed our implementation. Otherwise, they would break
if they depended upon on specific details of our 
implementation. 

<string> is a class that we've been using
for a long time, with public functions like
.size(). We cannot access or modify its private members.


### Accessors

What if we really do need to know a private data member?
Give access to it via a public function, e.g. 

    int Target::getCurrentPos()
    {
        return pos;
    }
    

### Mutators

What if we want to change a private data member?
Do it via a public function. Why this instead of
doing so directly? It allows us to control the 
changes possible to an object. 

Example:
    
    void Target::importHistory(string other)
    {
        history = other;
    }
    

### Non-Member Functions

Some additional function used in main():

    void repeatMove(Target& x, int nTimes, char dir)
    {
        for (int k = 0; k < nTimes; k++)
        {
            x.move(dir);
        }
    }

So here, we've used the public interface
of an object as part of a non-member function.

Another example:

    void report(Target& x)
    {
        cout << "There's a target at position "
                << x.getCurrentPos() << endl;
    }

Why do we pass a Target object by reference?

That would work, but we'd actually be working
with a copy of the object we intended to work
upon--that would involve copying over all the 
data members. 


### Const Member Functions

What if we did void report(const Target& x)?

Compile-time error! Why? Because it doesn't know
for sure that the member function we call won't
modify the object. The compiler won't know, because
the implementation could be in a totally different
file. 

To know if a member function will not modify
an object's data members, the compiler can only
by looking at the data type declaration. This will
allow us to create functions that pass by constant
reference.

To do so:

    // Member functions
    
    void replayHistory() const;

This const must go in the data type declaration
and in the member function declaration.

Syntax:

    <return_type> <member_function>(parameters) const;
    
This is a promise to not modify the target object. 

Always ask ourselves: do we need this member function
to modify the object? No? Make it const. 

Note that constructors cannot be const, as their job
is to correctly initialize any created objects. 

.size(), for example, is a const member function.

Note that we can have member functions that promise
not to modify arguments passed to them but that
may modify the object, e.g.:

    void foo(const string& str);
    
The reason this is allowed is because that's a
promise not to act upon the argument, rather 
than a promise not to modify an object created
from a class. In the latter case, we would need:

    void foo(const string& str) const;
    
Which would promise that when we call the member function:

    object.foo(str);
    
We won't modify str and we won't modify object. 


### Classes

The reason we use struct is because C has
struct for amalgamating together variables
of different types. 

C++ structs are different for C ones, though,
as they allow for class features.

So, everything we've done thus far could have
been done with:

    class Target
    {
        public:
            ...
        private:
            ...
    };
    
Classes and structs are basically identical
in C++, but *classes default to private* while
*structs default to public*. To change this,
just use access specifiers.  

In C, structs will just group together data
members, with no member functions possible.

The convention is to use structs for 
grouping together data members where
we don't have interesting behavior,
with the data members tending to be public. 

This allows for something like:

    struct Coordinate
    {
        double x;
        double y;
    }
    
All coordinates will then be one variable instead
of 
    
When we have interesting behavior that 
requires member functions, etc., declare
it as a class. 

Note that C++11 allows for us to 
assign default values to data members
of a struct or class. 

The constructor takes precedence though
if it also acts upon that data member.

Constructors can be private but this is
only useful in certain cases. 



## Supplemental Notes: 29 November 2013

// Extended weekend for Thanksgiving Weekend


### Based on the Book

Here follow notes from my annotated copy of 
Absolute C++, 5th edition.


#### The new Operator

First, some notes from the book.

*new* creates variables that do not have
identifiers to serve as their names.
The type of this new variable must be
specified.

Instead, new *returns a pointer* to them,
which we can store into a pointer variable,
and then use that to manipulate the 
dynamically-allocated variable (which is somewhere
in memory; the pointer is how we know where).

Syntax:

    new <type>;
    
This gives the returned pointer to nothing though.
Instead:

    <pointer-var> = new <type>;
    
To initialize a primitive type or to call a class
constructor:

    <pointer-var> = new <type/class>(args);
    
Make sure that the pointer type matches the type
of the allocated variable!

One last note: NEVER accidentally replace that
pointer variable pointing to the dynamic variable.
We won't be able to delete the variable otherwise,
and we'll have a memory leak.


#### Memory Management

The area of memory that new allocates variables into
is called the **freestore** or **heap**.

Variables allocated into them are called **dynamic variables**.

Contrast this with **automatic variables**, the ones we've
been using thus far. They are variables local to a function
(including main()) and are automatically handled for us.

They will be created when the function is called
and destroyed when it ends.

Contrast this again with **statically allocated variables**
or **global variables**, ones declared outside of any
function or class definition, including main(). The book
notes that static class variables are static in a different
sense.

Note that if too many variables are dynamically
allocated, then newer compilers will cause the program
to automatically end with an error message. Technically,
an exception is thrown by new, which can be caught.

Once a dynamically-allocated variable is no longer needed,
use the **delete** operator and wipe it out:

    delete <variable>;
    
Note however, that the variable is destroyed, not the pointer
to it that we created when we used new. 

That **dangling pointer** should  then be set to the 
**nullptr** to prevent that messy set of undefined behavior!


#### Dynamic Arrays

Previously, we've had arrays
that were fixed in size; their size
had to be known at compile-time or
else we'd have a build-error.

Dynamic arrays are dynamically-allocated
and avoid this problem. To create them:

    _baseType* ptrTo = new _baseType[SIZE]
    
If we omit the square brackets altogether,
then enough storage will be allocated for just
one variable of that base type.

Now, we can prompt for user or other program
input to determine an array size before we
actually create it, and the resulting array
can be used normally, as all array identifers
are really const pointers to their first indexed
variable.

To delete them from the heap when we're done, 
use:

    delete [] <dynamic_array>;
    
Do NOT forget about the []!

It is undefined to use "delete" all by itself
on a dynamic array.

Note also that the [] comes right after delete,
NOT after the array identifier.


#### An Array of Class Objects

Let's say we had a need for an array
of objects of a class. 

We could do:

    Target t_array[100];
    
But this will call the default constructor
to make 100 objects of type Target!

This also tells us that constructors are called
to fill arrays, even if we only need part of the
array. We don't want to create the objects until
we need them, e.g. what if the player loses early?


#### Returning an Array from a Function

To return array from a function:

    _baseType* _functionName(parameters);
    
Then, in the function itself, we can create
a dynamic array and return that (don't forget to
delete it later on!) or modify some array that was
passed as an argument.


#### Multidimensional Dynamic Arrays

Multidimensional dynamic arrays are perfectly possible,
but we need to remember to call delete [] on each
row and then on the table itself.

Basically, every time we call new, there should be
a corresponding delete or delete [].

To create them, we cannot use the convenient shorthand
of _name[][]. As Xcode dutifully reports, only the first
dimension of an allocated array may have dynamic size.

So instead, we create a dynamic array, then we cycle through
it and create a dynamic array for each of its elements:

Note that we'll need a dynamic array of pointers,
each of which will point to the start of a dynamic array.

    int **cinemaComplex = new int*[3];

To store the result of that dynamic allocation, we actually
need a pointer to a pointer. When we want to access one particular
int, we'll have to dereference with **cinemaComplex[#].

Now, we fill the pointer array with pointers to dynamic arrays:
    
    for (int i = 0; i < 3; i++)
        cinemaComplex[i] = new int[4];
        
Now, we have a multidimensional array.

To delete it after use:

    // Free 2D dynamic array from heap
    for (int d = 0; d < 3; d++)
        delete cinemaComplex[d];
    delete [] cinemaComplex;

This deletes each dynamic array in the dynamic
array of pointers, then deletes the pointer array.

Also note that [][] on an array in pointer terms is:

    *( *(cinemaComplex + j) + k)
    
Here, we evaluate from the inside out.


##### Graphically: 2D Dynamic Array

For example, let's consider how to get to [1][2]
of our previously-created cinemaComplex array
of pointers.

We take the pointer that points to 
the first row of the table:

-->  [0]     [1]     [2]     [3]
    
     [0]     [1]     [2]     [3]
     
     [0]     [1]     [2]     [3]  

And move it forward:

     [0]     [1]     [2]     [3]
    
-->  [0]     [1]     [2]     [3]

     [0]     [1]     [2]     [3]

Then we dereference to that array column:

     [0]     [1]     [2]     [3]
     
     
-->  [0]     [1]     [2]     [3]
      ^
      |
      
     [0]     [1]     [2]     [3]
      
And advance that pointer:

     [0]     [1]     [2]     [3]
     
     
-->  [0]     [1]     [2]     [3]
                      ^
                      |
                      
     [0]     [1]     [2]     [3]

And then dereference, thus giving
us the value at [1][2].


In terms of subscripts of a 2D array,
it can be seen like this:

0:     [0]     [1]     [2]     [3]
    
1:     [0]     [1]     [2]     [3]
     
2:     [0]     [1]     [2]     [3]


The first [] gives us the row, the
second [] gives us the column, indices
of the constituent arrays. 


##### Machine-Level: 2D Dynamic Array

Having seen the pointer arithmetic
and graphical representations of this,
here's the machine-level one:

([1000] [1008] [1016] [1024])
   |       |      |      |
  ...      |     ...    ...
           |
        ([2016] [2020] [2024] [2028])
                         ^
                         |
  
Here, I use parantheses to indicate that
the sequence of addresses is an array.
Note that they are consecutive and that
the dynamically-allocated array is off  
somewhere else in memory.

Note that the sizes of pointers varies by platform.
Here, the pointers in the first dimension
of the array are 8 bytes. The ints in the arrays
pointed to are 4 bytes apart.

Remember that we have an array of 3 pointers; 
each of those pointers points to an array
of 4 ints dynamically allocated to
the heap.


##### Machine-Level: Non-Dynamic 2D Array

For a non-dynamic 2D array of 4x4 doubles,
it would look like:

([1000] [1032] [1064] [1096])
       |      |      |      |
       |     ...    ...    ...
       |
    ([1008] [1016] [1024])

Here, the pipettes indicate a blown-up
portion of the contiguous set of memory addresses.
Note that [1000-1024] is one row of the array.
with each of those addresses being one column of
that row.

Do not get confused and think that this is somehow
a 1D array or that it is an array of pointers.
The latter is what we did with the first example.

#### Toss


### Smallberg's Video Lectures

Here follow the notes on Smallberg's posted video lectures:


#### Dynamic Allocation

Instead, we'll create an array of pointers
to Targets. Recall that arrays are created like
this:

    _baseType _arrayName[SIZE];

So:

    Target* targets[100];

creates an array of 100 pointers-to-Targets
and each of these are left uninitialized. 
Do NOT try to follow them right now, haha.

We'll track the number of interesting Targets
via nTargets. 

Then, boom, we suddenly need a Target object
to be created, and then we'll create a pointer
to it and store that pointer in targets[].

We can do that via:

    targets[nTargets] = new Target;
    
new creates a dynamically-allocated Target
object, and returns a pointer, which we store 
into one of the elements of targets[].

A constructor will be called if new is used with
a class; arguments can be used if the class has
constructors that support them.

We update the count of interesting Targets.

    nTargets = 0;
    
To use the Targets that we dynamically allocated,
we'll access an elment of targets[] and then
follow the pointer stored there to the object,
which allows us then to call the object's 
public member functions, access any public
data members, etc.


#### Dynamic Deallocation

To delete something that was dynamically-allocated,
use:

    delete <pointer_to_single_object>;

To delete an array of dynamically-allocated objects:

    delete [] <pointer_to_array_of_objects>;
    
So for our example, where we allocated single
Target-class objects nTargets times:

    delete targets[k];
    
Note that object allocated in memory is 
removed and that memory indicated to be
free and restored to the system for use,
but *the pointer is left dangling*!

Following targets[2] would be undefined
behavior at that point!

So we have in the diagram:

[0]     [1]     [2]     [3]
ptr     ptr     d_ptr   ptr
|       |       |       |
|       |       |       |
obj     obj             obj


If we want to get rid of this
dangling pointer, we could assign
[2] the contents of [3] and decrement
nTargets so that we know that now have
one fewer actual targets. 

If nTargets is 3, we'll never care
about [3]; we'll only access [0-2].

An additional step for caution, set
[3] to the nullptr, so that even if we
did accidentally access more than we were
supposed to, we would get a clear error
rather than a confusing one.

So now, we can create objects as needed,
and delete them when done.


#### Constructors with Arguments 

Say we have this:

    class Pet
    {
        public:
            Pet();
            ...
        private:
            int m_health;
            string m_name;
    };
    
    Pet::Pet()
    {
        // Used to set default values
        m_health = ???;
        n_name =   ???;
    }
    
    int main()
    {
        Pet p
    }

But what if we want to create objects
where default values need to be modified
at creation, e.g. names?

Then:

    class Pet
    {
        public:
            Pet(string name; int initialHealth);
            Pet();
            ...
        private:
            int m_health;
            string m_name;
    };
    
    Pet::Pet(string name; int initialHealth)
    {
        m_name = name;
        m_health = initialHealth;
    }
    
    Pet::Pet()
    { // Default constructor };
    
    int main()
    {
        Pet p("Fido", 20);
    }

Here, we have a constructor that takes two arguments.
In main(), we call it, pass it the appropriate arguments,
and boom, we have that new, customized object.

If we have an array of pointers to pets, e.g.:

    Pet* pa[100];
    
This is an array pointers to pets, perfect
for dynamic allocation and deallocation,
where we create objects as needed.

If we don't have a default constructor,
then we'll have errors until we do the constructor
calls with the appropriate arguments, e.g.

    pa[0] = new Pet("Frisky", 15);
    

#### Follow the Pointer Again and Again

Say each pet might have a favorite toy, 
which we'll represent via the 
Toy class. 

    class Toy
    {
        
    };
    
If every pet always had a favorite Toy,
we might have Toy m_favoriteToy in class Pet:

    ...
    Toy m_favoriteToy;
    
But what if we don't have a favorite Toy?
We can do a pointer instead, which might
lead to the nullptr!

    ...
    Toy* m_favoriteToy;
    ...
    
This allows us to dynamically allocate
favorite Toys, saving pointers to them
in m_favoriteToy, which will point to nullptr
by default:

    Pet::Pet(string nm, int initialHealth)
    {
        ...
        m_favoriteToy = nullptr;
        ...
    }
    
So how do we give a Pet a favorite toy?

Let's have another member function do that:

    void Pet::setToy(Toy* p)
    {
        m_favoriteToy = p;
    }

Parameter p should point to a dynamically allocated
Toy object:

    Pet dog1("Fido", 20); // New dog1 object of class Pet
    
    Toy* tp = new Toy; // Dyn-allo a Toy; pointer stored in tp
    
    dog1.setToy(tp); // Favorite toy is now tp, a pointer
                     // copied to m_favoriteToy
                    

#### Destructors
                     
Recall that local variable Toy* p was a pointer
copied by value and will pass out of scope
after setToy returns.

This applies to objects created from classes too,
but dynamically allocated objects are not automatically
deallocated; a failure to do so is a **memory leak**.

So, we want a function to clean-up after an object is destroyed.

To do so, we create a destructor for the class:

    ~Pet();
    
    ~ClassName();
    
Again, no return type, but it also CANNOT take arguments.

It is automatically called when an object of the class is 
about to be destroyed, as when we pass out of scope, 
and we can--should--implement it to destroy dynamically-allocated objects.

After it runs these clean-up tasks, the object is destroyed
scheduled.

Example:

    Pet::~Pet()
    {
        delete m_favoriteToy;
    }
  
What if we someone calls .setToy() repeatedly?
There should only be one favorite Toy.
Repeated calls would replace the previous
favorite Toy, which would also destroy the pointer
to the dynamically-allocated object, rendering it
garbage and a memory leak.

So, we'll delete any dynamically allocated
object previously created to and pointed to by
m_favoriteToy before we create and point to a new one:

    void Pet::setToy(Toy* p)
    {
        delete m_favoriteToy;
        m_favoriteToy = p;
    }
    
Just don't try to follow the m_favoriteToy
before it's been reassigned to a new pointer
to a new object. 

What about the very first run of .setToy(), though?

Well, a Pet will have m_favoriteToy set to NULL
by default. What will delete do to a NULL?
The answer is...nothing. Perfectly harmless; no need
to check to see if it's null and do something else if 
it is. 

So, this improved version of .setToy() works. 


### Toss



## Lecture 18: 2 December 2013

### Creating Many Instances from a Class

What if we had something like:

    int main
    {
        Targeg ta[100];
        ta[3].move('R');
        ...
    }

What if the game has only using part of that
array, including possibly none of it?

The thing is, when we declare that array,
we actually call that constructor 100
times!

We want to able to delay the construction
of Target objects.

We'll create an array of pointers to Targets, instead.

    Target* targets[100];
    
Right now, those pointers point to junk.


### The new Operator

This will create a new something, properly initialize
it and return a pointer to it. It will have no
identifier though; we can only access via the returned pointer.

    Target* targets[100];
    int nTargets = 0;
    ...
    targets[nTargets] = new Target;
    nTargets++;
    ...
    
targets: [0]
          |
          |
          V
        +----+  
        |  0 |
        | "" |
        +----+

To access individual Targets, we follow the pointer
stored in the array:

    targets[#]->move('R');
    
Named local variables ("automatic variables") live
on the **stack**

Variables declared outside of any function live in
the global storage area ("static storage area"),
the **store**

Dynamic storage lives on the **heap**. This is what
we're using here. It is created/killed during execution
and the lifetime of stuff in it is directly under
our control. 


### The delete Operator

Let's say a Target object is hot and must now be 
destroyed. How do we get rid of it and free up
the memory formerly used by it?

The **delete** operator. 

Syntax:

    delete <ptrToObject>; 
    
    // Dynamically allocated objects are
    // usable only through pointers pointing
    // to them
    
    delete [] <ptrToArrayOfDynamicObjects>;
    
Note that delete/delete [] can only be used
on things allocated dynamically, i.e. created with
new. 
    
This will delete the object, but does not automatically
set the pointer still pointing to it to nullptr. 

Example:

    delete targets[0];
    
targets[0] is now a dangling pointer. 

To get rid of this, we could just shift all
the other elements down, replacing the dangling
one in the process. If the order of the objects
in the array doesn't matter, move the last element
to replace the first, dangling one. 

    targets[0] = targets[8];
    nTargets--;
    
The first statement copies the pointer over;
the second decrements our counter of interesting
objects in the array, so we now forget about
the one at the end. 

We could also force the forgotten one to
be a nullptr, if so desired.

    targets[8] = nullptr;
    
To wipe out all the objects pointed to,
use a for-loop in combo with delete.

What would happen if we forgot to call delete
and did:

    targets[0] = targets[1];
    
We just lost the pointer to the object
created when we assigned targets[0] something
to point to!

We can no longer access/delete that object!
But it still takes up storage, which is now
*garbage". 

**Memory leak**!

When the entire program terminates, the
heap will be purge, but a long-running game
would create a lot of garbage, and we'll
encounter the problem of running out of memory
because we never recycled the storage we were using!

Analogy to a tank of water that represents
the amount of memory we have. We take water,
use it, then put it back. The problem is if we
never put back water, which would be akin to a
leak in the tank, eventually leading to a 
no memory situation. Small memory leaks are 
often difficult to notice; we won't see its
deleterious effects unless we have the program 
running for a long time. 

Real-world example: an ATM manipulating
Transaction objects, but fails to delete them afterward.
Eventually, the ATM will freeze up; but this won't be noticed
if it's restarted every night or something like that. 


### Constructor with Arguments

Example:

    class Pet
    {
        public:
            Pet(string nm, int initialHealth);
            string name() const;
            
        private:
            string m_name; 
            int m_health;
    };
    
Conventions: 

To distinguish data members
from parameters and member functions, we can do:

    m_member

Another convention uses a trailing underscore: 

    member_

***

We cannot have more than one
member with the same name, regardless of if one
is a member function, data member, public or private,
etc. 

***

    // Initialize custom pet
    Pet::Pet(string nm, int initialHealth):;
    {
        m_name = nm; 
        m_health = initialHealth;
    }
    
    // Accessor for name
    string Pet::name() const
    {
        return m_name;
    }
    
    int main()
    {
        Pet p1("Fido", 20);
        
        cout << "I have a pet named " << p1.name() << endl;
    }

Among the private data member, the member function parameter,
and the public function, the public function should have the
best, i.e. most readable, name. 

What if we now do:

    Pet p2;
    
Error! Won't compile! Why? There's no *default constructor*,
i.e. one that takes no arguments, aka, a *zero-argument constructor*. 

An object with primitive types for its data members created
with a compiler-created default constructor will have junk
data for those values. Data members that are of a class type
will have *their* default constructors called. Note that we need
to define our own assignment operator (=) when we have a class
type with dynamic data members. This prevents overwiting of pointers,
which would lead to memory leaks.

The only time we have a default one automatically
generated for us is when there are no constructors defined
for the class/struct. 

If we want our own default constructor, just define it:

    Pet::Pet()
    {
        m_name = "";
        m_initialHealth = 0;
    }

As long as the overloaded constructors differ in their
types and number of parameters, the compiler will be able to 
tell which one we want to call. 


### Dynamic Data Members

What if we want a function toyObject.addToy(), that lets
us add a favorite toy when we want to. They will start
with no favorite toy at construction; having one will
be optional. Instead of a data member of type Toy, it'll be 
a pointer to such a member:

    class Pet
    {
        public:
            Pet(string nm, int initialHealth);
            string name() const;
            void addToy();
            
        private:
            string m_name; 
            int m_health;
            Toy* m_favoriteToy; 
    };
    
    // Initialize custom pet
    Pet::Pet(string nm, int initialHealth):;
    {
        m_name = nm; 
        m_health = initialHealth;
        m_favoriteToy = nullptr; 
    }
    
    // Accessor for name
    string Pet::name() const
    {
        return m_name;
    }
    
    // Add a favorite toy
    Pet::addToy()
    {
        m_favoriteToy = new Toy;
    }
    
    void f()
    {
        pet p1("Fido", 20);
        p1.addToy();
    }
    
    
### Destructors    

But what about when we leave the function?
What happens to this dynamically-allocated
favorite Toy? Well, it's in the heap, not
the stack! It is *not* an automatic local
variable and so will *not* be automatically 
destroyed. 

p1 will pass out of scope and be destroyed,
including the pointer m_favoriteToy,
but NOT the Toy object it pointed to. 

ONLY *delete* can handle that task. Memory leak!

We could write a member function designed
to handle clean-up tasks (e.g., deallocate things),
but we want it to run automatically, the same
way constructors are run automatically when we
want to properly initialize an object. 

Syntax:

    ~ClassName()
    {
        ...
        delete ...
        ...
    }
    
Again no return type, not even void, but also
NO arguments! This also means NO overloading destructors.

LOL, Smallberg introduced this as the MAGICCLEANUP()
function:

    Pet::MAGICCLEANUP()
    {
        delete m_favoriteToy;
    }
    
Note that we don't have to worry about nullifying
pointers left behind by deleting the objects they point to,
as when a destructor is automatically called. Why?
Because a destructor is called right when an object is 
passing out of scope; those data member pointers-to-objects
will pass out of scope and disappear.

Real-life examples: closing network connections, cleaning off 
objects no longer needed on screen, etc. 

Problem with our previous implementation of .addToy():
what if it's called multiple times? We'd replacing
m_favoriteToy with a new pointer, causing a memory leak
as we lose access to the first favorite toy. This is true
even if we a destructor; it only has m_favoriteToy 

What about delete on a nullptr? No biggie; harmless. 

Fix:

    void Pet::addToy()
    {
        delete m_favoriteToy; 
        m_favoriteToy = new Toy;
    }



## Lecture 20: 4 December 2013


### Recall

For selecting members of an object, use
the dot operator (.) when the lvalue is an
actual object; use the arrow operator (->) when
the lvalue is a POINTER to an object:

    object.member;
    
    ptrToObject->member;


### Creating Objects from a Class

When it comes to the <string> class,
it's something like:

    class String 
    {
        public:
            string(const char*)
            string();
            int size() const;
            ...
        private:
            ...
    };
    
Here, <string> has two constructors; a default one
that takes no arguments, and one that takes an argument,
a C-string that then creates a <string> object with
that initialization. 

Examples: 

    string s("Hello"); // Here, s has "Hello"
    string s2; // Here, s2 has "", the empty string
    
    cout << s.size(); // Writes 5
    
But wait, we always did:

    string t = "Hello";
    
Well, this is the same thing as string t("Hello"),
when a class has a constructor that takes only one 
argument. 

Example code:

    #include <iostream>
    
    using namespace std;
    
    class Test
    {
        public:
        
            Test(int first);
            ~Test();
            void display() const; 
            
            
        private:
        
            int* array;
    };
    
    Test::Test(int first)
    {
        array = new int; 
        
        *array = first;
    }
    
    Test::~Test()
    {
        delete array;
    }
    
    void Test::display() const
    {
        cout << *array << endl;
    }
    
    
    int main(int argc, char *argv[]) 
    {
        Test t1(9);
        
        Test t2 = 10;
        
        t1.display(); // Outputs 9
        
        t2.display(); // Outputs 10
    }


Two arguments: Blah b2(10,20);

One argument:  Blah b1(10);

No arguments:  Blah b0;

"Blah b0()" would not call the default constructor.

Why? Consider this: "int f()", which is a *function declaration*. 

So, Blah b0() would actually be declaring a function that
takes no arguments and returns an object of type Blah. 

This is why we need to consider <class> <objectName> to be the
syntax for default construction instead. 

For all other constructors (that take arguments), then we 
use parantheses. 

If we declare no constructor for a class, then the compiler
writes a default constructor us, leaving data members of 
primitive data types uninitialized, and class types default
constructed.

This is what we saw with the earlier Employee class. 

It is not always necessary to create default constructor
if it makes no sense to have one, e.g. we really want to 
restrict the characteristics of an object of a class. 

Note also that we can overload constructors, so long as they
differ in the parameter data types or number of parameters. 


### Pointer Data Members

Example game where killer robots throw
rocks at us; they may or may not be carrying a rock. 

    class Rock
    {
        public:
        
            double weight() const; 
            ...
        
        private:
            ...
    };
    
Every robot has a cooling fan, which is not optional for
a robot. 

    class Fan
    {
        public:
            void turnOn();
            ...
        private:
            ...
    };
    
Then for the Robot class:

    class Robot
    {
        ...
        private:
            Fan m_cooler;
            Rock* m_rock;
    };
    
The Robot constructor will initialize
m_rock to the nullptr by default. It may
or may not have a rock; having a pointer
to a Rock lets us dynamically allocate
and deallocate. 

Example:

    void Robot::blah()
    {
        ... // Check if robot is carrying a heavy rock
        
        if (m_rock->weight() > 50) // m_rock is a pointer
            m_cooler.turnOn(); // m_cooler is an actual object
        ...
        
    }
    
But what if the robot doesn't have a rock?
That'd be following the nullptr--undefined behavior!

We try this:

    if (m_rock->weight() > 50 & m_rock != nullptr)
        ...
        
We still get an error. Why? The Boolean AND operator (&&)
checks Left to Right, because it's designed to shortcut:
if loperand is false, skip checking the roperand; we already
know that it'll be false. 

Similary, the OR operator skips checking its right operand
if the left operand is TRUE, as only one needs to be true. 

Always test for the nullptr FIRST!

Similary, check array bounds before performing an operation
on that array. 


### Complex Numbers Class Example

Let's say we need to write our own class for complex numbers,
(the library actually already has one for this). 

    class Complex
    {
        public:
            Complex(double real; double imaginary);
    };
    
    int main()
    {
        Complex c1(4, -3); // 4 - 3i
    }

Would default constructing a complex number make sense? 

Maybe; we'd likely initialize it to 0. 

So:

    class Complex
    {
        public:
            Complex(double real, double imaginary);
            Complex();
            
            double real() const; // Display real part
            double imaginary() const; // Display imaginary part
        
        private:
            double m_real;
            double m_imag;
    };

    Complex::Complex(double real, double imaginary)
    {
        m_real = real;
        m_imag = imaginary;
    }
    
    Complex::Complex()
    {
        m_real = 0;
        m_imag = 0; 
    }
    
    double Complex::real() const
    {
        return m_real;
    }
    
    double Complex::imaginary() const
    {
        return m_imag;
    }
    
    int main()
    {
        Complex c1(4, -3); // 4 - 3i
        Complex c2;        // 0 + 0i
        cout << c1.real(); // Writes 4
    }
    
Let's say that our metric find that people
are constantly multiplying/dividing complex
numbers and representing them in polar coordinates
would improve our class' performance. 

We can do this without changing the interface. 
Why? The data members are private!

Now we'd have something like:

    double Complex::real() const
    {
        return m_rho * cos(m_theta);
    }
    
Doing a bit o' math:

    Complex::Complex(double re, double im)
    {
        m_rho = sqrt(re*re + im*im);
        m_theta = atan(im, re);
        m_real = re;
        m_imag = im;
    }
    
We have not changed the visible, public interface
of our code, but we have completely revamped 
the implementation "under the hood". 

This is known as:


#### Encapsulation

**encapsulation** also called **information hiding**
or **data abstraction**.

Guideline: Except for simple types with no interesting behavior,
data members should be private. 

As long as something works correctly, we don't care
how it works--unless we're the ones trying to make it
work well, haha. 

// 9,000+ lines of notes!


#### Overloading

In C, every function must have a different name; 
there, we'd have to name them differently. 

In C++, we can overload. 

We can overload functions (reuse a name)
if the functions differ in the number or
types of arguments. 

Examples:

    void draw(Rectangle r);
    
    void draw(Circle c);
    
The compiler can also cast automatically,
e.g. when we pass an int to a constructor that
expects a double, or vice-versa. 

Say we had:

    void f(double d);

    void f(int i);

    f(42); // Calls void f(int i);
    
Compilers prefers functions that are an exact
match parameter-wise.

But what if we had:

    void g(int i, double d);
    void g(double d, int i);
    ...
    g(10, 20); // If both candidates are equally good,
               // it'll consider this ambiguous and
               // complain, giving a build error
               
    g(10, 20.0); // No problem here


### Interfacing Classes

Say we had a Company object, with Employee
members that can earn a bonus, and that bonus will
be given as a percentage of the salary. 

// See the example code in the parent folder

    class Employee
    {
    
        public:
            Employee(string nm, double sal, int ag);
    
        private:
            string m_name;
            double m_salary;
            int m_age;
    };

    Employee::Employee(string nm, double sal, int ag)
    {
        m_name = nm;
        m_salary = sal;
        m_age = ag;
    }

    class Company
    {
        public:
            Company();
            void hire(string nm, double sal, int ag);
            void setBonusRate(double r);
            void giveBonuses() const;
        
        private:
            // A collection of employees, not all
            // immediately hired
            
            Employee* m_employees[100];
            int m_numEmployees;
    };

    Company::Company()
    {
        m_numEmployees = 0; 
    }

    void Company::hire(string nm, double sal, int age)
    {
        if (n_numEmployees == 100) 
        { // ERROR }
        
        
        m_employees[n_numEmployees] = new Employee(nm, sal, ag);
        m_numEmployees++;
    }

Bonus rate will be stored with the Company class.

    void Company::setBonusRate(double rate)
    {
        m_bonusRate = rate;
    }
    
    void Company::giveBonuses()
    {
        for (int k = 0; k < m_numEmployees; k++)
            m_numEmployees[k]->receiveBonus();
    }
    
Here's receiveBonus():


    void Employee::receiveBonus()
    {
        cout << "Pay to the order of " << m_name
                << "$" << ... << endl;
    }
    
We need a percentage of the salary.

We have a data member with the Employee object
for the salary. What about the bonus rate? It's
stored with the company object. Can the employee ask
the company for the bonus rate? 

Yes, if we implement that:

    double Company::bonusRate() const
    {
        return m_bonusRate()'
    }
    
The problem? The employee doesn't know for whom it
works! 

So, let's modify Employee:

    class Employee
    {
    
        public:
            Employee(string nm, double sal, int ag);
    
        private:
            string m_name;
            double m_salary;
            int m_age;
            Company m_company;
    };

What if we added "Company m_company" as a member?
No, that makes no sense, as each employee would then
contain a different company object altogether!

Just have a pointer to the hiring company. 

    class Employee
    {
    
        public:
            Employee(string nm, double sal, int ag);
    
        private:
            string m_name;
            double m_salary;
            int m_age;
            
            Company* m_company;
    };

To initialize this new data member, we need to modify
the constructor for Employee and Company's hire function:

    Employee::Employee(Company* cp, string nm, double sal, int ag)
    {
        m_name = nm;
        m_salary = sal;
        m_age = ag;
        
        m_company = cp;
    }

    void Company::hire(string nm, double sal, int age)
    {
        if (n_numEmployees == 100) 
        { // ERROR MESSAGE: "Too many employees--LEAN is MEAN!"}
        
        
        m_employees[n_numEmployees] = new Employee(this, nm, sal, ag);
        m_numEmployees++;
    }
    
We use **this**. Why? Every member function is automatically
passed a pointer to the calling object, meaning we can tell
the new employee will have a pointer to the Company object
that called the hire() function. 

So, finally:

    void Employee::receiveBonus()
    {
        cout << "Pay to the order of " << m_name
                << "$"
                << (m_company->bonusRate() * m_salary)
                << endl;
    }

This is an obvious allegory to the Arena and Zombie
classes in Project 7.

Remember also that Company will need a destructor to
deallocate those new-created Employees.

    Company::~Company()
    {

Can we do just "delete m_employees"? NO! It's not
even dynamically allocated! The employees (referred to via
the pointers stored in the array) are dynamically allocated.

    for (int k = 0; k < m_numEmployees; k++)
        delete m_employees[k];
    }
    
Be careful of the for-loop condition; we'd try to follow
a dangling pointer otherwise. Remember also that we don't
need to set everything to nullptr; the destructor is only called
when the object is about to pass out of scope, which would
destroy all the pointers as well. 

And that was our last ever CS 31 lecture! :O

















