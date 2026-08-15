# wassem ambigram — proposed secondary mark

`wassem` rotated 180° reads as `wassem`. These files are the vector masters.

**Status: a proposal, not an approved brand asset.** The primary wordmark is still
Fraunces 900 italic (`logo.svg` and friends) — nothing here replaces it. Nothing on the
site references these files yet.

## Files

| File                         | Use                                                      |
|------------------------------|----------------------------------------------------------|
| `ambigram-wordmark.svg`      | Ink type, orange `a`/`e`, transparent bg — primary master |
| `ambigram-wordmark-dark.svg` | Cream type for dark grounds, orange accent unchanged      |
| `ambigram-seal.svg`          | Circular seal on yellow — stamps, stickers, avatars       |

These are the **Stamp** cut: one even weight, stroke 25 on a 100-unit x-height, round caps
and joins. Because it is monoline, each master is just the centreline stroked — small,
exact, and editable, rather than a flattened outline. Three other cuts exist (modulated,
italic, condensed); all are generated from this same skeleton by changing weight, contrast
and slant, so switching is a regeneration rather than a redraw.

## How it is built

Rotating a word reverses its letter order *and* inverts every letter, so `wassem`
survives only if `w`↔`m`, `s`↔`s` and `a`↔`e`. The first two pairs are already each
other upside down; `a`→`e` is the only one that has to be drawn.

Three masters are drawn — `w`, `a`, `s` — and the other three letters are emitted as
exact 180° rotations of them. The symmetry is therefore guaranteed by construction, not
eyeballed: if you edit a glyph, its partner follows automatically.

The `a`/`e` glyph exploits the fact that an `a` (enclosed bowl low, open hood arching
over) and an `e` (enclosed counter high, open stroke sweeping under) are the same object
rotated. Two details carry it: a long straight right stem — without it the shape reads as
a schwa `ə` — which becomes the flat left side of the `e`; and a terminal hooking
down-left, which rotation sends up-right, exactly where an `e` ends. Aperture size is the
one property that cannot be tuned twice and is set at the midpoint, which is why the mark
is sized for logo use rather than text.

## Constraints

- Monoline **by choice, not necessity.** A 180 degree rotation preserves stroke angle, so
  contrast and italic slant both work fine (only mirroring would break them). Monoline is
  chosen because it survives small sizes and being pressed into dough.
- `bakes` is not symmetrical (no partner for `b` or `k`). On the seal it goes in the ring
  instead, set twice at opposite ends, so the seal turns onto itself as a whole.
- Colour follows the palette: ink `#1A1714`, orange `#FF8F1C`, yellow `#FFD451`,
  cream `#E8DCC8`. Both the `a` and the `e` are orange, which keeps the accent
  rotationally symmetric too.
