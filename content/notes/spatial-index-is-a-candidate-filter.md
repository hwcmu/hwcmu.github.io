---
title: "A Spatial Index Is a Candidate Filter, Not Geometry"
date: 2026-10-17
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
description: "Why Hilbert and Z-order mappings accelerate multidimensional search without replacing exact spatial predicates."
url: "/blogs/spatial-index-is-a-candidate-filter/"
series: ["Data Systems Notes"]
tags: ["Spatial Indexing", "Database Design", "Space-Filling Curves"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/"
  - "https://s2geometry.io/devguide/s2cell_hierarchy"
  - "https://s2geometry.io/devguide/cpp/quickstart.html"
  - "https://github.com/google/s2geometry"
  - "https://arxiv.org/abs/1711.04473"
  - "https://www.vldb.org/conf/1998/p194.pdf"
---

A spatial index returns records worth checking. Unless the indexed cell representation exactly matches the requested geometry, those records are not yet the answer.

This boundary is easy to miss because the index feels geometric. Underneath, many systems have converted multidimensional position into sortable keys or hierarchical cells. That conversion accelerates candidate retrieval by preserving some locality. It does not preserve every spatial relationship exactly.

> Use the index to make the candidate set small. Use the geometric predicate to decide which candidates are true matches.

## Why a Database Wants One Dimension

A point may have latitude and longitude. A conventional ordered index prefers a scalar key that can be sorted into pages and scanned as ranges.

Space-filling traversals bridge the two representations. A finite grid is recursively divided into cells, and each cell receives a position along a one-dimensional order.

- **Z-order or Morton order** interleaves coordinate bits. Encoding and hierarchical partitioning are relatively simple.
- **Hilbert order** rotates and reflects the traversal recursively. It often clusters nearby cells more tightly, with more complex encoding.

The result is a scalar or hierarchical key that an ordered store can sort and scan.

```mermaid
flowchart LR
    A["Coordinate or geometry"] --> B["Cover with indexed cells"]
    B --> C["Convert cells to key ranges"]
    C --> D["Retrieve candidates"]
    D --> E["Apply exact predicate"]
    E --> F["Return matches"]
```

Skipping the exact predicate is safe only when the query is defined entirely in terms of the indexed cells.

## Locality Is Useful but Incomplete

Nearby curve positions tend to correspond to nearby cells. This improves storage locality and reduces the number of pages or partitions touched by a query.

The reverse is not guaranteed. Two spatial neighbors can lie on opposite sides of a curve boundary and receive distant keys. A rectangle, radius, or polygon may also intersect several separated portions of the traversal, producing multiple key intervals.

The index therefore approximates a multidimensional neighborhood with a collection of one-dimensional ranges. It can create:

- **false-positive candidates:** indexed cells overlap the query, but the exact geometry does not;
- **range fragmentation:** one spatial window becomes many scalar scans;
- **resolution error:** coarse cells retrieve too much, while fine cells increase index and query complexity.

These are design tradeoffs, not implementation accidents.

## S2 Shows the Two Layers Clearly

Google's S2 Geometry library maps the sphere to six cube faces and organizes cells along linked Hilbert-like traversals. Hierarchical cell identifiers encode position and level, giving useful locality for indexing geographic data.

S2 also retains exact spherical geometry operations. Its [indexing quick start](https://s2geometry.io/devguide/cpp/quickstart.html) retrieves a candidate set that can include near-intersections, then checks the original geometry to produce exact results. That separation is the architecture to remember, even when another system uses a different curve or tree.

## Choose the Curve Through the Workload

| Decision | What to measure |
| --- | --- |
| Z-order or Hilbert-like ordering | Encoding cost, interval count, and candidate locality |
| Cell resolution | False-positive candidates versus index depth |
| Partition boundaries | Hot regions, write balance, and cross-partition queries |
| Query decomposition | Number and size of key ranges per query shape |
| Post-filter | CPU cost and exact-match selectivity |

Neither ordering dominates every workload. Compare them using the actual windows, polygons, update rates, and distributions the system must serve.

A visual comparison of curves is not a benchmark.

## Where the Approximation Weakens

Space-filling approaches become less attractive when dimensionality grows, data occupies an irregular subset of space, queries cut across many curve segments, or one scalar order must serve incompatible query shapes.

High-dimensional neighborhoods also become sparse. A mapping can preserve a useful order without solving the curse of dimensionality; a [VLDB analysis of high-dimensional similarity search](https://www.vldb.org/conf/1998/p194.pdf) shows how partitioning and clustering methods can degrade as dimensionality rises.

Test at least four cases before choosing the index:

1. dense queries in common regions;
2. sparse or boundary-crossing queries;
3. large windows that cover many cells;
4. hot regions that may overload one key range or partition.

Report candidate count and exact-match count separately. Their ratio reveals how much work the approximation passes to the post-filter.

## The Decision Boundary

Space-filling curves are valuable because they let one-dimensional storage structures approximate multidimensional locality. That is already a powerful result. Treating the approximation as exact geometry asks it to do a different job.

The design succeeds when the index removes most irrelevant records, the range decomposition remains manageable, and the exact predicate is cheap on the survivors.

An index that returns candidates quickly is working. Correctness begins with what happens next.

## Sources

- Geoffrey West. [*Scale*](https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/). Penguin Books.
- S2 Geometry. [S2 Cell Hierarchy](https://s2geometry.io/devguide/s2cell_hierarchy).
- S2 Geometry. [C++ Quick Start](https://s2geometry.io/devguide/cpp/quickstart.html).
- Google. [S2 Geometry Library](https://github.com/google/s2geometry).
- Haverkort H. [Sixteen Space-Filling Curves and Traversals for d-Dimensional Cubes and Simplices](https://arxiv.org/abs/1711.04473). 2018.
- Weber R, Schek H-J, Blott S. [A Quantitative Analysis and Performance Study for Similarity-Search Methods in High-Dimensional Spaces](https://www.vldb.org/conf/1998/p194.pdf). *Proceedings of the 24th VLDB Conference*. 1998.
