---
layout: default
title: "Object class"
parent: "Class reference"
---

# Object Class

**Brief:** provides functions for Value that are objects

## Detailed description

The Object class provides a uniform way to access the data members of an object.

An Object can be constructed from any Value. If the Value represents an Object, isValid() will return true.

## Members documentation

### Object()

**Brief:** constructs a null object

### Object(const Object& other)

**Brief:** copy constructor

Warning: this does not copy the underlying object.

### Object(const Value& val)

**Brief:** constructs an object from a value

### bool isNull() const

**Brief:** returns whether the object is null

### Class instanceOf() const

**Brief:** returns the class associated with the object

### const Value& at(size_t i) const

**Brief:** returns the data-member at the given offset

### size_t size() const

**Brief:** returns the actual number of data-member in the object

### Value get(const std::string & attrName) const

**Brief:** returns the data-member with the given name

If no such data member exists, this returns a default constructed Value.

### Engine* engine() const

**Brief:** Returns the script engine.

### bool operator==(const Object& other) const

**Brief:** tests if two objects are the same object

This function does not compare based on the object value but rather the object address.

