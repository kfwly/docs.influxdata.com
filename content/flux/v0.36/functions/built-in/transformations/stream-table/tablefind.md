---
title: tableFind() function
description: >
  The `tableFind()` function extracts the first table in a stream of tables whose
  group key values match a predicate. If no table is found, the function errors.
menu:
  flux_0_36:
    name: tableFind
    parent: Stream & table
weight: 1
---

The `tableFind()` function extracts the first table in a stream of tables whose
group key values match a predicate. If no table is found, the function errors.

_**Function type:** Stream and table_  

```js
tableFind(column: "_value")
```

## Parameters

### fn
A predicate function for matching keys in a table's group key.
`tableFind` returns the first table that resolves as `true`.
It expects a `key` argument which represents a group key in the input stream.

_**Data type:** Function_

##### Example fn function
```js
(key) => key._field == "fieldName"
```

## Example
```js
t = from(bucket:"telegraf/autogen")
    |> range(start: -5m)
    |> filter(fn:(r) => r._measurement == "cpu")
    |> tableFind(fn: (key) => key._field == "usage_idle")

// t represents the first table in a stream whose group key
// contains "_field" with a value of "usage_idle".
```

{{% note %}}
You can use `t` from the example above as input for [`getColumn()`](/flux/v0.36/functions/built-in/transformations/stream-table/getcolumn/)
and [`getRecord()`](/flux/v0.36/functions/built-in/transformations/stream-table/getrecord/).
{{% /note %}}
