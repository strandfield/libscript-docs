---
layout: default
title: "Prototype class"
parent: "Class reference"
---

# Prototype Class

**Brief:** represents a function prototype.

## Detailed description

The Prototype class describes the signature of any function; that is, its return type and parameters.

This class does not own the list of parameters: it only holds a [begin, end) range of parameters. As such, a Prototype cannot be copied. Subclasses are expected to actually hold the list of parameters.

## Members documentation

### const Type& returnType() const

**Brief:** returns the return type

### void setReturnType(const Type& rt)

**Brief:** sets the prototype return's type

### size_t parameterCount() const

**Brief:** returns the number of parameters of the prototype

### size_t count() const

**Brief:** returns the number of parameters of the prototype

### size_t size() const

**Brief:** same as count

### const Type& parameter(size_t index) const

**Brief:** retrieves one of the parameter of the prototype

### const Type& at(size_t index) const

**Brief:** retrieves one of the parameter of the prototype

### std::vector\<Type> parameters() const

**Brief:** returns the parameters as a vector

### const Type* begin() const

**Brief:** returns a pointer to the first parameter

### const Type* end() const

**Brief:** returns a pointer after the last parameter

### void setParameter(size_t index, const Type& t)

**Brief:** set one parameter

### Type& operator\[](size_t index)

**Brief:** access a parameter by its index

