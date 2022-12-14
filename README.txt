                            A N T L R 
======================================================================
 *SOFTWARE RIGHTS*

 ANTLR 1989-2006 Developed by Terence Parr @ University of San Francisco

 We reserve no legal rights to the ANTLR--it is fully in the
 public domain. An individual or company may do whatever
 they wish with source code distributed with ANTLR or the
 code generated by ANTLR, including the incorporation of
 ANTLR, or its output, into commerical software.

 We encourage users to develop software with ANTLR. However,
 we do ask that credit is given to us for developing
 ANTLR. By "credit", we mean that if you use ANTLR or
 incorporate any source code into one of your programs
 (commercial product, research project, or otherwise) that
 you acknowledge this fact somewhere in the documentation,
 research report, etc... If you like ANTLR and have
 developed a nice tool with the output, please mention that
 you developed it using ANTLR. In addition, we ask that the
 headers remain intact in our source code. As long as these
 guidelines are kept, we expect to continue enhancing this
 system and expect to make other tools available as they are
 completed.

 The primary ANTLR guy:

 Terence Parr
 parrt@cs.usfca.edu
 parrt@antlr.org

______________________________________________________________________

WELCOME TO ANTLR!

If you have problems or think you have found a bug in ANTLR, see the
section BUGS in the ANTLR manual.

Please consult the INSTALL.txt file for information on tested
configurations.  If you have a comment about an already tested
configuration, or have tried ANTKR on a new configuration, please let 
us know as described in INSTALL.txt. Free software only works if we 
all help out.

Finally, we cannot guarantee that this release will not completely 
wipe out all of your work from your system.  We do some simple testing 
before each release, but you are completely on your own.  We recommend
testing this release on a source repository that is not critical to 
your work.  

         THIS SOFTWARE IS SUPPLIED COMPLETELY "AS IS".  
                       NO WARRANTY....

Thanks for your support!

  -The ANTLR Team-

______________________________________________________________________

WHAT IS ANTLR?

 ANTLR, (AN)other (T)ool for (L)anguage (R)ecognition - formerly known 
 as PCCTS - is a language tool that provides a framework for 
 constructing recognizers, compilers, and translators from grammatical 
 descriptions containing actions in the following languages:

  Java, 
  C++, 
  C# or
  Python
 
 (You can use PCCTS 1.xx to generate C-based parsers).

 Computer language translation has become a common task. While 
 compilers and tools for traditional computer languages (such as C or 
 Java) are still being built, their number is dwarfed by the thousands 
 of mini-languages for which recognizers and translators are being 
 developed. Programmers construct translators for database formats, 
  graphical data files (e.g., PostScript, AutoCAD), text processing
 files (e.g., HTML, SGML).  ANTLR is designed to handle all of your 
 translation tasks.

 Prof. Terence Parr has been working on ANTLR since 1989 and, together
 with his colleagues, has made a number of fundamental contributions
 to parsing theory and language tool construction, leading to the 
 resurgence of LL(k)-based recognition tools.

 Have a look at the history section at the end of this document on 
 how ANTLR has evolved over time. For  most  up-to-date informaton 
 read http://www.antlr.org/history.html.
______________________________________________________________________

UPGRADING?

 See

   http://www.antlr.org/blog/CHANGES-2.7.7.txt

 for a description of features new in this version. There are no
 incompatibilties known to a previous 2.7.x installation. If you found
 a problem please let us know.

______________________________________________________________________


INSTALLATION?

 Please read the INSTALL.txt file for installation instructions. The
 brief summary is:

  $ ./configure 
  $ make
  $ make test         # optional
  $ su root           # optional
  $ make install

______________________________________________________________________

ANTLR IS INSTALLED - WHAT'S NEXT?

 Please read "doc/getting-started.html" on what you are supposed to
 do. Here's a very brief summary for the impatient:

 ANTLR is a command line tool. To run ANTLR you need to have JAVA
 installed. The basic steps are:

  a. write a grammar file - mygrammar.g

  b. run ANTLR like

       $ CLASSPATH=antlr.jar

       $ java antlr.Tool mygrammar.g

  c. write a driver program using source code generated by ANTLR, ie.
     Main.java, main.cpp, Main.cs or main.py

  d. link generated code, your driver code, ANTLR's core library and
     any additional library you are using together to get an 
     executable

  f. run the executable on arbitrary input to be parsed

 For a set of standard examples have a look into directory "examples"
 and appropriate subdirectories.

______________________________________________________________________

WANT TO KNOW MORE?
  
 The documentation is in the "doc" subdirectory and "index.html" is 
 the main entry point. 

 Further information available at

 http://www.antlr.org

______________________________________________________________________

WHO CONTRIBUTED TO THIS MESS?

 Project Lead and Supreme Dictator Terence Parr, University of San 
 Franciso

 Help with initial coding John Lilly, Empathy Software 

 C++ code generator by Peter Wells and Ric Klaren

 C# code generation by Micheal Jordan, Kunle Odutola and Anthony 
 Oguntimehin. 

 Python's universe has been extended by Wolfgang H?felinger and Marq 
 Kole

 Substantial intellectual effort donated by Loring Craymer, Monty 
 Zukowski, Jim Coker, Scott Stanchfield, John Mitchell, Chapman 
 Flack (UNICODE, streams)

 Source changes for Eclipse and NetBeans by Marco van Meegen and 
 Brian Smith

 Infrastructure support from Perforce - The world's best source 
 code control system


______________________________________________________________________

WANNA KNOW ABOUT ANTLR's HISTORY?

 The PCCTS project began as a parser-generator project for a graduate 
 course at Purdue University in the Fall of 1988 taught by Hank Dietz
 "translator-writing systems". Under the guidance of Professor Dietz, 
 the parser generator, ANTLR (originally called YUCC), continued after
 the termination of the course and eventually became the subject of 
 Terence Parr?s Master?s thesis. Originally, lexical analysis was 
 performed via a simple scanner generator which was soon replaced by 
 Will Cohen?s DLG in the Fall of 1989 (DFA-based lexical-analyzer 
 generator, also an offshoot of the graduate translation course). 

 The alpha version of ANTLR was totally rewritten resulting in 1.00B. 
 Version 1.00B was released via an internet newsgroup (comp.compilers) 
 posting in February of 1990 and quickly gathered a large following. 
 1.00B generated only LL(1) parsers, but allowed the merged 
 description of lexical and syntactic analysis. It had rudimentary 
 attribute handling similar to that of YACC and did not incorporate 
 rule parameters or return values; downward inheritance was very 
 awkward. 1.00B-generated parsers terminated upon the first syntax 
 error. Lexical classes (modes) were not allowed and DLG did not have
 an interactive mode. 

 Upon starting his Ph.D. at Purdue in the Fall of 1990, Terence Parr
 began the second total rewrite of ANTLR. The method by which grammars
 may be practically analyzed to generate LL(k) lookahead information 
 was discovered in August of 1990 just before Terence's return to 
 Purdue. Version 1.00 incorporated this algorithm and included the AST
 mechanism, lexical classes, error classes, and automatic error 
 recovery; code quality and portability were higher. In February of 
 1992 1.00 was released via an article in SIGPLAN Notices. Peter Dahl,
 then Ph.D. candidate, and Professor Matt O'Keefe (both at the 
 University of Minnesota) tested this version extensively. Dana 
 Hoggatt (Micro Data Base Systems, Inc.) tested 1.00 heavily. 

 Version 1.06 was released in December 1992 and represented a large 
 feature enhancement over 1.00. For example, rudimentary semantic 
 predicates were introduced, error messages were significantly 
 improved for k>1 lookahead and ANTLR parsers could indicate that 
 lookahead fetches were to occur only when necessary for the parse 
 (normally, the lookahead "pipe" was constantly full). Russell Quong
 joined the project in the Spring of 1992 to aid in the semantic 
 predicate design. Beginning and advanced tutorials were created and
 released as well. A makefile generator was included that sets up 
 dependencies and such correctly for ANTLR and DLG. Very few 1.00 
 incompatibilities were introduced (1.00 was quite different from 
 1.00B in some areas). 

 Version 1.10 was released on August 31, 1993 after Terence?s release
 from Purdue and incorporated bug fixes, a few feature enhancements 
 and a major new capability -- an arbitrary lookahead operator 
 (syntactic predicate), "(a)?b". This feature was codesigned with 
 Professor Russell Quong also at Purdue. To support infinite 
 lookahead, a preprocessor flag, ZZINF_LOOK, was created that forced
 the ANTLR() macro to tokenize all input prior to parsing. Hence, at 
 any moment, an action or predicate could see the entire input 
 sentence. The predicate mechanism of 1.06 was extended to allow 
 multiple predicates to be hoisted; the syntactic context of a 
 predicate could also be moved along with the predicate. 

 In February of 1994, SORCERER was released. This tool allowed the
 user to parse child-sibling trees by specifying a grammar rather than
 building a recursive-descent tree walker by hand. Aaron Sawdey at The
 University of Minnesota became a second author of SORCERER after the 
 initial release. On April 1, 1994, PCCTS 1.20 was released. This was 
 the first version to actively support C++ output. It also included 
 important fixes regarding semantic predicates and (..)+ subrules. 
 This version also introduced token classes, the "not" operator, and 
 token ranges. 

 On June 19, 1994, SORCERER 1.00B9 was released. Gary Funck of 
 Intrepid Technology joined the SORCERER team and provided very 
 valuable suggestions regarding the "transform" mode of SORCERER. 

 On August 8, 1994, PCCTS 1.21 was released. It mainly cleaned up the
 C++ output and included a number of bug fixes. 

 From the 1.21 release forward, the maintenance and support of all 
 PCCTS tools was picked up by Parr Research Corporation. 

 A sophisticated error handling mechanism called "parser exception 
 handling" was released for version 1.30. 1.31 fixed a few bugs. 

 Release 1.33 is the version corresponding to the initial book release. 

 ANTLR 2.0.0 came out around May 1997 and was partially funded so 
 Terence hired John Lilley, a maniac coder and serious ANTLR hacker, 
 to build much of the initial version. Terence did the grammar 
 analyzer, naturally. 

 John Mitchell, Jim Coker, Scott Stanchfield, and Monty Zukowski 
 donate lots of brain power to ANTLR 2.xx in general. 

 ANTLR 2.1.0, July 1997, mainly improved parsing performance, 
 decreased parser memory requirements, and added a lot of cool lexer
 features including a case-insensitivity option. 

 ANTLR 2.2.0, December 1997, saw the introduction of the new 
 http://www.antlr.org website.  This release also added grammar 
 inheritance, enhanced AST support, and enhanced lexical translation
 support (each lexical rule now was considered to return a Token 
 object even when referenced by another lexical rule). 

 ANTLR 2.3.0, June 1998, was the first version to have Peter Wells
 C++ code generator. 

 ANTLR 2.4.0, September 1998, introduced the ParseView parser debugger
 by Scott Stanchfield.  This version also had a semi-functional -html
 option to generate HTML from your grammar for reading purposes. Scott
 and Terence updated the file I/O to be JDK 1.1. 

 ANTLR 2.5.0, November 1998, introduced the filter option for the lexer
 that lets ANTLR behave like SED or AWK. 

 ANTLR 2.6.0, March 1999, introduced token streams. Chapman Flack, 
 Purdue Graduate student, pounded me at the right moment about streams,
 nudging me in the right direction. 

 MageLang Institute currently provides support and continues 
 development of ANTLR. 

 MageLang becomes jGuru.com as we quit doing Java training and start 
 building the jGuru Java developer's website. 

 2.7.0 released January 19, 2000 had the following enhancements:

  * Nongreedy subrules 
  * Heterogeneous trees 
  * Element options.  To support heterogeneous trees, elements such 
    as token references may now include options. 
  * Exception hierarchy redesign 
  * XML serialization 
  * Improved C++ code generator 
  * New Sather code generator 

 2.7.1 released October 1, 2000 had the following enhancements 

  * ANTLR now allows UNICODE characters because Terence made case-
    statement expressions more efficient ;)  See the unicode example 
    in the distribution and the brief blurb in the documentation. 
  * Massively improved C++ code generator (Thanks to Ric Klaren). 
  * Added automatic column setting support. 
  * Ter added throws to tree and regular parsers . 

 2.7.2 release January 19, 2003 was mainly a bug fix release, 
 
  * but also included a C# code generator by Micheal Jordan, Kunle 
    Odutola and Anthony Oguntimehin. :) 
  * I (who, Ter?) added an antlr.build.Tool 'cause I hate ANT. This
    release does UNICODE properly now. Added limited lexical lookahead
    hoisting. Sather code generator disappears. Source changes for 
    Eclipse and NetBeans by Marco van Meegen and Brian Smith. 

 2.7.3 released March 22, 2004 was mainly a bug fix release, 

  * but included the parse-tree/derivation code to aid in debugging 
  * plus the cool TokenStreamRewriteEngine that makes rewriting or 
    tweaking input files particularly easy. 

 2.7.4 released May 9, 2004 was mainly a bug fix release.

 2.7.5 release Xmas 2004 had the following enhancements:

  * A Python code generator has been implemented and contributed
    by Wolfang Haefelinger and Marq Kole.

  * A new make/autoconf framework as been contributed by Wolfgang
    Haefelinger

  * A MSI based installer has been contributed by Wolfgang Haefelinger. 

 2.7.6 release xmas 2005 was mainly a bug fix release.

  * Scott Stanchfield added file/line information for Java target and
    cleaned up a bunch of classloader stuff.

  * Added stuff to support Prashant Deva's cool ANTLRStudio.

 2.7.7 release September 7, 2006 was a bug fix release.
    
======================================================================
             README.txt - last update September 6th, 2006
