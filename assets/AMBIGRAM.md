# wassem ambigram — proposed secondary mark

`wassem` rotated 180° reads as `wassem`. These files are the vector masters.

**Status: a proposal, not an approved brand asset.** The primary wordmark is still
Fraunces 900 italic (`logo.svg` and friends) — nothing here replaces it. Nothing on the
site references these files yet.

## Files

| File                          | Use                                                       |
|-------------------------------|-----------------------------------------------------------|
| `ambigram-wordmark.svg`       | `wassem` alone — the rotating mark. Ink + multicolour a/e |
| `ambigram-wordmark-dark.svg`  | Same, cream letters for dark grounds                      |
| `ambigram-wordmark-mono.svg`  | Single ink — stamps, embossing, one-colour print          |
| `ambigram-lockup.svg`         | `wassem bakes`, two lines                                 |
| `ambigram-lockup-dark.svg`    | Lockup, cream letters for dark grounds                    |
| `ambigram-lockup-mono.svg`    | Lockup, single ink                                        |

## The face

A grotesque: straight sides, terminals cut square, stroke 19 on a 100-unit x-height.
The `w` has **flat vertices** — its V bottoms are cut flat rather than pointed, which
matters because the `m` is the `w` turned over: pointed vertices gave the `m` spikes and
a middle leg that stopped short of the baseline.

## How it is built

Rotating a word reverses its letter order *and* inverts every letter, so `wassem`
survives only if `w`↔`m`, `s`↔`s` and `a`↔`e`. The first two pairs are already each
other upside down; `a`→`e` is the only one that has to be drawn.

Three masters are drawn — `w`, `a`, `s` — and the other three letters are emitted as
exact 180° rotations of them. The symmetry is guaranteed by construction, not eyeballed:
edit a glyph and its partner follows.

The `a`/`e` glyph works because an `a` (enclosed bowl low, open hood arching over) and an
`e` (enclosed counter high, open stroke sweeping under) are the same object rotated. A
long straight right stem is what stops it reading as a schwa `ə`, and that stem becomes
the flat left side of the `e`.

## Colour

One rule: **the bowl carries the word's own colour; the hood, stem and bar take the three
brand accents.**

- hood — orange `#FF8F1C`
- stem — blue `#8DB9CA`
- bar — yellow `#FFD451`
- bowl + all other letters — ink `#241D17` (or cream `#E8DCC8` reversed)

Only the `a` and `e` of `wassem` are coloured. **`bakes` stays single ink** — its vowels
are not accented.

Because the `a` and the `e` are one drawing used twice, the colouring is rotationally
symmetric too: turn the mark over and every colour lands where that colour was.

## Constraints

- Monoline **by choice, not necessity.** A 180° rotation preserves stroke angle, so
  contrast and italic slant both work fine (only mirroring would break them).
- `bakes` is not symmetrical — no partner for `b` or `k` — so only `wassem` turns. In the
  lockup `bakes` sits as a fixed second line, and its `b` and `k` are the only ascenders
  in the design.
- Use the mono file below roughly 120px wide; four colours across a 19-unit stroke go
  muddy at small sizes.
