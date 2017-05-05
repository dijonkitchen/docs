---
menu:
  main:
    parent: "Math"
title: "tan"
---

# tan

Calculate the tangent of an angle

## Syntax

```eve
y = tan[radians]
y = tan[degrees]
```

## Attributes

- `radians` - the angle in radians
- `degrees` - the angle in degrees

## Description

`y = tan[degrees]` calculates the tangent of an input in degrees. 

`y = tan[radians]` calculates the tangent of an input in radians.

`tan` operates element-wise on its inputs.

## Examples

```eve
search
  y = tan[degrees: 90]

bind 
  [#view/value text: y]
```

## See Also

[cos](../cos) | [sin](../sin)