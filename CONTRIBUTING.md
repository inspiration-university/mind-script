# Contributing to MindScript

MindScript aims to stay small, readable, and useful.

## Design principles

1. Prefer ordinary language over programmer-only syntax.
2. Prefer a small reusable construct over a special-case keyword.
3. Keep process (`something()`) distinct from state (`something`).
4. Separate observation from interpretation when modeling people.
5. Do not add syntax until repeated real-world use demonstrates the need.

## Proposing syntax changes

Please include:

- the modeling problem
- at least two examples where the new construct helps
- the simpler alternatives considered
- any ambiguity introduced

## Style

Use camelCase for script and variable names.

```mind
evaluateRisk()
dangerLevel
```

Use uppercase for structural and logical keywords.

```text
WHEN
WHERE
IF
ELSE
WHILE
DO
RETURN
AND
OR
NOT
```

## Examples

New language features should include at least one example under `/examples`.

## Behavioral models

Avoid presenting hypotheses about a person's motives as facts.

Prefer:

```mind
OBSERVED:
    contactBecomesIntermittent

ASSUMES:
    validationSeeking
        confidence = medium
```

over declaring an inferred motive as certain.
