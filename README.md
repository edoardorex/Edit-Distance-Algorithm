# Edit Distance and Dictionary Matching

An educational Python project exploring string similarity through dynamic
programming, character n-grams, and Jaccard similarity. Its experiments compare
dictionary-search strategies using an included Italian word list.

## What is included

- An edit-distance matrix with insertion, deletion, replacement, copying, and
  adjacent-character transposition operations.
- Configurable operation costs through `DistanceManager.set_costo()`.
- Character n-gram generation and Jaccard similarity.
- Timed dictionary-search experiments and Matplotlib plots.

| File | Purpose |
| --- | --- |
| [edit_distance.py](edit_distance.py) | `DistanceManager` and dictionary preparation |
| [test.py](test.py) | Three dictionary-matching experiments and plotting |
| [60000_parole_italiane.txt](60000_parole_italiane.txt) | Input word list |

## Getting started

The original implementation requires **Python 2.7** and a compatible Matplotlib
installation. It contains Python 2 `print` statements and relies on the
Python 2 behavior of `zip`. Use an isolated legacy environment; Python 2 is
end-of-life.

From the repository root:

```sh
python2 edit_distance.py
python2 test.py
```

The first command creates `dizionario.p`. Importing `edit_distance` also performs
this preparation, so the word-list file must be available in the working
directory. The second command runs all three experiments, writes timing files,
and displays their comparison.

## Using the implementation

`edit_distance(a, b)` populates `matrice` rather than returning a distance.
Read `matrice[len(a)][len(b)]` after calling it. The `operazione` matrix records
the selected transformations; `_sequenza_operazioni(i, j)` prints a backtrace.

The benchmarks scan the dictionary repeatedly and may take time to finish.
They are exploratory scripts rather than isolated unit tests. Only load pickle
files you generated or otherwise trust.

## Project provenance

This repository is a fork of
[edoardore/Edit-Distance-Algorithm](https://github.com/edoardore/Edit-Distance-Algorithm).
The original implementation and history are preserved.
