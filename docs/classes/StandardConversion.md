---
layout: default
title: "StandardConversion class"
parent: "Class reference"
---

# StandardConversion Class

**Brief:** The StandardConversion class represents a builtin conversion.

## Detailed description

Standard conversions are one of the building blocks of Conversions.

A standard conversion can represent the following operations:

- a copy
- conversions between fundamental types
- derived-to-base conversions
- enum to int conversions

Additionally, a standard conversion can hold two flags for:

- conversion from non-`const` to `const`
- reference conversions

## Members documentation

### StandardConversion()

Constructs a reference-conversion that, when applied to a Value, has no effects.

### StandardConversion(const Type & src, const Type & dest)

Parameters:
- a fundamental 'source' type
- a fundamental 'dest' type

Constructs a standard conversion from two fundamental types. The input types can be references and can have different `const` qualifications.

### StandardConversion(QualificationAdjustment qualadjust)

