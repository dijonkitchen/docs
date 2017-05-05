---
menu:
  main:
    parent: "Core Language"
title: "Actions"
weight: 3
---

# Actions

## Description

There are three actions in Eve: `search`, `bind`, and `commit`.

`search` is used to find records in the Eve database.

`bind` and `commit` actions are used when you want to update records in the database, but they differ how long those updates persist.

- bound records have a lifetime equal to the records used to derive them. When supporting records change, then bound records are updated, replacing any previously bound records.

- committed records persist in the database until they are explicitly changed or removed. When supporting records change, then a new record is committed, leaving any previously committed records still intact.

## Examples

Because it is bound, a student's GPA updates whenever a new score is added to his or her record

```eve
search
  student = [#student scores]
  calculated-gpa = average[given: scores]

bind
  student.gpa = calculated-gpa
```

## See Also

[search](../search) | [bind](../bind) | [commit](../commit)
