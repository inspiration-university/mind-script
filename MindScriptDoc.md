# MindScriptDoc

MindScriptDoc is the documentation convention for MindScript scripts.

It borrows the readability of JavaDoc without requiring Java knowledge.

## Documentation comments

```java
/**
 * Generates strong motivation when reality falls far short
 * of an important but achievable vision.
 *
 * @purpose Convert vision/reality mismatch into action.
 * @requires valueComparison()
 * @risk impatience, tunnel vision
 * @replacement groundedMissionDrive()
 */
missionImpossibleDrive(goal) {
    ...
}
```

## Recommended tags

```text
@purpose
@param
@requires
@trigger
@where
@belief
@returns
@risk
@replacement
@learned
@observed
@assumes
@confidence
@status
@example
@see
```

## Suggested evidence/status vocabulary

For behavioral or psychological models:

```text
@status established
@status supported
@status hypothesis
@status metaphor
@status experimental
```

Optional confidence:

```text
@confidence low
@confidence medium
@confidence high
```

## Principle

MindScriptDoc should clarify the script without duplicating its implementation.

Use comments for:

- provenance
- evidence
- uncertainty
- examples
- interpretation
- limitations
