# Melodic Structure Notation (MSN)

MSN is a concise, symbolic system for describing, analyzing, and generating melodies based on motivic gestures, phrase roles, and transformational logic.

MSN is intentionally orthogonal to harmony and rhythm. It focuses on
melodic meaning: how short pitch gestures function as questions,
answers, comments, and closures across a phrase.

## Design Goals

-   Concise and human-readable
-   Relative (scale-degree--based), not absolute pitch
-   Generative, not just analytical
-   Phrase- and conversation-oriented
-   Engineer-friendly and DSL-compatible

## Core Concepts

### 1. Motifs

A motif is a short melodic gesture expressed as relative scale
degrees or intervals.

Examples:
```
A = [1 ♭3 4]
B = [R m3 4]
C = [1 4 5]
```

Motifs describe shape, not duration, rhythm, or harmony.

### 2. Phrase Roles

Each motif instance can be annotated with a conversational role.

| Symbol | Role | Meaning |
|--------|------|------------------------------|
| `?` | Question | Call, opening, implication, statement |
| `!` | Answer | Response, resolution |
| `~` | Comment | Reflection or meta-statement |
| `=` | Reinforce | Repetition or confirmation |

These roles are semantic, not prescriptive.

### 3. Transformations

Motifs may be transformed when reused.

| Symbol | Transformation |
|--------|----------------|
| `'` | Variation (small change) |
| `←` | Reverse |
| `<` | Expansion |
| `>` | Contraction |
| `↑` | Transpose up |
| `↓` | Transpose down |

Example:
```
B = A'
C = A↑
```

## Phrase Grammar

MSN phrases are written as ordered chains of motif-role pairs.

### Canonical Call-Response Pattern

```
A = [1 ♭3 4]
B = A←

[A? B! A~ B=]
```

Interpretation:

1.  A introduces a question
2.  B responds with variation
3.  A comments on the original idea
4.  B reinforces and closes

### Repetition-Driven Variant

```
[A? B! A= B=]
```

## Examples

### Minor-Key Gesture

```
A = [R m3 4]
B = [R 4 5]

[A? B! A~ B=]
```

### Simple Folk Structure

```
A = [1 2 3]
B = A←

[A? B B~ A=]
```

## Generative Use

MSN is suitable for:
-   Algorithmic composition
-   Melody generators
-   Structural analysis
-   Sketching musical ideas quickly

## Non-Goals

MSN is not:
- A replacement for staff notation
- A rhythmic notation system
- A performance specification

It is a structural and semantic layer.

## Status

MSN is experimental and evolving.

The symbol set is intentionally small. New roles or transformations
should only be added when they clearly enable expressive power without
reducing clarity.
