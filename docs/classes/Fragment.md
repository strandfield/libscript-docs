---
layout: default
title: "Fragment class"
parent: "Class reference"
---

# Fragment Class

**Brief:** a range in a token list

## Detailed description

## Enumerations

### FragmentKind

**Brief:** provides a description for subfragments

This enum is used by the TokenReader class for constructing subfragment.

## Members documentation

### Fragment(const std::vector\<Token>& tokens)

**Brief:** constructs a fragment consisting of the full token list

### Fragment(iterator begin, iterator end)

**Brief:** constructs a fragment from an explicitely specified range

### iterator begin() const

**Brief:** returns the begin iterator of the fragment

### iterator end() const

**Brief:** returns the end iterator of the fragment

### size_t size() const

**Brief:** returns the number of tokens in the fragment

### bool operator==(const Fragment& lhs, const Fragment& rhs)

**Brief:** compares two fragments for equality

Note that comparing two fragments constructed from different token lists is undefined behavior.

### bool operator!=(const Fragment& lhs, const Fragment& rhs)

**Brief:** compares two fragments for inequality

Note that comparing two fragments constructed from different token lists is undefined behavior.

