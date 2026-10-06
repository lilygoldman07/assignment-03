# CMPS 2200 Assignment 3
## Answers

**Name:**Lily Goldman


Place all written answers from `assignment-03.md` here for easier grading.


**1: Searching Unsorted Lists**

- **1b.** Work and span of `isearch` implementation

  `iterate` goes through the list one element at a time, doing O(1) work per step, and nothing runs in parallel.
  Work = O(n), Span = O(n)

- **1d.** Work and span of `rsearch` implementation

  The `map` has O(n) work and O(1) span. For `reduce`:
  W(n) = 2W(n/2) + O(1), which is O(n)
  S(n) = S(n/2) + O(1), which is O(log n)
  Total: Work = O(n), Span = O(log n)

- **1e.** Work and span of `rsearch` using `ureduce`

  `ureduce` splits the list into sizes n/3 and 2n/3.
  W(n) = W(n/3) + W(2n/3) + O(1), which is O(n)
  S(n) = S(2n/3) + O(1), which is O(log n) (the larger half shrinks by a factor of 3/2 each time)
  Work = O(n), Span = O(log n). The Big-O is the same as before, but the span has a larger constant because the split is uneven.

**3: Parenthesis Matching**

- **3b.** Recurrences and Big-Oh solutions for `parens_match_iterative`

  W(n) = W(n-1) + O(1), which is O(n)
  S(n) = S(n-1) + O(1), which is O(n)

- **3d.** Work and Span for `parens_match_scan`

  map: Work O(n), Span O(1)
  scan: Work O(n), Span O(log n)
  reduce: Work O(n), Span O(log n)
  Total: Work = O(n), Span = O(log n)

- **3f.** Recurrences and Big-Oh solutions for `parens_match_dc_helper`

  W(n) = 2W(n/2) + O(1), which is O(n)
  S(n) = S(n/2) + O(1), which is O(log n)