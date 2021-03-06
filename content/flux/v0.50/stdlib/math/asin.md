---
title: math.asin() function
description: The math.asin() function returns the arcsine of `x` in radians.
menu:
  flux_0_50:
    name: math.asin
    parent: Math
weight: 1
aliases:
  - /flux/v0.50/functions/math/asin/
---

The `math.asin()` function returns the arcsine of `x` in radians.

_**Output data type:** Float_

```js
import "math"

math.asin(x: 0.22)

// Returns 0.22181447049679442
```

## Parameters

### x
The value used in the operation.
`x` should be greater than -1 and less than 1.
Otherwise, the function will return `NaN`.

_**Data type:** Float_

## Special cases
```js
math.asin(x: ±0)  // Returns ±0
math.asin(x: <-1) // Returns NaN
math.asin(x: >1)  // Returns NaN
```
