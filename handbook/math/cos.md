---
menu:
  main:
    parent: "Math"
title: "cos"
---

# cos

Calculate the cosine of an angle

## Syntax

```eve
y = cos[radians]
y = cos[degrees]
```

## Attributes

- `radians` - the angle in radians
- `degrees` - the angle in degrees

## Description

`y = cos[degrees]` calculates the cosine of an input in degrees. 

`y = cos[radians]` calculates the cosine of an input in radians.

`cos` operates element-wise on its inputs.

## Examples

Calculate the cosine of 90 degrees

```eve
search
  y = cos[degrees: 90]
  
bind
  [#view/value text: y]
```

## See Also

[sin](../sin) | [tan](../tan) 