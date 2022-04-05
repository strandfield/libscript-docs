---
layout: default
title: "DelimitersCounter class"
parent: "Class reference"
---

# DelimitersCounter Class

**Brief:** a basic facility to count matching delimiters

## Detailed description

The DelimitersCounter class can be used to verify proper nesting of delimiters that comes in pair; i.e. {}, () and [].

## Members documentation

### void reset()

**Brief:** resets all counters to zero

### void feed(const Token& tok)

**Brief:** updates the counters

Parameters:
- input token

### bool balanced() const

**Brief:** returns whether delimiters are properly balanced

### bool invalid() const

**Brief:** returns whether the counters are in a state that makes balancing impossible

This state is reached when a closing delimiter is encountered before its matching opening delimiter; e.g. ")[])"

