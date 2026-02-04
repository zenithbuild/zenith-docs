# Zenith Contract

> [!IMPORTANT]
> **Precedence Rule**: If any code, comment, or document conflicts with `zenith-contract.md`, **this document is authoritative**. Conflicting code must be changed or deleted.

## 1. Guarantees

Zenith guarantees the following properties for all valid programs:

1.  **Mechanical Certainty**: All behavior is statically analyzable at compile time. There is no runtime guessing.
2.  **Zero Runtime Abstraction**: The output contains no Virtual DOM, no reactive proxies, no "framework" code, and no runtime scope resolution.
3.  **Structural Integrity**: The output structure matches the input structure (macro expansion). Components do not create runtime boundaries.
4.  **Deterministic Identity**: Interactive anchors and bindings resolve to stable, deterministic references at build time.
5.  **Simplicity**: Code exists only if proven necessary by an invariant. Deletion is preferred over abstraction.

## 2. Non-Goals (Explicitly Forbidden)

Zenith explicitly does **NOT** support or allow:

1.  **Runtime Ambiguity**: No behavior dependent on runtime introspection of types or structures.
2.  **Intent-Guessing**: The compiler does not infer intent. It enforces explicit instructions.
3.  **Future-Proofing**: No "helper" layers or abstractions added for hypothetical future use.
4.  **Runtime Scope Resolution**: No looking up identifiers at runtime. All bindings are resolved at compile time.
5.  **Complex Reactivity**: No fine-grained reactivity engine or dependency tracking unless fully resolved at compile time.
6.  **Heuristics**: No fuzzy matching or "best effort" recovery.

## 3. Compiler Emissions

The compiler is **permitted** to emit:

1.  **Static HTML**: Logic-less, optimized HTML markup.
2.  **Static CSS**: CSS assets derived from styles.
3.  **Minimal JavaScript**: "Dumb" bindings that map native events to pre-compiled instructions.

The compiler is **forbidden** from emitting:

1.  **Runtime Parsers**: Logic to parse or interpret data/strings at runtime.
2.  **framework.js**: Any generic runtime library code.
3.  **Hydration Logic**: Complex state re-hydration mechanisms.

**Phase Order Constraint**:
The compiler must operate in specific order: Parse → Scope → Safety → Renaming → Lowering → Emit. Reordering is forbidden.

## 4. Runtime Execution Constraints

The runtime is **permitted** to:

1.  **Bind Events**: Attach native listeners to compiled anchors.
2.  **Execute Instructions**: Run specific, compiler-approved function calls.
3.  **Schedule Effects**: Perform DOM updates strictly as directed by the compiled output.

The runtime is **forbidden** from:

1.  **Interpreting Syntax**: No processing of template strings or expressions.
2.  **Deriving State**: No state management logic beyond simple values.
3.  **Recovering Errors**: Runtime errors indicate compiler failure; the runtime must not attempt to recover.
4.  **Scanning the DOM**: No searching the DOM for directives or markers.

## 6. Resources & Implementation Details

For detailed package behaviors and public interfaces, refer to the authoritative documentation:

- [Onboarding & Developer Guide](./onboarding.md)
- [Compiler API Reference](./api/compiler.md)
- [Runtime API Reference](./api/runtime.md)
- [Router API Reference](./api/router.md)
- [CLI Reference](./api/core.md)
