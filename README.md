# Melodic Engineering Language (MEL)
**Version:** 1.0.0

MEL is a symbolic system for describing and analyzing melodies based on motivic gestures, phrase roles, and transformational logic.

## Model: Captures vs Ignores

| Captures | Ignores |
| :--- | :--- |
| Melodic meaning / function | Absolute pitch / key |
| Motivic transformations | Exact rhythmic values |
| Conversational structure | Harmonic progression |
| Scale-degree relationships | Instrumentation / Articulation |

## Canonical Syntax

```text
MEL ::= <MotifDef> <Phrase>
MotifDef ::= <Identifier> ":" "[" <Degrees> "]"
Phrase   ::= "[" <MotifInstance>+ "]"
MotifInstance ::= <Identifier> [<Transformation>+] [<Role>]
```

Example: `A : [1 ♭3 4] [A? A←!]`

## Symbol Table

### 1. Degrees
- `1`..`7`: Diatonic scale degrees.
- `♭` / `♯`: Chromatic alterations.
- `↓` / `↑`: Octave shifts.

### 2. Phrase Roles
- `?`: **Question:** Call, opening, implication.
- `!`: **Answer:** Response, resolution.
- `~`: **Comment:** Reflection or meta-statement.
- `=`: **Reinforce:** Repetition or confirmation.

### 3. Transformations
- `'`: **Variation:** Small melodic change.
- `←`: **Reverse:** Retrograde.
- `<`: **Expansion:** Interval stretching.
- `>` : **Contraction:** Interval shrinking.
- `↑` / `↓`: **Transpose:** Octave shifts.

## Semantics Rules

- **Relative Pitch:** All degrees are relative to the current tonal center (unspecified in MEL).
- **Functional Context:** Roles define the *conversational* intent of a motif within a phrase.
- **Transformational Stacking:** Transformations are applied left-to-right (e.g., `A←'` is Reverse then Varied).
- **Implicit Closure:** Phrases are assumed to form a complete musical thought.

## Constraints / Invariants

- Motifs must be defined before use in a phrase.
- Transformations only apply to the motif immediately preceding them.
- MEL does not encode duration; it describes pitch-contour and function.
