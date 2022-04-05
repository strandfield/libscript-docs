---
layout: default
title: "FunctionFlags class"
parent: "Class reference"
---

# FunctionFlags Class

**Brief:** Provides a type-safe OR-combination of function and access specifiers.

## Detailed description

The FunctionFlags is used to store flags describing a Function. It is used to store both FunctionSpecifier (i.e. is the function static, or virtual, or deleted) and an AccessSpecifier (public, protected, private).

Internally, the access specifier is stored on the two first bits and the FunctionSpecifier on the remaining bits.

## Members documentation

### FunctionFlags(FunctionSpecifier val)

### bool test(FunctionSpecifier fs) const

**Brief:** Test if the given specifier is set.

Parameters:
- function specifier to test

### void set(FunctionSpecifier fs)

**Brief:** Sets the given function specifier.

Parameters:
- function specifier to set

### AccessSpecifier getAccess() const

**Brief:** Returns the currently set access specifier.

### void set(AccessSpecifier as)

**Brief:** Sets the access specifier

Parameters:
- the access specifier to set

The previous access specifier is erased.

