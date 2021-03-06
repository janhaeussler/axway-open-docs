---
title: Filtering APIs to be discovered
linkTitle: Filtering APIs to be discovered
draft: false
weight: 80
description: Learn how to set up tag-based condition expression(s) using the
  APIMANAGER_FILTER environment variable to discover APIs that could be added to
  AMPLIFY Central.
---
Conditional expressions statements use logical operators to compare values. This section provides sample syntax for defining expressions.

{{< alert title="Note" color="primary" >}}For tag-based filtering, the conditional expression should have "tag" as the prefix / selector in the symbol name.
The expression can be a simple condition or a compound condition in which multiple conditions are evaluated using logical operators. See Logical operators and Comparative operators, below.{{< /alert >}}

```
tag.<tagName> == <tagValue>
```

## Before you start

* Familiarize yourself with  the [APIMANAGER_FILTER] (/docs/central/connect-api-manager/discovery-agent-variables/)
* Review Logical operators and Comparative operators, below

## Objectives

Learn how to set filtering based on tag name, tag value, partial value and MatchRegEx to discover APIs that can be added to AMPLIFY Central.

## Filter based on tag name

```
tag.<tagName>.Exists() == true | false
```

## Filter based on tag value

```
tag.Any() == | != <tagValue>
```

## Filter based on tag name and tag value

```
tag.<tagName> == | != <tagValue>
```

## Filter based on partial value

```
tag.<tagName>.contains(<value>) == true |  false
```

## Filter using MatchRegEx

```
tag.<tagName>.matchRegEx(<regularExpression>)
```

## Logical operators

Logical operators are used for evaluating multiple conditions. These can be combined with comparative operators and any of the above expressions.

| Operator | Description                                                                |   |
|----------|----------------------------------------------------------------------------|---|
| `&&`      | Logical AND operator, returns true if conditions on both sides are true.   |   |
| `\|\|`       | Logical OR operator, returns true if the condition on either side is true. |   |

## Comparative operators

Comparative operators are used for comparing two values. These can be combined with logical operators and any of the above expressions.

| Operator | Description                                                                                                    |   |
|----------|----------------------------------------------------------------------------------------------------------------|---|
| `==`       | Equal to operator, returns true if values on both sides are equal.                                             |   |
| `!=`       | Not equal to operator, returns true if the value on the left side is not equal to the value on the right side. |   |
