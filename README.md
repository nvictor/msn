# Melodic Engineering Language (MEL)
**Version:** 1.1.0

MEL is a symbolic system for describing and analyzing melodies by motivic gestures, phrase roles, and transformational logic.

## Model: Captures vs Ignores

| Captures | Ignores |
| :--- | :--- |
| Melodic meaning / function | Absolute pitch / key |
| Motivic transformations | Exact rhythmic values |
| Conversational structure | Harmonic progression |
| Scale-degree relationships | Instrumentation / Articulation |

## Canonical Syntax

```text
MEL ::= <MotifDef>+ <Phrase>
MotifDef ::= <Identifier> ":" "[" <Degrees> "]"
Identifier ::= <Letter> ["'"]*
Phrase ::= "[" <MotifInstance>+ "]"
MotifInstance ::= <Identifier> [<Transformation>+] [<Role>]
```

Example: `A : [1 b3 4] [A? A←!]`

Identifiers use letters and may include apostrophe suffixes for named motif variants. Uppercase names are conventional in canonical notation; lowercase names are useful in live shorthand. For example, `A' : [4 4 4 b3 1]` defines a separate motif from `A`.

When an apostrophe appears in transform position after a motif instance, it means variation. `A'←<` means motif variant `A'`, then reverse and expand. `A←'` means motif `A`, then reverse and vary.

## Symbol Table

### 1. Degrees

Defines melody as relative scale-degree motion.

- `1`..`7`: Diatonic scale degrees.
- `b` / `#`: Chromatic alterations.
- `↓` / `↑`: Octave displacement inside a degree list.

Unicode accidentals `♭` and `♯` may be used in display notation, but ASCII `b` and `#` are the canonical forms.

### 2. Phrase Roles

Defines the conversational function of a motif instance.

- `?`: Question, call, opening, implication.
- `!`: Answer, response, resolution.
- `~`: Comment, reflection, or meta-statement.
- `=`: Reinforce, repetition, or confirmation.

Roles are final phrase-function markers and normally appear after transformations: `A←!`, `A'<=`.

### 3. Transformations

Defines how a motif instance changes.

- `'`: Variation, a small melodic change.
- `←`: Reverse, or retrograde.
- `<`: Expansion, interval stretching.
- `>`: Contraction, interval shrinking.
- `↑` / `↓`: Octave transposition when used after a motif instance.

Transformations stack left-to-right. `A←'` is read as reverse, then vary.

## Semantics Rules

- **Relative Pitch:** All degrees are relative to the current tonal center, which MEL leaves unspecified.
- **Motivic Identity:** Named motif variants such as `A'` and `B'` may be defined as distinct related motifs.
- **Functional Context:** Roles define the conversational intent of a motif within a phrase.
- **Transformational Stacking:** Transformations are applied left-to-right.
- **Implicit Closure:** Phrases are assumed to form a complete musical thought.

## Constraints / Invariants

- Motifs must be defined before use in a phrase.
- Every motif instance must reference a defined motif identifier.
- Transformations only apply to the motif instance immediately preceding them.
- A motif instance has at most one phrase role, written at the end.
- MEL does not encode duration; it describes pitch contour and function.
- If a distinction requires exact rhythm, harmony, articulation, or instrumentation, it is outside the scope of MEL.

## Live Mode (Shorthand)

Optimized for high-speed capture during listening.

- Use lowercase identifiers for quick motif names: `a`, `b`, `c`.
- Omit brackets in simple chains if the reading is unambiguous.
- Use ASCII accidentals while typing: `b3`, `#4`.
- Keep one role per motif instance.

Example: `a:1 b3 4  a? a←!` is equivalent to `A : [1 b3 4] [A? A←!]`.

## Examples

### Call-Response

```text
A : [1 b3 4]

[A? A←!]
```

Songs:
* Chorus of "Hallelujah" (Leonard Cohen)
* Chorus of "It Is Well" (Bethel Music, Kristene DiMarco)
* Verse of "Way Maker" (Leeland)

### Awesome God

"Awesome God" (Rich Mullins):

```text
A  : [1 1 1 2 b3 b7↓ 5↓]
B  : [4 4 2 b3 b3 2 1]
A' : [b7↓ 1 2 b3 b7↓ 5↓]
B' : [4 4 5 4 b3 2 1]

[A? B! A'~ B'=]
```

### The Terminator Theme

"The Terminator Theme" (Brad Fiedel):

```text
A  : [1 2 b3]
B  : [2 b7↓ b3↓]
C  : [2 b7↓ 5 4]
D  : [2 b7↓ 4↓]
E  : [b3↓ 1↓]
E' : [b3↓ 2↓ 1↓]

[A? B! A? C! A? D! E~ E'=]
```

## Quick Reference

- `A : [1 b3 4]`: Define motif `A`.
- `A' : [4 4 4 b3 1]`: Define motif variant `A'`.
- `A?`: Motif `A` as a question.
- `A!`: Motif `A` as an answer.
- `A~`: Motif `A` as a comment.
- `A=`: Motif `A` as reinforcement.
- `A←`: Motif `A` reversed.
- `A'←<`: Motif variant `A'`, reversed and expanded.
- `A←'`: Motif `A`, reversed and varied.
- `A↑`: Motif `A` transposed up an octave.
- `5↓`: Scale degree 5 displaced down an octave.
