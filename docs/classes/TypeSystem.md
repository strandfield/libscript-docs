---
layout: default
title: "TypeSystem class"
parent: "Class reference"
---

# TypeSystem Class

**Brief:** Represents the type system

## Detailed description

## Members documentation

### Engine* engine() const

**Brief:** Returns the engine that owns this type-system

### bool exists(const Type & t) const

**Brief:** Returns whether a given type exists.

Parameters:
- input type

### Class getClass(Type id) const

**Brief:** Returns the Class for the given type.

Parameters:
- input type

### Enum getEnum(Type id) const

**Brief:** Returns the Enum associated with the given type.

Parameters:
- input type

### ClosureType getLambda(Type id) const

**Brief:** Returns typeinfo associated with the given closure type.

Parameters:
- input type

### FunctionType getFunctionType(Type id) const

**Brief:** Returns type info for the given type id.

Parameters:
- function type

### FunctionType getFunctionType(const Prototype & proto)

**Brief:** Returns type info for the function type associated with the prototype.

Parameters:
- prototype

If no such type exists, it is created.

### bool isDefaultConstructible(const Type & t) const

**Brief:** Returns whether a type is default constructible.

Parameters:
- input type

### bool isCopyConstructible(const Type & t) const

**Brief:** Returns whether a given type can be copied.

Parameters:
- input type

Note that the `const` and `&` qualifiers of `t` are ignored.

### bool isMoveConstructible(const Type & t) const

**Brief:** Returns whether a given type can be move-constructed.

Parameters:
- input type

### Conversion conversion(const Type& src, const Type& dest) const

Parameters:
- source type
- destination type

### bool canConvert(const Type& srcType, const Type& destType) const

**Brief:** Returns whether conversion from a type to another is possible.

Parameters:
- source type
- destination type

This function computes the actual Conversion with conversion() and checks that its rank is not `ConversionRank::NotConvertible`.

### Type typeId(const std::string & typeName, const Scope & scope) const

**Brief:** Searchs for a type by name.

Parameters:
- type name
- scope

Throws UnknownTypeError if the type could not be resolved.

### std::string typeName(Type t) const

**Brief:** Returns the name of a type.

Parameters:
- input type

### bool isInitializerList(const Type & t) const

**Brief:** Returns whether a type is an initializer list type.

Parameters:
- input type

### size_t reserve(Type::TypeFlag flag, size_t count)

**Brief:** reserves type ids

Parameters:
- flag indicating what kind of types are to be reserved
- number of type ids to reserve

**Returns:** the offset of the first reserved id

Note that for now, only class and enum type id can be reserved.

### void addListener(TypeSystemListener* listener)

**Brief:** Adds a listener to the typesystem.

Parameters:
- listener

The TypeSystem takes ownership of the listener.

### void removeListener(TypeSystemListener* listener)

**Brief:** Removes a listener.

Parameters:
- listener

Ownership is transferred back to the caller of this function.

