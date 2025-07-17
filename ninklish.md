---
layout: default
title: Zephyr Code
---

# 📘 **Ninklish**

## Notation

### Solfage

| Note | Symbol |
| ---- | ------ |
| Do   |  `D`   |
| da   |  `d`   |
| Re   |  `R`   |
| ri   |  `r`   |
| Mi   |  `M`   |
| Fa   |  `F`   |
| fi   |  `f`   |
| So   |  `S`   |
| su   |  `s`   |
| Lu   |  `L`   |
| le   |  `l`   |
| Ti   |  `T`   |


### Voice

| Symbol | Meaning |
| ---- | ------ |
| (none)   |  default Bell voice   |
| `'`  | Bell Voice |
| `*` | Whistle Voice |

| usage  | Meaning |
| ---- | ------ |
| `DRM `  |  DoReMi in Bell voice |
| `'DRM `  | DoReMi in Bell voice |
| `*DRM` | DoReMi in Whistle Voice  |
| `*D'RM` | Do in whistle voice, ReMi in Bell voice |

### Octave

| Octave Marker | Semitone Shift |
| ------------- | -------------- |
| `\\`          | –24 (lower)    |
| `\`           | –12 (low)      |
| (none) or `#` | +0  (natural)  |
| `//`          | +24 (high)     |
| `/`           | +12 (higher)   |

| usage  | Meaning |
| ---- | ------ |
| `DRM `  |  DoReMi in natural octave |
| ` /DRM `  | DoReMi in high octave |
| `//DR#M` | DoRe in higher octave, Mi in natural cotave  |
| `D\R\\M` | Do in natural octave, Re in low octave, Mi in lower octave |


### Lenght

| Marker | Duration |
| ------ | -------- |
| none   | 1 beat   |
| `:`    | ½ beat   |
| `::`   | ¼ beat   |
| `_`    | 2 beats  |
| `__`   | 4 beats  |


| usage  | Meaning |
| ---- | ------ |
| `DRM `  |  DoReMi in 1 beat in lenght |
| `DR:M `  | DoRe are 1 beat each, Mi in half beat |
| `::D::RM ` | Do and Re in quarter beat, Mi in one feat  |
| `__DR_M ` | Do in quad beat, Re in one beat, Mi in double beat |
| `_DR:M ` | Do in double beat, Re in one beat, Mi in half beat |

### Rest

| Marker | Duration |
| ------ | -------- |
| none   | 1 rest   |
| `.`    | 1 rest   |

| usage  | Meaning |
| ---- | ------ |
| `DRM `  |  DoReMi with no rests |
| `DR M `  | DoRe, rest, Mi |
| `DR.M ` | DoRe, rest, Mi  |
| `D.R..M ` | Do, rest, Re, rest,rest, Mi|
| `D.R_.M ` | Do, rest, Re, double rest, Mi|
| `D.R::.M ` | Do, rest, Re, quarter rest, Mi|
| `D.R:: M ` | Do, rest, Re, quarter rest, Mi|
| `D.R::.::M ` | Do, rest, Re, quarter rest, quarter Mi|



## DoTi mode

| Mode              | Notation  |
| ----------------- | --------- |
| **Numbers**       | `*:D:T`   |
| **Letters**       | `':D:T`   |
| **Nink Names**    | `':D*:T`  |
| **Foreign Names** | `*:D':T`  |

### Numbers

| Note   | Digit |
| ------ | ----- |
| `d`    |  0    |
| `R`    |  1    |
| `r`    |  2    |
| `M`    |  3    |
| `F`    |  4    |
| `f`    |  5    |
| `S`    |  6    |
| `s`    |  7    |
| `L`    |  8    |
| `l`    |  9    |

- `*:D:T RrM` : 123
- `*:D:T l` : 9
- `*:D:T sd R` : 70, 1
- `*:D:T M M d` : 3, 3, 0

### Letters

| High | letter |   | Natural | letter |   | Low  | letter |
|------|--------|---|---------|--------|---|------|--------|
| `/s` | A      |   | `l`     | I      |   | `\T` | S      |
| `/f` | B      |   | `L`     | J      |   | `\l` | T      |
| `/F` | C      |   | `s`     | K      |   | `\L` | U      |
| `/M` | D      |   | `S`     | L      |   | `\s` | V      |
| `/r` | E      |   | `f`     | M      |   | `\S` | W      |
| `/R` | F      |   | `F`     | N      |   | `\f` | X      |
| `/d` | G      |   | `M`     | O      |   | `\F` | Y      |
| `/D` | H      |   | `r`     | P      |   | `\M` | Z      |
|      |        |   | `R`     | Q      |   |      |        |
|      |        |   | `d`     | R      |   |      |        |

- `':D:T /sdF` : ABC
- `':D:T \fFM` : XYZ
- `':D:T RMF` : QON
- `':D:T \Tl/s#d\l` : START


### Nink Names

Nink names start with at least one letter, followed by numbers: D935, T983, B137, KR1574, A923, GW797. 

- `':D*:T '/M#*lMf` : D935
- `':D*:T '\l#*lLM` : T983
- `':D*:T '/f#*RMs` : B137
- `':D*:T 'sd#*Rfs` : KR157
- `':D*:T '/s#*lrM` : A923
- `':D*:T '/d\S#*sls` : GW797

#### Nink name normalization
Nink names are often normalized to make them easier to pronounce or remember. This can involve substituting parts of the name based on how they sound when spoken, or by using visual similarities between letters and numbers. For example, the number "4" resembles the letter "A" and, when pronounced, "four" can be used in place of "F" or "FO".

- `D935` : Demitri
- `T983` : Tina
- `B137` : Birt
- `KR157` : Krista
- `A923` : Anya
- `GW797` : Gwen

### Foreign Name

used to adress others that are not Nink. the vowels are considere. they are maped to the twelve notes. any note that matches is acceptable. 

| Vowel | Options              |
| ----- | -------------------- |
| A     | `d` , `F`           |
| E     | `R` , `l`           |
| I     | `r`, `M`, `f` , `T` |
| O     | `D` , `S`           |
| U     | `s` , `L`           |

- Sara : `*:D':T dF`
- Sara : `*:D':T /F'F`
- Manuel : `*:D':T FsR`
- Leonardo : `*:D':T lDFS`
- Sonia : `*:D':T SMd`

## Voice Properties

Each Nink has unique properties that shape their vocal characteristics:

- **Natural Tone:** The root note for their voice, which determines their vocal range. This typically falls between A1 and C#7.
- **Whistle Offset:** The whistle voice’s root note is set as an offset from the bell voice’s natural tone, but must remain within the A1 to C#7 range.
- **Developed Octave:** Ninks possess three octaves by default. As they mature, they may gain a fourth octave, either higher or lower than their initial range.
- **Full Range:** Calculated from the natural tone, spanning –12 semitones for the lowest note and +23 for the highest. If a fourth octave is developed, –12 is added for a lower octave or +12 for a higher octave. The whistle range is derived by applying the whistle offset to the full range.
- **Personal Shift:** Ninks can modulate their voices by shifting their natural note, affecting both bell and whistle voices equally. This does not alter their full range. Attempting notes outside their range may strain their voice.

> Name: D935 - "Dimiri"  
> Natural Tone: C3  
> Whistle Offest: 0  
> Fourth Octave: Higher  
> Full Range: : C2 - B5  
> Note: Shift -4 when speaking to M174 - "Mila"  