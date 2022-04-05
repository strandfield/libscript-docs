---
layout: default
title: "Value class"
parent: "Class reference"
---

# Value Class

**Brief:** represents a value

## Detailed description

The Value class stores an implicitly-shared value of any C++ type as well as values created from the scripting system.

## Members documentation

### Value()

**Brief:** constructs an invalid, null value

### Value(const Value& other)

**Brief:** constructs a new reference to a value

Note that because Value is implicitly shared, this does not copy the underlying value but rather the pointer to the value.

Use Engine::copy() to create a true copy of the value.

### ~Value()

**Brief:** destroys the reference to the value

If this instance was the last reference, the underlying value is destroyed.

### bool isNull() const

**Brief:** returns whether this instance does not reference a valid value

### Type type() const

**Brief:** returns the value's type

### bool isConst() const

**Brief:** returns whether the value is marked as const

Note that this is just informative, the underlying value is never const and can always be modified programmatically.

### bool isReference() const

**Brief:** returns whether this instance stores a reference

When a Value stores a reference, it is not responsible for the lifetime of the actual object; the object should outlive the Value.

### bool isBool() const

**Brief:** returns whether the value is a boolean

This is the C++ type `bool`.

### bool isChar() const

**Brief:** returns whether the value is a character

This is the C++ type `char`.

### bool isInt() const

**Brief:** returns whether the value is an integer.

This is the C++ type `int`.

### bool isFloat() const

**Brief:** returns whether the value is a floating point number

This is the C++ type `float`.

### bool isDouble() const

**Brief:** returns whether the value is a double-precision floating point number

This is the C++ type `double`.

### bool isPrimitive() const

**Brief:** returns whether the value is of fundamental type

Fundamental types are bool, char, int, float, double.

### bool isString() const

**Brief:** returns whether the value is a string

### bool isObject() const

**Brief:** returns whether the value is an object

### bool isArray() const

**Brief:** returns whether the value is an array

See the Array class.

### bool isInitializerList() const

**Brief:** returns whether the value is an initializer list

### bool toBool() const

**Brief:** returns the value as a boolean

Pre-condition: isBool() returns true.

### char toChar() const

**Brief:** returns the value as a character

Pre-condition: isChar() returns true.

### int toInt() const

**Brief:** returns the value as an integer

Pre-condition: isInt() returns true.

### float toFloat() const

**Brief:** returns the value as a floating point number

Pre-condition: isFloat() returns true.

### double toDouble() const

**Brief:** returns the value as a double-precision floating point number

Pre-condition: isDouble() returns true.

### String toString() const

**Brief:** returns the value as a string

Pre-condition: isString() returns true.

### Function toFunction() const

**Brief:** returns the value as a function

If this value is not a function, this returns a null Function.

### Object toObject() const

**Brief:** returns the value as an object

If this value is not an object, this returns a null Object.

### Array toArray() const

**Brief:** returns the value as an array

If this value is not an array, this returns a null Array.

### Enumerator toEnumerator() const

**Brief:** returns the value as an enumerator

If this value is not an enumerator, this returns a null Enumerator.

### Lambda toLambda() const

**Brief:** returns the value as a lambda

If this value is not a lambda, this returns a null Lambda.

### InitializerList toInitializerList() const

**Brief:** returns the value as an initializer list

If this value is not an initializer list, this returns a null InitializerList.

### void* data() const

**Brief:** returns a pointer to the value's underlying data

### Engine* engine() const

**Brief:** returns a pointer to the script engine

## Non-Members documentation

### bool operator==(const Value& lhs, const Value& rhs)

**Brief:** returns whether two Values are the same

Note that this does not compare the two values for equality but rather whether lhs and rhs have the same memory address.

### bool operator!=(const Value& lhs, const Value& rhs)

**Brief:** returns whether two Values are different

Note that this does not compare the two values for inequality but rather whether lhs and rhs have a different memory address.

### T& get\<T>(const Value& val)

**Brief:** template function to retrieve a value stored in the Value class

Calling this function with a type that does not match with the actual type of the value stored in the Value is undefined behavior.

