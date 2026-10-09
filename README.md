


# Unstructured BASIClog

> "A smiling finger to academic papers."

_Rock Paper Scissor_

> "A masterpiece in usefulness."

_100% AI Gamer_

> "I only use metanode!"

_The Boomer_

---

**Unstructured BASIClog** is the only revolutionary REPL automaton that can save the world, one day. Make your share, do your duty, join us now!

**As a REPL automaton,** Unstructured BASIClog offers state-of-the-art ergonomics that feel just like operating an authentic modern home computer: Amstrad CPC 464, ZX Spectrum, Commodore 64, Thomson MO5...

**And that's** about it. But as a production/deduction rule system, with timers and triggers, a behavior tree, and a logic knowledge base, all operated through a pure line-numbered assembly language REPL, offline.



## Semantics

```peg
source_code_snapshot
  <- numbered_line*

numbered_line
  <- number payload

payload
  <- constant_blob
   / variable
   / comment
   / typed_node
   / goal

constant_blob
  <- '"' base_64_string '"'

variable
  <- "(" [a-z0-9 ]+ ")"

comment
  <- "REM" [^\n]*

typed_node
  <- selection
   / behavior
   / rule

linenumber
  <- number
   / "HERE"
   / "THE CURRENT ASSERTION LINE"
   / "THE NEXT FREE LINE AFTER" linenumber

selection
  <- "LINE" linenumber
   / "THOSE FROM" linenumber "TO" linenumber
   / "THOSE LIKE" goal
   / "THOSE UNLIKE" goal
   / "THE ENTIRE SNAPSHOT"
   / "THE EMPTY SELECTION"
   / "THE INVERSE OF" selection
   / "UNION OF" selection+
   / "INTERSECTION OF" selection+
   / "DIFFERENCE OF" selection selection

behavior
  <- "STEP" distance
   / "LOCATE" size
   / "ASSERT" linenumber
   / "RETRACT" selection
   / "WAIT FOR" goal
   / "SEQUENCE" behavior+
   / "FALLBACK" behavior+
   / "PARALLEL" behavior+
   / "FAIL ALL" behavior+
   / "FAIL ANY" behavior+
   / "WHILE" behavior
   / "UNTIL" behavior
   / "FOR" selection behavior
   / "THINK" goal

rule
  <- "EVERY" time "DO" behavior
   / "AFTER" time "DO" behavior
   / "WHEN" goal "DO" behavior
   / "IF" goal "THEN" proposition

proposition
  <- proposition_part+

proposition_part
  <- predicate_part linenumber+

predicate_part
  <- [A-Z ]+

goal
  <- proposition {
  // Take all variables and keep an eye on them
}

size
  <- number

distance
  <- number

time
  <- number

number
  <- [0-9]+

```



## Examples

```

01 (a parent)
02 (a child)
03 (another child)

10 IF 20 THEN 50
20 SEQUENCE 30 40
30 A PARENT OF 02 IS 01
40 A PARENT OF 03 IS 01
50 FALLBACK 60 70
60 ARE SIBLINGS 02 03
70 ARE EQUAL 02 03

```



## Asserting

Assertion happens at the assertion point, which is the first free line from the LOCATE line down N STEP forward, where N is a natural integer.

It is usually a compound activity where SEQUENCE and FALLBACK orchestrate ASSERT, following the structure of a prototype struct, to clone it locally. 

