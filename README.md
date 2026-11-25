# Chord Diagrams / Хордові діаграми

A dependency-free, single-file browser application for enumerating, drawing, and exploring chord diagrams.

Самодостатня HTML-програма без залежностей для перебору, побудови та дослідження хордових діаграм.

- **Author / Автор:** Alexandr Prishlyak / Олександр Пришляк       ORCID: 0000-0002-7164-807X
- **Organization / Організація:** Taras Shevchenko National University of Kyiv
- **License / Ліцензія:** MIT (see [`LICENSE`](LICENSE))

## Quick start

1. Download or clone this repository.
2. Open [`chords.html`](chords.html) in a modern browser. No build step, server, or internet connection is required.
3. Select the number of chords `k`, the desired cycle count, and whether the diagram is oriented; click **Generate**.

The language button in the page header switches between Ukrainian and English.

## Features

- Enumerates perfect matchings of the `2k` vertices of a regular polygon.
- Keeps one representative under rotations and reflections; colored diagrams are compared together with their chord signs.
- **Oriented: Yes** generates all-blue diagrams. **Oriented: No** generates every sign assignment, including the all-blue assignment; different colorings can have different cycle counts.
- Displays the rotation-system code and pairing (substitution) code for each diagram.
- Lets you enter either code to reconstruct a diagram.
- Animates endpoint sliding in either direction and applies the resulting diagram.
- Shows the full result list as paged thumbnails. Short-arc chords (under 30°) are curved inward in thumbnail mode.
- Exports the current diagram or complete list as SVG, and saves the list as rotation-system or pairing codes.

## Codes and colors

The rotation-system code lists chord labels while walking around the circle. The signs after a space give chord colors in order of first appearance: `-` is red and `+` is blue. For example:

```text
11223434 -+-+
```

The pairing code lists the endpoint pairs, followed by the same sign sequence, for example:

```text
(12)(34)(57)(68) -+-+
```

For vertex numbers above 9, the pairing code uses commas, such as `(1,13)`.

## Cycles

A cycle alternates between traversing a chord and moving along a circle arc. Traversing a red chord reverses the direction of travel along the circle. The program treats the two opposite traversals of the same unoriented boundary cycle as one cycle.

## Enumeration size

The number of pairings grows as `(2k - 1)!!`; unoriented mode also considers up to `2^k` color assignments per pairing. Large values of `k` can take substantial time and memory. The application warns before the largest configured searches.

## Ліцензія та авторство

Програму створив Олександр Пришляк (Alexandr Prishlyak), КНУТШ. Код поширюється за ліцензією MIT; повний текст наведено у файлі [`LICENSE`](LICENSE).
