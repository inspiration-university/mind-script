# MindScript

*A human-readable language for modeling behavior, decisions, and causal systems.*

MindScript is designed to be:

- readable by non-programmers
- familiar to programmers
- structured enough for software to parse
- simple enough to write by hand

It borrows selectively from Java, SQL, and ordinary algebra.

```mind
accountabilitySelector(problem) {

    WHEN:
        problemDetected

    IF punishmentForMistakes > high:
        RETURN:
            shield(problem)

    ELSE IF psychologicalSafety > high:
        RETURN:
            bridge(problem)
}
```

## Core ideas

- `something()` is a script/process.
- `something` is data or state.
- Uppercase keywords describe logic and structure.
- Plain English is preferred over programmer-only symbols.
- Algebraic notation is preferred over operators such as `+=`, `!=`, `&&`, or `||`.

## Documentation

- [Language Specification](SPEC.md)
- [MindScriptDoc Reference](MindScriptDoc.md)
- [Grammar](grammar/mindscript.ebnf)
- [Examples](examples/)

## Status

MindScript is currently an experimental language specification at version **0.1**.

The syntax is intentionally small and expected to evolve through real-world use.

## Relationship to Inspiration OS

MindScript is an independent language.

[Inspiration OS](https://github.com/inspiration-university/inspiration-os) is one system that can be modeled and composed using MindScript.

## License

GNU GPL v3. See [LICENSE](LICENSE).
