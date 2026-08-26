# Junior School Math Olympiad — Problem Bank

A browsable bank of **1,350 olympiad problems** for primary pupils, aimed at Years 3–6 (British programme) / Grades 1–4 (Kazakhstan and former Soviet programmes). Problems are collected from olympiads and sorted by topic, year and difficulty.

The repository is a self-contained static site: open `index.html` and the whole bank is filterable, printable and exportable in the browser.

## Running it

The page loads `problems.json` with `fetch`, so it needs to be served over HTTP — opening the file directly with `file://` will fail.

```bash
python3 -m http.server
# then open http://localhost:8000
```

It also works as-is on GitHub Pages (Settings → Pages → deploy from `main`, root folder).

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | The viewer: filtering, problem-set builder, print view, progress tracking |
| `problems.json` | The problem bank — a flat JSON array of 1,350 problems |
| `images/` | 286 figures referenced by problems (grids, clocks, nets, diagrams) |

## Problem schema

Each entry in `problems.json` is an object:

```json
{
  "n": 1,
  "topic": "Age problems",
  "year": 3,
  "prob": "Two sisters have birthdays on the same day...",
  "diff": 2,
  "source": "FEMO",
  "imgs": []
}
```

| Field | Meaning |
| --- | --- |
| `n` | Unique problem ID, `1`–`1353` (a few numbers are unused where duplicates were removed) |
| `topic` | One of 38 topics (see below) |
| `year` | Target year group |
| `prob` | Problem statement (may contain newlines) |
| `diff` | Difficulty, `1` (easiest) – `4` (hardest) |
| `source` | Originating olympiad |
| `imgs` | Array of image paths, e.g. `["images/p700_rings.jpg"]`; empty when the problem has no figure |

## Composition

**By year group** — Year 3: 324 · Year 4: 304 · Year 5: 377 · Year 6: 337 · Year 1: 8

**By difficulty** — 1: 72 · 2: 324 · 3: 545 · 4: 409

**By source** — FEMO: 865 · Saint Petersburg Mathematical Olympiad: 485

**By topic**

| Topic | Count |
| --- | ---: |
| Arithmetic word problem – finding the whole or part | 106 |
| Digit properties / number puzzles | 105 |
| Equations | 103 |
| Spatial reasoning | 100 |
| Logic – quantitative bounding | 94 |
| Combinatorics – arrangements / permutations | 65 |
| Sets – inclusion–exclusion | 58 |
| Logic – knights and liars | 56 |
| Age problems | 54 |
| Arithmetic – net displacement | 49 |
| Iterative / process counting | 45 |
| Counting 2D figures | 43 |
| Number sequences & patterns | 40 |
| Geometry – perimeter of combined figures | 38 |
| Counting digits | 37 |
| Figures and numbers | 37 |
| Cryptarithm | 36 |
| Cuts and pieces (fencepost counting) | 32 |
| Logic – matching | 32 |
| Work rate / productivity | 29 |
| Heads and legs | 27 |
| Logic – sequence / correspondence reasoning | 24 |
| Remainder / equal distribution | 22 |
| Counting consecutive numbers | 21 |
| Geometry – area of combined figures | 19 |
| Clock / time reading | 18 |
| Calendar reasoning | 18 |
| Circular arrangement | 16 |
| LCM / common multiples (cycles) | 8 |
| Graph colouring | 5 |
| Ciphers / decoding | 4 |
| Logic – casework counting | 2 |
| Tournaments / handshakes | 2 |
| Symmetry | 1 |
| Odd one out / visual pattern recognition | 1 |
| Logic – hat puzzles / common knowledge | 1 |
| Dividing a figure into regions | 1 |
| Route traversal / Euler routes | 1 |

## Editing the bank

The viewer can hide problems and export a revised `problems.json` via **Download problems.json**. Hidden problems live in browser storage until exported, so replace the file in this repository and commit it to make changes permanent.
