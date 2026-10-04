# MindScript Language Specification v0.1

## 1. Design goals

MindScript is a small domain-specific language for describing:

- behavior
- decisions
- feedback loops
- emotional processes
- learned patterns
- social and organizational dynamics
- causal systems

Its primary design rule is:

> If understanding a symbol requires programming experience, prefer ordinary language.

MindScript uses:

- Java-like script calls and braces
- SQL-like uppercase logical keywords
- ordinary English
- simple algebra

## 2. Scripts

A script is something that runs.

```mind
scriptName(parameters) {

    WHEN:
        trigger

    DO:
        action()

    RETURN:
        result
}
```

Parentheses always indicate a script or process.

```mind
evaluateRisk()
buildTrust(person)
accountabilitySelector(problem)
```

## 3. State and values

State is written without parentheses.

```mind
fear
trust
dangerLevel
selfConfidence
```

Values are simple words or numbers.

```mind
fear = high
dangerLevel = immediate
adviceStatus = requested
```

Recommended qualitative values include:

```text
none
low
medium
high
veryHigh
```

## 4. Comments

```java
// single-line comment

/*
   multi-line comment
*/

/**
 * MindScriptDoc comment
 */
```

## 5. Core keywords

### REQUIRES

Declares dependencies on other scripts.

```mind
REQUIRES:
    evaluateRisk()
    valueComparison()
```

### NEEDS

Declares prerequisite state.

```mind
NEEDS:
    selfConfidence >= high
```

### WHEN

Defines what activates the script.

```mind
WHEN:
    perceivedMistake
```

### WHERE

Narrows the context in which the script applies.

```mind
WHERE:
    relationship = close
    OR consequences > significant
```

### DO

Defines actions or state changes.

```mind
DO:
    explainRisk()
    trust = trust + medium
```

### IF / ELSE

```mind
IF dangerLevel = immediate:
    intervene()

ELSE:
    offerPerspective()
```

### WHILE

```mind
WHILE validation < enough:
    seekReassurance()
```

### RETURN

Returns the result of a script.

```mind
RETURN:
    dangerLevel
```

## 6. Logical operators

MindScript uses:

```text
AND
OR
NOT
```

Example:

```mind
IF personUnderstands AND NOT immediateDanger:
    returnAgency()
```

## 7. Comparisons and algebra

Preferred:

```text
=
>
<
>=
<=
+
-
*
/
()
```

Avoid programmer-specific operators such as:

```text
==
!=
+=
-=
&&
||
!
```

Examples:

```mind
fear = fear + medium

rsdIntensity =
    (myValue - theirValue)
    * confidenceIAmRight
```

## 8. Script vs state

A central MindScript convention is:

```text
something() = process
something   = state/data
```

Example:

```mind
anger = generateAnger(event)
```

`generateAnger()` is a process.

`anger` is state.

## 9. Optional semantic sections

MindScript Core defines control flow and composition.

Domain models may use additional structured sections such as:

```text
PURPOSE
BELIEF
BELIEFS
OBSERVED
ASSUMES
LEARNED
RISKS
REPLACEMENT
STATE
VALUES
```

These are intentionally descriptive rather than strictly computational.

## 10. Example

```mind
offerConfirmReturnAgency(person) {

    PURPOSE:
        help without taking ownership of another adult's decisions

    WHEN:
        potentialHarmDetected

    DO:
        dangerLevel = evaluateDanger()

    IF dangerLevel = immediate:

        DO:
            intervene()

        RETURN:
            immediateProtection

    ELSE:

        DO:
            adviceStatus = askIfAdviceWanted()

        IF adviceStatus = requested:

            DO:
                explainPerspective()
                understanding = confirmUnderstanding()

            IF understanding = confirmed:
                returnAgency()

        ELSE:
            returnAgency()

    RETURN:
        autonomyPreserved
}
```

## 11. Status

Version 0.1 is experimental.

The language should remain intentionally small until recurring real-world modeling problems justify new syntax.
