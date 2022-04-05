---
layout: default
title: "Enum class"
parent: "Class reference"
---

# Enum Class

**Brief:** represents an enumeration type

## Detailed description

## Members documentation

### int id() const

**Brief:** returns the id of this enumeration

### bool isNull() const

**Brief:** returns whether this instance is null

Calling any other function than isNull() on a null instance is undefined behavior.

### const std::string& name() const

**Brief:** returns the enumeration's name

### bool isEnumClass() const

**Brief:** returns whether the enumeration is an enum class

### const std::map\<std::string, int>& values() const

**Brief:** returns the enumeration's value

### bool hasKey(const std::string& k) const

**Brief:** returns whether there is a value with a given key in the enum

### bool hasValue(int val) const

**Brief:** returns whether the enum has a given value

### int getValue(const std::string& k, int defaultValue) const

**Brief:** returns a value given its key

If there is no value with the given key, defaultValue is returned.

### const std::string& getKey(int val) const

**Brief:** returns the key given its value

If there is none, this function throws an exception.

### int addValue(const std::string& key, int value)

**Brief:** add a value to the enumeration

### Class memberOf() const

**Brief:** returns the class in which this enum was defined

If this enum wasn't defined in a class, this returns a null Class.

### Namespace enclosingNamespace() const

**Brief:** returns the namespace in which the enum is defined

If the enum was defined in a class, this returns the namespace in which the class was defined.

### Engine* engine() const

**Brief:** returns the script engine

### Script script() const

**Brief:** returns the script in which this enum was defined

