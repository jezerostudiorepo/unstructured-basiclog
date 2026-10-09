


# Unstructured BASIClog DESIGN

> "A smiling finger to academia papers."

_Rock Paper Scissor_

> "A masterpiece in usefulness."

_100% AI Gamer_

> "I only use metanode!"

_The Boomer_

---

**Unstructured BASIClog** is the only revolutionary REPL automaton that can save the world, one day. Make your share, do your duty, join us now!

**As a REPL automaton,** Unstructured BASIClog offers state-of-the-art ergonomics that feels just like operating an authentic modern home computer: Amstrad CPC 464, ZX Spectrum, Commodore 64, Thomson MO5...

**And that's** about it. But as a production/deduction rule system, with timers and triggers, a behavior tree, and a logic knowledge base, all operated through a pure line-numbered assembly language REPL, offline.



## Semantics

```peg
source_code_snapshot
= numbered_line_*

numbered_line
= number_payload

payload
= constant_blob
/ variable
/ typed_node

constant_blob
= double_quote base_64_string double_guote

variable
= opening_parenthesis glyph_string comment closing_parenthesis

typed_node
= selection
/ behavior
/ rule

selection
= "THOSE FROM" linenumber "TO" linenumber
/ "THOSE LIKE" goal
/ "THOSE UNLIKE" goal
/ "THE ENTIRE SNAPSHOT"
/ "THE EMPTY SELECTION"
/ "THE INVERSE OF" selection
/ "UNION OF" selection_+
/ "INTERSECTION OF" selection_+
/ "DIFFERENCE OF" selection selection

behavior
= "STEP" distance
/ "LOCATE" size
/ "ASSERT" proposition
/ "PARSE" proposition "AS" grammar
/ "RETRACT" goal
/ "WAIT FOR" goal
/ "SEQUENCE" behavior_+
/ "FALLBACK" behavior_+
/ "PARALLEL" behavior_+
/ "FAIL ALL" behavior_+
/ "FAIL ANY" behavior_+
/ "WHILE" behavior
/ "UNTIL" behavior
/ "FOR" selection behavior
/ "THINK" proposition

rule
= "EVERY" time "DO" behavior
/ "AFTER" time "DO" behavior
/ "WHEN" goal "DO" behavior
/ "IF" goal "THEN" proposition

grammar
= rule_definition_+

grammar_token
= rule_definition
/ ordered_choice
/ next_choice
/ add suffix
/ terminal

rule_definition
= "IS" linenumber "PATTERN" linenumber

next_choice
= "IS" linenumber "FOLLOWED BY PATTERN" linenumber

ordered_choice
= "IS" linenumber "OR PATTERN" linenumber

add_suffix
= "IS" linenumber "ONE OR MORE" linenumber
/ "IS" linenumber "ZERO OR MORE" linenumber
/ "IS" linenumber "ZERO OR ONE" linenumber

terminal
= "IS" linenumber "TERMINAL" linenumber

proposition
= predicate_part_+

predicate_part
= double_quote [A-Z ]_+ double_quote linenumber_+

goal
= proposition {
  // Take all variables and keep an eye on them
}

linenumber
= number

distance
= number

time
= number

number
= [0-9]+

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



## Roadmap

- `[ ]` Rework the interaction model, with the concepts of workspaces and events.
- `[ ]` Add random name generator.
- `[ ]` Implement generic buttons in the toolbar.
- `[ ]` Implement generic input API.
- `[ ]` Detach Workspace from Unstructured BASIClog.
- `[ ]` Make it a system where the source code and the interface is one and same thing.
- `[ ]` When you look at a page of code, you're actually looking at an interactable UI you can use to launch services or shut them down, make queries, etc.
- `[ ]` Add crypto functionality to blobs. Important because it allows authorization math.



## Agents

There's only one agent in Unstructured BASIClog: Unstructured BASIClog itself. We only speak of agents to conceive, design and create its communication mechanisms.

Because we thing it should behave consistently with its environment in a seamless input/output flow.



## Workspaces

Workspaces are an equivalent of logical variables but for parts of the source code snapshot of agents, that is shared across agents.

In other words, it's a selection of lines that an agent can choose to share or not. The selected lines are maintained identical in those that share them.

The selection can be expressed using set operators, line number ranges, and queries in a same context.

Basically, it's a window an agent opens for communication.

Things tending to stay the same, when a new agent joins the workspace, the worspace currently shared lines overwrite its own.



```




















```

# Unstructured BASIClog RECYCLE BIN

> "A smiling finger to academia papers."

_Rock Paper Scissor_

> "A masterpiece in usefulness."

_100% AI Gamer_

> "I only use metanode!"

_The Boomer_

> "One of the five metanodes"

_Me_

> "five types of content blocks"

_Me_



**Unstructured BASIClog** is the only revolutionary REPL automaton that can save the world, one day. Make your share, do your duty, join us now!

**As a REPL automaton,** Unstructured BASIClog offers state-of-the-art ergonomics that feels just like operating an authentic modern home computer: Amstrad CPC 464, ZX Spectrum, Commodore 64, Thomson MO5...

**And that's** about it. But as a production/deduction rule system, with timers and triggers, a behavior tree, and a logic knowledge base, all operated through a pure line-numbered assembly language REPL, offline.



## Roadmap

- `[ ]` Rework the interaction model, with the concepts of workspaces and events.
- `[ ]` Add random name generator.
- `[ ]` Implement generic buttons in the toolbar.
- `[ ]` Implement generic input API.
- `[ ]` Detach Workspace from Unstructured BASIClog.
- `[ ]` Make it a system where the source code and the interface is one and same thing.
- `[ ]` When you look at a page of code, you're actually looking at an interactable UI you can use to launch services or shut them down, make queries, etc.
- `[ ]` Add crypto functionality to blobs. Important because it allows authorization math.



## Workspaces

Workspaces are an equivalent of logical variables but for parts of the source code snapshot of agents, that is shared across agents.

In other words, it's a selection of lines that an agent can choose to share or not. The selected lines are maintained identical in those that share them.

The selection can be expressed using set operators, line number ranges, and queries in a same context.

Basically, it's a window an agent opens for communication.

Things tending to stay the same, when a new agent joins the workspace, the worspace currently shared lines overwrite its own.



## Screen zones

- Top: custom toolbar,
- Left: source code snapshot tree,
- Right top: node editor,
- Right bottom: user input/output terminal.

Usage:
- click on nodes in the tree to toggle their display in editor as head of their own block,
- double-click on line numbers in editor to toggle visibility of children nodes in the same block,
- double-click on a predicate to execute it (and select it entirely).

The global screen zone concept is built upon the core idea that every token on every line, in the editor, is clickable: each one toggles the visibility of its children.

The same can be done from the softcode.



## Usage

The command-line interface is similar to that of a home computer running BASIC. First you prepare your input, then you send your input.

Preparing an input is like writing a tiny old BASIC program:

```
10 PRINT 20
20 "Hello world"
```

- A line numbered is called a "node". A node is a numbered line.

- To create or overwrite a node, you simply type it.

  - Either `<node> "value"`  is a constant blob value, like line 20,

  - Or `<node> <type> <content>` makes it a typed node_+ arguments, like line 10.

- In the case of a constant blob, only 1 literal is given, enclosed in double quotes.

- In the case of a typed node, arguments are given as a list of nodes 

- You can also edit a line with `EDIT <node>`, which simply puts the content of a node in the keyboard input textbox.

When you're done preparing your input, you send it with `RUN`.

You can also save with `SAVE <node>` in which case the input, from `<node>` to its descendants, will spawn in the knowledge base for persistence, and the address at which it is stored will be returned.

You can clear the currently edited input using `CLEAR`. 



## An automaton

Unstructured BASIClog is an **automaton**: there is no difference between "source code" and "snapshot".

During execution, it maintains as a list of **numbered lines**:
- A current **Knowledge Base**,
- A current **Pointer Graph**,
- A current **Executing Behavior**,
- A current **Documentation**,
- A current **User Input**.



## Syntax

Here is the syntax of a source code snapshot.

```EBNF
L_ source code snapshot = { node } ;
  L_ node = unique line number, payload ;
     L_ unique line number = line number ;
        (*unique per source code snapshot*)
     L_ payload = typed datum | literal | dataset | logical variable ;
       L_ typed datum = data type, { line number } ;
       L_ literal = '"', string, '"' ;
       L_ dataset = { line number } ;
       L_ logical variable = '(', string, ')' ;
  L_ line number = natural integer ;
  L_ data type = string ;
```

- Each unique line number can only begin one node.
- Except empty lines, each line must have a unique line number.
- Comments can exist in `REM` data.



## Code generation

When a new piece of code needs to be inserted, the size (distance between the minimum and maximmum line number) of the new code is noted, and a place is found where the new **numbered lines** can be inserted one ofter anoter. It starts with an offset in the hundreds if size < 100, in the thousands if size < 1000, and so on.

This specificity is what makes it so easy to communicate with Unstructured BASIClog. When such new code is inserted, if it's related to communication with the user, then each new set of nodes in the current source code snapshot are default-marked as being:
- A **PRINT message**,
- An **INPUT prompt**, or
- An **answer or command INPUT**.

!!! needs to be rewritten



## Source code snapshot

**Everything** is stored in the same line number space: the Knowledge Base, the Pointer Graph, the Executing Behavior, the Documentation, and the User Input.

These five elements are the **five types of content blocks** displayed to the user, queried from the user, used as source code, or manipulated in or by Unstructured BASIClog.

- **A node** is a numbered line, with a type (a string) and arguments (line numbers).
- **A list of nodes** is an environment.
- The environment stores a Knowledge Base.
- The environment stores a Pointer Graph state.
- The environment stores an Executing Behavior state.
- The environment stores the current documentation.
- **The Knowledge Base** stores logic facts and rules.
- **The Pointer Graph** keeps track of what nodes are POINTING TO.
- **The Executing Behavior** keeps track of current activity.
- **The Documentation** keeps track of comments on the current sourcce code snapshot state.
- **The User Input** marks all original content authentically spawned by user input.



### Knowledge Base

Each node is part of **The Knowledge Base**: the compete list of numbered lines (made of a type which is a string and arguments which are line numbers) contained in the source code snapshot.

```JSON
05 REM // example
10 SOME 20 30
20 ARBITRARY 40
30 SMALL 40
40 STRUCTURE
```



### Pointer Graph

Each node is (conceptually) potentially part of the **Pointer Graph** in the source code snapshot. It defaults to what it's been spawned POINTING TO or being POINTED TO by.

Pointers are variables. They can be seen as an agnostic asymmetric relationship. They form the Pointer Graph over the entire database. 

They are necessary to implement the notion of _identity of another node_.

```JSON
05 REM // example of pointer state
10 => 20 30
10 <= 90 80 70
20 <= 10
```



### Executing Behavior

Some nodes are part of the **Executing Behavior**, which is the execution context of the current behavior of the source code snapshot.

```JSON
05 REM // example of Executing Behavior state
10 CAUSED 20 40
20 EVERY 30 40
30 "250"
40 ...
```



### Documentation

Some nodes are part of the **Documentation**, which is the set of comments (remarks) in the source code snapshot.

```JSON
05 REM // example of Documentation line
```


## Events

Several things can happen, events like:

- An `AFTER` or `EVERY` attempt to execute something,
- A registered trigger actually `TRIGGERS` now,
- A `WAIT` goal actually succeeds now,
- ...etc.

In those cases, entire series of nodes may be created and deleted, as part of the state update process. Typically, these nodes are handled by builtin **metanodes**.

For any type of event, 1 occurrence of the event corresponds to only 1 series of modifications, seen as management of instances update.



## Spawning stuff

When a `<node>` spawns, an `IS INSTANCE OF` metanode is also spawned to link the `<occurrence>` of an event to its `<event>` type.

When a `<node>` is wasted, the `IS INSTANCE OF` metanode, that was linking the `<occurrence>` of an event to its `<event>` type, is also wasted.



## Datasets

A dataset is a node containing only references to other line numbers. Syntactically, it is the special case of node type being the empty string.

It generally means literally, "these ones can and should be used instead of me".



## Vocabulary list

Any `<node>` refers to a line number and all its descendants. Their names are for convenience, all types of lines are equally nodes.

```xml
commands
<action>    RUN <start> <arguments> ...

states
<metanode>  KNOWLEDGE BASE
<metanode>  POINTER GRAPH
<metanode>  EXECUTING BEHAVIOR
<metanode>  DOCUMENTATION
<metanode>  USER INPUT
<metanode>  NOTHING
<metanode>  IDLE
<metanode>  <= <pointer> ...
<metanode>  => <target> ...
<metanode>  CAUSED <enactor> <action>
<metanode>  ENDED <enactor> <action>
<metanode>  IS INSTANCE OF <occurrence> <event>
<metanode>  IS AN INSTANCE <node>
<metanode>  IS A USER INPUT <node> !!!!!!!!!!!!!
<metanode>  REM <node>

source code
<metanode>  NODE SOURCE <node> <content> ...
<metanode>  NODE ID <literal>
<metanode>  NODE TYPE <literal>
<metanode>  NODE PAYLOAD <reference> ...
<metanode>  LITERAL <literal>
<metanode>  REFERENCE <literal> ...

behavior tree
<action>    SEQUENCE <outcome> ...
<action>    FALLBACK <outcome> ...
<action>    PARALLEL <outcome> ...
<action>    NEGATIVE <outcome>
<action>    WHILE <outcome>
<action>    UNTIL <outcome>
<action>    EVERY <msec> <outcome>
<action>    AFTER <msec> <outcome>
<outcome>   HAS SUCCEEDED <outcome>
<outcome>   HAS FAILED <outcome>
<outcome>   IS RUNNING <outcome>
<outcome>   NO RUN YET <outcome>

assert retract
<action>    SPAWN FROM <proposition> <pointer>
<action>    SPAWN TO <proposition> <target>
<action>    WASTE <proposition>

interaction
<action>    PRINT <message>
<action>    INPUT FROM <prompt> <pointer>
<action>    INPUT TO <prompt> <target>
<action>    UNEXPECTED FROM <pointer>
<action>    UNEXPECTED TO  <target>

directed graph
<outcome>   POINTING FROM <target> <pointer>
<outcome>   POINTING TO <pointer> <target>

deduction production
<rule>      IMPLIES <goal> <deduction>
<rule>      TRIGGERS <goal> <action>
<rule>      CONSIDERING WAIT <goal> <outcome>
<rule>      CONSIDERING RUN <goal> <action>
<rule>      CONSIDERING DEDUCE <goal> <deduction>

```



## Vocabulary description

Launch the execution of a `<start>` node with provided arguments.

```xml
<metanode>  KNOWLEDGE BASE
```

A metanode meaning, "the current state of the Knowledge Base", everything including what's not related to the current state of the Pointer Graph, or to the currently Executing Behavior, or to the Documentation: any kind of knowledge e.g. facts, rules, thoughts, prompts, messages, ...etc.

One of the five metanodes that make Unstructured BASIClog an automaton, along with any combination of those five.

- It always succeeds.

```xml
<metanode>  POINTER GRAPH
```

A metanode meaning, "the current state of the Pointer Graph", detailing which node is currently pointing to which other node.

One of the five metanodes that make Unstructured BASIClog an automaton, along with any combination of those five.

```xml
<metanode>  EXECUTING BEHAVIOR
```

A metanode meaning, "the currently Executing Behavior", a snapshot of the contextual structure of the current behavior.

One of the five metanodes that make Unstructured BASIClog an automaton, along with any combination of those five.

- It always succeeds.

```xml
<metanode>  DOCUMENTATION
```

A metanode meaning, "this is part of the Documentation", the current comments about the source code snapshot state (or a part of a state).

One of the five metanodes that make Unstructured BASIClog an automaton, along with any combination of those five.

- It always succeeds.

```xml
<metanode>  USER INPUT
```

A metanode meaning, "this is from User Input", the current user commands and prompt replies in the source code snapshot state (or a part of a state).

One of the five metanodes that make Unstructured BASIClog an automaton, along with any combination of those five.

- It always succeeds.

```xml
<metanode>  NOTHING
```

A Logical Tree `NOTHING` metanode. It means, "the empty list". It's the opposite of `KNOWLEDGE BASE`.

- It always succeeds.

```xml
<metanode>  IDLE
```

A Behavior Tree `IDLE` metanode. It queries Unstructured BASIClog's current activity.
- It succeeds if Unstructured BASIClog has no Behavior Tree node currently running.
- It fails if Unstructured BASIClog has at least one Behavior Tree node currently running.
- It is never still running.

```xml
<metanode>  <= <pointer> ...
```

A Logical Tree `<=` metanode. It means, "the list of pointers that are POINTING TO here".

- It succeeds if the node which this node represents is pointed to by all the nodes which the `<pointer>` nodes represent.
- It fails if the node which this node represents is not pointed to by all the nodes which the `<pointer>` nodes represent.
- It is still running if the information is not available.

```xml
<metanode>  => <target> ...
```

A Logical Tree `=>` metanode. It means, "the list of pointers that here is POINTING to".

- It succeeds if the node which this node represents is pointing to all the nodes which the `<target>` nodes represent.
- It fails if the node which this node represents is not pointing to all the nodes which the `<target>` nodes represent.
- It is still running if the information is not available.

```xml
<metanode>  CAUSED <enactor> <action>
```

A Behavior Tree `CAUSED` logic node. It means that the `<enactor>` node caused the Executing Behavior `<action>` node to be spawned.

- It succeeds if `<enactor>` did cause `<action>`.
- It fails otherwise.
- It is still running if data is currently unavailable.

```xml
<metanode>  ENDED <enactor> <action>
```

A Behavior Tree `ENDED` logic node. It means that the `<enactor>` node caused the Executing Behavior `<action>` node to be ended.

- It succeeds if `<enactor>` did end `<action>`.
- It fails otherwise.
- It is still running if data is currently unavailable.

```xml
<metanode>  IS INSTANCE OF <occurrence> <event>
```

A Behavior Tree `IS INSTANCE OF` logic node. It means that `<occurrence>` was spawned as a metarepresentation of the `<event>` that occurred.

- It succeeds if `<occurrence>` represents actually an occurrence of the `<event>` that occurred.
- It fails otherwise.
- It is still running if data is currently unavailable.

```xml
<metanode>  IS AN INSTANCE <node>
```

A Behavior Tree `IS INSTANCE` logic node. It means that `<node>` was spawned as a metarepresentation of an event that occurred.

- It succeeds if `<node>` represents actually an occurrence of some event that occurred.
- It fails otherwise.
- It is still running if data is currently unavailable.

```xml
<metanode>  REM <node>
```

A no-operation `REM` metanode. It means that `<node>` has no effect, and is part of the Documentation.

- It always succeeds.

```xml
<action>    SEQUENCE <outcome> ...
```

A Behavior Tree `SEQUENCE` control flow node. It executes its children one by one.

- It succeeds if all children succeed.
- It fails if any child fails.
- It is still running if any child is still running.

```xml
<action>    FALLBACK <outcome> ...
```

A Behavior Tree `FALLBACK` control flow node. It executes its children one by one.

- It succeeds if any child succeeds.
- It fails if all children fail.
- It is still running if any child is still running.

```xml
<action>    PARALLEL <outcome> ...
```

A Behavior Tree `PARALLEL` control flow node. It executes its children all at once.

- It succeeds if there is no child still running.
- It never fails.
- It is still running if any child is still running.

```xml
<action>    NEGATIVE <outcome>
```

A Behavior Tree `NEGATIVE` control flow node. It executes its child.

- It succeeds if the child fails.
- It fails if the child succeeds.
- It is still running if the child is still running.

```xml
<action>    WHILE <outcome>
```

A Behavior Tree `WHILE` control flow node. It executes its child while the child succeeds.

- It succeeds if the child fails.
- It is still running if the child is still running.

```xml
<action>    UNTIL <outcome>
```

A Behavior Tree `UNTIL` control flow node. It executes its child until the child succeeds.

- It succeeds if the child succeeds.
- It is still running if the child is still running.

```xml
<action>    EVERY <msec> <outcome>
```

A Behavior Tree `EVERY` control flow node. It attempts to execute its child every `<msec>` milliseconds.

- It succeeds if Unstructured BASIClog was not busy and could execute the last attempt.
- It fals if Unstructured BASIClog could not execute the last attempt because it was busy.
- It is always still running.

```xml
<action>    AFTER <msec> <outcome>
```

A Behavior Tree `AFTER` control flow node. It attempts to execute its child after `<msec>` milliseconds.

- It succeeds if Unstructured BASIClog was not busy and could execute that attempt..
- It fals if Unstructured BASIClog could not execute that attempt because it was busy.
- It is still running before `<msec>` milliseconds.

```xml
<outcome>   HAS SUCCEEDED <outcome>
```

A Behavior Tree `HAS SUCCEEDED` control flow node. It queries the current status of an Executing Behavior node.

- It succeeds if the node has succeeded.
- It fails otherwise.
- It is never still running

```xml
<outcome>   HAS FAILED <outcome>
```

A Behavior Tree `HAS FAILED` control flow node. It queries the current status of an Executing Behavior node.

- It succeeds if the node has failed.
- It fails otherwise.
- It is never still running

```xml
<outcome>   IS RUNNING <outcome>
```

A Behavior Tree `IS RUNNING` control flow node. It queries the current status of an Executing Behavior node.

- It succeeds if the node is still running.
- It fails otherwise.
- It is never still running

```xml
<outcome>   NO RUN YET <outcome>
```

A Behavior Tree `NO RUN YET` control flow node. It queries the current status of an Executing Behavior node.

- It succeeds if the node has never been executed.
- It fails otherwise.
- It is never still running

```xml
<action>    SPAWN FROM <proposition> <pointer>
```

A Behavior Tree `SPAWN FROM` execution node. It asserts a new instance of a `<proposition>` node, and makes it pointed to by one or more `<pointer>` nodes.

- It succeeds if `<proposition>` and `<pointer>` are not `NOTHING`.
- It fails otherwise.
- It is never still running

```xml
<action>    SPAWN TO <proposition> <target>
```

A Behavior Tree `SPAWN TO` execution node. It asserts a new instance of a `<proposition>` node, and makes it be POINTING TO one or more `<target>` nodes.

- It succeeds if `<proposition>` and `<target>` are not `NOTHING`.
- It fails otherwise.
- It is never still running

```xml
<action>    WASTE <proposition>
```

A Behavior Tree `WASTE` execution node. It retracts instances of a `<proposition>` node.

- It always succeeds.
- It never fails.
- It is never still running.

```xml
<action>    OBJECT OF <object> <message_or_prompt> ...
```

A Behavior Tree `OBJECT OF` logic node. It means the message / prompt will have an associated `OBJECT`.

- It always succeeds.
- It never fails.
- It is never still running.

```xml
<action>    PRINT <message> ...
```

A Behavior Tree `PRINT` execution node. It attempts to display a set of `<message>` nodes to the user.

The messages appear in the inbox of the user, as a list of `<object>` of `<message>` nodes.

- It succeeds if the user displayed all the `<message>` nodes.
- It fails if at least one `<message>` was discarded and others have been managed.
- It is still running if the `<message>` has not been displayed or discarded yet.

```xml
<action>    INPUT FROM <prompt> <pointer>
```

A Behavior Tree `INPUT FROM` execution node. It attempts to display a series of `<prompt>` nodes to the user, waits for a set of answer nodes from the user, and as soon as an answer arrives, it spawns it and makes the answer pointed to by one or more `<pointer>` nodes.

> it spawns it and makes one or more `<pointer>` nodes be `POINTING TO` the answer.

The prompts appear in the inbox of the user, as a list of `<object>` of `<prompt>` nodes. 

- It succeeds if every `<prompt>` had an answer.
- It fails if at least one `<prompt>` was cancelled and others have been managed.
- It is still running if any `<prompt>` received neither answer nor cancel.

```xml
<action>    INPUT TO <prompt> <target>
```

A Behavior Tree `INPUT TO` execution node. It attempts to display a series of `<prompt>` nodes to the user, waits for a set of answer nodes from the user, and as soon as an answer arrives, it spawns it and makes it be POINTING TO one or more `<target>` nodes.

> it spawns the answer and makes it be `POINTING TO` one or more `<pointer>` nodes be `POINTING TO`.

The prompts appear in the inbox of the user, as a list of `<object>` of `<prompt>` nodes. 

- It succeeds if every `<prompt>` had an answer.
- It fails if at least one `<prompt>` was cancelled and others have been managed.
- It is still running if any `<prompt>` received neither answer nor cancel.

```xml
<action>    UNEXPECTED FROM <pointer>
```

A Behavior Tree `UNEXPECTED FROM` execution node. It receives a set of unrequested command nodes from the user, and as soon as an unrequested command arrives, it spawns it and makes that command pointed to by one or more `<pointer>` nodes.

>

The commands is as a list of `<command>` nodes. 

- It succeeds if every `<prompt>` had an answer.
- It fails if at least one `<prompt>` was cancelled and others have been managed.
- It is still running if any `<prompt>` received neither answer nor cancel.

```xml
<action>    UNEXPECTED TO  <target>
```

A Behavior Tree `UNEXPECTED TO` execution node. It receives a set of unrequested command nodes from the user, and as soon as an unrequested command arrives, it spawns it and makes that command pointing to one or more `<pointer>` nodes.

>

The commands is as a list of `<command>` nodes. 

- It succeeds if every `<prompt>` had an answer.
- It fails if at least one `<prompt>` was cancelled and others have been managed.
- It is still running if any `<prompt>` received neither answer nor cancel.






```xml
<outcome>   POINTING FROM <target> <pointer>
```

A Behavior Tree `POINTING FROM` logic node. It relates `<pointer>` nodes to the `<target>` nodes they're pointing to.

- It succeeds if at least one `<pointer>` is POINTING TO `<target>`.
- It fails if no `<pointer>` points to `<target>`.
- It is still running if the information is unavailable.

```xml
<outcome>   POINTING TO <pointer> <target>
```

A Logical Tree `POINTING TO` logic node. It relates `<pointer>` nodes to the `<target>` nodes they're pointing to.

- It succeeds if at least one `<pointer>` is POINTING TO `<target>`.
- It fails if no `<pointer>` points to `<target>`.
- It is still running if the information is unavailable.

```xml
<rule>      IMPLIES <goal> <deduction>
```

A Logical Tree `IMPLIES` logic node. It relates a `<goal>` node to the `<deduction>` nodes it may have CAUSED.

The question is not whether it is currently implying something, but whether or not that **deduction rule** is currently registered as actual.

- It succeeds if `<goal>` implies `<deduction>`.
- It fails if `<goal>` does not imply `<deduction>`.
- It is still running if the information is unavailable.

```xml
<rule>      TRIGGERS <goal> <action>
```

A Logical Tree `TRIGGERS` logic node. It relates a `<goal>` node to the `<action>` nodes it may have CAUSED or ENDED.

The question is not whether it is currently triggering something, but whether or not that **production rule** is currently registered as actual.

- It succeeds if `<goal>` can/does trigger `<action>`.
- It fails if `<goal>` can/does not trigger `<action>`.
- It is still running if the information is unavailable.

```xml
<outcome>   CONSIDERING RUN <goal> <action>
```

A Behavior Tree `CONSIDERING RUN` control flow node. In the context of a `goal,` it tries and queries the success of an `action`.

- It succeeds if the `action` can be found or proven and executed successfully.
- It fails if the `action` cannot be found or proven and executed successfully.
- It is still running if the outcome is not known yet.

```xml
<outcome>   CONSIDERING WAIT <goal> <outcome>
```

A Behavior Tree `CONSIDERING WAIT` control flow node. In the context of a `goal,` it waits for an `outcome` to be true.

- It succeeds if the `outcome` can be found or proven and executed successfully.
- It never fails.
- It is still running if the `outcome` cannot be found or proven and executed successfully.

```xml
<outcome>   CONSIDERING DEDUCE <goal> <premise> <deduction>
```

A Behavior Tree `CONSIDERING WAIT` control flow node. In the context of a `goal,` it links every `deduction` to its `premise`.

- It succeeds if a non-empty `deduction` can be found or proven and executed successfully from the `premise`.
- It fails if a only the empty `deduction` can be found or proven and executed successfully from the `premise`.
- It is still running if the `outcome` cannot be found or proven and executed successfully.



## Explicit node type declaration

```JSON

10 ="MY NEW FUN <arg1> <arg2>" 20 30
20 = (arg1)
30 = (arg2)

```



## Node math

For every node, we know:

- Which node comes next in lane,
- Which node comes previous,
- Which nodes it has as arguments,
- Which nodes have it as argument,
- Which nodes defines this node type in the documentation.



## Examples

Just random syntax tests...

```JSON

05 REM // spaghetti

10 SPAWN FROM 20 11
11 USER
20 IMPLIES 30 40
30 SEQUENCE 31 32
31 IS MORTAL 39
32 IS ALIVE 39
39 (something thats gonna die)
40 IS GOING TO DIE 39



05 REM // best practice

10 (sibling 1)
11 (sibling 2)
20 (parent)
30 IMPLIES 40 50
40 SEQUENCE 41 42
41 IS PARENT OF 20 10
42 IS PARENT OF 20 11
50 ARE SIBLINGS 10 11
60 SPAWN FROM 30 70
70 USER



05 REM // structured content

10 HELLO 20
20 AND 30 40
30 WORLD
40 WHOEVER LIVES IN 30
50 SPAWN FROM 10 60
60 USER



05 REM // bang

10 SPAWN FROM 20 70
20 TRIGGERS 30 40
30 FALLBACK 31 32
31 ITS RAINING
32 UNDER A SHOWER
40 NEED TO DRY
70 USER



05 REM // before the spawn

10 SPAWN FROM 20 40
20 SOME 30
30 LOOT
40 USER



05 REM // after the spawn

10 SPAWN FROM 20 40
20 SOME 30
30 LOOT
40 USER
50 SOME 60
60 LOOT

```












