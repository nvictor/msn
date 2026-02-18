# MEL Examples

This document gives various examples using the Melodic Engineering Language (MEL) system.

## Basic Structure

### Simple Folk Structure
```text
A : [1 2 3]

[A? A←! A←~ A=]
```

### Canonical Call-Response
```text
A : [1 ♭3 4]

[A? A←! A~ A←=]
```

#### Examples

Chorus of Hallelujah (Leonard Cohen), Chorus of It Is Well (Bethel Music, Kristene DiMarco):

```text
A : [3 5 5 6]

[A? A←'! A~ A←<=]
```

Verse 1 & 2 of Way Maker (Leeland):
```text
A  : [1 ♭3 4]
A' : [4 4 4 ♭3 1]
B  : [1 5↓ 1 2]
B' : [1 ♭3 1 6↓]

[A? A'←< B! B'=]
```

### Awesome God (Rich Mullins)
```text
A  : [1 1 1 2 ♭3 ♭7↓ 5↓]
B  : [4 4 2 ♭3 ♭3 2 1]
A' : [♭7↓ 1 2 ♭3 ♭7↓ 5↓]
B' : [4 4 5 4 ♭3 2 1]

[A? B! A'~ B'=]
```

### The Terminator Theme (Brad Fiedel)
```text
A  : [1 2 ♭3]
B  : [2 ♭7↓ ♭3↓]
C  : [2 ♭7↓ 5 4]
D  : [2 ♭7↓ 4↓]
E  : [♭3↓ 1↓]
E' : [♭3↓ 2↓ 1↓]

[A? B! A? C! A? D! E~ E'=]
```
