---
menu:
  main:
    parent: "Statistics"
title: "random"
---

# random

generates a random number between 0 and 1

## Syntax

```eve
y = random[seed]
```

## Attributes

- `seed` - initializes the random number generator. The seed itself does not need to be random.

## Description

`y = random[seed]` generates a pseudorandom number drawn from the [standard uniform distribution][1], meaning the generated number is restricted to be between 0 and 1. To generate a number between a custom range, see the examples.

As with all functions in Eve, `random` is referentially transparent, meaning the function will return consistent output for a given input. When you supply a seed, this is used to generate a random number which is then memoized, insuring that the output will be the same when supplied with a previously used seed. Therefore, you must take care in your choice of seed, or the random might not work as you expect. 

Examples of a common seeds are the current timestamp, or the number of frames that have been rendered since the start of the application.

[1]: https://en.wikipedia.org/wiki/Uniform_distribution_(continuous)#Standard_uniform

## Examples

Prints a random number every second. The time attribute in `#div` is used to make each generated number unique for display purposes.

```eve
search 
  [#time minutes seconds]
  x = random[seed: seconds]

commit
  [#view/value time: "{{minutes}}{{seconds}}" | value: x]
```

Generate a random number between `min` and `max`

```eve
search
  min = 5
  max = 10
  x = random[seed: 1] * (max - min) + min

bind @browser
  [#div text: x]
```

Generate 10 random numbers

```eve
search
  i = range[from: 1, to: 10]
  x = random[seed: i]

bind
  [#view/value | value: x]
```

### Example Usage

- [Flappy Bird](https://github.com/witheve/Eve/blob/master/examples/flappy.eve)

## See Also

[gaussian][../gaussian]
