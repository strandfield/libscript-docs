---
layout: default
title: "Type class"
parent: "Class reference"
---

# Type Class

**Brief:** represents a type

## Detailed description

This class is used to represent types.

## Members documentation

### Type()

**Brief:** constructs an invalid type

### Type(int baseType, int flags)

**Brief:** constructs a type from an id and flags

### bool isValid() const

**Brief:** returns whether the type is valid

### Type baseType() const

**Brief:** returns the base type

This function returns the type without const and reference.

### bool isConst() const

**Brief:** returns whether the type is const

### void setConst(bool on)

**Brief:** sets whether the type is const

### bool isReference() const

**Brief:** returns whether the type is a reference

This function returns true only for simple references, it returns false for forwarding references.

### void setReference(bool on)

**Brief:** sets whether the type is a reference

### bool isRefRef() const

**Brief:** returns whether the type is a forwarding reference

This function returns false for simple references.

### bool isConstRef() const

**Brief:** returns whether the type is a const reference

### Type withConst() const

**Brief:** returns this type with const

### Type withoutConst() const

**Brief:** returns this type without const

### Type withoutRef() const

**Brief:** returns this type without reference

This function removes both simple and forwarding references.

@TODO: not consistent with isRef().

### bool isFundamentalType() const

**Brief:** returns whether the type is a fundamental type

Fundamental types are bool, char, int, float, double.

This function ignores const and references.

### bool isObjectType() const

**Brief:** returns whether the type is a class

### bool isEnumType() const

**Brief:** returns whether the type is an enum

### bool isClosureType() const

**Brief:** returns whether the type is a lambda

### bool isFunctionType() const

**Brief:** returns whether the type is a function type

### bool testFlag(TypeFlag flag) const

**Brief:** test whether a flag is set

### void setFlag(TypeFlag flag)

**Brief:** sets a flag

### Type withFlag(TypeFlag flag) const

**Brief:** returns this type with an additional flag

### Type withoutFlag(TypeFlag flag) const

**Brief:** returns this type with a flag removed

### static Type ref(const Type& base)

**Brief:** creates a reference type

### static Type cref(const Type& base)

**Brief:** creates a const-reference type

### static Type rref(const Type& base)

**Brief:** creates a forwarding reference type

### int data() const

**Brief:** returns the internal storage data

